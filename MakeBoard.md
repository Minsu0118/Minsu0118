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
