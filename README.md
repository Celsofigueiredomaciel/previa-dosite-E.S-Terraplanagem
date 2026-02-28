<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>E.S Terraplenagem e Construções LTDA</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@400;500;600;700&family=Barlow+Condensed:wght@700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --yellow: #FFD700;
      --yellow-dark: #e6c200;
      --black: #0a0a0a;
      --dark: #111111;
      --dark2: #1a1a1a;
      --gray: #888;
      --light-gray: #f5f5f5;
      --white: #ffffff;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Barlow', sans-serif;
      background: var(--black);
      color: var(--white);
      overflow-x: hidden;
    }

    /* ========== NAVBAR ========== */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 1000;
      background: rgba(10,10,10,0.95);
      backdrop-filter: blur(10px);
      border-bottom: 2px solid var(--yellow);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 5%;
      height: 70px;
    }

    .nav-logo {
      display: flex;
      align-items: center;
      gap: 12px;
      text-decoration: none;
    }

    .nav-logo-icon {
      font-size: 2rem;
    }

    .nav-logo-text {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.4rem;
      color: var(--yellow);
      letter-spacing: 2px;
      line-height: 1.1;
    }

    .nav-logo-text span {
      display: block;
      font-family: 'Barlow', sans-serif;
      font-size: 0.65rem;
      font-weight: 600;
      color: var(--gray);
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 2rem;
    }

    .nav-links a {
      color: var(--white);
      text-decoration: none;
      font-weight: 600;
      font-size: 0.85rem;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      position: relative;
      transition: color 0.3s;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px; left: 0;
      width: 0; height: 2px;
      background: var(--yellow);
      transition: width 0.3s;
    }

    .nav-links a:hover { color: var(--yellow); }
    .nav-links a:hover::after { width: 100%; }

    .nav-cta {
      background: var(--yellow);
      color: var(--black) !important;
      padding: 8px 20px;
      font-weight: 700 !important;
      transition: background 0.3s !important;
    }

    .nav-cta:hover { background: var(--yellow-dark) !important; }
    .nav-cta::after { display: none !important; }

    .menu-toggle {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      background: none;
      border: none;
      padding: 5px;
    }

    .menu-toggle span {
      display: block;
      width: 24px; height: 2px;
      background: var(--yellow);
      transition: all 0.3s;
    }

    /* ========== HERO ========== */
    #hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      position: relative;
      overflow: hidden;
      background: var(--dark);
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse at 70% 50%, rgba(255,215,0,0.08) 0%, transparent 60%),
        linear-gradient(135deg, #0a0a0a 0%, #111 50%, #0a0a0a 100%);
    }

    .hero-pattern {
      position: absolute;
      inset: 0;
      background-image:
        repeating-linear-gradient(
          0deg,
          transparent,
          transparent 40px,
          rgba(255,215,0,0.03) 40px,
          rgba(255,215,0,0.03) 41px
        ),
        repeating-linear-gradient(
          90deg,
          transparent,
          transparent 40px,
          rgba(255,215,0,0.03) 40px,
          rgba(255,215,0,0.03) 41px
        );
    }

    .hero-content {
      position: relative;
      z-index: 2;
      padding: 0 5%;
      padding-top: 70px;
      max-width: 900px;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(255,215,0,0.1);
      border: 1px solid rgba(255,215,0,0.3);
      color: var(--yellow);
      padding: 6px 16px;
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 3px;
      text-transform: uppercase;
      margin-bottom: 2rem;
      animation: fadeInUp 0.6s ease both;
    }

    .hero-tag::before {
      content: '';
      width: 6px; height: 6px;
      background: var(--yellow);
      border-radius: 50%;
      animation: pulse 1.5s infinite;
    }

    .hero-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(3.5rem, 8vw, 7rem);
      line-height: 0.95;
      letter-spacing: -1px;
      animation: fadeInUp 0.6s 0.1s ease both;
    }

    .hero-title .line-yellow { color: var(--yellow); }

    .hero-title .line-stroke {
      -webkit-text-stroke: 2px rgba(255,215,0,0.4);
      color: transparent;
    }

    .hero-subtitle {
      margin-top: 1.5rem;
      font-size: 1.1rem;
      color: #aaa;
      max-width: 500px;
      line-height: 1.7;
      animation: fadeInUp 0.6s 0.2s ease both;
    }

    .hero-actions {
      margin-top: 2.5rem;
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      animation: fadeInUp 0.6s 0.3s ease both;
    }

    .btn-primary {
      background: var(--yellow);
      color: var(--black);
      padding: 14px 32px;
      font-weight: 700;
      font-size: 0.9rem;
      letter-spacing: 1px;
      text-transform: uppercase;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s;
      clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
    }

    .btn-primary:hover {
      background: var(--yellow-dark);
      transform: translateY(-2px);
      box-shadow: 0 10px 30px rgba(255,215,0,0.3);
    }

    .btn-secondary {
      border: 2px solid rgba(255,255,255,0.2);
      color: var(--white);
      padding: 14px 32px;
      font-weight: 600;
      font-size: 0.9rem;
      letter-spacing: 1px;
      text-transform: uppercase;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s;
    }

    .btn-secondary:hover {
      border-color: var(--yellow);
      color: var(--yellow);
    }

    .hero-stats {
      position: absolute;
      right: 5%;
      bottom: 10%;
      display: flex;
      gap: 3rem;
      animation: fadeInUp 0.6s 0.4s ease both;
    }

    .stat {
      text-align: center;
    }

    .stat-num {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 3rem;
      color: var(--yellow);
      line-height: 1;
    }

    .stat-label {
      font-size: 0.7rem;
      color: var(--gray);
      letter-spacing: 2px;
      text-transform: uppercase;
      margin-top: 4px;
    }

    .hero-scroll {
      position: absolute;
      bottom: 2rem;
      left: 5%;
      display: flex;
      align-items: center;
      gap: 10px;
      color: var(--gray);
      font-size: 0.75rem;
      letter-spacing: 2px;
      text-transform: uppercase;
      animation: fadeInUp 0.6s 0.5s ease both;
    }

    .scroll-line {
      width: 40px; height: 1px;
      background: var(--gray);
    }

    /* ========== SECTIONS ========== */
    section { padding: 6rem 5%; }

    .section-tag {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      color: var(--yellow);
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 3px;
      text-transform: uppercase;
      margin-bottom: 1rem;
    }

    .section-tag::before {
      content: '';
      width: 30px; height: 2px;
      background: var(--yellow);
    }

    .section-title {
      font-family: 'Bebas Neue', sans-serif;
      font-size: clamp(2.5rem, 5vw, 4rem);
      line-height: 1;
      letter-spacing: 1px;
    }

    /* ========== SERVIÇOS ========== */
    #servicos {
      background: var(--dark2);
    }

    .servicos-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-bottom: 3rem;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .servicos-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5px;
    }

    .servico-card {
      background: var(--dark);
      padding: 2.5rem 2rem;
      position: relative;
      overflow: hidden;
      transition: all 0.4s;
      cursor: default;
    }

    .servico-card::before {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      width: 0; height: 3px;
      background: var(--yellow);
      transition: width 0.4s;
    }

    .servico-card:hover::before { width: 100%; }
    .servico-card:hover { background: #161616; transform: translateY(-4px); }

    .servico-icon {
      font-size: 2.5rem;
      margin-bottom: 1.2rem;
      display: block;
    }

    .servico-num {
      position: absolute;
      top: 1.5rem; right: 1.5rem;
      font-family: 'Bebas Neue', sans-serif;
      font-size: 4rem;
      color: rgba(255,215,0,0.05);
      line-height: 1;
    }

    .servico-card h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.3rem;
      font-weight: 700;
      letter-spacing: 1px;
      text-transform: uppercase;
      margin-bottom: 0.8rem;
      color: var(--white);
    }

    .servico-card p {
      color: #888;
      font-size: 0.9rem;
      line-height: 1.7;
    }

    /* ========== SOBRE ========== */
    #sobre {
      background: var(--black);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
    }

    .sobre-text .section-title { margin-bottom: 1.5rem; }

    .sobre-text p {
      color: #aaa;
      line-height: 1.8;
      font-size: 1rem;
      margin-bottom: 1.5rem;
    }

    .sobre-diferenciais {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      margin-top: 2rem;
    }

    .diferencial {
      display: flex;
      align-items: flex-start;
      gap: 10px;
    }

    .diferencial-icon {
      width: 36px; height: 36px;
      background: rgba(255,215,0,0.1);
      border: 1px solid rgba(255,215,0,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1rem;
      flex-shrink: 0;
    }

    .diferencial-text {
      font-size: 0.85rem;
      color: #ccc;
      font-weight: 600;
      line-height: 1.4;
    }

    .sobre-visual {
      position: relative;
    }

    .sobre-img-container {
      position: relative;
      background: var(--dark2);
      aspect-ratio: 4/3;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .sobre-img-container img {
      width: 80%;
      max-width: 320px;
      object-fit: contain;
    }

    .sobre-badge {
      position: absolute;
      bottom: -1.5rem;
      right: -1.5rem;
      background: var(--yellow);
      color: var(--black);
      padding: 1.5rem;
      font-family: 'Bebas Neue', sans-serif;
      text-align: center;
      line-height: 1.1;
    }

    .sobre-badge-num { font-size: 2.5rem; }
    .sobre-badge-text { font-size: 0.85rem; letter-spacing: 1px; }

    .sobre-accent {
      position: absolute;
      top: -1rem; left: -1rem;
      width: 60px; height: 60px;
      border-top: 3px solid var(--yellow);
      border-left: 3px solid var(--yellow);
    }

    /* ========== GALERIA ========== */
    #projetos {
      background: var(--dark2);
    }

    .projetos-header {
      margin-bottom: 2.5rem;
    }

    .galeria-filtros {
      display: flex;
      gap: 0.5rem;
      flex-wrap: wrap;
      margin-top: 1.5rem;
    }

    .filtro-btn {
      background: none;
      border: 1px solid rgba(255,255,255,0.15);
      color: #888;
      padding: 6px 16px;
      font-family: 'Barlow', sans-serif;
      font-size: 0.8rem;
      font-weight: 600;
      letter-spacing: 1px;
      text-transform: uppercase;
      cursor: pointer;
      transition: all 0.3s;
    }

    .filtro-btn.active, .filtro-btn:hover {
      background: var(--yellow);
      border-color: var(--yellow);
      color: var(--black);
    }

    .galeria-grid {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      grid-auto-rows: 200px;
      gap: 6px;
      margin-top: 1.5rem;
    }

    .galeria-item {
      background: var(--dark);
      position: relative;
      overflow: hidden;
      cursor: pointer;
    }

    .galeria-item:nth-child(1) { grid-column: span 5; grid-row: span 2; }
    .galeria-item:nth-child(2) { grid-column: span 4; grid-row: span 1; }
    .galeria-item:nth-child(3) { grid-column: span 3; grid-row: span 1; }
    .galeria-item:nth-child(4) { grid-column: span 4; grid-row: span 1; }
    .galeria-item:nth-child(5) { grid-column: span 3; grid-row: span 1; }
    .galeria-item:nth-child(6) { grid-column: span 5; grid-row: span 1; }
    .galeria-item:nth-child(7) { grid-column: span 7; grid-row: span 1; }

    .galeria-item img, .galeria-item video {
      width: 100%; height: 100%;
      object-fit: cover;
      display: block;
    }

    .galeria-placeholder {
      width: 100%; height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #1a1a1a 0%, #222 100%);
      border: 2px dashed rgba(255,215,0,0.15);
      color: rgba(255,215,0,0.3);
      gap: 8px;
      transition: all 0.3s;
    }

    .galeria-placeholder:hover {
      border-color: rgba(255,215,0,0.4);
      background: #1f1f1f;
    }

    .galeria-placeholder-icon { font-size: 2rem; }
    .galeria-placeholder-text { font-size: 0.75rem; letter-spacing: 2px; text-transform: uppercase; }

    .galeria-overlay {
      position: absolute;
      inset: 0;
      background: rgba(0,0,0,0.7);
      display: flex;
      align-items: center;
      justify-content: center;
      opacity: 0;
      transition: opacity 0.3s;
    }

    .galeria-item:hover .galeria-overlay { opacity: 1; }

    .galeria-overlay-icon { font-size: 2.5rem; }

    /* ========== CONTATO ========== */
    #contato {
      background: var(--black);
    }

    .contato-grid {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 5rem;
      align-items: start;
      margin-top: 3rem;
    }

    .contato-info h3 {
      font-family: 'Barlow Condensed', sans-serif;
      font-size: 1.5rem;
      font-weight: 700;
      letter-spacing: 1px;
      text-transform: uppercase;
      margin-bottom: 0.5rem;
    }

    .contato-info p {
      color: #888;
      line-height: 1.7;
      font-size: 0.95rem;
      margin-bottom: 2rem;
    }

    .contato-items {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .contato-item {
      display: flex;
      align-items: center;
      gap: 1rem;
      padding: 1rem;
      background: var(--dark2);
      border-left: 3px solid var(--yellow);
      text-decoration: none;
      color: var(--white);
      transition: all 0.3s;
    }

    .contato-item:hover { background: #1f1f1f; padding-left: 1.5rem; }

    .contato-item-icon {
      font-size: 1.4rem;
      width: 40px;
      text-align: center;
    }

    .contato-item-label {
      font-size: 0.7rem;
      color: var(--yellow);
      letter-spacing: 2px;
      text-transform: uppercase;
      font-weight: 700;
    }

    .contato-item-value {
      font-size: 0.95rem;
      font-weight: 600;
    }

    .whatsapp-btn {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      background: #25D366;
      color: white;
      padding: 16px 32px;
      font-weight: 700;
      font-size: 1rem;
      letter-spacing: 1px;
      text-transform: uppercase;
      text-decoration: none;
      margin-top: 2rem;
      transition: all 0.3s;
      clip-path: polygon(0 0, calc(100% - 12px) 0, 100% 12px, 100% 100%, 12px 100%, 0 calc(100% - 12px));
    }

    .whatsapp-btn:hover {
      background: #20bc5a;
      transform: translateY(-2px);
      box-shadow: 0 10px 30px rgba(37,211,102,0.3);
    }

    /* Formulário */
    .contato-form {
      background: var(--dark2);
      padding: 2.5rem;
      border-top: 3px solid var(--yellow);
    }

    .contato-form h3 {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.8rem;
      letter-spacing: 2px;
      margin-bottom: 1.5rem;
    }

    .form-group {
      margin-bottom: 1.2rem;
    }

    .form-group label {
      display: block;
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--yellow);
      margin-bottom: 6px;
    }

    .form-group input,
    .form-group textarea,
    .form-group select {
      width: 100%;
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(255,255,255,0.1);
      color: var(--white);
      padding: 12px 16px;
      font-family: 'Barlow', sans-serif;
      font-size: 0.95rem;
      outline: none;
      transition: border-color 0.3s;
      -webkit-appearance: none;
    }

    .form-group select option { background: #222; }

    .form-group input:focus,
    .form-group textarea:focus,
    .form-group select:focus {
      border-color: var(--yellow);
    }

    .form-group textarea { resize: vertical; min-height: 100px; }

    .form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }

    .btn-submit {
      width: 100%;
      background: var(--yellow);
      color: var(--black);
      border: none;
      padding: 14px;
      font-family: 'Barlow', sans-serif;
      font-size: 0.9rem;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
      cursor: pointer;
      transition: all 0.3s;
      margin-top: 0.5rem;
    }

    .btn-submit:hover {
      background: var(--yellow-dark);
      box-shadow: 0 5px 20px rgba(255,215,0,0.3);
    }

    /* ========== FOOTER ========== */
    footer {
      background: var(--dark2);
      border-top: 1px solid rgba(255,255,255,0.05);
      padding: 3rem 5%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .footer-logo {
      font-family: 'Bebas Neue', sans-serif;
      font-size: 1.5rem;
      color: var(--yellow);
      letter-spacing: 2px;
    }

    .footer-logo span {
      display: block;
      font-family: 'Barlow', sans-serif;
      font-size: 0.65rem;
      color: var(--gray);
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .footer-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .footer-links a {
      color: var(--gray);
      text-decoration: none;
      font-size: 0.85rem;
      transition: color 0.3s;
    }

    .footer-links a:hover { color: var(--yellow); }

    .footer-copy {
      color: #555;
      font-size: 0.8rem;
    }

    /* ========== MODAL DE FOTO ========== */
    .modal-overlay {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.95);
      z-index: 9999;
      display: none;
      align-items: center;
      justify-content: center;
      padding: 2rem;
    }

    .modal-overlay.active { display: flex; }

    .modal-img {
      max-width: 90vw;
      max-height: 85vh;
      object-fit: contain;
    }

    .modal-close {
      position: absolute;
      top: 1.5rem; right: 1.5rem;
      background: none;
      border: none;
      color: var(--white);
      font-size: 2rem;
      cursor: pointer;
      transition: color 0.3s;
    }

    .modal-close:hover { color: var(--yellow); }

    /* ========== WHATSAPP FLUTUANTE ========== */
    .float-whatsapp {
      position: fixed;
      bottom: 2rem;
      right: 2rem;
      z-index: 999;
      background: #25D366;
      color: white;
      width: 60px; height: 60px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.8rem;
      text-decoration: none;
      box-shadow: 0 4px 20px rgba(37,211,102,0.5);
      animation: float 3s ease-in-out infinite;
      transition: transform 0.3s;
    }

    .float-whatsapp:hover { transform: scale(1.1); }

    /* ========== ANIMATIONS ========== */
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.5; transform: scale(0.8); }
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-8px); }
    }

    /* Reveal on scroll */
    .reveal {
      opacity: 0;
      transform: translateY(40px);
      transition: all 0.7s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ========== RESPONSIVO ========== */
    @media (max-width: 900px) {
      #sobre {
        grid-template-columns: 1fr;
        gap: 3rem;
        padding: 4rem 5%;
      }

      .sobre-badge { bottom: -1rem; right: 0; }

      .contato-grid {
        grid-template-columns: 1fr;
        gap: 3rem;
      }

      .hero-stats {
        position: static;
        margin-top: 3rem;
        flex-wrap: wrap;
        gap: 2rem;
      }

      .galeria-grid {
        grid-template-columns: 1fr 1fr;
        grid-auto-rows: 160px;
      }

      .galeria-item:nth-child(n) {
        grid-column: span 1;
        grid-row: span 1;
      }
      .galeria-item:nth-child(1) { grid-column: span 2; }

      nav { padding: 0 4%; }

      .nav-links { display: none; }
      .nav-links.open {
        display: flex;
        flex-direction: column;
        position: absolute;
        top: 70px; left: 0; right: 0;
        background: rgba(10,10,10,0.98);
        padding: 1.5rem;
        gap: 1rem;
        border-bottom: 2px solid var(--yellow);
      }

      .menu-toggle { display: flex; }

      .form-row { grid-template-columns: 1fr; }

      .sobre-diferenciais { grid-template-columns: 1fr; }

      footer {
        flex-direction: column;
        text-align: center;
      }

      .footer-links { flex-wrap: wrap; justify-content: center; }
    }

    @media (max-width: 480px) {
      .hero-content { padding-top: 100px; }
      .hero-actions { flex-direction: column; }
      .btn-primary, .btn-secondary { text-align: center; justify-content: center; }
    }
  </style>
</head>
<body>

<!-- NAVBAR -->
<nav id="navbar">
  <a href="#hero" class="nav-logo">
    <div class="nav-logo-text">
      E.S Terraplenagem
      <span>e Construções LTDA</span>
    </div>
  </a>
  <ul class="nav-links" id="navLinks">
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#projetos">Projetos</a></li>
    <li><a href="#contato" class="nav-cta">Orçamento</a></li>
  </ul>
  <button class="menu-toggle" id="menuToggle" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-pattern"></div>
  <div class="hero-content">
    <div class="hero-tag">🚜 Especialistas em Terraplenagem</div>
    <h1 class="hero-title">
      <div>Movemos</div>
      <div class="line-yellow">A Terra.</div>
      <div class="line-stroke">Construímos</div>
      <div>O Futuro.</div>
    </h1>
    <p class="hero-subtitle">
      Soluções completas em terraplenagem e construção civil. Equipamentos modernos, equipe especializada e compromisso com cada projeto.
    </p>
    <div class="hero-actions">
      <a href="#contato" class="btn-primary">📋 Solicitar Orçamento</a>
      <a href="#projetos" class="btn-secondary">🏗️ Ver Projetos</a>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat">
      <div class="stat-num">10+</div>
      <div class="stat-label">Anos de<br>Experiência</div>
    </div>
    <div class="stat">
      <div class="stat-num">200+</div>
      <div class="stat-label">Projetos<br>Concluídos</div>
    </div>
    <div class="stat">
      <div class="stat-num">100%</div>
      <div class="stat-label">Clientes<br>Satisfeitos</div>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    Role para baixo
  </div>
</section>

<!-- SERVIÇOS -->
<section id="servicos">
  <div class="servicos-header reveal">
    <div>
      <div class="section-tag">O que fazemos</div>
      <h2 class="section-title">Nossos Serviços</h2>
    </div>
    <p style="color: #888; max-width: 350px; font-size: 0.95rem; line-height: 1.6;">
      Atendemos projetos de todos os portes com equipamentos de última geração.
    </p>
  </div>
  <div class="servicos-grid">
    <div class="servico-card reveal">
      <span class="servico-icon">🏔️</span>
      <span class="servico-num">01</span>
      <h3>Terraplenagem</h3>
      <p>Corte, aterro e nivelamento de terrenos para obras civis, loteamentos e projetos industriais.</p>
    </div>
    <div class="servico-card reveal">
      <span class="servico-icon">🏗️</span>
      <span class="servico-num">02</span>
      <h3>Construção Civil</h3>
      <p>Execução de obras estruturais com qualidade e segurança em todas as etapas do processo.</p>
    </div>
    <div class="servico-card reveal">
      <span class="servico-icon">🚧</span>
      <span class="servico-num">03</span>
      <h3>Abertura de Vias</h3>
      <p>Abertura e pavimentação de estradas, acessos rurais e vias urbanas.</p>
    </div>
    <div class="servico-card reveal">
      <span class="servico-icon">💧</span>
      <span class="servico-num">04</span>
      <h3>Drenagem</h3>
      <p>Sistemas de drenagem superficial e subterrânea para controle de águas pluviais.</p>
    </div>
    <div class="servico-card reveal">
      <span class="servico-icon">🔩</span>
      <span class="servico-num">05</span>
      <h3>Contenção de Encostas</h3>
      <p>Soluções de estabilização de taludes e contenção de erosão em terrenos críticos.</p>
    </div>
    <div class="servico-card reveal">
      <span class="servico-icon">📐</span>
      <span class="servico-num">06</span>
      <h3>Preparação de Terrenos</h3>
      <p>Limpeza, destoca, compactação e preparação de terrenos para qualquer finalidade.</p>
    </div>
  </div>
</section>

<!-- SOBRE -->
<section id="sobre">
  <div class="sobre-text reveal">
    <div class="section-tag">Quem somos</div>
    <h2 class="section-title">Experiência que<br>Você Pode Confiar</h2>
    <p>
      A <strong style="color:var(--white)">E.S Terraplenagem e Construções LTDA</strong> é uma empresa sólida, com anos de atuação no mercado de terraplenagem e construção civil. Nossa trajetória é marcada por projetos executados com excelência técnica e compromisso com os prazos.
    </p>
    <p>
      Contamos com uma frota de equipamentos modernos e uma equipe altamente qualificada, pronta para enfrentar os mais diversos desafios do setor.
    </p>
    <div class="sobre-diferenciais">
      <div class="diferencial">
        <div class="diferencial-icon">⚡</div>
        <div class="diferencial-text">Agilidade na execução</div>
      </div>
      <div class="diferencial">
        <div class="diferencial-icon">🛡️</div>
        <div class="diferencial-text">Segurança em primeiro lugar</div>
      </div>
      <div class="diferencial">
        <div class="diferencial-icon">🎯</div>
        <div class="diferencial-text">Comprometimento com prazos</div>
      </div>
      <div class="diferencial">
        <div class="diferencial-icon">🏆</div>
        <div class="diferencial-text">Alta qualidade garantida</div>
      </div>
    </div>
  </div>
  <div class="sobre-visual reveal">
    <div class="sobre-accent"></div>
    <div class="sobre-img-container">
      <!-- Substitua o src pelo caminho da logo real -->
      <img src="images/logo/logo.jpeg" alt="E.S Terraplenagem" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex'">
      <div style="display:none; flex-direction:column; align-items:center; gap:1rem; color: rgba(255,215,0,0.5); text-align:center; padding:2rem;">
        <div style="font-size:4rem;">🚜</div>
        <div style="font-family:'Bebas Neue',sans-serif; font-size:1.5rem; letter-spacing:3px;">E.S TERRAPLENAGEM</div>
        <div style="font-size:0.75rem; letter-spacing:2px; color:#666; text-transform:uppercase;">e Construções LTDA</div>
      </div>
    </div>
    <div class="sobre-badge">
      <div class="sobre-badge-num">10+</div>
      <div class="sobre-badge-text">Anos no<br>Mercado</div>
    </div>
  </div>
</section>

<!-- PROJETOS / GALERIA -->
<section id="projetos">
  <div class="projetos-header reveal">
    <div class="section-tag">Portfólio</div>
    <h2 class="section-title">Nossos Projetos</h2>
    <div class="galeria-filtros">
      <button class="filtro-btn active">Todos</button>
      <button class="filtro-btn">Terraplenagem</button>
      <button class="filtro-btn">Construção</button>
      <button class="filtro-btn">Estradas</button>
    </div>
  </div>

  <!-- 
    GALERIA DE FOTOS E VÍDEOS
    Para adicionar fotos: substitua o conteúdo dentro de .galeria-item
    Exemplo com foto:
      <img src="images/projetos/foto1.jpg" alt="Projeto 1">
    Exemplo com vídeo:
      <video autoplay muted loop playsinline>
        <source src="videos/projeto1.mp4" type="video/mp4">
      </video>
  -->
  <div class="galeria-grid">
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">📷</div>
        <div class="galeria-placeholder-text">Foto Principal</div>
      </div>
      <div class="galeria-overlay"><div class="galeria-overlay-icon">🔍</div></div>
    </div>
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">🎬</div>
        <div class="galeria-placeholder-text">Vídeo</div>
      </div>
    </div>
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">📷</div>
        <div class="galeria-placeholder-text">Foto</div>
      </div>
      <div class="galeria-overlay"><div class="galeria-overlay-icon">🔍</div></div>
    </div>
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">📷</div>
        <div class="galeria-placeholder-text">Foto</div>
      </div>
      <div class="galeria-overlay"><div class="galeria-overlay-icon">🔍</div></div>
    </div>
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">🎬</div>
        <div class="galeria-placeholder-text">Vídeo Loop</div>
      </div>
    </div>
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">📷</div>
        <div class="galeria-placeholder-text">Foto</div>
      </div>
      <div class="galeria-overlay"><div class="galeria-overlay-icon">🔍</div></div>
    </div>
    <div class="galeria-item reveal">
      <div class="galeria-placeholder">
        <div class="galeria-placeholder-icon">📷</div>
        <div class="galeria-placeholder-text">Foto</div>
      </div>
      <div class="galeria-overlay"><div class="galeria-overlay-icon">🔍</div></div>
    </div>
  </div>
</section>

<!-- CONTATO -->
<section id="contato">
  <div class="section-tag reveal">Fale Conosco</div>
  <h2 class="section-title reveal">Solicite seu Orçamento</h2>

  <div class="contato-grid">
    <div class="contato-info reveal">
      <h3>Entre em Contato</h3>
      <p>Estamos prontos para atender seu projeto. Entre em contato e receba um orçamento personalizado.</p>
      <div class="contato-items">
        <a href="https://wa.me/5500000000000" class="contato-item" target="_blank" id="whatsapp-link">
          <div class="contato-item-icon">📱</div>
          <div>
            <div class="contato-item-label">WhatsApp</div>
            <div class="contato-item-value">(00) 00000-0000</div>
          </div>
        </a>
        <a href="mailto:contato@esterraplenagem.com.br" class="contato-item" id="email-link">
          <div class="contato-item-icon">📧</div>
          <div>
            <div class="contato-item-label">E-mail</div>
            <div class="contato-item-value">contato@esterraplenagem.com.br</div>
          </div>
        </a>
        <div class="contato-item">
          <div class="contato-item-icon">📍</div>
          <div>
            <div class="contato-item-label">Endereço</div>
            <div class="contato-item-value">Seu Endereço Aqui</div>
          </div>
        </div>
        <div class="contato-item">
          <div class="contato-item-icon">🕐</div>
          <div>
            <div class="contato-item-label">Horário</div>
            <div class="contato-item-value">Seg–Sex: 7h às 18h | Sáb: 7h às 13h</div>
          </div>
        </div>
      </div>
      <a href="https://wa.me/5500000000000" class="whatsapp-btn" target="_blank" id="whatsapp-btn">
        <span style="font-size:1.3rem">📱</span>
        Chamar no WhatsApp
      </a>
    </div>

    <div class="contato-form reveal">
      <h3>Solicitar Orçamento</h3>
      <div class="form-row">
        <div class="form-group">
          <label>Nome</label>
          <input type="text" placeholder="Seu nome completo" id="f-nome">
        </div>
        <div class="form-group">
          <label>Telefone</label>
          <input type="tel" placeholder="(00) 00000-0000" id="f-tel">
        </div>
      </div>
      <div class="form-group">
        <label>Serviço Desejado</label>
        <select id="f-servico">
          <option value="">Selecione...</option>
          <option>Terraplenagem</option>
          <option>Construção Civil</option>
          <option>Abertura de Vias</option>
          <option>Drenagem</option>
          <option>Contenção de Encostas</option>
          <option>Preparação de Terreno</option>
          <option>Outro</option>
        </select>
      </div>
      <div class="form-group">
        <label>Descreva seu Projeto</label>
        <textarea placeholder="Conte-nos sobre seu projeto, localização, área aproximada..." id="f-msg"></textarea>
      </div>
      <button class="btn-submit" onclick="enviarWhatsApp()">
        📋 Enviar via WhatsApp
      </button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">
    E.S Terraplenagem
    <span>e Construções LTDA</span>
  </div>
  <ul class="footer-links">
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#projetos">Projetos</a></li>
    <li><a href="#contato">Contato</a></li>
  </ul>
  <div class="footer-copy">© 2025 E.S Terraplenagem e Construções LTDA. Todos os direitos reservados.</div>
</footer>

<!-- MODAL -->
<div class="modal-overlay" id="modal">
  <button class="modal-close" onclick="fecharModal()">✕</button>
  <img class="modal-img" id="modalImg" src="" alt="">
</div>

<!-- WhatsApp Flutuante -->
<a href="https://wa.me/5500000000000" class="float-whatsapp" target="_blank" id="float-wa" title="Chamar no WhatsApp">
  📱
</a>

<script>
  // ===== CONFIGURAÇÃO =====
  // TROQUE AQUI com os dados reais da empresa!
  const CONFIG = {
    whatsapp: '5500000000000',  // Ex: 5591999999999
    email: 'contato@esterraplenagem.com.br',
    endereco: 'Seu Endereço Aqui'
  };

  // Atualiza links de WhatsApp
  document.querySelectorAll('#whatsapp-link, #whatsapp-btn, #float-wa').forEach(el => {
    el.href = `https://wa.me/${CONFIG.whatsapp}`;
  });

  // ===== MENU MOBILE =====
  const menuToggle = document.getElementById('menuToggle');
  const navLinks = document.getElementById('navLinks');
  menuToggle.addEventListener('click', () => navLinks.classList.toggle('open'));
  navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => navLinks.classList.remove('open')));

  // ===== SCROLL REVEAL =====
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // ===== GALERIA - ABRIR MODAL =====
  document.querySelectorAll('.galeria-item img').forEach(img => {
    img.addEventListener('click', () => {
      document.getElementById('modalImg').src = img.src;
      document.getElementById('modal').classList.add('active');
    });
  });

  function fecharModal() {
    document.getElementById('modal').classList.remove('active');
  }

  document.getElementById('modal').addEventListener('click', function(e) {
    if (e.target === this) fecharModal();
  });

  // ===== FILTROS DA GALERIA =====
  document.querySelectorAll('.filtro-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      document.querySelectorAll('.filtro-btn').forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
    });
  });

  // ===== FORMULÁRIO → WHATSAPP =====
  function enviarWhatsApp() {
    const nome = document.getElementById('f-nome').value || 'Não informado';
    const tel = document.getElementById('f-tel').value || 'Não informado';
    const servico = document.getElementById('f-servico').value || 'Não selecionado';
    const msg = document.getElementById('f-msg').value || 'Sem descrição';

    const texto = `*Solicitação de Orçamento - E.S Terraplenagem*\n\n` +
      `👤 *Nome:* ${nome}\n` +
      `📞 *Telefone:* ${tel}\n` +
      `🔧 *Serviço:* ${servico}\n` +
      `📝 *Projeto:* ${msg}`;

    const url = `https://wa.me/${CONFIG.whatsapp}?text=${encodeURIComponent(texto)}`;
    window.open(url, '_blank');
  }

  // ===== NAVBAR SCROLL =====
  window.addEventListener('scroll', () => {
    const nav = document.getElementById('navbar');
    if (window.scrollY > 50) {
      nav.style.boxShadow = '0 4px 30px rgba(0,0,0,0.5)';
    } else {
      nav.style.boxShadow = 'none';
    }
  });
</script>
</body>
</html>
