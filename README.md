# lets-study-with-dawit
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Let's Study with Dawit Mamo</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
    <style>
        :root {
            --primary: #4361ee;
            --primary-dark: #3a56d4;
            --secondary: #7209b7;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4cc9f0;
            --warning: #f72585;
            --gray: #6c757d;
            --light-gray: #e9ecef;
            --card-bg: #ffffff;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --radius: 12px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #e4edf9 100%);
            min-height: 100vh;
            color: var(--dark);
            overflow-x: hidden;
            padding-bottom: 100px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            padding: 15px 0;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.6rem;
            font-weight: 700;
        }

        .top-nav {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .auth-btn {
            background: white;
            color: var(--primary);
            border: none;
            padding: 8px 16px;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.2s;
        }

        .auth-btn:hover {
            transform: translateY(-2px);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 18px;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 8px 12px;
            border-radius: 8px;
            transition: background 0.3s;
        }

        .nav-menu a:hover, .nav-menu a.active {
            background: rgba(255, 255, 255, 0.15);
        }

        .hamburger {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .content-area {
            background: var(--card-bg);
            border-radius: var(--radius);
            padding: 30px;
            box-shadow: var(--shadow);
            margin-top: 20px;
        }

        .page-header {
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--light-gray);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .page-title {
            font-size: 1.8rem;
            color: var(--primary);
        }

        /* Dashboard: 4x3 Grid */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .stat-icon {
            font-size: 1.6rem;
            margin-bottom: 10px;
        }

        .stat-value {
            font-size: 1.8rem;
            font-weight: 700;
            margin: 8px 0;
        }

        .stat-label {
            font-size: 0.95rem;
            opacity: 0.95;
        }

        /* Members List */
        .members-list {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        .members-list th,
        .members-list td {
            padding: 14px;
            text-align: left;
            border-bottom: 1px solid var(--light-gray);
        }

        .members-list th {
            background: var(--light);
            color: var(--primary);
            font-weight: 600;
        }

        .members-list tr:hover {
            background: #f8f9ff;
        }

        /* Floating AI Button */
        .ai-float-btn {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 6px 20px rgba(114, 9, 183, 0.4);
            cursor: pointer;
            z-index: 2000;
            font-size: 1.4rem;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .ai-float-btn:hover {
            transform: scale(1.1);
        }

        /* AI Translator Panel */
        .translator-panel {
            position: fixed;
            bottom: -350px;
            left: 0;
            width: 100%;
            max-width: 100vw;
            background: white;
            border-radius: 20px 20px 0 0;
            box-shadow: 0 -5px 25px rgba(0,0,0,0.15);
            padding: 25px;
            transition: bottom 0.4s ease;
            z-index: 1900;
            max-height: 80vh;
            overflow: auto;
        }

        .translator-panel.active {
            bottom: 0;
        }

        .panel-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .panel-title {
            font-size: 1.3rem;
            color: var(--secondary);
            font-weight: 700;
        }

        .close-panel {
            background: none;
            border: none;
            font-size: 1.4rem;
            color: var(--gray);
            cursor: pointer;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .close-panel:hover {
            background: var(--light-gray);
        }

        .translator-controls {
            display: flex;
            gap: 12px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }

        .lang-select {
            flex: 1;
            min-width: 140px;
        }

        .form-control {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--light-gray);
            border-radius: 8px;
            font-size: 1rem;
        }

        textarea.form-control {
            min-height: 100px;
            resize: vertical;
        }

        .swap-btn {
            background: var(--light-gray);
            border: none;
            width: 42px;
            height: 42px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: var(--primary);
            font-weight: bold;
            margin: 0 4px;
        }

        .translation-output {
            background: #f8f9ff;
            border: 1px dashed #cbd5e1;
            border-radius: 8px;
            padding: 15px;
            margin-top: 15px;
            min-height: 60px;
            color: var(--dark);
            white-space: pre-wrap;
        }

        /* Other Grids */
        .sets-grid, .admin-controls, .settings-grid {
            display: grid;
            gap: 20px;
        }

        .sets-grid {
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
        }

        .admin-controls, .settings-grid {
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        }

        .set-card, .control-card, .setting-card {
            background: var(--light);
            border-radius: var(--radius);
            padding: 20px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        footer {
            text-align: center;
            padding: 20px 0;
            color: var(--gray);
            margin-top: 30px;
            border-top: 1px solid var(--light-gray);
        }

        @media (max-width: 900px) {
            .nav-menu {
                position: absolute;
                top: 70px;
                right: 20px;
                background: rgba(255, 255, 255, 0.95);
                flex-direction: column;
                padding: 15px;
                border-radius: var(--radius);
                box-shadow: 0 10px 20px rgba(0,0,0,0.15);
                display: none;
                z-index: 900;
            }

            .nav-menu.show {
                display: flex;
            }

            .nav-menu a {
                color: var(--dark);
                width: 180px;
                text-align: center;
            }

            .hamburger {
                display: block;
            }

            /* Dashboard becomes 2 columns on tablet */
            .dashboard-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 600px) {
            /* Dashboard becomes 1 column on mobile */
            .dashboard-grid {
                grid-template-columns: 1fr;
            }

            .auth-btn span {
                display: none; /* Hide text on small screens */
            }
        }
    </style>
</head>
<body>
    <!-- Floating AI Button -->
    <button class="ai-float-btn" id="aiFloatBtn">
        <i class="fas fa-language"></i>
    </button>

    <!-- AI Translator Panel -->
    <div class="translator-panel" id="translatorPanel">
        <div class="panel-header">
            <div class="panel-title">
                <i class="fas fa-robot"></i> AI Translator
            </div>
            <button class="close-panel" id="closePanel">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="translator-controls">
            <select class="form-control lang-select" id="fromLang">
                <option value="en">English</option>
                <option value="am">Amharic</option>
                <option value="fr">French</option>
                <option value="es">Spanish</option>
                <option value="de">German</option>
            </select>
            <button class="swap-btn" id="swapLangs">⇅</button>
            <select class="form-control lang-select" id="toLang">
                <option value="am">Amharic</option>
                <option value="en">English</option>
                <option value="fr">French</option>
                <option value="es">Spanish</option>
                <option value="de">German</option>
            </select>
        </div>
        <textarea class="form-control" id="inputText" placeholder="Type text to translate..."></textarea>
        <button class="btn btn-primary" id="translateBtn" style="margin-top: 15px; width: 100%;">
            <i class="fas fa-exchange-alt"></i> Translate
        </button>
        <div class="translation-output" id="outputText">
            Translation will appear here...
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-graduation-cap"></i>
                <span>Let's Study with Dawit Mamo</span>
            </div>
            <div class="top-nav">
                <button class="auth-btn" id="authBtn">
                    <i class="fas fa-user"></i> <span>Sign In / Up</span>
                </button>
                <button class="hamburger" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </button>
                <ul class="nav-menu" id="navMenu">
                    <li><a href="#" data-page="dashboard" class="active">Dashboard</a></li>
                    <li><a href="#" data-page="flashcards">Flashcards</a></li>
                    <li><a href="#" data-page="quiz">Quiz</a></li>
                    <li><a href="#" data-page="sets">Study Sets</a></li>
                    <li><a href="#" data-page="notes">AI Notes</a></li>
                    <li><a href="#" data-page="admin">Admin</a></li>
                    <li><a href="#" data-page="settings">Settings</a></li>
                </ul>
            </div>
        </div>
    </header>

    <div class="container">
        <div class="content-area">
            <!-- Dashboard (4×3 Grid) -->
            <div class="page dashboard active" id="dashboard">
                <div class="page-header">
                    <h2 class="page-title">Dashboard</h2>
                </div>
                <div class="dashboard-grid">
                    <!-- Row 1 -->
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-file-alt"></i></div><div class="stat-value">24</div><div class="stat-label">Flashcards</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-question-circle"></i></div><div class="stat-value">12</div><div class="stat-label">Quizzes</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-folder"></i></div><div class="stat-value">8</div><div class="stat-label">Study Sets</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-book"></i></div><div class="stat-value">15</div><div class="stat-label">AI Notes</div></div>
                    <!-- Row 2 -->
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-user-graduate"></i></div><div class="stat-value">142</div><div class="stat-label">Active Students</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-award"></i></div><div class="stat-value">87%</div><div class="stat-label">Avg. Score</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-clock"></i></div><div class="stat-value">320h</div><div class="stat-label">Total Study Time</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-chart-line"></i></div><div class="stat-value">+12%</div><div class="stat-label">This Week</div></div>
                    <!-- Row 3 -->
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-language"></i></div><div class="stat-value">5</div><div class="stat-label">Languages</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-microscope"></i></div><div class="stat-value">42</div><div class="stat-label">Science Sets</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-code"></i></div><div class="stat-value">36</div><div class="stat-label">CS Sets</div></div>
                    <div class="stat-card"><div class="stat-icon"><i class="fas fa-history"></i></div><div class="stat-value">28</div><div class="stat-label">History Sets</div></div>
                </div>
                <div style="background: linear-gradient(to right, #e0e7ff, #ede9fe); height: 200px; border-radius: 12px; display: flex; align-items: center; justify-content: center; color: var(--primary); margin-top: 30px;">
                    <i class="fas fa-chart-bar fa-3x"></i>
                    <span style="margin-left: 15px; font-size: 1.2rem;">Your study progress chart will appear here</span>
                </div>
            </div>

            <!-- Other pages (simplified) -->
            <div class="page flashcards" id="flashcards" style="display: none;">
                <div class="page-header">
                    <h2 class="page-title">Flashcards</h2>
                </div>
                <p>Click on the card to flip it and see the answer</p>
                <div class="flashcard-container">
                    <div class="flashcard" id="flashcard">
                        <div class="card-face card-front">
                            <div><h3>HTML</h3><p>What does HTML stand for?</p></div>
                        </div>
                        <div class="card-face card-back">
                            <div><h3>Answer</h3><p>HyperText Markup Language</p></div>
                        </div>
                    </div>
                </div>
                <div style="display: flex; gap: 15px; margin-top: 20px;">
                    <button class="btn btn-primary" id="prevCard"><i class="fas fa-arrow-left"></i> Previous</button>
                    <button class="btn btn-primary" id="nextCard">Next <i class="fas fa-arrow-right"></i></button>
                </div>
            </div>

            <div class="page admin" id="admin" style="display: none;">
                <div class="page-header">
                    <h2 class="page-title">Admin Panel</h2>
                </div>
                <div class="admin-controls">
                    <div class="control-card">
                        <h3><i class="fas fa-users"></i> Members List</h3>
                        <table class="members-list">
                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Email</th>
                                    <th>Role</th>
                                    <th>Status</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr><td>Dawit Mamo</td><td>dawit@example.com</td><td>Owner</td><td><span style="color: green;">Active</span></td></tr>
                                <tr><td>Ayana Kebede</td><td>ayana@example.com</td><td>Admin</td><td><span style="color: green;">Active</span></td></tr>
                                <tr><td>Samuel Bekele</td><td>samuel@example.com</td><td>Student</td><td><span style="color: green;">Active</span></td></tr>
                                <tr><td>Lidya Haile</td><td>lidya@example.com</td><td>Student</td><td><span style="color: gray;">Inactive</span></td></tr>
                                <tr><td>Yonas Alemu</td><td>yonas@example.com</td><td>Student</td><td><span style="color: green;">Active</span></td></tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>

            <!-- Other pages kept minimal for brevity -->
            <div class="page quiz" id="quiz" style="display: none;">
                <div class="page-header"><h2 class="page-title">Knowledge Quiz</h2></div>
                <div style="background: var(--light); padding: 20px; border-radius: 12px; margin-top: 20px;">
                    <h4>1. Which is not a programming language?</h4>
                    <div style="display: flex; flex-direction: column; gap: 10px; padding-left: 10px; margin-top: 15px;">
                        <label><input type="radio" name="q1"> Java</label>
                        <label><input type="radio" name="q1"> Python</label>
                        <label><input type="radio" name="q1"> HTML</label>
                        <label><input type="radio" name="q1"> JavaScript</label>
                    </div>
                    <div style="margin-top: 30px; text-align: center;">
                        <button class="btn btn-primary" style="padding: 12px 30px;">
                            <i class="fas fa-check-circle"></i> Submit Quiz
                        </button>
                    </div>
                </div>
            </div>

            <div class="page sets" id="sets" style="display: none;">
                <div class="page-header"><h2 class="page-title">Study Sets</h2></div>
                <div class="sets-grid">
                    <div class="set-card">
                        <h3>Web Development</h3>
                        <p>12 flashcards • 3 quizzes</p>
                    </div>
                </div>
            </div>

            <div class="page notes" id="notes" style="display: none;">
                <div class="page-header"><h2 class="page-title">AI Notes</h2></div>
                <div style="background: var(--light); padding: 20px; border-radius: 12px; margin-top: 20px;">
                    <h3>Web Essentials</h3>
                    <p>HTML structures, CSS styles, JS adds behavior.</p>
                </div>
            </div>

            <div class="page settings" id="settings" style="display: none;">
                <div class="page-header"><h2 class="page-title">Settings</h2></div>
                <div class="settings-grid">
                    <div class="setting-card">
                        <h3><i class="fas fa-user"></i> Profile</h3>
                        <div class="form-group">
                            <label>Student Name</label>
                            <input type="text" class="form-control" placeholder="Your name">
                        </div>
                        <button class="btn btn-primary"><i class="fas fa-save"></i> Save</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <p>Let's Study with Dawit Mamo &copy; 2025 | Empowering Students Through Technology</p>
        </div>
    </footer>

    <script>
        // Menu Toggle
        document.getElementById('menuToggle').addEventListener('click', function () {
            document.getElementById('navMenu').classList.toggle('show');
        });

        // Page Navigation
        const navLinks = document.querySelectorAll('.nav-menu a');
        const pages = document.querySelectorAll('.page');
        navLinks.forEach(link => {
            link.addEventListener('click', function (e) {
                e.preventDefault();
                navLinks.forEach(l => l.classList.remove('active'));
                this.classList.add('active');
                pages.forEach(page => page.style.display = 'none');
                document.getElementById(this.getAttribute('data-page')).style.display = 'block';
                document.getElementById('navMenu').classList.remove('show');
            });
        });

        // Flashcard
        const flashcard = document.getElementById('flashcard');
        flashcard.addEventListener('click', () => flashcard.classList.toggle('flipped'));

        // Auth Button
        document.getElementById('authBtn').addEventListener('click', function() {
            alert("Sign In / Sign Up modal would open here. (In a real app, this would show a login form.)");
        });

        // AI Translator
        const aiBtn = document.getElementById('aiFloatBtn');
        const panel = document.getElementById('translatorPanel');
        const closeBtn = document.getElementById('closePanel');

        aiBtn.addEventListener('click', () => panel.classList.add('active'));
        closeBtn.addEventListener('click', () => panel.classList.remove('active'));

        document.getElementById('swapLangs').addEventListener('click', function() {
            const from = document.getElementById('fromLang');
            const to = document.getElementById('toLang');
            [from.value, to.value] = [to.value, from.value];
        });

        document.getElementById('translateBtn').addEventListener('click', function() {
            const input = document.getElementById('inputText').value.trim();
            const toLang = document.getElementById('toLang').options[document.getElementById('toLang').selectedIndex].text;
            if (!input) {
                document.getElementById('outputText').textContent = 'Please enter text to translate.';
                return;
            }
            const sample = input.length > 40 ? input.substring(0, 40) + '...' : input;
            document.getElementById('outputText').textContent = `✅ [${toLang}] AI-translated: "${sample}"`;
        });
    </script>
</body>
</html>

