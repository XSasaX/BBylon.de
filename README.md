<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BBylon - Personalvermittlung für europäische Fachkräfte</title>
    <style>
        /* Google Fonts Import */
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&family=Open+Sans:wght@400;600&display=swap');

        /* Globale Stile & Reset */
        :root {
            --primary-color: #003366; /* Dunkles Blau */
            --secondary-color: #4a708b; /* Gedämpftes Blau */
            --accent-color: #f0f8ff; /* Sehr helles Blau / AliceBlue */
            --text-color: #333333;
            --light-text-color: #ffffff;
            --background-color: #ffffff;
            --section-bg-color: #f8f9fa; /* Leichtes Grau */
            --heading-font: 'Montserrat', sans-serif;
            --body-font: 'Open Sans', sans-serif;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--body-font);
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--background-color);
        }

        /* Container */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background-color: var(--background-color);
            padding: 1rem 0;
            border-bottom: 1px solid #eee;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* --- Logo Styling --- */
        .logo {
            font-family: var(--heading-font);
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--primary-color);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        #header-logo {
            height: 60px; /* Angepasste Höhe für bessere Proportionen */
            width: auto;
        }
        /* --- Ende Logo Styling --- */


        nav ul {
            list-style: none;
            display: flex;
        }

        nav ul li {
            margin-left: 30px;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--primary-color);
            font-weight: 600;
            transition: color 0.3s ease;
            font-size: 1rem;
        }

        nav ul li a:hover,
        nav ul li a.active { /* .active Klasse könnte man per JS hinzufügen */
            color: var(--secondary-color);
        }

        /* Hero Section */
        #hero {
            /* Optional: Hintergrundbild mit Farbüberlagerung */
            /* background: linear-gradient(rgba(0, 51, 102, 0.8), rgba(0, 51, 102, 0.8)), url('dein-hintergrundbild.jpg'); */
            background-color: var(--primary-color); /* Fallback oder Haupt-Hintergrund */
            background-size: cover;
            background-position: center;
            color: var(--light-text-color);
            text-align: center;
            padding: 100px 20px; /* Padding auch seitlich für schmalere Viewports */
        }

        #hero h1 {
            font-family: var(--heading-font);
            font-size: 2.8rem;
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        #hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-button {
            display: inline-block;
            background-color: var(--secondary-color);
            color: var(--light-text-color);
            padding: 12px 25px;
            font-size: 1rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.3s ease, transform 0.2s ease;
            border: none; /* Sicherstellen, dass kein Button-Rand da ist */
            cursor: pointer; /* Mauszeiger ändern */
        }

        .cta-button:hover {
            background-color: #3a5f7a; /* Etwas dunkleres Sekundärblau */
            transform: translateY(-2px);
        }

        /* Sektionen Allgemein */
        section {
            padding: 80px 0;
        }

        section:nth-child(even) { /* Gilt für section innerhalb von main */
            background-color: var(--section-bg-color);
        }
        /* Korrektur: Die erste Sektion (#hero) soll *nicht* den even-Style bekommen,
           daher zielen wir auf die Sections *innerhalb* von <main> */
        main section:nth-child(odd) {
             background-color: var(--background-color); /* Standard-Weiß */
        }
         main section:nth-child(even) {
             background-color: var(--section-bg-color); /* Leichtes Grau */
         }


        .section-title {
            font-family: var(--heading-font);
            font-size: 2rem;
            color: var(--primary-color);
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 3px;
            background-color: var(--secondary-color);
            margin: 10px auto 0;
        }

        /* Über Uns Sektion */
        #about p {
            max-width: 800px;
            margin: 0 auto 20px auto;
            text-align: center;
        }

        /* Leistungen Sektion */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .service-item {
            background-color: var(--background-color);
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .service-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.12);
        }

        .service-item h3 {
            font-family: var(--heading-font);
            color: var(--primary-color);
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        /* Prozess Sektion */
        .process-steps {
            list-style: none; /* Wichtig: Entfernt Standard-Nummerierung */
            counter-reset: process-counter;
            max-width: 800px;
            margin: 30px auto 0 auto;
            padding-left: 0; /* Entfernt Standard-Einrückung der Liste */
        }

        .process-steps li {
            counter-increment: process-counter;
            margin-bottom: 30px;
            position: relative;
            padding-left: 50px; /* Platz für die Nummer */
        }

        .process-steps li::before {
            content: counter(process-counter);
            position: absolute;
            left: 0;
            top: 0;
            width: 35px;
            height: 35px;
            background-color: var(--secondary-color);
            color: var(--light-text-color);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            font-family: var(--heading-font);
        }

        .process-steps h4 {
            font-family: var(--heading-font);
            color: var(--primary-color);
            margin-bottom: 5px;
        }

        /* Warum Wir Sektion */
        #why-us .benefits-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            list-style: none; /* Wichtig: Standard-Aufzählungszeichen entfernen */
            margin-top: 30px;
            padding-left: 0; /* Standard-Einrückung entfernen */
        }

        #why-us .benefits-list li {
           padding-left: 25px;
           position: relative;
           margin-bottom: 10px; /* Etwas Abstand zwischen den Punkten */
        }
         #why-us .benefits-list li::before {
            content: '✓'; /* Checkmark Symbol */
            position: absolute;
            left: 0;
            color: var(--secondary-color);
            font-weight: bold;
         }


        /* Kontakt Sektion */
        #contact p.intro-text {
            text-align: center;
            margin-bottom: 40px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        #contact form {
            max-width: 600px;
            margin: 30px auto 0 auto;
            padding: 30px; /* Etwas mehr Padding */
            background-color: var(--background-color);
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
        }

        #contact .form-group {
            margin-bottom: 20px;
        }

        #contact label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--primary-color);
        }

        #contact input[type="text"],
        #contact input[type="email"],
        #contact input[type="tel"],
        #contact textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-family: var(--body-font);
            font-size: 1rem;
        }

        #contact input:focus,
        #contact textarea:focus {
             border-color: var(--secondary-color);
             outline: none;
             box-shadow: 0 0 0 2px rgba(74, 112, 139, 0.2); /* Leichter Fokus-Ring */
        }


        #contact button[type="submit"] {
            display: block; /* Lässt den Button die volle Breite einnehmen */
            width: 100%;   /* Volle Breite innerhalb des Formulars */
            max-width: 250px; /* Maximale Breite für Ästhetik */
            margin: 10px auto 0 auto; /* Zentriert den Button */
            background-color: var(--primary-color);
            color: var(--light-text-color);
            padding: 12px 25px;
            font-size: 1rem;
            font-weight: 600;
            text-decoration: none;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        #contact button[type="submit"]:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
        }

        /* Sternchen für Pflichtfelder */
        label .required-star {
            color: red;
            margin-left: 2px;
        }

        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: var(--accent-color); /* Hellere Schrift für besseren Kontrast auf dunklem Blau */
            text-align: center;
            padding: 30px 20px; /* Mehr Padding */
            margin-top: 60px;
        }

        footer p {
            font-size: 0.9rem;
            margin: 0; /* Standard-Absatz-Margin entfernen */
        }
        footer a {
             color: var(--accent-color); /* Links im Footer auch hell */
             text-decoration: none;
             transition: color 0.3s ease;
        }
        footer a:hover {
            color: var(--light-text-color); /* Etwas heller beim Hover */
            text-decoration: underline;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header .container {
                flex-direction: column;
                align-items: center;
            }

            .logo {
                 margin-bottom: 15px;
                 font-size: 1.1rem;
            }
            #header-logo {
                height: 50px; /* Logo etwas kleiner auf Mobile */
            }

            nav {
                width: 100%; /* Volle Breite für die Navi auf Mobile */
            }
            nav ul {
                margin-top: 0;
                padding: 0;
                justify-content: center;
                flex-wrap: wrap; /* Erlaubt Umbruch bei vielen Menüpunkten */
            }
            nav ul li {
                margin: 5px 10px; /* Kleinere Abstände */
            }
            nav ul li a {
                font-size: 0.95rem; /* Leicht kleinere Schrift */
            }

            #hero {
                padding: 80px 20px;
            }
            #hero h1 {
                font-size: 2.2rem;
            }
            #hero p {
                font-size: 1.1rem; /* Angepasst */
            }

            section {
                 padding: 60px 0; /* Weniger Padding auf Mobile */
            }

            .section-title {
                font-size: 1.8rem;
            }

            .services-grid {
                grid-template-columns: 1fr; /* Einspaltig auf Mobile */
            }

             .process-steps li {
                 padding-left: 45px;
             }
             .process-steps li::before {
                 width: 30px;
                 height: 30px;
                 font-size: 0.9rem;
             }

             #why-us .benefits-list {
                 grid-template-columns: 1fr; /* Einspaltig auf Mobile */
             }

             #contact form {
                 padding: 20px; /* Weniger Padding im Formular */
             }
        }

         @media (max-width: 480px) {
             #hero h1 {
                 font-size: 1.8rem; /* Noch kleiner auf sehr schmalen Geräten */
             }
             #hero p {
                 font-size: 1rem;
             }
             .section-title {
                 font-size: 1.6rem;
             }
             .cta-button, #contact button[type="submit"] {
                 font-size: 0.95rem;
                 padding: 10px 20px;
             }
              #header-logo {
                height: 45px; /* Logo noch kleiner */
              }
              nav ul li {
                margin: 5px 8px; /* Noch kleinere Abstände */
              }
              nav ul li a {
                font-size: 0.9rem;
              }
         }

    </style>
</head>
<body>

    <header>
        <div class="container">
            <!-- Logo mit Bild UND Text -->
            <a href="#hero" class="logo">
                <!-- WICHTIG: Stelle sicher, dass der Pfad zum Logo korrekt ist! -->
                <img src="BBylon_Logo.png" alt="BBylon Logo" id="header-logo">
                <span>BBylon</span>
            </a>
            <nav>
                <ul>
                    <li><a href="#about">Über Uns</a></li>
                    <li><a href="#services">Leistungen</a></li>
                    <li><a href="#process">Prozess</a></li>
                    <li><a href="#why-us">Warum Wir</a></li>
                    <li><a href="#contact">Kontakt</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="hero">
            <div class="container">
                <h1>Verbinden europäische Unternehmen mit Top-Talenten</h1>
                <p>Wir sind Ihr spezialisierter Partner für die Rekrutierung und Vermittlung vorqualifizierter Fachkräfte aus ganz Europa. Finden Sie die Mitarbeiter, die Ihr Unternehmen wirklich voranbringen.</p>
                <!-- Verlinkt zum Kontaktbereich -->
                <a href="#contact" class="cta-button">Unverbindliche Anfrage</a>
            </div>
        </section>

        <section id="about">
            <div class="container">
                <h2 class="section-title">Über Uns</h2>
                <p>
                    BBylon versteht die Herausforderungen des modernen Arbeitsmarktes. Unser Ziel ist es, europäischen Unternehmen den Zugang zu qualifizierten und motivierten Mitarbeitern aus dem europäischen Raum zu erleichtern. Wir legen Wert auf einen seriösen, transparenten und effizienten Vermittlungsprozess. Authentizität und die Passgenauigkeit zwischen Unternehmen und Kandidat stehen für uns an erster Stelle.
                </p>
                 <p>
                    Unsere Expertise liegt in der sorgfältigen Vorauswahl und Qualifizierung von Kandidaten, sodass Sie nur Profile erhalten, die Ihren Anforderungen wirklich entsprechen. Wir bauen Brücken zwischen Kulturen und Kompetenzen für Ihren nachhaltigen Unternehmenserfolg.
                 </p>
            </div>
        </section>

        <section id="services">
            <div class="container">
                <h2 class="section-title">Unsere Leistungen für Unternehmen</h2>
                <div class="services-grid">
                    <div class="service-item">
                        <h3>Bedarfsanalyse & Profilerstellung</h3>
                        <p>Wir analysieren gemeinsam mit Ihnen präzise Ihren Personalbedarf und erstellen detaillierte Anforderungsprofile für die gesuchten Positionen.</p>
                    </div>
                    <div class="service-item">
                        <h3>Europaweites Sourcing</h3>
                        <p>Durch unser Netzwerk und gezielte Suchstrategien identifizieren wir potenzielle Kandidaten in verschiedenen europäischen Ländern.</p>
                    </div>
                    <div class="service-item">
                        <h3>Strikte Vorqualifizierung</h3>
                        <p>Jeder Kandidat durchläuft unseren mehrstufigen Prüfprozess, inkl. Überprüfung von Qualifikationen, Sprachkenntnissen und Motivation.</p>
                    </div>
                     <div class="service-item">
                        <h3>Passgenaue Kandidatenpräsentation</h3>
                        <p>Sie erhalten aussagekräftige Profile von sorgfältig ausgewählten Kandidaten, die Ihren Kriterien entsprechen.</p>
                    </div>
                     <div class="service-item">
                        <h3>Interview-Koordination</h3>
                        <p>Wir unterstützen Sie bei der Planung und Durchführung von Vorstellungsgesprächen (online oder vor Ort).</p>
                    </div>
                     <div class="service-item">
                        <h3>Unterstützung im Prozess</h3>
                        <p>Wir begleiten den Prozess von der Auswahl bis zur Vertragsunterzeichnung und unterstützen bei Bedarf bei administrativen Schritten.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="process">
            <div class="container">
                <h2 class="section-title">Unser bewährter Prozess</h2>
                <ol class="process-steps">
                    <li>
                        <h4>Analyse & Beratung</h4>
                        <p>Gemeinsames Verständnis Ihres Bedarfs und Definition der Anforderungen.</p>
                    </li>
                    <li>
                        <h4>Suche & Identifikation</h4>
                        <p>Aktive Suche nach passenden Kandidaten in unserem europäischen Netzwerk.</p>
                    </li>
                    <li>
                        <h4>Vorauswahl & Prüfung</h4>
                        <p>Intensive Prüfung der Bewerberprofile, Qualifikationen und Referenzen.</p>
                    </li>
                     <li>
                        <h4>Interviews & Qualifizierung</h4>
                        <p>Strukturierte Interviews zur Bewertung von Fachkompetenz, Soft Skills und Cultural Fit.</p>
                    </li>
                    <li>
                        <h4>Kandidatenpräsentation</h4>
                        <p>Vorstellung der Top-Kandidaten mit detaillierten Berichten an Sie.</p>
                    </li>
                    <li>
                        <h4>Ihre Auswahl & Einstellung</h4>
                        <p>Sie führen die finalen Gespräche und treffen Ihre Entscheidung. Wir unterstützen bis zum Abschluss.</p>
                    </li>
                </ol>
            </div>
        </section>

        <section id="why-us">
            <div class="container">
                <h2 class="section-title">Warum BBylon?</h2>
                 <p style="text-align: center; max-width: 800px; margin: 0 auto 30px auto;">
                    Setzen Sie auf einen Partner, der Seriosität, Effizienz und europäische Expertise vereint.
                 </p>
                <ul class="benefits-list">
                    <li><strong>Fokus Europa:</strong> Spezialisiertes Wissen über europäische Arbeitsmärkte und Kulturen.</li>
                    <li><strong>Qualitätsgarantie:</strong> Strenge Vorqualifizierung spart Ihnen Zeit und Ressourcen.</li>
                    <li><strong>Effizienz:</strong> Schlanker und transparenter Prozess von Anfang bis Ende.</li>
                    <li><strong>Netzwerk:</strong> Zugang zu einem breiten Pool an Talenten aus verschiedenen europäischen Ländern.</li>
                    <li><strong>Authentizität:</strong> Wir legen Wert auf ehrliche Kommunikation und nachhaltige Partnerschaften.</li>
                    <li><strong>Maßgeschneidert:</strong> Individuelle Lösungen, angepasst an Ihre spezifischen Unternehmensbedürfnisse.</li>
                </ul>
            </div>
        </section>

        <section id="contact">
            <div class="container">
                <h2 class="section-title">Kontaktieren Sie Uns</h2>
                <p class="intro-text">
                    Haben Sie Interesse oder Fragen? Füllen Sie einfach das Formular aus und wir werden uns umgehend bei Ihnen melden. Wir freuen uns darauf, von Ihnen zu hören!
                </p>

                <!-- ====== Start Kontaktformular - Verwendet Deine Formspree URL ====== -->
                <!-- Stelle sicher, dass die action URL korrekt ist! -->
                <form action="https://formspree.io/f/mpwpkpwz" method="POST">
                    <div class="form-group">
                        <label for="vorname">Vorname <span class="required-star">*</span></label>
                        <input type="text" id="vorname" name="Vorname" required>
                    </div>
                    <div class="form-group">
                        <label for="nachname">Nachname <span class="required-star">*</span></label>
                        <input type="text" id="nachname" name="Nachname" required>
                    </div>
                    <div class="form-group">
                        <label for="email">E-Mail-Adresse <span class="required-star">*</span></label>
                        <input type="email" id="email" name="E-Mail" required>
                    </div>
                    <div class="form-group">
                        <label for="telefon">Telefonnummer <span class="required-star">*</span></label>
                        <input type="tel" id="telefon" name="Telefonnummer" required>
                    </div>
                    <div class="form-group">
                        <label for="nachricht">Ihre Nachricht</label> <!-- Optional, daher kein Stern -->
                        <textarea id="nachricht" name="Nachricht" rows="5" placeholder="Geben Sie hier Ihre Nachricht oder Frage ein..."></textarea>
                    </div>

                     <!-- Optional: Honeypot-Feld gegen einfache Bots (versteckt) -->
                     <input type="text" name="_gotcha" style="display:none !important"> <!-- Wichtig: !important um sicherzustellen, dass es versteckt bleibt -->

                    <!-- Zentrierter Button -->
                    <button type="submit" class="cta-button">Anfrage senden</button>

                </form>
                 <!-- ====== Ende Kontaktformular ====== -->

            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <!-- Hinweis: Ersetze #impressum und #datenschutz durch echte Links zu deinen Seiten/Abschnitten -->
            <p>© 2024 BBylon. Alle Rechte vorbehalten. | <a href="#impressum">Impressum</a> | <a href="#datenschutz">Datenschutz</a></p>
            <!-- Du müsstest noch Abschnitte oder separate Seiten für Impressum und Datenschutz erstellen -->
        </div>
    </footer>

    <!-- Optional: JavaScript hinzufügen, falls benötigt (z.B. für aktive Menüpunkte, erweiterte Formularvalidierung etc.) -->
    <!-- <script src="script.js"></script> -->

</body>
</html>
