<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GAS-TRET Connect | Transportasi Ramah Lingkungan</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-green: #2E7D32;
            --light-green: #4CAF50;
            --lighter-green: #8BC34A;
            --dark-green: #1B5E20;
            --eco-blue: #2196F3;
            --eco-yellow: #FFC107;
            --eco-cream: #FFF8F0;
            --text-dark: #333;
            --text-light: #f5f5f5;
        }

        body {
            font-family: 'Roboto', sans-serif;
            background-color: var(--eco-cream);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Poppins', sans-serif;
            color: var(--dark-green);
            margin-bottom: 1rem;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        section {
            padding: 5rem 0;
        }

        /* Header Styles */
        header {
            background-color: var(--primary-green);
            padding: 1rem 0;
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo h1 {
            color: white;
            font-size: 1.8rem;
            margin: 0;
        }

        .logo i {
            font-size: 2rem;
            color: var(--lighter-green);
            animation: pulse 2s infinite;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 1.5rem;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            padding: 0.5rem;
            border-radius: 4px;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        nav a:hover, nav a.active {
            background-color: var(--light-green);
            transform: translateY(-3px);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(46, 125, 50, 0.8), rgba(46, 125, 50, 0.9)), url('https://images.unsplash.com/photo-1532996122724-e3c354a0b15b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 9rem 1rem 5rem;
            margin-bottom: 3rem;
        }

        .hero h2 {
            color: white;
            font-size: 2.5rem;
            margin-bottom: 1rem;
            animation: fadeInDown 1s ease;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 2rem;
            animation: fadeInUp 1s ease;
        }

        .btn {
            display: inline-block;
            background-color: var(--lighter-green);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .btn:hover {
            background-color: var(--light-green);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        }

        /* Section Styles */
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--light-green);
            margin: 0.5rem auto;
            border-radius: 2px;
        }

        /* Event Hijau Section */
        .event-form {
            background: white;
            padding: 2.5rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            margin-bottom: 3rem;
            animation: slideInLeft 0.8s ease;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: var(--dark-green);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            border-color: var(--light-green);
            outline: none;
            box-shadow: 0 0 0 3px rgba(76, 175, 80, 0.2);
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        .events-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
        }

        .event-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: all 0.4s ease;
            animation: fadeIn 0.8s ease;
        }

        .event-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }

        .event-header {
            background: linear-gradient(to right, var(--light-green), var(--lighter-green));
            color: white;
            padding: 1.5rem;
        }

        .event-header h3 {
            color: white;
            margin-bottom: 0.5rem;
        }

        .event-date {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.95rem;
        }

        .event-body {
            padding: 1.8rem;
        }

        .event-location {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--dark-green);
            margin-bottom: 1.2rem;
            font-weight: 500;
        }

        .event-description {
            color: #666;
            margin-bottom: 1.8rem;
            line-height: 1.7;
        }

        /* Jejak Hijau Section */
        .jejak-section {
            background: linear-gradient(to bottom, rgba(139, 195, 74, 0.1), rgba(255, 255, 255, 0.8));
        }

        .jejak-form {
            background: white;
            padding: 2.5rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            max-width: 700px;
            margin: 0 auto 3rem;
            animation: slideInRight 0.8s ease;
        }

        .transport-inputs {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .transport-card {
            background: var(--eco-cream);
            border-radius: 12px;
            padding: 1.5rem;
            text-align: center;
            border: 2px dashed var(--light-green);
            transition: all 0.3s;
        }

        .transport-card:hover {
            transform: translateY(-5px);
            border-style: solid;
        }

        .transport-card i {
            font-size: 2.5rem;
            color: var(--light-green);
            margin-bottom: 1rem;
        }

        .transport-card h4 {
            margin-bottom: 1rem;
            color: var(--dark-green);
        }

        .distance-input {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .distance-input input {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            text-align: center;
        }

        .results-container {
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            padding: 2.5rem;
            max-width: 900px;
            margin: 0 auto;
            display: none;
            animation: fadeIn 0.8s ease;
        }

        .co2-results {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .co2-card {
            background: linear-gradient(to bottom, white, var(--eco-cream));
            border-radius: 12px;
            padding: 1.8rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s;
        }

        .co2-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
        }

        .co2-card i {
            font-size: 2.5rem;
            color: var(--light-green);
            margin-bottom: 1.2rem;
        }

        .co2-card h4 {
            margin-bottom: 0.8rem;
            color: var(--dark-green);
        }

        .co2-amount {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-green);
        }

        .eco-message {
            background: linear-gradient(to right, var(--light-green), var(--lighter-green));
            color: white;
            padding: 1.8rem;
            border-radius: 12px;
            text-align: center;
            font-size: 1.3rem;
            display: none;
            animation: pulse 2s infinite;
        }

        .eco-message.show {
            display: block;
            animation: fadeIn 0.5s ease, pulse 2s infinite;
        }

        /* Map Section */
        .map-container {
            position: relative;
            height: 500px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            margin-bottom: 2rem;
            animation: fadeIn 0.8s ease;
        }

        .map-container iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        .map-overlay {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.9);
            padding: 1.5rem;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            z-index: 10;
            backdrop-filter: blur(5px);
        }

        .legend-title {
            margin-bottom: 1rem;
            color: var(--dark-green);
            text-align: center;
            font-weight: 600;
        }

        .legend-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            gap: 12px;
        }

        .legend-item:last-child {
            margin-bottom: 0;
        }

        .legend-icon {
            font-size: 1.5rem;
            width: 35px;
            height: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            background: rgba(0,0,0,0.05);
        }

        .bus-icon {
            color: #2196F3;
        }

        .light-icon {
            color: #FFC107;
        }

        .walk-icon {
            color: #4CAF50;
        }

        .school-icon {
            color: #9C27B0;
        }

        /* Game Section */
        .game-section {
            background: linear-gradient(to bottom, rgba(33, 150, 243, 0.1), rgba(255, 255, 255, 0.8));
        }

        .game-container {
            background: white;
            border-radius: 15px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            padding: 2.5rem;
            max-width: 800px;
            margin: 0 auto;
            animation: fadeIn 0.8s ease;
        }

        .game-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .game-title {
            font-size: 1.8rem;
            color: var(--dark-green);
            margin-bottom: 1rem;
        }

        .level-indicator {
            display: inline-block;
            background: var(--light-green);
            color: white;
            padding: 0.5rem 1.2rem;
            border-radius: 30px;
            font-weight: 600;
        }

        .game-dialog {
            background: var(--eco-cream);
            border-left: 5px solid var(--light-green);
            padding: 1.5rem;
            border-radius: 8px;
            margin-bottom: 2rem;
            font-size: 1.1rem;
            line-height: 1.7;
            animation: fadeIn 0.5s ease;
        }

        .question-container {
            margin-bottom: 2rem;
            animation: fadeIn 0.5s ease;
        }

        .question-text {
            font-size: 1.2rem;
            font-weight: 500;
            margin-bottom: 1.5rem;
            color: var(--dark-green);
        }

        .options-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1rem;
        }

        .option {
            background: white;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 1.2rem;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            gap: 12px;
        }

        .option:hover {
            transform: translateY(-3px);
            border-color: var(--light-green);
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        .option.selected {
            border-color: var(--light-green);
            background: rgba(139, 195, 74, 0.1);
        }

        .option.correct {
            border-color: #4CAF50;
            background: rgba(76, 175, 80, 0.1);
        }

        .option.incorrect {
            border-color: #F44336;
            background: rgba(244, 67, 54, 0.1);
        }

        .option-letter {
            font-weight: 700;
            color: var(--dark-green);
        }

        .game-controls {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
        }

        .game-result {
            text-align: center;
            padding: 2rem;
            display: none;
            animation: fadeIn 0.8s ease;
        }

        .score-display {
            font-size: 5rem;
            font-weight: 700;
            color: var(--light-green);
            margin: 1rem 0;
            text-shadow: 0 5px 10px rgba(0,0,0,0.1);
        }

        .result-message {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            color: var(--dark-green);
        }

        /* Footer */
        footer {
            background: linear-gradient(to right, var(--dark-green), var(--primary-green));
            color: var(--text-light);
            padding: 4rem 0 2rem;
            margin-top: 3rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2.5rem;
            margin-bottom: 2.5rem;
        }

        .footer-logo {
            font-size: 1.8rem;
            margin-bottom: 1.2rem;
            color: var(--lighter-green);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-about p {
            margin-bottom: 1.5rem;
            color: rgba(255, 255, 255, 0.8);
        }

        .social-icons {
            display: flex;
            gap: 1rem;
        }

        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .social-icons a:hover {
            background: var(--light-green);
            transform: translateY(-5px);
        }

        .footer-links h3 {
            color: var(--lighter-green);
            margin-bottom: 1.8rem;
            font-size: 1.4rem;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 1rem;
        }

        .footer-links a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            transition: color 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .footer-links a:hover {
            color: white;
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 1rem;
            color: rgba(255, 255, 255, 0.7);
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInDown {
            from { 
                opacity: 0;
                transform: translateY(-20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from { 
                opacity: 0;
                transform: translateY(20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInLeft {
            from { 
                opacity: 0;
                transform: translateX(-50px);
            }
            to { 
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from { 
                opacity: 0;
                transform: translateX(50px);
            }
            to { 
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .transport-inputs {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 1.2rem;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero {
                padding: 7rem 1rem 3rem;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .event-form, .jejak-form, .results-container, .game-container {
                padding: 1.8rem;
            }
            
            .map-container {
                height: 400px;
            }
        }

        @media (max-width: 480px) {
            .events-grid {
                grid-template-columns: 1fr;
            }
            
            .hero h2 {
                font-size: 1.8rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title {
                margin-bottom: 2rem;
            }
            
            .game-controls {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-leaf"></i>
                <h1>GAS-TRET Connect</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#" class="active"><i class="fas fa-home"></i> Beranda</a></li>
                    <li><a href="#event"><i class="fas fa-calendar-alt"></i> Event Hijau</a></li>
                    <li><a href="#jejak"><i class="fas fa-footsteps"></i> Jejak Hijau</a></li>
                    <li><a href="#map"><i class="fas fa-map-marked-alt"></i> Peta</a></li>
                    <li><a href="#game"><i class="fas fa-gamepad"></i> Game</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>Selamat Datang di GAS-TRET Connect</h2>
            <p>Platform hijau untuk mewujudkan Kalimantan Selatan yang lebih ramah lingkungan dan berkelanjutan. Mari bersama-sama menciptakan perubahan positif bagi bumi kita melalui transportasi berkelanjutan.</p>
            <a href="#event" class="btn">Mulai Berpartisipasi</a>
        </div>
    </section>

    <!-- Event Hijau Section -->
    <section id="event">
        <div class="container">
            <div class="section-title">
                <h2>Event Hijau</h2>
                <p>Ajukan dan temukan acara ramah lingkungan di sekitar Kalimantan Selatan</p>
            </div>
            
            <div class="event-form">
                <h3>Ajukan Event Hijau Baru</h3>
                <form id="eventForm">
                    <div class="form-group">
                        <label for="eventTitle">Judul Event</label>
                        <input type="text" id="eventTitle" placeholder="Contoh: Car Free Day Banjarmasin" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="eventDesc">Deskripsi Event</label>
                        <textarea id="eventDesc" placeholder="Deskripsikan event dan manfaatnya bagi lingkungan..." required></textarea>
                    </div>
                    
                    <div class="form-group">
                        <label for="eventLocation">Lokasi</label>
                        <input type="text" id="eventLocation" placeholder="Contoh: Jalan Sudirman, Banjarmasin" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="eventDate">Tanggal</label>
                        <input type="date" id="eventDate" required>
                    </div>
                    
                    <button type="submit" class="btn"><i class="fas fa-plus-circle"></i> Ajukan Event</button>
                </form>
            </div>
            
            <h3 style="margin-bottom: 1.5rem; text-align: center;">Event Terbaru</h3>
            <div class="events-grid" id="eventsContainer">
                <!-- Events will be added here dynamically -->
                <div class="event-card">
                    <div class="event-header">
                        <h3>Car Free Day Banjarmasin</h3>
                        <div class="event-date">
                            <i class="far fa-calendar"></i>
                            <span>15 Oktober 2023</span>
                        </div>
                    </div>
                    <div class="event-body">
                        <div class="event-location">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Jalan Sudirman, Banjarmasin</span>
                        </div>
                        <p class="event-description">Aktivitas bebas kendaraan bermotor setiap minggu pagi. Mari berjalan kaki, bersepeda, atau menggunakan transportasi umum untuk mengurangi polusi udara.</p>
                        <a href="#" class="btn"><i class="fas fa-ticket-alt"></i> Daftar Sekarang</a>
                    </div>
                </div>
                
                <div class="event-card">
                    <div class="event-header">
                        <h3>Penanaman Mangrove</h3>
                        <div class="event-date">
                            <i class="far fa-calendar"></i>
                            <span>22 Oktober 2023</span>
                        </div>
                    </div>
                    <div class="event-body">
                        <div class="event-location">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>Pantai Takisung, Tanah Laut</span>
                        </div>
                        <p class="event-description">Kegiatan penanaman 1000 bibit mangrove untuk menjaga ekosistem pesisir. Terbuka untuk umum dan keluarga. Perlengkapan disediakan.</p>
                        <a href="#" class="btn"><i class="fas fa-ticket-alt"></i> Daftar Sekarang</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Jejak Hijau Section -->
    <section id="jejak" class="jejak-section">
        <div class="container">
            <div class="section-title">
                <h2>Jejak Hijau</h2>
                <p>Hitung kontribusi Anda dalam mengurangi emisi karbon</p>
            </div>
            
            <div class="jejak-form">
                <form id="jejakForm">
                    <div class="transport-inputs">
                        <div class="transport-card">
                            <i class="fas fa-walking"></i>
                            <h4>Berjalan Kaki</h4>
                            <div class="distance-input">
                                <input type="number" id="walkDistance" step="0.1" min="0" placeholder="Jarak (km)" required>
                                <span>km</span>
                            </div>
                        </div>
                        
                        <div class="transport-card">
                            <i class="fas fa-running"></i>
                            <h4>Berlari</h4>
                            <div class="distance-input">
                                <input type="number" id="runDistance" step="0.1" min="0" placeholder="Jarak (km)" required>
                                <span>km</span>
                            </div>
                        </div>
                        
                        <div class="transport-card">
                            <i class="fas fa-bicycle"></i>
                            <h4>Bersepeda</h4>
                            <div class="distance-input">
                                <input type="number" id="bikeDistance" step="0.1" min="0" placeholder="Jarak (km)" required>
                                <span>km</span>
                            </div>
                        </div>
                    </div>
                    
                    <button type="submit" class="btn" style="width: 100%;"><i class="fas fa-calculator"></i> Hitung Pengurangan CO2</button>
                </form>
            </div>
            
            <div class="results-container" id="resultsContainer">
                <h3 style="text-align: center; margin-bottom: 2rem;">Hasil Perhitungan Jejak Karbon</h3>
                <div class="co2-results">
                    <div class="co2-card">
                        <i class="fas fa-motorcycle"></i>
                        <h4>Sepeda Motor</h4>
                        <p>CO2 yang dihemat:</p>
                        <div class="co2-amount" id="motorResult">0 kg</div>
                    </div>
                    
                    <div class="co2-card">
                        <i class="fas fa-car"></i>
                        <h4>Mobil Pribadi</h4>
                        <p>CO2 yang dihemat:</p>
                        <div class="co2-amount" id="carResult">0 kg</div>
                    </div>
                    
                    <div class="co2-card">
                        <i class="fas fa-bus"></i>
                        <h4>Bus Umum</h4>
                        <p>CO2 yang dihemat:</p>
                        <div class="co2-amount" id="busResult">0 kg</div>
                    </div>
                </div>
                
                <div class="eco-message" id="ecoMessage">
                    <p><i class="fas fa-trophy"></i> Luar biasa! Anda telah menyelamatkan bumi dengan berjalan lebih dari 1 km tanpa kendaraan pribadi atau umum!</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Map Section -->
    <section id="map">
        <div class="container">
            <div class="section-title">
                <h2>Peta Hijau Kalimantan Selatan</h2>
                <p>Jelajahi infrastruktur ramah lingkungan di Kalimantan Selatan</p>
            </div>
            
            <div class="map-container">
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d8161363.427719313!2d113.18873640000001!3d-2.5000000000000004!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2df690d5d8c58d53%3A0x3039d80b220d3c0!2sSouth%20Kalimantan!5e0!3m2!1sen!2sid!4v1697800000000!5m2!1sen!2sid" allowfullscreen="" loading="lazy"></iframe>
                
                <!-- Map Overlay Legend -->
                <div class="map-overlay">
                    <div class="legend-title">Legenda Peta</div>
                    <div class="legend-item">
                        <div class="legend-icon bus-icon"><i class="fas fa-bus"></i></div>
                        <span>Halte Bus</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-icon light-icon"><i class="fas fa-traffic-light"></i></div>
                        <span>Lampu Lalu Lintas</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-icon walk-icon"><i class="fas fa-walking"></i></div>
                        <span>Jalan Pedestrian</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-icon school-icon"><i class="fas fa-school"></i></div>
                        <span>SMKN 1 PELAIHARI</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Game Section -->
    <section id="game" class="game-section">
        <div class="container">
            <div class="section-title">
                <h2>Game: Lalu Lintas Angkutan Jalan</h2>
                <p>Uji pengetahuan Anda tentang keselamatan transportasi</p>
            </div>
            
            <div class="game-container">
                <div class="game-header">
                    <div class="game-title">Kuis Transportasi Hijau</div>
                    <div class="level-indicator">Level 1</div>
                </div>
                
                <div class="game-dialog" id="gameDialog">
                    Selamat datang di Kota Transporta! Siap belajar jadi pelopor keselamatan berkendara?
                </div>
                
                <div class="question-container" id="questionContainer">
                    <div class="question-text" id="questionText">
                        Apa arti rambu ini? 🛑
                    </div>
                    
                    <div class="options-grid" id="optionsGrid">
                        <div class="option" data-value="A">
                            <span class="option-letter">A</span>
                            <span class="option-text">Jalan satu arah</span>
                        </div>
                        <div class="option" data-value="B">
                            <span class="option-letter">B</span>
                            <span class="option-text">Dilarang masuk</span>
                        </div>
                        <div class="option" data-value="C">
                            <span class="option-letter">C</span>
                            <span class="option-text">Dilarang parkir</span>
                        </div>
                        <div class="option" data-value="D">
                            <span class="option-letter">D</span>
                            <span class="option-text">Dilarang berhenti</span>
                        </div>
                    </div>
                </div>
                
                <div class="game-controls">
                    <button class="btn" id="prevBtn" disabled><i class="fas fa-arrow-left"></i> Sebelumnya</button>
                    <button class="btn" id="nextBtn">Selanjutnya <i class="fas fa-arrow-right"></i></button>
                </div>
                
                <div class="game-result" id="gameResult">
                    <h3>Permainan Selesai!</h3>
                    <div class="score-display" id="finalScore">0/5</div>
                    <div class="result-message" id="resultMessage">Selamat! Anda telah menyelesaikan kuis ini!</div>
                    <button class="btn" id="restartBtn"><i class="fas fa-redo"></i> Main Lagi</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-about">
                    <div class="footer-logo">
                        <i class="fas fa-leaf"></i> GAS-TRET Connect
                    </div>
                    <p>Platform hijau untuk mewujudkan Kalimantan Selatan yang lebih ramah lingkungan dan berkelanjutan melalui transportasi berkelanjutan.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-links">
                    <h3>Menu Utama</h3>
                    <ul>
                        <li><a href="#"><i class="fas fa-chevron-right"></i> Beranda</a></li>
                        <li><a href="#event"><i class="fas fa-chevron-right"></i> Event Hijau</a></li>
                        <li><a href="#jejak"><i class="fas fa-chevron-right"></i> Jejak Hijau</a></li>
                        <li><a href="#map"><i class="fas fa-chevron-right"></i> Peta Hijau</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h3>Kontak Kami</h3>
                    <ul>
                        <li><a href="#"><i class="fas fa-map-marker-alt"></i> Tanah Laut, Kalimantan Selatan</a></li>
                        <li><a href="#"><i class="fas fa-phone"></i> +62 857 8707 1368 </a></li>
                        <li><a href="#"><i class="fas fa-envelope"></i> info@gastretconnect.id</a></li>
                        <li><a href="#"><i class="fas fa-globe"></i> www.gastretconnect.id</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2025 GAS-TRET Connect. Seluruh hak cipta dilindungi.</p>
            </div>
        </div>
    </footer>

    <script>
        // Event Hijau Form Submission
        document.getElementById('eventForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form values
            const title = document.getElementById('eventTitle').value;
            const description = document.getElementById('eventDesc').value;
            const location = document.getElementById('eventLocation').value;
            const date = new Date(document.getElementById('eventDate').value);
            
            // Format date
            const formattedDate = date.toLocaleDateString('id-ID', {
                day: 'numeric',
                month: 'long',
                year: 'numeric'
            });
            
            // Create event card HTML
            const eventCard = `
                <div class="event-card">
                    <div class="event-header">
                        <h3>${title}</h3>
                        <div class="event-date">
                            <i class="far fa-calendar"></i>
                            <span>${formattedDate}</span>
                        </div>
                    </div>
                    <div class="event-body">
                        <div class="event-location">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>${location}</span>
                        </div>
                        <p class="event-description">${description}</p>
                        <a href="#" class="btn"><i class="fas fa-ticket-alt"></i> Daftar Sekarang</a>
                    </div>
                </div>
            `;
            
            // Add new event to the container
            document.getElementById('eventsContainer').insertAdjacentHTML('afterbegin', eventCard);
            
            // Reset form
            this.reset();
            
            // Show success message
            alert('Event berhasil diajukan! Terima kasih atas kontribusi Anda.');
        });
        
        // Jejak Hijau Form Submission
        document.getElementById('jejakForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get distance values
            const walkDistance = parseFloat(document.getElementById('walkDistance').value) || 0;
            const runDistance = parseFloat(document.getElementById('runDistance').value) || 0;
            const bikeDistance = parseFloat(document.getElementById('bikeDistance').value) || 0;
            
            // Calculate total distance
            const totalDistance = walkDistance + runDistance + bikeDistance;
            
            if (totalDistance <= 0) {
                alert('Masukkan jarak yang valid');
                return;
            }
            
            // Calculate CO2 savings
            const motorcycleCO2 = (totalDistance * 0.15).toFixed(2);
            const carCO2 = (totalDistance * 0.27).toFixed(2);
            const busCO2 = (totalDistance * 0.08).toFixed(2);
            
            // Update results
            document.getElementById('motorResult').textContent = `${motorcycleCO2} kg`;
            document.getElementById('carResult').textContent = `${carCO2} kg`;
            document.getElementById('busResult').textContent = `${busCO2} kg`;
            
            // Show results container
            document.getElementById('resultsContainer').style.display = 'block';
            
            // Show eco message if total distance > 1 km
            if (totalDistance > 1) {
                document.getElementById('ecoMessage').classList.add('show');
            } else {
                document.getElementById('ecoMessage').classList.remove('show');
            }
            
            // Scroll to results
            document.getElementById('resultsContainer').scrollIntoView({ behavior: 'smooth' });
        });
        
        // Game Logic
        const gameData = [
            {
                level: 1,
                dialog: "Selamat datang di Kota Transporta! Siap belajar jadi pelopor keselamatan berkendara?",
                question: "Apa arti rambu ini? 🛑",
                options: [
                    { text: "Jalan satu arah", correct: false },
                    { text: "Dilarang masuk", correct: true },
                    { text: "Dilarang parkir", correct: false },
                    { text: "Dilarang berhenti", correct: false }
                ]
            },
            {
                level: 2,
                dialog: "Wah, ada simpang jalan! Coba lihat rambu di depan. Kamu harus bisa membacanya agar perjalananmu aman.",
                question: "Berapa batas berat maksimum untuk angkutan barang di jalan tol?",
                options: [
                    { text: "10 ton", correct: false },
                    { text: "18 ton", correct: false },
                    { text: "24 ton", correct: false },
                    { text: "Tergantung klasifikasi jalan", correct: true }
                ]
            },
            {
                level: 3,
                dialog: "Kamu kini mengendarai truk angkutan barang. Awas jangan melebihi muatan!",
                question: "Apa yang dilakukan saat lampu kuning berkedip?",
                options: [
                    { text: "Tetap melaju", correct: false },
                    { text: "Melambat dan hati-hati", correct: true },
                    { text: "Berhenti", correct: false },
                    { text: "Nyalakan hazard", correct: false }
                ]
            },
            {
                level: 4,
                dialog: "Ada kecelakaan di depan. Kamu harus melambat dan beri jalan untuk ambulans.",
                question: "Kendaraan umum berhenti di depan. Apa yang kamu lakukan?",
                options: [
                    { text: "Klakson", correct: false },
                    { text: "Salip dari kiri", correct: false },
                    { text: "Tunggu dengan sabar", correct: true },
                    { text: "Lewat trotoar", correct: false }
                ]
            },
            {
                level: 5,
                dialog: "Kamu memasuki zona sekolah. Apa batas kecepatan di sini?",
                question: "Kamu dengar sirine dari belakang. Apa yang harus dilakukan?",
                options: [
                    { text: "Tambah kecepatan", correct: false },
                    { text: "Pindah ke kanan", correct: false },
                    { text: "Diam di jalur", correct: false },
                    { text: "Menepi dan beri jalan", correct: true }
                ]
            }
        ];
        
        let currentQuestion = 0;
        let score = 0;
        
        const gameDialog = document.getElementById('gameDialog');
        const questionText = document.getElementById('questionText');
        const optionsGrid = document.getElementById('optionsGrid');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const levelIndicator = document.querySelector('.level-indicator');
        const gameContainer = document.querySelector('.question-container');
        const gameResult = document.getElementById('gameResult');
        const finalScore = document.getElementById('finalScore');
        const resultMessage = document.getElementById('resultMessage');
        const restartBtn = document.getElementById('restartBtn');
        
        function loadQuestion(index) {
            const question = gameData[index];
            
            // Update level indicator
            levelIndicator.textContent = `Level ${question.level}`;
            
            // Update dialog and question
            gameDialog.textContent = question.dialog;
            questionText.textContent = question.question;
            
            // Clear options
            optionsGrid.innerHTML = '';
            
            // Add new options
            question.options.forEach((option, i) => {
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.dataset.value = String.fromCharCode(65 + i);
                optionElement.innerHTML = `
                    <span class="option-letter">${String.fromCharCode(65 + i)}</span>
                    <span class="option-text">${option.text}</span>
                `;
                optionsGrid.appendChild(optionElement);
                
                // Add click event
                optionElement.addEventListener('click', () => {
                    // Remove any existing selections
                    document.querySelectorAll('.option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    
                    // Select this option
                    optionElement.classList.add('selected');
                    
                    // Check if correct
                    if (option.correct) {
                        optionElement.classList.add('correct');
                    } else {
                        optionElement.classList.add('incorrect');
                    }
                    
                    // Update score if correct
                    if (option.correct) {
                        score++;
                    }
                });
            });
            
            // Update button states
            prevBtn.disabled = index === 0;
            nextBtn.textContent = index === gameData.length - 1 ? "Selesai" : "Selanjutnya";
        }
        
        // Initial load
        loadQuestion(currentQuestion);
        
        // Next button click
        nextBtn.addEventListener('click', () => {
            // Check if an option is selected
            if (!document.querySelector('.option.selected')) {
                alert('Pilih jawaban terlebih dahulu!');
                return;
            }
            
            if (currentQuestion < gameData.length - 1) {
                currentQuestion++;
                loadQuestion(currentQuestion);
            } else {
                // Game finished
                gameContainer.style.display = 'none';
                gameResult.style.display = 'block';
                finalScore.textContent = `${score}/5`;
                
                if (score === 5) {
                    resultMessage.textContent = "Sempurna! Anda benar-benar ahli transportasi hijau!";
                } else if (score >= 3) {
                    resultMessage.textContent = "Bagus! Pengetahuan Anda tentang transportasi hijau cukup baik!";
                } else {
                    resultMessage.textContent = "Terus belajar! Anda bisa lebih memahami transportasi hijau!";
                }
            }
        });
        
        // Previous button click
        prevBtn.addEventListener('click', () => {
            if (currentQuestion > 0) {
                currentQuestion--;
                loadQuestion(currentQuestion);
            }
        });
        
        // Restart game
        restartBtn.addEventListener('click', () => {
            currentQuestion = 0;
            score = 0;
            gameContainer.style.display = 'block';
            gameResult.style.display = 'none';
            loadQuestion(currentQuestion);
        });
        
        // Smooth scrolling for navigation
        document.querySelectorAll('nav a, .btn[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                document.querySelector(targetId).scrollIntoView({
                    behavior: 'smooth'
                });
                
                // Update active nav link
                document.querySelectorAll('nav a').forEach(link => {
                    link.classList.remove('active');
                });
                this.classList.add('active');
            });
        });
    </script>
</body>
</html>
