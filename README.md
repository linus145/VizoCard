# VizoCard
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Vizocard - The Future of Digital Cards</title>
  <style>
    /* Reset & Global Styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      color: #333;
    }
    
    /* Navigation */
    nav {
      background: #fff;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      position: sticky;
      top: 0;
      width: 100%;
      z-index: 100;
    }
    nav .container {
      max-width: 1200px;
      margin: auto;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav .logo {
      font-size: 1.5rem;
      font-weight: bold;
      color: #3b8d99;
    }
    nav .nav-links {
      list-style: none;
      display: flex;
    }
    nav .nav-links li {
      margin-left: 1.5rem;
    }
    nav .nav-links li a {
      text-decoration: none;
      color: #333;
      font-weight: 500;
      transition: color 0.3s;
    }
    nav .nav-links li a:hover {
      color: #3b8d99;
    }
    
    /* Hero Section */
    #hero {
      display: flex;
      align-items: center;
      justify-content: space-around;
      padding: 4rem 2rem;
      background: linear-gradient(135deg, #f6f9fc, #e9eff5);
      flex-wrap: wrap;
    }
    .hero-content {
      max-width: 500px;
    }
    .hero-content h1 {
      font-size: 2.5rem;
      margin-bottom: 1rem;
      color: #3b8d99;
    }
    .hero-content p {
      font-size: 1.2rem;
      margin-bottom: 2rem;
    }
    .hero-content button {
      padding: 0.8rem 1.5rem;
      font-size: 1rem;
      background: #3b8d99;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .hero-content button:hover {
      background: #337a87;
    }
    .hero-card {
      margin-top: 2rem;
    }
    
    /* Vizocard Styles (Interactive Card) */
    .card-container {
      perspective: 1000px;
      animation: fadeInUp 1s ease-out;
    }
    .card {
      width: 320px;
      height: 200px;
      border-radius: 15px;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 0.8s;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      cursor: pointer;
    }
    .card.flip {
      transform: rotateY(180deg);
    }
    .card-side {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 15px;
      padding: 20px;
      box-sizing: border-box;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .card-front {
      background: linear-gradient(135deg, #3b8d99, #6b6b83, #aa4b6b);
      color: #fff;
    }
    .card-back {
      background: linear-gradient(135deg, #aa4b6b, #6b6b83, #3b8d99);
      transform: rotateY(180deg);
      color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5em;
    }
    .chip {
      width: 50px;
      height: 40px;
      background: #d4af37;
      border-radius: 8px;
    }
    .card-number {
      margin-top: 30px;
      letter-spacing: 2px;
      font-size: 1.2em;
    }
    .card-info {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
      font-size: 0.9em;
    }
    
    /* Process Section */
    #process {
      padding: 4rem 2rem;
      background: #fff;
      text-align: center;
    }
    #process h2 {
      font-size: 2rem;
      margin-bottom: 2rem;
      color: #3b8d99;
    }
    .process-steps {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
    }
    .step {
      background: #f6f9fc;
      border-radius: 10px;
      padding: 2rem;
      margin: 1rem;
      flex: 1;
      min-width: 250px;
      opacity: 0;
      transform: translateY(50px);
      transition: all 0.6s ease-out;
    }
    .step.animate {
      opacity: 1;
      transform: translateY(0);
    }
    .step h3 {
      margin-bottom: 1rem;
      color: #3b8d99;
    }
    .step p {
      color: #555;
    }
    
    /* Contact Section */
    #contact {
      padding: 4rem 2rem;
      background: linear-gradient(135deg, #e9eff5, #f6f9fc);
      text-align: center;
    }
    #contact h2 {
      font-size: 2rem;
      margin-bottom: 2rem;
      color: #3b8d99;
    }
    #signupForm {
      max-width: 400px;
      margin: auto;
      display: flex;
    }
    #signupForm input[type="email"] {
      flex: 1;
      padding: 0.8rem;
      border: 2px solid #3b8d99;
      border-right: none;
      border-radius: 5px 0 0 5px;
      font-size: 1rem;
    }
    #signupForm button {
      padding: 0.8rem 1.5rem;
      border: 2px solid #3b8d99;
      border-left: none;
      border-radius: 0 5px 5px 0;
      background: #3b8d99;
      color: #fff;
      font-size: 1rem;
      cursor: pointer;
      transition: background 0.3s;
    }
    #signupForm button:hover {
      background: #337a87;
    }
    
    /* Footer */
    footer {
      background: #333;
      color: #fff;
      text-align: center;
      padding: 1rem;
    }
    
    /* Animations */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(50px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    /* Responsive Styles */
    @media (max-width: 768px) {
      #hero {
        flex-direction: column;
      }
      .process-steps {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <!-- Navigation -->
  <nav>
    <div class="container">
      <div class="logo">Vizocard</div>
      <ul class="nav-links">
        <li><a href="#hero">Home</a></li>
        <li><a href="#process">Process</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>
  
  <!-- Hero Section -->
  <section id="hero">
    <div class="hero-content">
      <h1>Welcome to Vizocard</h1>
      <p>The future of digital business cards is here. Create, customize, and share your unique Vizocard with ease.</p>
      <button id="createButton">Create Your Vizocard</button>
    </div>
    <div class="hero-card">
      <!-- Interactive Vizocard -->
      <div class="card-container">
        <div class="card" id="vizocard">
          <!-- Front Side -->
          <div class="card-side card-front">
            <div class="chip"></div>
            <div class="card-number" id="vizocardNumber">1234 5678 9012 3456</div>
            <div class="card-info">
              <div class="card-holder">JOHN DOE</div>
              <div class="card-expiry">12/24</div>
            </div>
          </div>
          <!-- Back Side -->
          <div class="card-side card-back">
            <div>Vizocard</div>
          </div>
        </div>
      </div>
      <!-- End Interactive Vizocard -->
    </div>
  </section>
  
  <!-- Process Section -->
  <section id="process">
    <h2>How It Works</h2>
    <div class="process-steps">
      <div class="step">
        <h3>Step 1: Sign Up</h3>
        <p>Create your account to start designing your Vizocard.</p>
      </div>
      <div class="step">
        <h3>Step 2: Customize</h3>
        <p>Choose from multiple templates and add your personal touch.</p>
      </div>
      <div class="step">
        <h3>Step 3: Share</h3>
        <p>Instantly share your Vizocard with potential clients and partners.</p>
      </div>
    </div>
  </section>
  
  <!-- Contact/Sign-Up Section -->
  <section id="contact">
    <h2>Get Started Now</h2>
    <form id="signupForm">
      <input type="email" placeholder="Your Email" required />
      <button type="submit">Sign Up</button>
    </form>
  </section>
  
  <!-- Footer -->
  <footer>
    <p>&copy; 2025 Vizocard. All rights reserved.</p>
  </footer>
  
  <script>
    // --- Interactive Vizocard Flip & Random Number Generator ---
    const vizocard = document.getElementById('vizocard');
    vizocard.addEventListener('click', function() {
      this.classList.toggle('flip');
    });
    
    function generateRandomCardNumber() {
      let cardNumber = '';
      for (let i = 0; i < 4; i++) {
        const part = Math.floor(1000 + Math.random() * 9000);
        cardNumber += part + (i < 3 ? ' ' : '');
      }
      return cardNumber;
    }
    document.getElementById('vizocardNumber').innerText = generateRandomCardNumber();
    
    // --- Animate Process Steps on Scroll ---
    const steps = document.querySelectorAll('.step');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('animate');
        }
      });
    }, { threshold: 0.5 });
    
    steps.forEach(step => observer.observe(step));
    
    // (Optional) You can add more interactive functionality here.
  </script>
</body>
</html>
