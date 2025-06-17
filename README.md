# web4
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>유퀴즈 온더 트립!</title>

  <!-- Pretendard 불러오기 -->
  <link href="https://cdn.jsdelivr.net/npm/pretendard/dist/web/static/pretendard.css" rel="stylesheet">

  <style>
     #topnav {
      background: #000;
    }
    #topnav nav ul {
      display: flex;
      align-items: center;
      list-style: none;
      max-width: 1200px;
      margin: auto;
      padding: 0.5rem 1rem;
    }
    #topnav nav ul li {
      margin-right: 1.5rem;
    }
    #topnav nav ul li.logo-title {
      margin-right: auto;
    }
    #topnav nav ul li a {
      color: #fff;
      text-decoration: none;
      transition: opacity 0.3s;
      font-size: 0.9rem;      /* 원래 1rem였다면 0.9rem 정도로 줄여봅니다 */
      font-weight: 600;
    }
    #topnav nav ul li.logo-title a {
      font-size: 1rem;
      font-weight: 700;
    }
    #topnav nav ul li a:hover {
      opacity: 0.7;
    }
    /* Reset & 기본 스타일 */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Pretendard', sans-serif;
      color: #000;
      line-height: 1.5;
    }
    h1, h2 { font-weight: 700; }
    p, .tag, .caption { font-weight: 400; }

    /* 해시태그 공통 */
    .hashtags {
      display: flex;
      justify-content: center;
      gap: 0.8rem;
      flex-wrap: wrap;
      margin-top: 1rem;
    }
    .hashtags .tag {
      padding: 0.4rem 1rem;
      border-radius: 20px;
      background: rgba(255,255,255,0.7);
      font-size: 0.9rem;
      transition: 0.2s;
    }
    .hashtags .tag:hover {
      background: rgba(255,255,255,0.9);
      transform: translateY(-2px);
    }

    /* 1. Hero 섹션 */
    #hero {
      position: relative;
      background: url('images/summer-hero.png') center/cover no-repeat;
      height: 80vh;
      text-align: center;
      padding: 4rem 1rem 2rem;
    }
    #hero .pretitle {
      display: inline-block;
      background: rgba(255,255,255,0.8);
      padding: 0.5rem 1rem;
      border-radius: 5px;
      font-size: 1rem;
    }
    /* 로고 이미지 컨테이너 */
    #hero .logo-container {
      margin: 1.5rem auto 0;
      max-width: 200px;    /* 필요시 더 작게 조정 */
    }
    #hero .logo {
      display: block;
      width: 100%;
      height: auto;
    }

    /* 2. 포인트 카드 섹션 */
    #points {
      background: linear-gradient(to bottom, #ffffff 0%, #87CEFA 100%);
      padding: 4rem 1rem;
      text-align: center;
    }
    #points .intro {
      font-size: 1.5rem;
      margin-bottom: 2rem;
      white-space: pre-line;
    }
    #points .cards {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1.5rem;
    }
    #points .card {
      background: rgba(255,255,255,0.8);
      border-radius: 10px;
      overflow: hidden;
      width: 280px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      transition: transform .3s;
    }
    #points .card:hover {
      transform: translateY(-5px);
    }
    #points .card img {
      width: 100%;
      height: 160px;
      object-fit: cover;
    }
    #points .card .caption {
      padding: 1rem;
      font-size: 1rem;
      font-weight: 700;
      color: #000;
    }

    /* 3. QUIZ 섹션 */
    #quiz {
      padding: 4rem 1rem;
      text-align: center;
    }
    #quiz h2 {
      font-size: 2.2rem;
      margin-bottom: 1rem;
    }
    #quiz .question {
      font-size: 1.3rem;
      margin-bottom: 2rem;
    }
    #quiz .map img {
      width: 100%;
      max-width: 800px;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }

    /* 반응형 */
    @media (max-width: 768px) {
      #hero .logo-container { max-width: 120px; }
      #points .cards { flex-direction: column; align-items: center; }
      #quiz .map img { max-width: 100%; }
    }
  </style><link href="https://cdn.jsdelivr.net/npm/pretendard/dist/web/static/pretendard.css" rel="stylesheet">

<style>
  /* Reset & 기본 스타일 */
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    font-family: 'Pretendard', sans-serif;
    color: #000;
    line-height: 1.5;
  }
  h1, h2 { font-weight: 700; }
  p, .tag, .caption { font-weight: 400; }

  /* 해시태그 공통 (변경 없음) */
  .hashtags { /* … */ }
  .hashtags .tag { /* … */ }

  /* 1. Hero 섹션 (변경 없음) */
  #hero { /* … */ }
  #hero .pretitle { /* … */ }
  #hero .logo-container { /* … */ }
  #hero .logo { /* … */ }

  /* 2. 포인트 카드 섹션 */
  #points {
    background: linear-gradient(to bottom, #ffffff 0%, #87CEFA 100%);
    padding: 4rem 1rem;
    text-align: center;
  }
  /* ★ Pretendard 굵은체로 변경 ★ */
  #points .intro {
    font-family: 'Pretendard', sans-serif;
    font-weight: 700;      /* ← 추가 */
    font-size: 1.5rem;
    margin-bottom: 2rem;
    white-space: pre-line;
  }
  #points .cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.5rem;
    margin-top: -1rem;     /* ← 카드들을 위로 살짝 당기기 */
  }
  #points .card { /* … */ }
  #points .card:hover { /* … */ }
  #points .card img { /* … */ }
  #points .card .caption { /* … */ }

  /* 3. QUIZ 섹션 */
  #quiz {
    padding: 4rem 1rem;
    text-align: center;
  }
  /* 제목 변경 */
  #quiz h2 {
    font-size: 2.2rem;
    margin-bottom: 1rem;
    font-weight: 700;
  }
  /* ★ Pretendard 굵은체로 변경 ★ */
  #quiz .question {
    font-family: 'Pretendard', sans-serif;
    font-weight: 700;      /* ← 추가 */
    font-size: 1.3rem;
    margin-bottom: 2rem;
  }
  /* 파란색 글자 */
  #quiz .question .blue {
    color: #007BFF;
  }

  /* 버튼 스타일 */
  .options {
    margin-bottom: 2rem;
  }
  .options button {
    padding: 0.6rem 1.2rem;
    margin: 0 0.5rem;
    font-family: 'Pretendard', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    border: 2px solid #87CEFA;
    border-radius: 20px;
    background: #fff;
    cursor: pointer;
    transition: background 0.3s, color 0.3s;
  }
  .options button:hover,
  .options button.active {
    background: #87CEFA;
    color: #fff;
  }

  /* 답변 영역: 기본 숨김 */
  .answer-content .content {
    display: none;         /* ← 선택 전엔 보이지 않음 */
    max-width: 800px;
    margin: auto;
    text-align: left;
  }
  .answer-content .place h3 { font-weight: 700; }
  .answer-content .place p { margin-bottom: 0.5rem; }
  .answer-content .place img,
  .answer-content .map img {
    width: 100%; max-width: 400px; border-radius: 5px;
  }

  /* 반응형 (필요시 조정) */
  @media (max-width:768px) {
    #hero .logo-container { max-width:120px; }
    #points .cards { flex-direction:column; align-items:center; margin-top:0; }
    .options button { display:block; margin:0.5rem auto; }
    .answer-content .place img,
    .answer-content .map img { max-width:100%; }
  }
</style>
</head>

</head>

<body>
 <!-- 최상단 네비게이션 -->
 <header id="topnav">
  <nav>
    <ul>
      <li class="logo-title"><a href="index.html">유퀴즈 온더 트립!</a></li>

      <li><a href="계절네스푼.html">계절 네스푼</a></li>
      <!-- 요기를 이렇게 고쳐주세요 -->
      <li><a href="./테마별지도.html">테마별 지도</a></li>
      <li><a href="내 여행.html">내 여행</a></li>
      <li><a href="로그인.html">로그인</a></li>
    </ul>
  </nav>
</header>
  <!-- 1. Hero 섹션 -->
  <section id="hero">
    <div class="pretitle">국내여행, 계절에 맞게 떠나볼까요?</div>

    <div class="logo-container">
      <img src="images/logo.png" alt="유퀴즈 온더 트립!" class="logo">
    </div>

    <div class="hashtags">
      <span class="tag">#이번여름첫여행</span>
      <span class="tag">#2025여름핫플</span>
      <span class="tag">#국내여행감성</span>
    </div>
  </section>

  <!-- 2. 포인트 카드 섹션 -->
  <section id="points">
    <div class="intro">
      다신돌아오지않을 2025 여름,
      당신에게 어울리는 여행을 찾아드려요
    </div>
    <div class="cards">
      <div class="card">
        <img src="images/card-camp.jpeg" alt="캠핑 이미지">
        <div class="caption">여름날 계곡에서 느끼는 시원함</div>
      </div>
      <div class="card">
        <img src="images/card-thrill.png" alt="액티비티 이미지">
        <div class="caption">이열치열, 뜨거운 여름을 날리는 짜릿함</div>
      </div>
      <div class="card">
        <img src="images/card-village.jpg" alt="시골 이미지">
        <div class="caption">시골에서 찾은 나만의 여유로움</div>
      </div>
    </div>
  </section>

   <!-- 3. QUIZ 섹션 (완전 교체) -->
  <section id="quiz">
    <h2>6월의 YOU QUIZ?</h2>
    <div class="question">
      <span class="blue">주</span>저앉고 싶을 때마다,
      <span class="blue">대</span>지를 바라보며 다시 일어설 힘을 얻는다.
    </div>

    <!-- 선택 버튼 -->
    <div class="options">
      <button id="option-ju">주</button>
      <button id="option-dae">대</button>
    </div>
   
</body>
</html>
