<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Top Berry — Premium Ice Cream | Samrala, Punjab</title>
<link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Quicksand:wght@400;500;600;700&family=Pacifico&display=swap" rel="stylesheet">
<style>
  :root {
    --berry: #D6196E;
    --berry-dark: #A8124F;
    --strawberry: #FF6B8A;
    --cream: #FFF8F0;
    --vanilla: #FFF3E0;
    --mint: #A8E6CF;
    --blueberry: #6C5CE7;
    --chocolate: #5D3A1A;
    --mango: #FDCB6E;
    --pistachio: #B8E994;
    --shadow: rgba(214, 25, 110, 0.15);
    --text: #2D1B33;
    --text-light: #6B5876;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Quicksand', sans-serif;
    background: var(--cream);
    color: var(--text);
    overflow-x: hidden;
  }

  /* ── Sprinkle Background ── */
  .sprinkles {
    position: fixed;
    inset: 0;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .sprinkle {
    position: absolute;
    width: 6px;
    height: 20px;
    border-radius: 10px;
    opacity: 0.12;
    animation: sprinkleFall linear infinite;
  }
  @keyframes sprinkleFall {
    0% { transform: translateY(-30px) rotate(0deg); }
    100% { transform: translateY(110vh) rotate(720deg); }
  }

  /* ── Navbar ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 1000;
    padding: 0.8rem 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: all 0.4s ease;
    background: transparent;
  }
  nav.scrolled {
    background: rgba(255, 248, 240, 0.95);
    backdrop-filter: blur(20px);
    box-shadow: 0 4px 30px var(--shadow);
  }
  .nav-logo {
    display: flex;
    align-items: center;
    gap: 0.6rem;
    text-decoration: none;
  }
  .nav-logo .logo-icon {
    width: 44px; height: 44px;
    background: linear-gradient(135deg, var(--berry), var(--strawberry));
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem;
    box-shadow: 0 4px 15px var(--shadow);
    transition: transform 0.3s;
  }
  .nav-logo:hover .logo-icon { transform: rotate(20deg) scale(1.1); }
  .nav-logo span {
    font-family: 'Fredoka One', cursive;
    font-size: 1.5rem;
    background: linear-gradient(135deg, var(--berry), var(--blueberry));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .nav-links { display: flex; gap: 2rem; align-items: center; }
  .nav-links a {
    text-decoration: none;
    color: var(--text);
    font-weight: 600;
    font-size: 0.95rem;
    position: relative;
    transition: color 0.3s;
  }
  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px; left: 0;
    width: 0; height: 3px;
    background: var(--berry);
    border-radius: 3px;
    transition: width 0.3s;
  }
  .nav-links a:hover { color: var(--berry); }
  .nav-links a:hover::after { width: 100%; }
  .nav-cta {
    background: linear-gradient(135deg, var(--berry), var(--strawberry)) !important;
    color: white !important;
    padding: 0.6rem 1.5rem;
    border-radius: 50px;
    -webkit-text-fill-color: white !important;
    box-shadow: 0 4px 15px var(--shadow);
    transition: transform 0.3s, box-shadow 0.3s !important;
  }
  .nav-cta:hover { transform: translateY(-2px); box-shadow: 0 6px 25px var(--shadow); }
  .nav-cta::after { display: none !important; }

  .hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    z-index: 1100;
  }
  .hamburger span {
    width: 28px; height: 3px;
    background: var(--berry);
    border-radius: 3px;
    transition: all 0.3s;
  }

  /* ── Hero ── */
  .hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    position: relative;
    padding: 8rem 5% 4rem;
    overflow: hidden;
  }
  .hero-bg-circle {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.25;
    z-index: 0;
  }
  .hero-bg-circle:nth-child(1) { width: 500px; height: 500px; background: var(--strawberry); top: -10%; right: -5%; }
  .hero-bg-circle:nth-child(2) { width: 400px; height: 400px; background: var(--mango); bottom: -10%; left: -5%; }
  .hero-bg-circle:nth-child(3) { width: 300px; height: 300px; background: var(--mint); top: 40%; left: 30%; }

  .hero-content {
    position: relative;
    z-index: 1;
    max-width: 650px;
    animation: fadeInUp 1s ease;
  }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: white;
    padding: 0.5rem 1.2rem;
    border-radius: 50px;
    font-size: 0.85rem;
    font-weight: 600;
    color: var(--berry);
    box-shadow: 0 4px 20px rgba(0,0,0,0.06);
    margin-bottom: 1.5rem;
    animation: fadeInUp 1s 0.2s ease both;
  }
  .hero h1 {
    font-family: 'Fredoka One', cursive;
    font-size: clamp(2.8rem, 6vw, 4.5rem);
    line-height: 1.1;
    margin-bottom: 1.2rem;
    animation: fadeInUp 1s 0.3s ease both;
  }
  .hero h1 .highlight {
    background: linear-gradient(135deg, var(--berry), var(--blueberry));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    position: relative;
  }
  .hero p {
    font-size: 1.15rem;
    color: var(--text-light);
    line-height: 1.7;
    margin-bottom: 2rem;
    max-width: 500px;
    animation: fadeInUp 1s 0.4s ease both;
  }
  .hero-btns {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    animation: fadeInUp 1s 0.5s ease both;
  }
  .btn-primary {
    display: inline-flex; align-items: center; gap: 0.5rem;
    padding: 1rem 2rem;
    background: linear-gradient(135deg, var(--berry), var(--strawberry));
    color: white;
    border: none;
    border-radius: 50px;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    box-shadow: 0 8px 30px var(--shadow);
    transition: all 0.3s;
    text-decoration: none;
  }
  .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 12px 40px var(--shadow); }
  .btn-secondary {
    display: inline-flex; align-items: center; gap: 0.5rem;
    padding: 1rem 2rem;
    background: white;
    color: var(--berry);
    border: 2px solid var(--berry);
    border-radius: 50px;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.3s;
    text-decoration: none;
  }
  .btn-secondary:hover { background: var(--berry); color: white; transform: translateY(-3px); }

  .hero-visual {
    position: absolute;
    right: 5%;
    top: 50%;
    transform: translateY(-50%);
    z-index: 1;
    animation: float 6s ease-in-out infinite;
  }
  .ice-cream-cone {
    width: 320px; height: 420px;
    position: relative;
  }
  .scoop {
    width: 140px; height: 140px;
    border-radius: 50%;
    position: absolute;
    box-shadow: inset -10px -10px 20px rgba(0,0,0,0.1), 0 8px 30px rgba(0,0,0,0.1);
    transition: transform 0.4s;
  }
  .scoop:hover { transform: scale(1.1); }
  .scoop-1 { background: linear-gradient(135deg, #FFB6C1, #FF69B4); top: 0; left: 50%; transform: translateX(-50%); z-index: 3; }
  .scoop-1:hover { transform: translateX(-50%) scale(1.1); }
  .scoop-2 { background: linear-gradient(135deg, var(--mint), #5DADE2); top: 80px; left: 20px; z-index: 2; }
  .scoop-3 { background: linear-gradient(135deg, var(--mango), #F39C12); top: 80px; right: 20px; z-index: 2; }
  .cone-shape {
    position: absolute;
    top: 180px; left: 50%;
    transform: translateX(-50%);
    width: 0; height: 0;
    border-left: 80px solid transparent;
    border-right: 80px solid transparent;
    border-top: 220px solid #D4A04A;
    z-index: 1;
    filter: drop-shadow(0 10px 20px rgba(0,0,0,0.1));
  }
  .cone-shape::before {
    content: '';
    position: absolute;
    top: -215px; left: -70px;
    width: 140px; height: 80px;
    background: repeating-linear-gradient(
      45deg, transparent, transparent 8px, rgba(0,0,0,0.05) 8px, rgba(0,0,0,0.05) 16px
    );
  }
  .cherry {
    position: absolute;
    top: -15px; left: 50%; transform: translateX(-50%);
    width: 28px; height: 28px;
    background: radial-gradient(circle at 35% 35%, #FF1744, #B71C1C);
    border-radius: 50%;
    z-index: 4;
    box-shadow: 0 4px 10px rgba(183,28,28,0.3);
  }
  .cherry::before {
    content: '';
    position: absolute;
    top: -12px; left: 50%;
    width: 2px; height: 14px;
    background: #2E7D32;
    border-radius: 2px;
    transform: rotate(15deg);
  }

  @keyframes float {
    0%, 100% { transform: translateY(-50%); }
    50% { transform: translateY(calc(-50% - 20px)); }
  }
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ── Section Styles ── */
  section { position: relative; z-index: 1; }
  .section-header {
    text-align: center;
    margin-bottom: 3.5rem;
  }
  .section-tag {
    display: inline-block;
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 3px;
    color: var(--berry);
    margin-bottom: 0.8rem;
  }
  .section-header h2 {
    font-family: 'Fredoka One', cursive;
    font-size: clamp(2rem, 4vw, 3rem);
    color: var(--text);
  }

  /* ── About ── */
  .about {
    padding: 6rem 5%;
    background: white;
  }
  .about-grid {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
  }
  .about-img {
    position: relative;
    height: 400px;
    border-radius: 30px;
    overflow: hidden;
    background: linear-gradient(135deg, var(--vanilla), var(--strawberry));
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .about-img .factory-icon {
    font-size: 8rem;
    filter: drop-shadow(0 10px 20px rgba(0,0,0,0.1));
    animation: float 5s ease-in-out infinite;
  }
  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.2rem;
    margin-top: 2rem;
  }
  .stat-card {
    background: var(--cream);
    padding: 1.2rem;
    border-radius: 16px;
    text-align: center;
    transition: transform 0.3s;
  }
  .stat-card:hover { transform: translateY(-5px); }
  .stat-card .stat-num {
    font-family: 'Fredoka One', cursive;
    font-size: 1.8rem;
    color: var(--berry);
  }
  .stat-card .stat-label {
    font-size: 0.8rem;
    color: var(--text-light);
    font-weight: 600;
  }

  /* ── Flavors ── */
  .flavors {
    padding: 6rem 5%;
    background: var(--cream);
  }
  .flavor-carousel {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 2rem;
  }
  .flavor-card {
    background: white;
    border-radius: 24px;
    padding: 2rem;
    text-align: center;
    box-shadow: 0 8px 30px rgba(0,0,0,0.05);
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }
  .flavor-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 4px;
    border-radius: 4px 4px 0 0;
    transition: height 0.3s;
  }
  .flavor-card:hover { transform: translateY(-10px); box-shadow: 0 20px 60px rgba(0,0,0,0.1); }
  .flavor-card:hover::before { height: 6px; }
  .flavor-emoji {
    font-size: 4rem;
    margin-bottom: 1rem;
    display: block;
    transition: transform 0.4s;
  }
  .flavor-card:hover .flavor-emoji { transform: scale(1.2) rotate(-10deg); }
  .flavor-card h3 {
    font-family: 'Fredoka One', cursive;
    font-size: 1.2rem;
    margin-bottom: 0.5rem;
  }
  .flavor-card p {
    font-size: 0.85rem;
    color: var(--text-light);
    line-height: 1.5;
  }
  .flavor-card .price {
    display: inline-block;
    margin-top: 1rem;
    font-weight: 700;
    color: var(--berry);
    font-size: 1rem;
    background: rgba(214,25,110,0.08);
    padding: 0.4rem 1rem;
    border-radius: 50px;
  }
  .fc-berry::before { background: var(--berry); }
  .fc-mango::before { background: var(--mango); }
  .fc-pista::before { background: var(--pistachio); }
  .fc-choco::before { background: var(--chocolate); }
  .fc-vanilla::before { background: #F5DEB3; }
  .fc-blueberry::before { background: var(--blueberry); }

  /* ── Products ── */
  .products {
    padding: 6rem 5%;
    background: white;
  }
  .product-grid {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 2rem;
  }
  .product-card {
    background: var(--cream);
    border-radius: 24px;
    padding: 2.5rem 1.5rem;
    text-align: center;
    transition: all 0.4s;
    cursor: pointer;
  }
  .product-card:hover { transform: translateY(-8px); box-shadow: 0 15px 40px rgba(0,0,0,0.08); }
  .product-icon {
    font-size: 3.5rem;
    margin-bottom: 1rem;
    display: block;
  }
  .product-card h3 {
    font-family: 'Fredoka One', cursive;
    font-size: 1.1rem;
    margin-bottom: 0.4rem;
  }
  .product-card p {
    font-size: 0.82rem;
    color: var(--text-light);
  }

  /* ── Testimonials ── */
  .testimonials {
    padding: 6rem 5%;
    background: linear-gradient(135deg, var(--berry), var(--blueberry));
    color: white;
    position: relative;
    overflow: hidden;
  }
  .testimonials::before {
    content: '';
    position: absolute;
    width: 400px; height: 400px;
    border-radius: 50%;
    background: rgba(255,255,255,0.05);
    top: -100px; right: -100px;
  }
  .testimonials .section-tag { color: var(--mango); }
  .testimonials .section-header h2 { color: white; }
  .testimonial-grid {
    max-width: 1000px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
  }
  .testimonial-card {
    background: rgba(255,255,255,0.1);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 20px;
    padding: 2rem;
    transition: transform 0.3s;
  }
  .testimonial-card:hover { transform: translateY(-5px); }
  .stars { color: var(--mango); font-size: 1.1rem; margin-bottom: 1rem; }
  .testimonial-card p {
    font-size: 0.95rem;
    line-height: 1.7;
    margin-bottom: 1.2rem;
    opacity: 0.95;
  }
  .testimonial-author {
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }
  .author-avatar {
    width: 42px; height: 42px;
    border-radius: 50%;
    background: rgba(255,255,255,0.2);
    display: flex; align-items: center; justify-content: center;
    font-weight: 700;
    font-size: 0.9rem;
  }
  .author-name { font-weight: 700; font-size: 0.9rem; }
  .author-loc { font-size: 0.75rem; opacity: 0.7; }

  /* ── Contact ── */
  .contact {
    padding: 6rem 5%;
    background: var(--cream);
  }
  .contact-wrapper {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: start;
  }
  .contact-info {
    background: white;
    border-radius: 24px;
    padding: 2.5rem;
    box-shadow: 0 8px 30px rgba(0,0,0,0.05);
  }
  .contact-info h3 {
    font-family: 'Fredoka One', cursive;
    font-size: 1.5rem;
    margin-bottom: 1.5rem;
    color: var(--berry);
  }
  .contact-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1.5rem;
  }
  .contact-icon {
    width: 48px; height: 48px;
    background: linear-gradient(135deg, rgba(214,25,110,0.1), rgba(214,25,110,0.05));
    border-radius: 14px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.3rem;
    flex-shrink: 0;
  }
  .contact-item .label {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: var(--text-light);
    font-weight: 700;
    margin-bottom: 0.2rem;
  }
  .contact-item .value {
    font-weight: 600;
    font-size: 1rem;
    color: var(--text);
  }
  .contact-item a {
    color: var(--berry);
    text-decoration: none;
    font-weight: 600;
  }
  .contact-form {
    background: white;
    border-radius: 24px;
    padding: 2.5rem;
    box-shadow: 0 8px 30px rgba(0,0,0,0.05);
  }
  .contact-form h3 {
    font-family: 'Fredoka One', cursive;
    font-size: 1.5rem;
    margin-bottom: 1.5rem;
    color: var(--berry);
  }
  .form-group {
    margin-bottom: 1.2rem;
  }
  .form-group label {
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--text-light);
    display: block;
    margin-bottom: 0.4rem;
  }
  .form-group input,
  .form-group textarea,
  .form-group select {
    width: 100%;
    padding: 0.9rem 1.2rem;
    border: 2px solid #eee;
    border-radius: 14px;
    font-family: 'Quicksand', sans-serif;
    font-size: 0.95rem;
    font-weight: 500;
    transition: border-color 0.3s;
    background: var(--cream);
    color: var(--text);
    outline: none;
    resize: none;
  }
  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus {
    border-color: var(--berry);
  }
  .form-group textarea { min-height: 100px; }
  .form-submit {
    width: 100%;
    padding: 1rem;
    background: linear-gradient(135deg, var(--berry), var(--strawberry));
    color: white;
    border: none;
    border-radius: 14px;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.3s;
    box-shadow: 0 8px 25px var(--shadow);
  }
  .form-submit:hover { transform: translateY(-2px); box-shadow: 0 12px 35px var(--shadow); }
  .form-submit:active { transform: scale(0.98); }

  /* ── Footer ── */
  footer {
    background: var(--text);
    color: white;
    padding: 4rem 5% 2rem;
  }
  .footer-grid {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 1fr;
    gap: 3rem;
    margin-bottom: 3rem;
  }
  .footer-brand .footer-logo {
    font-family: 'Fredoka One', cursive;
    font-size: 1.8rem;
    color: var(--strawberry);
    margin-bottom: 0.8rem;
  }
  .footer-brand p {
    color: rgba(255,255,255,0.6);
    font-size: 0.9rem;
    line-height: 1.6;
  }
  .footer-col h4 {
    font-family: 'Fredoka One', cursive;
    font-size: 1rem;
    margin-bottom: 1rem;
    color: var(--strawberry);
  }
  .footer-col a {
    display: block;
    color: rgba(255,255,255,0.6);
    text-decoration: none;
    font-size: 0.9rem;
    margin-bottom: 0.6rem;
    transition: color 0.3s;
  }
  .footer-col a:hover { color: white; }
  .footer-bottom {
    max-width: 1100px;
    margin: 0 auto;
    border-top: 1px solid rgba(255,255,255,0.1);
    padding-top: 1.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .footer-bottom p {
    color: rgba(255,255,255,0.4);
    font-size: 0.8rem;
  }
  .social-links { display: flex; gap: 1rem; }
  .social-links a {
    width: 40px; height: 40px;
    background: rgba(255,255,255,0.08);
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    color: rgba(255,255,255,0.6);
    text-decoration: none;
    font-size: 1.1rem;
    transition: all 0.3s;
  }
  .social-links a:hover { background: var(--berry); color: white; transform: translateY(-3px); }

  /* ── Floating WhatsApp ── */
  .whatsapp-btn {
    position: fixed;
    bottom: 2rem;
    right: 2rem;
    width: 60px; height: 60px;
    background: #25D366;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 1.8rem;
    text-decoration: none;
    box-shadow: 0 6px 25px rgba(37,211,102,0.4);
    z-index: 999;
    transition: all 0.3s;
    animation: pulse 2s infinite;
  }
  .whatsapp-btn:hover { transform: scale(1.1); }
  @keyframes pulse {
    0%, 100% { box-shadow: 0 6px 25px rgba(37,211,102,0.4); }
    50% { box-shadow: 0 6px 40px rgba(37,211,102,0.6); }
  }

  /* ── Scroll Animations ── */
  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── Mobile ── */
  @media (max-width: 900px) {
    .hero-visual { display: none; }
    .hero-content { max-width: 100%; }
    .about-grid { grid-template-columns: 1fr; }
    .contact-wrapper { grid-template-columns: 1fr; }
    .footer-grid { grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 650px) {
    .nav-links { 
      display: none; 
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(255,248,240,0.98);
      backdrop-filter: blur(20px);
      flex-direction: column;
      justify-content: center;
      align-items: center;
      gap: 2rem;
    }
    .nav-links.open { display: flex; }
    .nav-links a { font-size: 1.3rem; }
    .hamburger { display: flex; }
    .footer-grid { grid-template-columns: 1fr; }
    .hero { padding: 7rem 5% 3rem; }
  }

  /* Flavor tab filter */
  .flavor-filters {
    display: flex;
    justify-content: center;
    gap: 0.8rem;
    margin-bottom: 2.5rem;
    flex-wrap: wrap;
  }
  .filter-btn {
    padding: 0.5rem 1.4rem;
    border: 2px solid #eee;
    border-radius: 50px;
    background: white;
    font-family: 'Quicksand', sans-serif;
    font-size: 0.85rem;
    font-weight: 700;
    color: var(--text-light);
    cursor: pointer;
    transition: all 0.3s;
  }
  .filter-btn:hover,
  .filter-btn.active {
    border-color: var(--berry);
    background: var(--berry);
    color: white;
  }

  /* Counter animation */
  .counter-section {
    padding: 4rem 5%;
    background: linear-gradient(135deg, var(--vanilla), var(--cream));
  }
  .counter-grid {
    max-width: 900px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2rem;
    text-align: center;
  }
  .counter-item .count {
    font-family: 'Fredoka One', cursive;
    font-size: clamp(2rem, 4vw, 2.8rem);
    color: var(--berry);
  }
  .counter-item .count-label {
    font-size: 0.85rem;
    color: var(--text-light);
    font-weight: 600;
    margin-top: 0.3rem;
  }
  @media (max-width: 600px) {
    .counter-grid { grid-template-columns: 1fr 1fr; }
  }

  /* owner section */
  .owner-section {
    padding: 5rem 5%;
    background: white;
  }
  .owner-card {
    max-width: 700px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    gap: 2.5rem;
    background: var(--cream);
    padding: 2.5rem;
    border-radius: 30px;
    box-shadow: 0 8px 30px rgba(0,0,0,0.05);
  }
  .owner-avatar {
    width: 120px; height: 120px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--berry), var(--strawberry));
    display: flex; align-items: center; justify-content: center;
    font-size: 3rem;
    color: white;
    font-family: 'Fredoka One', cursive;
    flex-shrink: 0;
    box-shadow: 0 10px 30px var(--shadow);
  }
  .owner-info h3 {
    font-family: 'Fredoka One', cursive;
    font-size: 1.5rem;
    margin-bottom: 0.3rem;
  }
  .owner-info .owner-title {
    color: var(--berry);
    font-weight: 700;
    font-size: 0.9rem;
    margin-bottom: 0.8rem;
  }
  .owner-info p {
    color: var(--text-light);
    font-size: 0.9rem;
    line-height: 1.7;
  }
  @media (max-width: 600px) {
    .owner-card { flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<!-- Sprinkles Background -->
<div class="sprinkles" id="sprinkles"></div>

<!-- Navbar -->
<nav id="navbar">
  <a href="#" class="nav-logo">
    <div class="logo-icon">🍨</div>
    <span>Top Berry</span>
  </a>
  <div class="nav-links" id="navLinks">
    <a href="#about">About</a>
    <a href="#flavors">Flavors</a>
    <a href="#products">Products</a>
    <a href="#reviews">Reviews</a>
    <a href="#contact" class="nav-cta">Contact Us</a>
  </div>
  <div class="hamburger" id="hamburger">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- Hero -->
<section class="hero" id="hero">
  <div class="hero-bg-circle"></div>
  <div class="hero-bg-circle"></div>
  <div class="hero-bg-circle"></div>

  <div class="hero-content">
    <div class="hero-badge">🏭 Crafted with Love in Samrala, Punjab</div>
    <h1>Scoops of <br><span class="highlight">Pure Happiness</span></h1>
    <p>Welcome to Top Berry — where every scoop is a celebration! Made from the freshest ingredients and bursting with authentic Punjabi flavour, our ice cream brings joy to every bite.</p>
    <div class="hero-btns">
      <a href="#flavors" class="btn-primary">🍓 Explore Flavors</a>
      <a href="tel:9888897911" class="btn-secondary">📞 Call Now</a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="ice-cream-cone">
      <div class="cherry"></div>
      <div class="scoop scoop-1"></div>
      <div class="scoop scoop-2"></div>
      <div class="scoop scoop-3"></div>
      <div class="cone-shape"></div>
    </div>
  </div>
</section>

<!-- Counter Section -->
<section class="counter-section">
  <div class="counter-grid">
    <div class="counter-item reveal">
      <div class="count" data-target="25">0</div>
      <div class="count-label">Flavors & Counting</div>
    </div>
    <div class="counter-item reveal">
      <div class="count" data-target="10000">0</div>
      <div class="count-label">Happy Customers</div>
    </div>
    <div class="counter-item reveal">
      <div class="count" data-target="50">0</div>
      <div class="count-label">Retail Partners</div>
    </div>
    <div class="counter-item reveal">
      <div class="count" data-target="100">0</div>
      <div class="count-label">% Natural Ingredients</div>
    </div>
  </div>
</section>

<!-- About -->
<section class="about" id="about">
  <div class="section-header reveal">
    <div class="section-tag">Our Story</div>
    <h2>Made in Punjab, Loved Everywhere</h2>
  </div>
  <div class="about-grid">
    <div class="about-img reveal">
      <div class="factory-icon">🏭</div>
    </div>
    <div class="reveal">
      <p style="font-size:1.05rem; line-height:1.8; color:var(--text-light); margin-bottom:1.5rem;">
        Born in the heart of <strong>Samrala, Punjab</strong>, Top Berry started with a simple dream — to create ice cream that feels like home. Our state-of-the-art factory combines traditional recipes with modern craftsmanship, ensuring every tub and cone is packed with authentic flavor and unmatched quality.
      </p>
      <p style="font-size:1.05rem; line-height:1.8; color:var(--text-light);">
        Founded by <strong>Shivam Sharma</strong>, we believe in using only the finest ingredients — real milk from local dairies, fresh fruits, and natural flavoring. No shortcuts, no artificial additives. Just pure, creamy goodness that keeps you coming back for more.
      </p>
      <div class="about-stats">
        <div class="stat-card">
          <div class="stat-num">100%</div>
          <div class="stat-label">Natural Ingredients</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">Fresh</div>
          <div class="stat-label">Local Dairy Milk</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">FSSAI</div>
          <div class="stat-label">Certified Quality</div>
        </div>
        <div class="stat-card">
          <div class="stat-num">24/7</div>
          <div class="stat-label">Cold Chain System</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Flavors -->
<section class="flavors" id="flavors">
  <div class="section-header reveal">
    <div class="section-tag">Our Flavors</div>
    <h2>Choose Your Happiness</h2>
  </div>

  <div class="flavor-filters reveal">
    <button class="filter-btn active" data-filter="all">All</button>
    <button class="filter-btn" data-filter="classic">Classic</button>
    <button class="filter-btn" data-filter="fruit">Fruity</button>
    <button class="filter-btn" data-filter="premium">Premium</button>
  </div>

  <div class="flavor-carousel">
    <div class="flavor-card fc-berry reveal" data-category="fruit">
      <span class="flavor-emoji">🍓</span>
      <h3>Strawberry Bliss</h3>
      <p>Real strawberry chunks in a creamy pink paradise</p>
      <div class="price">₹80 / Scoop</div>
    </div>
    <div class="flavor-card fc-mango reveal" data-category="fruit premium">
      <span class="flavor-emoji">🥭</span>
      <h3>Punjabi Mango</h3>
      <p>Alphonso mangoes blended into golden perfection</p>
      <div class="price">₹90 / Scoop</div>
    </div>
    <div class="flavor-card fc-pista reveal" data-category="premium">
      <span class="flavor-emoji">🌰</span>
      <h3>Royal Pista</h3>
      <p>Premium pistachios with a hint of cardamom</p>
      <div class="price">₹100 / Scoop</div>
    </div>
    <div class="flavor-card fc-choco reveal" data-category="classic">
      <span class="flavor-emoji">🍫</span>
      <h3>Dark Chocolate</h3>
      <p>Rich Belgian cocoa for the chocolate lover</p>
      <div class="price">₹85 / Scoop</div>
    </div>
    <div class="flavor-card fc-vanilla reveal" data-category="classic">
      <span class="flavor-emoji">🍦</span>
      <h3>Classic Vanilla</h3>
      <p>Madagascar vanilla beans in silky smooth cream</p>
      <div class="price">₹70 / Scoop</div>
    </div>
    <div class="flavor-card fc-blueberry reveal" data-category="fruit premium">
      <span class="flavor-emoji">🫐</span>
      <h3>Blueberry Swirl</h3>
      <p>Wild blueberry ripple through creamy base</p>
      <div class="price">₹95 / Scoop</div>
    </div>
  </div>
</section>

<!-- Products -->
<section class="products" id="products">
  <div class="section-header reveal">
    <div class="section-tag">Product Range</div>
    <h2>Something for Everyone</h2>
  </div>
  <div class="product-grid">
    <div class="product-card reveal">
      <span class="product-icon">🍦</span>
      <h3>Cones</h3>
      <p>Crunchy waffle cones with generous scoops</p>
    </div>
    <div class="product-card reveal">
      <span class="product-icon">🧊</span>
      <h3>Party Packs</h3>
      <p>500ml & 1L tubs for family gatherings</p>
    </div>
    <div class="product-card reveal">
      <span class="product-icon">🍡</span>
      <h3>Kulfi Sticks</h3>
      <p>Desi flavors in classic kulfi style</p>
    </div>
    <div class="product-card reveal">
      <span class="product-icon">🍧</span>
      <h3>Ice Candy</h3>
      <p>Refreshing fruit bars for summer</p>
    </div>
    <div class="product-card reveal">
      <span class="product-icon">🎂</span>
      <h3>Ice Cream Cakes</h3>
      <p>Celebration cakes in custom flavors</p>
    </div>
    <div class="product-card reveal">
      <span class="product-icon">🥤</span>
      <h3>Shakes & Sundaes</h3>
      <p>Thick shakes and loaded sundaes</p>
    </div>
  </div>
</section>

<!-- Owner -->
<section class="owner-section">
  <div class="section-header reveal">
    <div class="section-tag">Meet the Founder</div>
    <h2>The Man Behind the Magic</h2>
  </div>
  <div class="owner-card reveal">
    <div class="owner-avatar">SS</div>
    <div class="owner-info">
      <h3>Shivam Sharma</h3>
      <div class="owner-title">Founder & CEO, Top Berry</div>
      <p>With a passion for quality and an unwavering commitment to bringing smiles, Shivam started Top Berry to share the flavors of Punjab with the world. Every scoop reflects his dedication to using only the finest local ingredients and time-tested recipes.</p>
    </div>
  </div>
</section>

<!-- Testimonials -->
<section class="testimonials" id="reviews">
  <div class="section-header reveal">
    <div class="section-tag">Testimonials</div>
    <h2>What People Are Saying</h2>
  </div>
  <div class="testimonial-grid">
    <div class="testimonial-card reveal">
      <div class="stars">★★★★★</div>
      <p>"Top Berry's mango ice cream tastes like real Punjabi mangoes! My kids absolutely love it. Best ice cream in Samrala, hands down."</p>
      <div class="testimonial-author">
        <div class="author-avatar">RS</div>
        <div>
          <div class="author-name">Ranjit Singh</div>
          <div class="author-loc">Samrala, Punjab</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card reveal">
      <div class="stars">★★★★★</div>
      <p>"We serve Top Berry at our restaurant and customers always ask for more. The quality and consistency is simply unmatched in this region."</p>
      <div class="testimonial-author">
        <div class="author-avatar">PK</div>
        <div>
          <div class="author-name">Priya Kaur</div>
          <div class="author-loc">Ludhiana, Punjab</div>
        </div>
      </div>
    </div>
    <div class="testimonial-card reveal">
      <div class="stars">★★★★★</div>
      <p>"The pista kulfi took me back to my childhood. Pure, authentic flavors with no artificial taste. Top Berry is the real deal!"</p>
      <div class="testimonial-author">
        <div class="author-avatar">AG</div>
        <div>
          <div class="author-name">Amandeep Gill</div>
          <div class="author-loc">Khanna, Punjab</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Contact -->
<section class="contact" id="contact">
  <div class="section-header reveal">
    <div class="section-tag">Get in Touch</div>
    <h2>Let's Connect</h2>
  </div>
  <div class="contact-wrapper">
    <div class="contact-info reveal">
      <h3>Contact Details</h3>
      <div class="contact-item">
        <div class="contact-icon">👤</div>
        <div>
          <div class="label">Owner</div>
          <div class="value">Shivam Sharma</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📞</div>
        <div>
          <div class="label">Phone / WhatsApp</div>
          <div class="value"><a href="tel:9888897911">+91 98888 97911</a></div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <div>
          <div class="label">Factory Location</div>
          <div class="value">Samrala, District Ludhiana,<br>Punjab, India</div>
        </div>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🕐</div>
        <div>
          <div class="label">Working Hours</div>
          <div class="value">Mon - Sat: 8:00 AM – 8:00 PM<br>Sunday: 10:00 AM – 6:00 PM</div>
        </div>
      </div>
      <div style="margin-top:1.5rem; padding:1.2rem; background:linear-gradient(135deg,rgba(214,25,110,0.05),rgba(108,92,231,0.05)); border-radius:16px; text-align:center;">
        <div style="font-size:0.75rem; text-transform:uppercase; letter-spacing:1.5px; font-weight:700; color:var(--text-light); margin-bottom:0.5rem;">For Bulk Orders & Distribution</div>
        <a href="tel:9888897911" style="font-family:'Fredoka One',cursive; font-size:1.3rem; color:var(--berry); text-decoration:none;">📞 +91 98888 97911</a>
      </div>
    </div>

    <div class="contact-form reveal">
      <h3>Send a Message</h3>
      <form id="contactForm" onsubmit="handleSubmit(event)">
        <div class="form-group">
          <label>Your Name</label>
          <input type="text" placeholder="Enter your name" required>
        </div>
        <div class="form-group">
          <label>Phone Number</label>
          <input type="tel" placeholder="+91 XXXXX XXXXX" required>
        </div>
        <div class="form-group">
          <label>Inquiry Type</label>
          <select required>
            <option value="">Select type...</option>
            <option>Retail Order</option>
            <option>Bulk / Wholesale</option>
            <option>Distribution Partnership</option>
            <option>Franchise Inquiry</option>
            <option>Event / Catering</option>
            <option>Other</option>
          </select>
        </div>
        <div class="form-group">
          <label>Message</label>
          <textarea placeholder="Tell us how we can help you..." required></textarea>
        </div>
        <button type="submit" class="form-submit">Send Message 🍨</button>
      </form>
      <div id="formSuccess" style="display:none; text-align:center; padding:2rem;">
        <div style="font-size:4rem; margin-bottom:1rem;">🎉</div>
        <h3 style="font-family:'Fredoka One',cursive; color:var(--berry); margin-bottom:0.5rem;">Thank You!</h3>
        <p style="color:var(--text-light);">We'll get back to you shortly.<br>Enjoy some Top Berry in the meantime!</p>
      </div>
    </div>
  </div>
</section>

<!-- Footer -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <div class="footer-logo">🍨 Top Berry</div>
      <p>Premium ice cream crafted with love in Samrala, Punjab. Bringing smiles one scoop at a time since day one.</p>
    </div>
    <div class="footer-col">
      <h4>Quick Links</h4>
      <a href="#about">About Us</a>
      <a href="#flavors">Flavors</a>
      <a href="#products">Products</a>
      <a href="#reviews">Reviews</a>
    </div>
    <div class="footer-col">
      <h4>Products</h4>
      <a href="#">Ice Cream Tubs</a>
      <a href="#">Kulfi Sticks</a>
      <a href="#">Cones & Cups</a>
      <a href="#">Ice Cream Cakes</a>
    </div>
    <div class="footer-col">
      <h4>Contact</h4>
      <a href="tel:9888897911">+91 98888 97911</a>
      <a href="#">Samrala, Punjab</a>
      <a href="https://wa.me/919888897911">WhatsApp Us</a>
    </div>
  </div>
  <div class="footer-bottom">
    <p>&copy; 2025 Top Berry Ice Cream. All rights reserved. | Crafted with ❤️ in Samrala</p>
    <div class="social-links">
      <a href="https://wa.me/919888897911" title="WhatsApp">💬</a>
      <a href="tel:9888897911" title="Call">📞</a>
      <a href="#" title="Instagram">📸</a>
      <a href="#" title="Facebook">👍</a>
    </div>
  </div>
</footer>

<!-- WhatsApp Float -->
<a href="https://wa.me/919888897911?text=Hi%20Top%20Berry!%20I'd%20like%20to%20know%20more%20about%20your%20ice%20cream."
   class="whatsapp-btn" title="Chat on WhatsApp" target="_blank">💬</a>

<script>
  // ── Sprinkles Generator ──
  const sprinklesContainer = document.getElementById('sprinkles');
  const colors = ['#D6196E','#FF6B8A','#FDCB6E','#A8E6CF','#6C5CE7','#5DADE2','#F39C12','#E74C3C'];
  for (let i = 0; i < 30; i++) {
    const s = document.createElement('div');
    s.className = 'sprinkle';
    s.style.left = Math.random() * 100 + '%';
    s.style.background = colors[Math.floor(Math.random() * colors.length)];
    s.style.animationDuration = (8 + Math.random() * 12) + 's';
    s.style.animationDelay = (Math.random() * 15) + 's';
    s.style.transform = `rotate(${Math.random()*360}deg)`;
    sprinklesContainer.appendChild(s);
  }

  // ── Navbar scroll ──
  window.addEventListener('scroll', () => {
    document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 50);
  });

  // ── Hamburger menu ──
  document.getElementById('hamburger').addEventListener('click', function() {
    document.getElementById('navLinks').classList.toggle('open');
  });
  document.querySelectorAll('.nav-links a').forEach(link => {
    link.addEventListener('click', () => document.getElementById('navLinks').classList.remove('open'));
  });

  // ── Scroll Reveal ──
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
      }
    });
  }, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // ── Counter Animation ──
  const counterObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const el = entry.target;
        const target = parseInt(el.dataset.target);
        let current = 0;
        const increment = target / 60;
        const timer = setInterval(() => {
          current += increment;
          if (current >= target) {
            current = target;
            clearInterval(timer);
          }
          el.textContent = target >= 1000 ? Math.floor(current).toLocaleString() + '+' : Math.floor(current) + (target === 100 ? '%' : '+');
        }, 30);
        counterObserver.unobserve(el);
      }
    });
  }, { threshold: 0.5 });
  document.querySelectorAll('.count').forEach(el => counterObserver.observe(el));

  // ── Flavor Filter ──
  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.addEventListener('click', function() {
      document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
      this.classList.add('active');
      const filter = this.dataset.filter;
      document.querySelectorAll('.flavor-card').forEach(card => {
        if (filter === 'all' || card.dataset.category.includes(filter)) {
          card.style.display = '';
          card.style.animation = 'fadeInUp 0.5s ease both';
        } else {
          card.style.display = 'none';
        }
      });
    });
  });

  // ── Form submit ──
  function handleSubmit(e) {
    e.preventDefault();
    e.target.style.display = 'none';
    document.getElementById('formSuccess').style.display = 'block';
  }
</script>

</body>
</html>
