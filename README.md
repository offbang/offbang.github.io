<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="My Movie Hub - Watch the latest movies and shows online.">
  <meta name="keywords" content="movies, shows, streaming, watch online">
  <meta name="author" content="Your Name">
  <title>My Movie Hub</title>
  <link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
  <style>
    /* Basic reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* Body styling */
    body {
      font-family: 'Helvetica Neue', Arial, sans-serif;
      background-color: #141414;
      color: white;
      line-height: 1.6;
    }

    /* Header styling */
    header {
      background-color: #141414;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
    }

    header h1 {
      font-size: 2rem;
      color: #e50914;
    }

    header nav a {
      margin: 0 1rem;
      color: white;
      text-decoration: none;
      font-weight: bold;
    }

    header nav a:hover {
      color: #e50914;
    }

    /* Hero section */
    .hero {
      background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://via.placeholder.com/1500x500');
      background-size: cover;
      background-position: center;
      height: 500px;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      margin-top: 60px; /* Offset for fixed header */
    }

    .hero h2 {
      font-size: 3rem;
      margin-bottom: 1rem;
    }

    .hero p {
      font-size: 1.5rem;
      margin-bottom: 2rem;
    }

    .hero button {
      background-color: #e50914;
      color: white;
      border: none;
      padding: 0.8rem 2rem;
      font-size: 1.2rem;
      cursor: pointer;
      border-radius: 5px;
    }

    .hero button:hover {
      background-color: #f40612;
    }

    /* Section styling */
    .section {
      padding: 2rem;
    }

    .section h2 {
      font-size: 1.8rem;
      margin-bottom: 1rem;
    }

    /* Grid layout for cards */
    .grid {
      display: flex;
      gap: 1rem;
      overflow-x: auto;
      padding-bottom: 1rem;
    }

    .grid::-webkit-scrollbar {
      height: 8px;
    }

    .grid::-webkit-scrollbar-thumb {
      background: #e50914;
      border-radius: 4px;
    }

    .grid::-webkit-scrollbar-track {
      background: #333;
    }

    .card {
      background-color: #222;
      padding: 1rem;
      border-radius: 8px;
      text-align: center;
      width: 200px;
      flex-shrink: 0;
      transition: transform 0.3s ease;
    }

    .card:hover {
      transform: scale(1.1);
      z-index: 10;
    }

    .card img {
      width: 100%;
      border-radius: 8px;
    }

    .card h3 {
      font-size: 1.2rem;
      margin: 1rem 0;
    }

    .card a {
      color: #e50914;
      text-decoration: none;
      font-weight: bold;
    }

    .card a:hover {
      text-decoration: underline;
    }

    /* Footer styling */
    footer {
      text-align: center;
      padding: 1rem 0;
      background-color: #222;
      color: #aaa;
    }

    footer a {
      color: #e50914;
      text-decoration: none;
    }

    footer a:hover {
      text-decoration: underline;
    }

    /* Responsive design */
    @media (max-width: 768px) {
      .hero h2 {
        font-size: 2rem;
      }

      .hero p {
        font-size: 1.2rem;
      }

      .card {
        width: 150px;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>My Movie Hub</h1>
    <nav>
      <a href="#movies">Movies</a>
      <a href="#shows">Shows</a>
    </nav>
  </header>

  <div class="hero">
    <div>
      <h2>Welcome to My Movie Hub</h2>
      <p>Watch the latest movies and shows anytime, anywhere.</p>
      <button>Get Started</button>
    </div>
  </div>

  <main>
    <section id="movies" class="section">
      <h2>Movies</h2>
      <div class="grid">
        <div class="card">
          <img src="https://via.placeholder.com/200x300" alt="Movie 1">
          <h3>Coming Soon</h3>
          <p><a href="#">Watch Now</a></p>
        </div>
        <div class="card">
          <img src="https://via.placeholder.com/200x300" alt="Movie 2">
          <h3>Beast Games</h3>
          <p><a href="https://cyyroro04xrqr.premilkyway.com/hls2/01/08240/19227vmkbyct_,l,n,h,.urlset/master.m3u8?t=4tCr0tjsYOLlr2EiLfWpjbNs3EpL1dFncFyihH8jIRE&s=1738327744&e=129600&f=41203938&srv=js4BwLKgfmTMJmVh&i=0.4&sp=500&p1=js4BwLKgfmTMJmVh&p2=js4BwLKgfmTMJmVh&asn=37075">Watch Now</a></p>
        </div>
        <!-- Add more movie cards -->
      </div>
    </section>

    <section id="shows" class="section">
      <h2>Shows</h2>
      <div class="grid">
        <div class="card">
          <img src="https://static.wikia.nocookie.net/shipping/images/1/14/Squid_Game_promotional_poster.jpg/revision/latest?cb=20211022040624" alt="Squid Game">
          <h3>beast games 9 </h3>
          <p><a href="https://cv9fqnu812v.premilkyway.com/hls2/01/08283/qnzbr7rm0ee6_,l,n,.urlset/master.m3u8?t=TYUWqRFZlt1JHBzwb8wwljhRqBXjeytSMae05hZ-vw4&s=1738929184&e=129600&f=41417796&srv=aB091Tg50YGN&i=0.4&sp=500&p1=aB091Tg50YGN&p2=aB091Tg50YGN&asn=37075">Watch Now</a></p>
        </div>
        <!-- Add more show cards -->
      </div>
    </section>
  </main>

  <footer>
    <p>&copy; 2024 Movie Hub</p>
    <a href="https://instagram.com/offbang.sk" target="_blank">Follow on Instagram</a>
  </footer>
</body>
</html>
