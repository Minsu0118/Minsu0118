# HTML

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>연락처 목록</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
<div class="edit-container">
  <div class="top-bar">
    <h1 id="list">연락처 목록</h1>
        <button type="button" class="plus-btn">
            <img src="img/plus.png" alt="추가" />
        </button>
  </div>

  <div class="search-bar">
        <input type="text" id="searchInput" placeholder="🔍검색어를 입력하세요" />
  </div> 
  <div id="contact-list"></div>
</div>

<script>
  document.querySelector('.plus-btn').addEventListener('click', () => {
    window.location.href = 'sub.html';
  });

  const contacts = JSON.parse(localStorage.getItem('contacts') || '[]');
  const contactList = document.getElementById('contact-list');

  if (contacts.length === 0) {
    contactList.innerHTML = '<p>저장된 연락처가 없습니다.</p>';
  } else {
    contacts.forEach((contact, index) => {
  const item = document.createElement('div');
  item.className = 'contact-item';
  item.innerHTML = `
  <div class="contact-info">
    <img src="${contact.image || 'img/person1.png'}" class="small-profile-img" data-index="${index}" />
    <div class="contact-text">
      <span class="contact-name">${contact.name}</span>
      <span class="contact-phone">${contact.phone}</span>
      <span class="contact-email">${contact.email}</span>
    </div>
  </div>
`;

  contactList.appendChild(item);
});

    document.querySelectorAll('.small-profile-img').forEach(img => {
      img.addEventListener('click', (event) => {
        const index = event.target.dataset.index;
        window.location.href = `main.html?edit=${index}`;
      });
    });
  }
</script>
</body>
</html>
```
