<script>
  import { onMount } from 'svelte';
  
  import brain from './assets/brain.jpeg';
  import market from './assets/market1.jpeg';
  import earth from './assets/earth1.jpeg';
  import brightEarth from './assets/brightEarth.jpeg';
  import logo from './assets/stoxplaylogo.png';
  import fp from './assets/frontpage1.png';
  import ceo from './assets/ceo.jpeg';

  let showInfo = "";
  let animationClass = "";

  const handleInfo = (info) => {
    showInfo = showInfo === info ? "" : info;
    animationClass = "animate-info";
    setTimeout(() => {
      animationClass = "";
    }, 300);
  };

  const addAnimation = () => {
    animationClass = "animate-info";
    setTimeout(() => {
      animationClass = "";
    }, 300);
  };

  onMount(() => {
    addAnimation();
  });
</script>

<main>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About Us</a></li>
      <li><a href="/services">Our Services</a></li>
      <li><a href="/features">Our Features</a></li>
      <li><a href="/contact">Contact Us</a></li>
    </ul>
  </nav>

  <head>
    <style>
      body {
        background-color: #18072B;
        color: #e0e0e0;
      }
    </style>
  </head>
  

  <header class="fp-container">
    <img src={fp} class="fp" alt="Front Page Image" />
    <img src={logo} class="logo-on-fp" alt="StoxPlay Logo" />
    <h1 class="animate-fade">WELCOME TO STOXPLAY</h1>
  </header>

  <!-- New Template Section -->
  <section class="template-section">
    <div class="template-container">
      <img src={brightEarth} class="template-image" alt="Bright Earth Image" />
      <div class="template-info">
        <h2>StoxPlay</h2>
        <p>STOXPLAY is your ultimate destination for online gaming excitement and cutting-edge predictive analytics. We offer a diverse range of thrilling games and leverage advanced analytics to provide our users with unparalleled insights and predictions. Whether you're a casual gamer or an investor, STOXPLAY has you covered with engaging games and powerful predictive tools.</p>
      </div>
    </div>
  </section>

  <section>
    <div class="info-section">
      <a on:click={() => handleInfo('about')}>
        <img src={brain} class="images" alt="Brain Image" />
        <p>About Us</p>
      </a>
      {#if showInfo === 'about'}
        <div class="info-content {animationClass}">
          <p>StoxPlay: Where Stock Market Expertise Meets Competitive Thrills!</p>
          <p>StoxPlay introduces an innovative platform that combines stock trading with the excitement of competition. It merges strategy, intuition, and the opportunity to win significant rewards. Whether you are an experienced investor or a beginner, StoxPlay provides an exciting arena to showcase your skills and leave your mark in the finance world.</p>
        </div>
      {/if}
    </div>

    <div class="info-section">
      <a on:click={() => handleInfo('services')}>
        <img src={earth} class="images" alt="Earth Image" />
        <p>Our Services</p>
      </a>
      {#if showInfo === 'services'}
        <div class="info-content {animationClass}">
          <p>1. Comprehensive Market Analysis</p>
          <p>We provide detailed market analysis to help you make informed trading decisions. Our expert team analyzes market trends, financial reports, and economic indicators to offer you the best insights.</p>
          <p>2. Real-Time Stock Data</p>
          <p>Stay up-to-date with the latest stock market data. Our platform offers real-time stock prices, charts, and news to keep you informed about the market movements.</p>
          <p>3. Personalized Trading Strategies</p>
          <p>Receive personalized trading strategies based on your risk tolerance and investment goals. Our platform uses advanced algorithms to recommend strategies that align with your preferences.</p>
        </div>
      {/if}
    </div>

    <div class="info-section">
      <a on:click={() => handleInfo('features')}>
        <img src={market} class="images" alt="Market Image" />
        <p>Our Features</p>
      </a>
      {#if showInfo === 'features'}
        <div class="info-content {animationClass}">
          <p>1. Discover the Thrill of Fantasy Gaming!</p>
          <p>As the clock strikes 9 AM, the bustling market springs to life, offering a gateway into the thrilling world of gaming and stock markets. Embark on a journey where every heartbeat resonates with excitement and every decision holds the promise of amazing rewards.</p>
          <p>2. Unlock Your Stock Market Skills!</p>
          <p>Join us to develop and enhance your stock market skills. Our platform not only empowers you to apply your knowledge of stocks in a dynamic environment but also develops your financial market skills. Whether you're a novice eager to learn or a seasoned investor looking to sharpen your strategies, we provide the tools and opportunities to elevate your understanding and performance.</p>
          <p>3. Welcome the Challenge!</p>
          <p>Take part in this exhilarating adventure where learning meets rewards. Upgrade your potential and seize the opportunities that await you. Join us today and dive into a world where knowledge unlocks rewards and every trade is a step towards success.</p>
        </div>
      {/if}
    </div>
  </section>

  <!-- CEO Section -->
  <section class="ceo-section">
    <div class="ceo-container">
      <img src={ceo} class="ceo-image" alt="CEO Image" />
      <div class="ceo-info">
        <h2><strong>Founder</strong></h2>
        <p>Meet our visionary leader who has been the driving force behind StoxPlay's success. With a passion for innovation and a deep understanding of both gaming and financial markets, our founder is dedicated to creating an exceptional platform for our users.</p>
      </div>
    </div>
  </section>

  <h2><strong>Are you Ready to level up!?</strong> </h2>
  <p>Don't miss out on the chance to enrich your expertise and reap the
    benefits of your newfound skills “Kyuki isme humari expertise hai!!”. Join
    us and embark on a journey towards financial growth and personal
    achievement. The clock is ticking—your next big move awaits.</p>

  <!-- Coming Soon Section -->
  <section class="coming-soon-section">
    <h2 class="coming-soon-text">Coming Soon!!</h2>
  </section>

  

  <footer>
    <p class="read-the-docs animate-fade">
      Download the App now !!
    </p>
  </footer>
</main>

<style>
  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }
  @keyframes slideIn {
    from { transform: translateY(20px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
  }
  @keyframes pulse {
    0% { opacity: 0.5; }
    50% { opacity: 1; }
    100% { opacity: 0.5; }
  }
  .animate-fade {
    animation: fadeIn 1s ease-in-out;
  }
  .animate-info {
    animation: slideIn 0.5s ease-in-out;
  }
  body {
    background-color: #4e2f73;
    color: #fff; /* Optional: Makes sure text is visible against the dark background */
  }
  main {
    text-align: center;
    padding: 2rem;
  }
  nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: left;
    gap: 1rem;
    background-color: #8A2BE2;
    padding: 1rem;
    border-radius: 0.5rem;
  }
  nav ul li {
    display: inline;
  }
  nav ul li a {
    text-decoration: none;
    color: #ffffff;
    font-weight: bold;
    transition: color 0.3s ease;
  }
  nav ul li a:hover {
    color: #ff3e00;
  }
  .logo {
    height: 10em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
    cursor: pointer;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  header {
    margin-bottom: 2rem;
  }
  .fp-container {
    position: relative;
    display: inline-block;
  }
  .fp {
    width: 100%;
    height: auto;
  }
  .logo-on-fp {
    position: absolute;
    top: 10px;
    right: 10px;
    width: 150px;
    height: auto;
  }
  .template-section {
    margin-bottom: 2rem;
  }
  .template-container {
    display: flex;
    align-items: center;
    border: 2.5px solid #5c0951;
    background-color: #18072B;
    padding: 2rem;
    border-radius: 0.5rem;
  }
  .template-image {
    height: 20em;
    margin-right: 2rem;
  }
  .template-info {
    text-align: left;
  }
  .template-info h2 {
    margin: 0;
    font-size: 2.5rem;
    color: #81e7f0;
  }
  .template-info p {
    margin: 1.5rem 0 0;
    color: #a7e3e8;
  }
  .info-section {
    display: inline-block;
    margin: 2rem;
    text-align: left;
  }
  .info-section a {
    text-decoration: none;
    color: inherit;
  }
  .images {
    height: 15em;
    margin-bottom: 0.5rem;
    transition: transform 0.3s ease;
  }
  .images:hover {
    transform: scale(1.05);
  }
  .info-content {
    padding: 1rem;
    background-color: #f0f0f0;
    border-radius: 0.5rem;
    margin-top: 1rem;
    color: #333;
  }
  .info-content p {
    margin: 0.5rem 0;
  }
  .read-the-docs {
    color: #888;
    margin-top: 2rem;
  }

  /* CEO Section Styles */
  .ceo-section {
    margin-top: 2rem;
    background-color: #18072B;
    padding: 2rem;
    border-radius: 0.5rem;
  }
  .ceo-container {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .ceo-image {
    height: 15em;
    margin-right: 2rem;
    border-radius: 50%;
  }
  .ceo-info {
    text-align: left;
  }
  .ceo-info h2 {
    margin: 0;
    font-size: 2rem;
    color: #81e7f0;
  }
  .ceo-info p {
    color: #a7e3e8;
  }

  /* Coming Soon Section Styles */
  .coming-soon-section {
    margin-top: 2rem;
    padding: 2rem;
    background-color: #18072B;
    border-radius: 0.5rem;
  }
  .coming-soon-text {
    font-size: 2rem;
    color: #ff3e00;
    animation: pulse 1.5s infinite;
  }
</style>
