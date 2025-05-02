## 필요 SQL
```sql
-- boards 테이블 생성(자료실=>게시판)
create table boards(
	bno number(38) primary key--번호
	,bwriter varchar2(50) not null--글쓴이
	,btitle varchar2(200) not null--글제목
	,bcontent varchar2(4000) not null--글내용
	,bdate date default sysdate--등록날짜, date는 오라클 날짜 타입, sysdate는 오라클 날짜함수, default sysdate 제약조건을 주면 해당
	--컬럼에 굳이 날짜/시간 값을 저장하지 않아도 기본값 날짜/시간 값이 저장된다.
	,bfilename varchar2(200) null--첨부파일명
	,bfiledata blob null--blob는 오라클에서 대용량 이진 데이터를 저장할 수 있는 자료형이다. BLOB은 'Binary Large Object'의 약자이다.
	--최대 4GB까지 저장가능하다. 순수 이진 데이터이므로 텍스트가 아닌 파일데이터(그림, 동영상, 오디오, PDF, 워드 파일등)을 그대로 저장가능하다.
);

select * from boards order by bno desc;
--boards 테이블에서 모든 레코드를 bno 컬럼을 기준으로 내림차순(desc) 정렬하여 조회하는 쿼리

--seq_bno 시퀸스 생성
create sequence seq_bno
start with 1
increment by 1
nocache
nocycle;

--seq_bno 다음 시퀸스 번호값 확인
select seq_bno.nextval as "다음 시퀸스번호값" from dual;
```

## 메인 JAVA
```java
package net.daum.controller;

import java.util.List;
import java.util.Scanner;

import net.daum.dao.BoardDAOImpl;
import net.daum.dto.BoardDTO;

public class BoardExample {//게시판

	private Scanner scan = new Scanner(System.in);
	
	//게시판 목록
	public void list() {
		System.out.println();
		System.out.println("[게시판 목록]");
		System.out.println("----------------------------------------------------------------------");
		System.out.printf("%-6s%-12s%-16s%-40s\n", "no", "writer" , "date" ,"title");
		/* %-6s는 문자열 출력형태 지정자이다. -는 왼쪽 정렬, 6은 최소 출력 너비 6칸, %s는 문자열 출력형태 지시자이다. 결국 %-6s는 문자열을
		 * 왼쪽 정렬하고 전체 너비를 6칸으로 맞추라는 의미이다. 빈 캄이 남으면 오른쪽에 공백이 들어간다.
		 */
		System.out.println("----------------------------------------------------------------------");
		
		BoardDAOImpl bdao = new BoardDAOImpl();
		List<BoardDTO> blist = bdao.getBoardList();//게시판 목록
		
		if(blist != null && blist.size() > 0) {
			for(BoardDTO b:blist) {
				System.out.printf("%-6s%-12s%-16s%-40s \n", b.getBno(), b.getBwriter(), b.getBdate(), b.getBtitle());
			}
		}else {
			System.out.println("게시판 목록이 없습니다!");
		}
		
		mainMenu();//메인 메뉴 메서드 호출
	}//list()  
	
	//메인 메뉴
	public void mainMenu() {
		System.out.println();
		System.out.println("----------------------------------------------------------------------");
		System.out.println("메인 메뉴: 1.Create | 2.Read | 3.Clear | 4.Exit");
		System.out.print("메뉴 선택: ");
		String menuNo = scan.nextLine();
		System.out.println();
		
		switch(menuNo) {
		 case "1" : create(); break; //게시판 저장
		 case "2" : read(); break; //게시판 읽기
		 case "4" : exit(); break; //게시판 종료
		}
	}//mainMenu()
	
	//게시판 읽기
	public void read() {
		System.out.println("[게시물 읽기]");
		System.out.print("게시판  번호 입력>>");
		int bno = Integer.parseInt(scan.nextLine());
		
		BoardDAOImpl bdao=new BoardDAOImpl();
		BoardDTO findBno = bdao.getFindNo(bno);//db로 부터 게시판 번호를 검색
		
		if(findBno != null) {
			BoardDTO bc = bdao.getBoardCont(bno);//번호에 해당하는 게시물 내용을 DB로 부터 가져오기
			
			/*
			 * 5월 2일 여기 할 차례이다.
			 */
		}else {
			System.out.println("해당 게시물 내용이 없습니다!");
			list();
		}
	}//read()
	
	//게시판 저장
	public void create() {
		BoardDTO board=new BoardDTO();
		System.out.println("[새 게시물 입력]");
		System.out.print("글쓴이 >>");
		board.setBwriter(scan.nextLine());
		System.out.print("글제목 >>");
		board.setBtitle(scan.nextLine());
		System.out.print("글내용 >>");
		board.setBcontent(scan.nextLine());
		
		//보조 메뉴 출력
		System.out.println("----------------------------------------------------------------------");
		System.out.println("보조 메뉴: 1.OK | 2.Cancel");
		System.out.print("메뉴 선택>>");
		String menuNo = scan.nextLine();
		
		if(menuNo.equals("1")) {//게시판 저장
			BoardDAOImpl bdao = new BoardDAOImpl();
			bdao.insertBoard(board);//실제 게시물 저장
			list();//게시판 목록보기
		}else {//Cancel
			list();
		}
	}//create()
	
	//게시판 종료
	public void exit() {
		System.out.println("**게시판 종료**");
		System.exit(0);//게시판 프로그램 정상적인 종료
	}//exit()
	
	public static void main(String[] args) {
		
		BoardExample boardExample=new BoardExample();
        boardExample.list();//게시판 목록보기
	}
}
```
##  오라클 DB와 연동하여 게시판 기능을 수행하는 DAO(Data Access Object) 클래스
```java
package net.daum.dao;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.util.ArrayList;
import java.util.List;

import net.daum.controller.BoardExample;
import net.daum.dto.BoardDTO;

public class BoardDAOImpl {//오라클 연동 클래스

	String driver = "oracle.jdbc.OracleDriver";//oracle.jdbc는 패키지명,  OracleDriver는 jdbc드라이버 클래스명
	String url = "jdbc:oracle:thin:@localhost:1521:xe";//오라클 접속주소, 1521은 포트번호, xe는 데이터베이스 명
	String user = "day";//오라클 접속 사용자
	String password = "day";//사용자 비번
	
	Connection con = null;//db연결
	PreparedStatement pt = null; //쿼리문 수행
	ResultSet rs = null;//검색 결과 레코드를 저장할 rs
	String sql = null;
	
	BoardExample exitB = new BoardExample();
	
	public BoardDAOImpl() {
		try {
			Class.forName(driver);
		}catch(Exception e) {
			e.printStackTrace();
			exitB.exit();//게시판 종료
		}
	}//생성자
	
	//게시판 목록
	public List<BoardDTO> getBoardList() {
		List<BoardDTO> blist=new ArrayList<>();
		
		try {
			con = DriverManager.getConnection(url, user, password);
			sql = "select * from boards order by bno desc";// 번호를 기준으로 내림차순 정렬 검색
			pt = con.prepareStatement(sql);//쿼리문을 미리 컴파일하여 수행할 pt생성
			rs = pt.executeQuery();//select 문 수행후 결과 레코드를 rs에 저장
			while(rs.next()) {//복수개의 레코드가 검색되면 while 반복문으로 처리, next() 메서드는 다음레코드가 존재하면 참
				BoardDTO b = new BoardDTO();
				b.setBno(rs.getInt(1));//1의 뜻은 select문 뒤에 검색되는 컬럼순번이다. 해당 컬럼으로 정수 숫자로 번호값을 가져와서
				//setter() 메서드에 저장
				b.setBwriter(rs.getString("bwriter"));//bwriter 컬럼에 저장된 작성자 레코드를 문자열로 가져와서 setter()메서드에
				//저장
				b.setBdate(rs.getDate("bdate"));
				b.setBtitle(rs.getString("btitle"));
				
				blist.add(b);//컬렉션에 추가
			}//while end
			
			rs.close();
			pt.close();
		}catch(Exception e) {
			e.printStackTrace();
			exitB.exit();
		}finally {
			try {
				if(con != null) con.close();
			}catch(Exception e) {e.printStackTrace();}
		}//finally
		return blist;
	}//getBoardList()	

	//게시판 저장
	public void insertBoard(BoardDTO board) {
		try {
			con = DriverManager.getConnection(url, user, password);
			sql = "insert into boards (bno,bwriter,btitle,bcontent) values(seq_bno.nextval,?,?,?)";
			pt = con.prepareStatement(sql);
			pt.setString(1, board.getBwriter());//쿼리문의 첫번째 물음표에 문자열로 글쓴이를 저장
			pt.setString(2, board.getBtitle());
			pt.setString(3, board.getBcontent());
			
			pt.executeUpdate();//저장 쿼리문 수행후 성공한 레코드 행의 개수를 반환
			
			pt.close();
		}catch(Exception e) {
			e.printStackTrace();
			exitB.exit();
		}finally {
			try {
				if(con != null) con.close();
			}catch(Exception e) {e.printStackTrace();}
		}
	}//insertBoard()

	//게시판 번호검색
	public BoardDTO getFindNo(int bno) {
		BoardDTO findNo = null;
		
		try {
			con = DriverManager.getConnection(url, user, password);
			sql = "select bno from boards where bno = ?";
			pt = con.prepareStatement(sql);
			pt.setInt(1, bno);
			rs = pt.executeQuery();
			
			if(rs.next()) {//검색된 레코드가 하나이면 if문으로 처리
				findNo = new BoardDTO();
				findNo.setBno(rs.getInt("bno"));
			}
			rs.close(); pt.close();
		}catch(Exception e) {
			e.printStackTrace();
			exitB.exit();
		}finally {
			try {
				if(con != null) con.close();
			}catch(Exception e) {e.printStackTrace();}
		}
		return findNo;
	}//getFindNo()

	//게시물 읽기
	public BoardDTO getBoardCont(int bno) {
		BoardDTO bc=null;
		
		try {
			con = DriverManager.getConnection(url, user, password);
			sql = "select * from boards where bno=?";
			pt = con.prepareStatement(sql);			
			pt.setInt(1, bno);
			rs = pt.executeQuery();
			if(rs.next()) {
				bc = new BoardDTO();
				bc.setBno(rs.getInt("bno"));
				bc.setBwriter(rs.getString("bwriter"));
				bc.setBtitle(rs.getString("btitle"));
				bc.setBcontent(rs.getString("bcontent"));
				bc.setBdate(rs.getDate("bdate"));
			}
		}catch(Exception e) {
			e.printStackTrace();
			exitB.exit();
		}finally {
		  try {
			  if(con != null) con.close();
		  }catch(Exception e) { e.printStackTrace(); }
		}		
		return bc;
	}//getBoardCont()
}

```
## DTO는 단순히 데이터를 저장하고 전달하는 역할
```java
package net.daum.dto;

import java.util.Date;

import lombok.Getter;
import lombok.Setter;

@Setter //setter()메서드 자동생성
@Getter //getter() 메서드 자동생성
public class BoardDTO {//중간 데이터 저장빈 클래스 -> 되도록이면 테이블 컬럼명과 일치하는 변수명을 정의한다.

	private int bno;//게시판 번호
	private String bwriter;//글쓴이
	private String btitle;//글제목
	private String bcontent; //글내용
	private Date bdate;//등록날짜
	
}
```
