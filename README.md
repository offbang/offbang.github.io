
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Movie Hub</title>
  <style>
    /* Basic reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* Body styling */
    body {
      font-family: Arial, sans-serif;
      background-color: #141414;
      color: white;
      line-height: 1.6;
    }

    /* Header styling */
    header {
      background-color: #e50914;
      color: white;
      padding: 1rem 2rem;
      text-align: center;
    }

    header h1 {
      font-size: 2.5rem;
    }

    header nav a {
      margin: 0 1rem;
      color: white;
      text-decoration: none;
      font-weight: bold;
    }

    header nav a:hover {
      text-decoration: underline;
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
      gap: 1.5rem;
      flex-wrap: wrap;
    }

    .card {
      background-color: #222;
      padding: 1rem;
      border-radius: 8px;
      text-align: center;
      width: 200px;
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
  <main>
    <section id="movies" class="section">
      <h2>Movies</h2>
      <div class="grid">
        <div class="card">
          <img src="https://via.placeholder.com/200x300" alt="Movie 1">
          <h3>coming soon</h3>
          <p><a href="#">Watch Now</a></p>
        </div>
        <div class="card">
          <img src="https://via.placeholder.com/200x300" alt="Movie 2">
          <h3>Coming soon</h3>
          <p><a href="#">Watch Now</a></p>
        </div>
      </div>
    </section>
    <section id="shows" class="section">
      <h2>Shows</h2>
      <div class="grid">
        <div class="card">
          <img src="https://static.wikia.nocookie.net/shipping/images/1/14/Squid_Game_promotional_poster.jpg/revision/latest?cb=20211022040624)">
          <h3>Squid game</h3>
          <p><a href="#">Watch Now</a></p>
        </div>
      </div>
    </section>
    <section id="episodes" class="section">
      <h2>Squid game S2</h2>
      <ul>
        <li><a href=" https://6wyav2r9i6j.premilkyway.com/hls2/01/07576/zatj4n16xpnm_,l,n,h,.urlset/master.m3u8?t=elkXkuPc20oXXumS5oc0AYJOusFcoqbsP3d1mVxqW-0&s=1735212295&e=129600&f=37883180&srv=js4BwLKgfmTMJmVh&i=0.0&sp=500&p1=js4BwLKgfmTMJmVh&p2=js4BwLKgfmTMJmVh&asn=27176 ">Episode 1</a></li>
        <li><a href="https://uicdn.cloud/local/0/e2131244311814d364536b58a9674402/master.m3u8">Episode 2</a></li>
        <li><a href="https://uicdn.cloud/local/0/e5df7f62103c2cfd25ad24a59ee3868e/master.m3u8">Episode 3</a></li>
        <li><a href="https://streamcdn.cloud/local/0/e5df7f62103c2cfd25ad24a59ee3868e/master.m3u8">Episode 4</a></li>
        <li><a href="https://uncdn.cloud/local/0/1d43070f3e68046861646714dc6590d3/master.m3u8">Episode 5</a></li>
        <li><a href="https://uncdn.cloud/local/0/9a9cb156762fd3141ea60ed1fbc2375d/master.m3u8">Episode 6</a></li>
        <li><a href="https://uicdn.cloud/local/0/e5e421d49e5e376d678ac597f1852731/master.m3u8">Episode 7</a></li>  
      </ul>
    </section>
  </main>
  <footer>
    <p>&copy; 2024 Movie Hub</p> <p></p>
  </footer>
</body>
</html>
