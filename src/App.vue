<template>
  <div id="app">
    <!-- Header -->
    <header class="header">
      <nav class="nav">
        <div class="container">
          <div class="nav-content">
            <div class="logo">
              <img src="/kiwi_logo.svg" alt="KIWi Logo" class="logo-img">
            </div>
            <div class="nav-links">
              <a href="#about" class="nav-link">Über KIWi</a>
              <a href="#goals" class="nav-link">Ziele</a>
              <a href="#modules" class="nav-link">Module</a>
              <a href="#partners" class="nav-link">Partner</a>
              <a href="#contact" class="nav-link">Kontakt</a>
              <a href="#kooperationszuschuesse" class="nav-link nav-link-cta">Kooperationszuschüsse</a>
            </div>
          </div>
        </div>
      </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" :style="{ backgroundColor: headerColor }">
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-title fade-in-up">
              KI & Wissenschaft:<br>
              <span class="hero-subtitle">KI-Workshops für Bildungseinrichtungen</span>
            </h1>
            <p class="hero-description fade-in-up">
              KIWi bringt Künstliche Intelligenz kindgerecht in Schulen. 
              Wir fördern kritisches Denken und wecken Begeisterung für Forschung und Technik.
            </p>
            <div class="hero-buttons fade-in-up">
              <a href="#goals" class="btn btn-hero-primary">Mehr erfahren</a>
              <a href="#contact" class="btn btn-hero-outline">Kontakt aufnehmen</a>
            </div>
          </div>
          <div class="hero-visual">
            <img src="/kiwi_icon.svg" alt="KIWi Icon" class="hero-icon">
          </div>
        </div>
      </div>
    </section>


    <!-- Goals Section -->
    <section id="goals" class="section section-alt">
      <div class="container">
        <div class="section-header">
          <h2>Ziele des Projekts</h2>
          <p class="section-description">
            Unser Ziel ist es, Kinder und Jugendliche frühzeitig mit KI vertraut zu machen 
            und wichtige Kompetenzen zu fördern.
          </p>
        </div>
        
        <div class="goals-grid grid grid-goals">
          <div class="goal-card card">
            <h3>KI-Kompetenzen</h3>
            <p>Verstehen, Anwenden, Gestalten und Reflektieren von KI-Technologien</p>
          </div>
          <div class="goal-card card">
            <h3>Entdeckendes Lernen</h3>
            <p>Förderung von <em>Inquiry-Based Learning</em> und forschendem Lernen</p>
          </div>
          <div class="goal-card card">
            <h3>MINT-Kompetenzen</h3>
            <p>Vermittlung von MINT- und Forschungskompetenzen durch praktische Projekte</p>
          </div>
          <div class="goal-card card">
            <h3>Gendergerechtigkeit</h3>
            <p>Gezielte Förderung von Mädchen und Diversität in der Technik</p>
          </div>
          <div class="goal-card card">
            <h3>Regionale Vernetzung</h3>
            <p>Verbindung zwischen Schulen, Forschung und Wirtschaft</p>
          </div>
          <div class="goal-card card">
            <h3>UN-SDGs</h3>
            <p>Beitrag zu den UN-Nachhaltigkeitszielen 4, 5 und 10</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Modules Section -->
    <section id="modules" class="section section-modules">
      <div class="container">
        <div class="section-header">
          <h2>Pädagogisches Konzept</h2>
          <p class="section-description">
            Das Projekt setzt auf drei altersgerechte Forschungsreisen mit verschiedenen Modulen, 
            die durch Experimentieren, Spielen und Kreativarbeit gestaltet sind.
          </p>
        </div>

        <div class="modules-tabs">
          <div class="tab-buttons">
            <button 
              v-for="(level, index) in schoolLevels" 
              :key="level.name"
              @click="activeTab = index"
              :class="['tab-btn', { active: activeTab === index }]"
            >
              {{ level.name }}
            </button>
          </div>
          
          <div class="tab-content">
            <div v-for="(level, index) in schoolLevels" :key="level.name" v-show="activeTab === index">
              <div class="modules-grid grid grid-2">
                <div v-for="module in level.modules" :key="module.name" class="module-card card">
                  <h4>{{ module.name }}</h4>
                  <p class="module-partner">{{ module.partner }}</p>
                  <p class="module-description">{{ module.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="kiwi-day card">
          <div class="kiwi-day-content">
            <h3>KIWi-Tag am Campus Hagenberg</h3>
            <p>
              Am Ende jeder Lernreise steht der <strong>KIWi-Tag</strong> am Campus Hagenberg, 
              an dem Schüler*innen ihre Ergebnisse präsentieren, von Unternehmen lernen und 
              Einblicke in Forschung und Wirtschaft erhalten.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Partners Section -->
    <section id="partners" class="section section-alt">
      <div class="container">
        <div class="section-header">
          <h2>Konsortium</h2>
          <p class="section-description">
            Ein starkes Netzwerk aus Forschung, Bildung und Wirtschaft arbeitet gemeinsam 
            an der Zukunft der KI-Bildung.
          </p>
        </div>

        <div class="partners-grid">
          <div class="partner-category">
            <h3>Forschung & Bildung</h3>
            <div class="partner-list">
              <a href="https://www.fh-ooe.at/campus-hagenberg" target="_blank" rel="noopener noreferrer" class="partner-item" aria-label="FH Oberösterreich, Campus Hagenberg – Website öffnen">
                <img src="/partners/fh-ooe.png" alt="FH Oberösterreich, Campus Hagenberg" class="partner-logo-img">
                <div class="partner-info">
                  <div class="partner-name">FH Oberösterreich, Campus Hagenberg</div>
                  <div class="partner-role">(Projektleitung)</div>
                </div>
              </a>
              <a href="https://www.risc-software.at" target="_blank" rel="noopener noreferrer" class="partner-item" aria-label="RISC Software GmbH – Website öffnen">
                <img src="/partners/risc.svg" alt="RISC Software GmbH" class="partner-logo-img">
                <div class="partner-info">
                  <div class="partner-name">RISC Software GmbH</div>
                </div>
              </a>
              <a href="https://www.scch.at" target="_blank" rel="noopener noreferrer" class="partner-item" aria-label="Software Competence Center Hagenberg (SCCH) – Website öffnen">
                <img src="/partners/scch.png" alt="Software Competence Center Hagenberg (SCCH)" class="partner-logo-img">
                <div class="partner-info">
                  <div class="partner-name">Software Competence Center Hagenberg (SCCH)</div>
                </div>
              </a>
            </div>
          </div>
          
          <div class="partner-category">
            <h3>Unternehmen</h3>
            <div class="partner-list">
              <a href="https://www.bluesource.at" target="_blank" rel="noopener noreferrer" class="partner-item" aria-label="bluesource – mobile solutions gmbh – Website öffnen">
                <img src="/partners/bluesource.svg" alt="bluesource – mobile solutions gmbh" class="partner-logo-img">
                <div class="partner-info">
                  <div class="partner-name">bluesource – mobile solutions gmbh</div>
                </div>
              </a>
              <a href="https://www.porscheinformatik.com" target="_blank" rel="noopener noreferrer" class="partner-item" aria-label="Porsche Informatik GmbH – Website öffnen">
                <img src="/partners/porsche-informatik.svg" alt="Porsche Informatik GmbH" class="partner-logo-img">
                <div class="partner-info">
                  <div class="partner-name">Porsche Informatik GmbH</div>
                </div>
              </a>
              <a href="https://www.rise2reality.com" target="_blank" rel="noopener noreferrer" class="partner-item partner-item-logo-dark" aria-label="Rise2Reality e.U. – Website öffnen">
                <img src="/partners/rise2reality.png" alt="Rise2Reality e.U." class="partner-logo-img">
                <div class="partner-info">
                  <div class="partner-name">Rise2Reality e.U.</div>
                </div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Schools Section -->
    <section id="schools" class="section section-alt">
      <div class="container">
        <div class="section-header">
          <h2>Beteiligte Schulen</h2>
          <p class="section-description">
            Schulen aus der Region, die am KIWi-Projekt teilnehmen.
          </p>
        </div>
        
        <div class="card">
          <div class="schools-grid">
            <div class="school-item">
              <div class="school-name">VS Hagenberg im Mühlkreis</div>
              <div class="school-tags">
                <span class="school-tag primar">Volksschule</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">VS Pregarten</div>
              <div class="school-tags">
                <span class="school-tag primar">Volksschule</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">VS Wartberg ob der Aist</div>
              <div class="school-tags">
                <span class="school-tag primar">Volksschule</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">MS Pregarten</div>
              <div class="school-tags">
                <span class="school-tag sek1">Sekundarstufe I</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">BG/BRG Freistadt</div>
              <div class="school-tags">
                <span class="school-tag sek1">Sekundarstufe I</span>
                <span class="school-tag sek2">Sekundarstufe II</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">Bischöfliches Gymnasium Petrinum Linz</div>
              <div class="school-tags">
                <span class="school-tag sek1">Sekundarstufe I</span>
                <span class="school-tag sek2">Sekundarstufe II</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">BORG Hagenberg</div>
              <div class="school-tags">
                <span class="school-tag sek2">Sekundarstufe II</span>
              </div>
            </div>
            <div class="school-item">
              <div class="school-name">ABZ Hagenberg (Agrarbildungszentrum)</div>
              <div class="school-tags">
                <span class="school-tag sek2">Sekundarstufe II</span>
              </div>
            </div>
          </div>
          
          <div class="schools-legend">
            <h4>Legende:</h4>
            <div class="legend-items">
              <div class="legend-item">
                <span class="legend-tag primar">Volksschule</span>
                <span class="legend-text">Primarstufe (ca. 6–10 Jahre)</span>
              </div>
              <div class="legend-item">
                <span class="legend-tag sek1">Sekundarstufe I</span>
                <span class="legend-text">Unterstufe (ca. 10–14 Jahre)</span>
              </div>
              <div class="legend-item">
                <span class="legend-tag sek2">Sekundarstufe II</span>
                <span class="legend-text">Oberstufe / Berufsbildung (ca. 15–19 Jahre)</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Benefits Section -->
    <section class="section section-nutzen">
      <div class="container">
        <div class="section-header">
          <h2>Nutzen</h2>
          <p class="section-description">
            KIWi schafft Mehrwert für alle Beteiligten und die gesamte Region.
          </p>
        </div>

        <div class="benefits-grid grid grid-benefits">
          <div class="benefit-card card">
            <h3>Für Schüler*innen</h3>
            <ul>
              <li>Verständnis und kritische Reflexion von KI</li>
              <li>Motivation für MINT-Berufe und Forschung</li>
              <li>Stärkung sozialer und methodischer Kompetenzen</li>
              <li>Praxisnahe Einblicke in regionale Unternehmen</li>
            </ul>
          </div>
          
          <div class="benefit-card card">
            <h3>Für Pädagog*innen</h3>
            <ul>
              <li>Zugang zu didaktisch aufbereiteten Lehrmaterialien</li>
              <li>Unterstützung bei der Einbindung von KI in den Unterricht</li>
              <li>Kooperation mit F&E-Expert*innen</li>
              <li>Regionale Vernetzung</li>
            </ul>
          </div>
          
          <div class="benefit-card card">
            <h3>Für die Region</h3>
            <ul>
              <li>Förderung technologischer Bildung im Mühlviertel</li>
              <li>Sichtbarkeit des Softwarepark Hagenberg</li>
              <li>Nachhaltige Verankerung von Forschung und Wirtschaft</li>
              <li>Innovationsstandort stärken</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- Funding Section -->
    <section class="section section-alt">
      <div class="container">
        <div class="funding-content">
          <h2>Förderung & Kooperationszuschüsse</h2>
          <div class="funding-grid grid grid-2">
            <div class="funding-card card">
              <h3>FFG-Förderung</h3>
              <a href="https://www.ffg.at" target="_blank" rel="noopener noreferrer" class="ffg-logo-link" aria-label="FFG – Österreichische Forschungsförderungsgesellschaft">
                <img src="/logos/ffg/FFG_Logo_DE_RGB_1000px.png" alt="FFG – Österreichische Forschungsförderungsgesellschaft" class="ffg-logo">
              </a>
              <p>
                Dieses Projekt wird aus Mitteln der FFG gefördert (<a href="https://www.ffg.at" target="_blank" rel="noopener noreferrer">www.ffg.at</a>). 
                Die FFG ist die zentrale nationale Förderorganisation und stärkt Österreichs Innovationskraft.
                Gefördert im Rahmen der Ausschreibung <em>Talente Regional 2024</em> mit einer Förderquote von 100% der anerkannten Projektkosten.
              </p>
            </div>
            <div id="kooperationszuschuesse" class="funding-card card funding-card-highlight funding-card-clickable" role="button" tabindex="0" @click="showKooperationsModal = true" @keydown.enter="showKooperationsModal = true" @keydown.space.prevent="showKooperationsModal = true">
              <h3>Kooperationszuschüsse</h3>
              <p>
                KIWi stellt <strong>10 Zuschüsse à €1.000</strong> für weitere Schulen bereit. 
                Diese können für Projekthardware, KI-Tool-Lizenzen, Exkursionen oder 
                Expert*innen-Vorträge genutzt werden.
              </p>
              <span class="btn btn-secondary">Mehr erfahren & bewerben</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
      <div class="container">
        <div class="section-header">
          <h2>Projektüberblick</h2>
          <p class="section-description">
            KIWi ist ein gemeinsames Bildungsprojekt des Softwarepark Hagenberg (SWPH), 
            das Künstliche Intelligenz kindgerecht in Schulen bringt.
          </p>
        </div>
        
        <div class="project-stats grid grid-4">
          <div class="stat-card card">
            <div class="stat-number">26</div>
            <div class="stat-label">Monate Laufzeit</div>
          </div>
          <div class="stat-card card">
            <div class="stat-number">€122.439</div>
            <div class="stat-label">Gesamtkosten</div>
          </div>
          <div class="stat-card card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Förderquote</div>
          </div>
          <div class="stat-card card">
            <div class="stat-number">8</div>
            <div class="stat-label">Beteiligte Schulen</div>
          </div>
        </div>

        <div class="project-details">
          <div class="detail-item">
            <h4>Förderprogramm</h4>
            <p>FFG <em>Talente Regional 2024</em></p>
          </div>
          <div class="detail-item">
            <h4>Projektleitung</h4>
            <p>FH Oberösterreich Forschungs- & Entwicklungs GmbH, Campus Hagenberg</p>
          </div>
          <div class="detail-item">
            <h4>Fördergeber</h4>
            <p>FFG – Österreichische Forschungsförderungsgesellschaft</p>
          </div>
        </div>

        <div class="project-info-link">
          <a href="https://projekte.ffg.at/projekt/5135929/pdf" target="_blank" rel="noopener noreferrer" class="btn btn-secondary">
            Projektbeschreibung (FFG) – PDF
          </a>
          <p class="project-info-hint">Weitere Projektinformationen in der FFG-Projektdatenbank</p>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
      <div class="container">
        <div class="section-header">
          <h2>Kontakt</h2>
          <p class="section-description">
            Haben Sie Fragen oder möchten Sie Teil des KIWi-Netzwerks werden? 
            Kontaktieren Sie uns!
          </p>
        </div>

        <div class="contact-content">
          <div class="contact-info card">
            <h3>Projektleitung</h3>
            <div class="contact-details">
              <p><strong>FH Oberösterreich Forschungs- & Entwicklungs GmbH</strong></p>
              <p>Campus Hagenberg</p>
              <p><strong>Projektleiter:</strong> Samuel Zühlke, MSc</p>
              <p>
                <a href="mailto:samuel.zuehlke@fh-hagenberg.at" class="contact-link">
                  📧 samuel.zuehlke@fh-hagenberg.at
                </a>
              </p>
            </div>
          </div>
          
          <div class="funding-notice card">
            <h3>Förderhinweis</h3>
            <p>
              Dieses Projekt wird aus Mitteln der FFG gefördert (<a href="https://www.ffg.at" target="_blank" rel="noopener noreferrer">www.ffg.at</a>). 
              Die FFG ist die zentrale nationale Förderorganisation und stärkt Österreichs Innovationskraft.
              Förderprogramm: <em>Talente Regional 2024</em>.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Back to Top Button -->
    <button 
      v-show="showBackToTop" 
      @click="scrollToTop" 
      class="back-to-top"
      :class="{ 'visible': showBackToTop }"
    >
      ↑
    </button>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <img src="/kiwi_logo.svg" alt="KIWi Logo" class="footer-logo-img">
            <span class="footer-logo-text">KIWi</span>
          </div>
          <div class="footer-info">
            <p>&copy; 2025 KIWi – KI & Wissenschaft. Alle Rechte vorbehalten.</p>
            <p>
              Dieses Projekt wird aus Mitteln der FFG gefördert (<a href="https://www.ffg.at" target="_blank" rel="noopener noreferrer">www.ffg.at</a>). 
              Die FFG ist die zentrale nationale Förderorganisation und stärkt Österreichs Innovationskraft.
            </p>
            <a href="https://www.ffg.at" target="_blank" rel="noopener noreferrer" class="footer-ffg-logo-link" aria-label="FFG – Österreichische Forschungsförderungsgesellschaft">
              <img src="/logos/ffg/FFG_Logo_DE_RGB_1000px.png" alt="FFG – Österreichische Forschungsförderungsgesellschaft" class="footer-ffg-logo">
            </a>
          </div>
        </div>
      </div>
    </footer>

    <!-- Kooperationszuschuss Modal -->
    <div v-show="showKooperationsModal" class="modal-overlay" @click.self="showKooperationsModal = false" role="dialog" aria-labelledby="modal-title" aria-modal="true">
      <div class="modal kooperations-modal">
        <button type="button" class="modal-close" aria-label="Schließen" @click="showKooperationsModal = false">&times;</button>
        <h2 id="modal-title" class="modal-title">Kooperationszuschüsse – Informationen & Bewerbung</h2>
        <div class="modal-body">
          <p class="modal-intro">
            KIWi vergibt <strong>10 Kooperationszuschüsse à €1.000</strong> an Schulen, die am Projekt teilnehmen möchten. 
            Die Zuschüsse können für Projekthardware, KI-Tool-Lizenzen, Exkursionen oder Expert*innen-Vorträge verwendet werden.
          </p>
          <section class="modal-docs">
            <h3>Unterlagen zum Download</h3>
            <div class="doc-cards">
              <a href="https://www.ffg.at/sites/default/files/2025-06/KIWi_Projektkurzbeschreibung_bf.pdf" target="_blank" rel="noopener noreferrer" class="doc-card">
                <span class="doc-card-badge">PDF</span>
                <span class="doc-card-title">Projektkurzbeschreibung KIWi</span>
                <span class="doc-card-desc">Kurze Übersicht über das KIWi-Projekt und die Kooperationszuschüsse.</span>
              </a>
              <a href="https://www.ffg.at/sites/default/files/2025-06/Infoblatt_Kooperationszuschuss_Lehrende_2025.pdf" target="_blank" rel="noopener noreferrer" class="doc-card">
                <span class="doc-card-badge">PDF</span>
                <span class="doc-card-title">Infoblatt für Pädagog*innen</span>
                <span class="doc-card-desc">Informationen zum Kooperationszuschuss speziell für Lehrkräfte.</span>
              </a>
              <a href="https://www.ffg.at/sites/default/files/2025-09/Antragsformular_Kooperationszuschuss_Talente_regional_bf.docx" target="_blank" rel="noopener noreferrer" class="doc-card">
                <span class="doc-card-badge">Word</span>
                <span class="doc-card-title">Antragsformular</span>
                <span class="doc-card-desc">Vorlage für Ihren Antrag – ausfüllen und per E-Mail an die Projektleitung senden.</span>
              </a>
              <a href="https://www.ffg.at/sites/default/files/2025-09/Abschlussbericht_Kooperationszuschuss_Talente_regional_bf.docx" target="_blank" rel="noopener noreferrer" class="doc-card">
                <span class="doc-card-badge">Word</span>
                <span class="doc-card-title">Abschlussbericht</span>
                <span class="doc-card-desc">Vorlage für den Abschlussbericht nach Ende der Kooperation.</span>
              </a>
            </div>
          </section>
          <section class="modal-apply">
            <h3>So bewerben Sie sich</h3>
            <p>
              Füllen Sie das <strong>Antragsformular</strong> (siehe oben) aus. Ihren ausgefüllten Antrag senden Sie per E-Mail an die <strong>Projektleitung</strong>:
            </p>
            <p class="modal-apply-recipient">
              <strong>Samuel Zühlke</strong><br>
              <span class="modal-apply-email">samuel.zuehlke@fh-hagenberg.at</span>
            </p>
            <p class="modal-apply-note">Der Klick auf den Button öffnet Ihr E-Mail-Programm mit dieser Adresse und dem Betreff „KIWi Kooperationszuschuss – Antrag“.</p>
            <a href="mailto:samuel.zuehlke@fh-hagenberg.at?subject=KIWi%20Kooperationszuschuss%20–%20Antrag" class="btn btn-primary modal-cta">E-Mail an Projektleitung (Samuel Zühlke) senden</a>
          </section>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      activeTab: 0,
      headerColor: this.getRandomHeaderColor(),
      showBackToTop: false,
      showKooperationsModal: false,
      schoolLevels: [
        {
          name: 'Volksschule',
          modules: [
            {
              name: 'Detektiv*innen der KI',
              partner: 'FH OÖ',
              description: 'Spielerisches Entdecken von KI-Grundlagen durch Detektivarbeit'
            },
            {
              name: 'KI oder Ich? Wer hat recht?',
              partner: 'Porsche Informatik',
              description: 'Kritisches Denken über KI-Entscheidungen entwickeln'
            },
            {
              name: 'KI-Geschichten- & Märchenwerkstatt',
              partner: 'RISC',
              description: 'Kreatives Schreiben mit KI-Unterstützung'
            }
          ]
        },
        {
          name: 'Sekundarstufe I',
          modules: [
            {
              name: 'Wie KI dich sieht',
              partner: 'FH OÖ',
              description: 'Verstehen von KI-Bilderkennung und -interpretation'
            },
            {
              name: 'KI-Baumblätterkenner',
              partner: 'RISC',
              description: 'Praktische Anwendung von KI in der Naturerkundung'
            },
            {
              name: 'Was kann KI?',
              partner: 'Rise2Reality',
              description: 'Erkundung der Möglichkeiten und Grenzen von KI'
            },
            {
              name: 'Entdecke das Potenzial von KI',
              partner: 'SCCH',
              description: 'Forschungsnahe Einblicke in KI-Technologien'
            }
          ]
        },
        {
          name: 'Sekundarstufe II',
          modules: [
            {
              name: 'DataDrive',
              partner: 'Bluesource',
              description: 'Datenanalyse und -visualisierung mit KI-Tools'
            },
            {
              name: 'Think Twice: Deepfake & Bias in der KI',
              partner: 'FH OÖ',
              description: 'Kritische Auseinandersetzung mit KI-Ethik und -Risiken'
            },
            {
              name: 'Forschung steckt an',
              partner: 'FH OÖ',
              description: 'Einblicke in aktuelle KI-Forschung und -Entwicklung'
            }
          ]
        }
      ]
    }
  },
  watch: {
    showKooperationsModal(isOpen) {
      document.body.style.overflow = isOpen ? 'hidden' : '';
    }
  },
  methods: {
    getRandomHeaderColor() {
      const colors = ['var(--kiwi-purple)', 'var(--kiwi-orange)', 'var(--kiwi-green)'];
      return colors[Math.floor(Math.random() * colors.length)];
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    },
    handleScroll() {
      this.showBackToTop = window.scrollY > 300;
    },
    handleModalKeydown(e) {
      if (e.key === 'Escape' && this.showKooperationsModal) {
        this.showKooperationsModal = false;
      }
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
    window.addEventListener('keydown', this.handleModalKeydown);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
    window.removeEventListener('keydown', this.handleModalKeydown);
    document.body.style.overflow = '';
  }
}
</script>

<style scoped>
/* Header Styles */
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--kiwi-gray-200);
  z-index: 1000;
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-img {
  height: 40px;
  width: auto;
}


.nav-links {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-link {
  color: var(--kiwi-dark);
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
  display: inline-flex;
  align-items: center;
}

.nav-link:hover {
  color: var(--kiwi-purple);
}

.nav-link-cta {
  background: var(--kiwi-purple);
  color: var(--kiwi-white);
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  display: inline-flex;
  align-items: center;
  line-height: 1.25;
}

.nav-link-cta:hover {
  background: var(--kiwi-orange);
  color: var(--kiwi-white);
}

/* Hero Styles */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  scroll-snap-align: start;
  scroll-snap-stop: always;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-title {
  margin-bottom: 1.5rem;
  color: var(--kiwi-white);
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.hero-subtitle {
  color: var(--kiwi-white);
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.hero-description {
  font-size: 1.25rem;
  margin-bottom: 2rem;
  color: var(--kiwi-white);
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.hero-buttons {
  display: flex;
  gap: 1rem;
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero-icon {
  width: 400px;
  height: auto;
}

/* Section Styles */
.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-description {
  font-size: 1.25rem;
  color: var(--kiwi-gray-600);
  max-width: 800px;
  margin: 0 auto;
}

/* Stats Styles */
.stat-card {
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
}

.stat-label {
  color: var(--kiwi-gray-600);
  font-weight: 500;
}

/* Project Details */
.project-details {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
  margin-top: 3rem;
}

.detail-item {
  flex: 1;
  text-align: center;
}

.detail-item h4 {
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
}

.project-info-link {
  margin-top: 2rem;
  text-align: center;
}

.project-info-link .btn {
  display: inline-block;
}

.project-info-hint {
  margin-top: 0.5rem;
  font-size: 0.875rem;
  color: var(--kiwi-gray-600);
}

/* Goals Styles */
.goal-card {
  text-align: center;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.goal-card h3 {
  font-size: 1.125rem;
  margin-bottom: 0.75rem;
}

.goal-card p {
  font-size: 0.875rem;
  line-height: 1.4;
  margin-bottom: 0;
}

.goal-icon {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: var(--kiwi-purple);
  background: var(--kiwi-gray-100);
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
}

/* Modules Styles */
.modules-tabs {
  margin-bottom: 3rem;
}

.tab-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-bottom: 2rem;
}

.tab-btn {
  padding: 0.75rem 1.5rem;
  border: 2px solid var(--kiwi-gray-300);
  background: var(--kiwi-white);
  color: var(--kiwi-gray-600);
  border-radius: 0.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.tab-btn.active {
  border-color: var(--kiwi-purple);
  background: var(--kiwi-purple);
  color: var(--kiwi-white);
}

.module-card h4 {
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
}

.module-partner {
  color: var(--kiwi-green);
  font-weight: 500;
  margin-bottom: 1rem;
}

.module-description {
  color: var(--kiwi-gray-600);
}

/* KIWi Day */
.kiwi-day {
  text-align: center;
  margin-top: 2rem;
}

.kiwi-day h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1rem;
}

.kiwi-day p {
  color: var(--kiwi-dark);
}

/* Partners Styles */
.partners-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 3rem;
  margin-bottom: 3rem;
}

.partner-category h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1.5rem;
  text-align: center;
}

.partner-list {
  display: grid;
  gap: 1rem;
  grid-template-rows: repeat(3, 1fr);
}

.partner-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  background: var(--kiwi-white);
  border-radius: 0.5rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  height: 120px;
  min-height: 120px;
}

a.partner-item {
  text-decoration: none;
  color: inherit;
  cursor: pointer;
  transition: box-shadow 0.2s ease, border-color 0.2s ease;
  border: 2px solid transparent;
}

a.partner-item:hover {
  box-shadow: 0 4px 12px rgba(102, 45, 145, 0.2);
  border-color: var(--kiwi-purple);
}

.partner-logo-img {
  width: 60px;
  height: 60px;
  object-fit: contain;
  flex-shrink: 0;
  border-radius: 0.5rem;
}

.partner-item-logo-dark .partner-logo-img {
  background: var(--kiwi-dark);
  padding: 0.35rem;
}

.partner-info {
  flex: 1;
}

.partner-name {
  font-weight: 500;
  margin-bottom: 0.25rem;
}

.partner-role {
  font-size: 0.875rem;
  color: var(--kiwi-gray-600);
  font-style: italic;
}

/* Schools Styles */
.schools-section {
  background: var(--kiwi-white);
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.schools-section h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1.5rem;
  text-align: center;
}

.schools-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 1rem;
}

.school-item {
  padding: 1rem;
  background: var(--kiwi-white);
  border-radius: 0.5rem;
  text-align: center;
  font-weight: 500;
  border: 2px solid var(--kiwi-gray-200);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.school-item:hover {
  border-color: var(--kiwi-green);
  background: var(--kiwi-light-green);
}

.school-name {
  font-weight: 600;
  color: var(--kiwi-dark);
}

.school-tags {
  display: flex;
  justify-content: center;
  gap: 0.25rem;
  flex-wrap: wrap;
}

.school-tag {
  padding: 0.125rem 0.375rem;
  border-radius: 0.25rem;
  font-size: 0.625rem;
  font-weight: 500;
  text-transform: uppercase;
  opacity: 0.8;
}

.school-tag.primar {
  background-color: var(--kiwi-green);
  color: var(--kiwi-white);
}

.school-tag.sek1 {
  background-color: var(--kiwi-orange);
  color: var(--kiwi-white);
}

.school-tag.sek2 {
  background-color: var(--kiwi-purple);
  color: var(--kiwi-white);
}

.schools-legend {
  margin-top: 2rem;
  padding-top: 1.5rem;
  border-top: 1px solid var(--kiwi-gray-200);
}

.schools-legend h4 {
  color: var(--kiwi-purple);
  margin-bottom: 1rem;
  text-align: center;
}

.legend-items {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: nowrap;
}

.legend-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.legend-tag {
  padding: 0.125rem 0.375rem;
  border-radius: 0.25rem;
  font-size: 0.625rem;
  font-weight: 500;
  text-transform: uppercase;
  opacity: 0.8;
}

.legend-tag.primar {
  background-color: var(--kiwi-green);
  color: var(--kiwi-white);
}

.legend-tag.sek1 {
  background-color: var(--kiwi-orange);
  color: var(--kiwi-white);
}

.legend-tag.sek2 {
  background-color: var(--kiwi-purple);
  color: var(--kiwi-white);
}

.legend-text {
  font-size: 0.875rem;
  color: var(--kiwi-gray-600);
}

/* Benefits Styles */
.benefit-card ul {
  list-style: none;
  padding: 0;
}

.benefit-card li {
  padding: 0.5rem 0;
  border-bottom: 1px solid var(--kiwi-gray-200);
}

.benefit-card li:last-child {
  border-bottom: none;
}

.benefit-card li::before {
  content: "✓";
  color: var(--kiwi-green);
  font-weight: bold;
  margin-right: 0.5rem;
}

/* Funding Styles */
.funding-grid {
  margin-top: 2rem;
}

.funding-card h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1rem;
}

.funding-card-highlight {
  background: linear-gradient(135deg, var(--kiwi-purple) 0%, var(--kiwi-orange) 100%);
  color: var(--kiwi-white);
  border: 3px solid var(--kiwi-orange);
  transform: scale(1.05);
  box-shadow: 0 10px 30px rgba(102, 45, 145, 0.3);
}

.funding-card-highlight h3 {
  color: var(--kiwi-white);
}

.funding-card-highlight p {
  color: var(--kiwi-white);
}

.funding-card-clickable {
  cursor: pointer;
}

.funding-card-clickable .btn {
  pointer-events: none;
}

/* Kooperationszuschuss Modal */
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2000;
  padding: 1rem;
  overflow-y: auto;
}

.modal {
  background: var(--kiwi-white);
  border-radius: 1rem;
  width: 100%;
  max-width: none;
  max-height: calc(100vh - 2rem);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
  position: relative;
}

.modal-close {
  position: absolute;
  top: 1rem;
  right: 1rem;
  width: 2.5rem;
  height: 2.5rem;
  border: none;
  background: var(--kiwi-gray-100);
  color: var(--kiwi-dark);
  font-size: 1.5rem;
  line-height: 1;
  border-radius: 0.5rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.2s ease;
}

.modal-close:hover {
  background: var(--kiwi-gray-200);
}

.modal-title {
  padding: 1.5rem 1.5rem 0;
  margin-bottom: 0.5rem;
  font-size: 1.5rem;
  color: var(--kiwi-purple);
}

.modal-body {
  padding: 1rem 1.5rem 1.5rem;
  overflow-y: auto;
}

.modal-intro {
  margin-bottom: 1.5rem;
  color: var(--kiwi-gray-800);
}

.modal-docs {
  margin-bottom: 1.5rem;
}

.modal-docs h3,
.modal-apply h3 {
  font-size: 1.125rem;
  color: var(--kiwi-purple);
  margin-bottom: 0.75rem;
}

.doc-cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
}

.doc-card {
  display: flex;
  flex-direction: column;
  padding: 1rem;
  background: var(--kiwi-gray-50);
  border: 1px solid var(--kiwi-gray-200);
  border-radius: 0.5rem;
  text-decoration: none;
  color: inherit;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.doc-card:hover {
  border-color: var(--kiwi-purple);
  box-shadow: 0 4px 12px rgba(102, 45, 145, 0.15);
}

.doc-card-badge {
  display: inline-block;
  align-self: flex-start;
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--kiwi-purple);
  background: rgba(102, 45, 145, 0.1);
  padding: 0.25rem 0.5rem;
  border-radius: 0.25rem;
  margin-bottom: 0.5rem;
}

.doc-card-title {
  font-weight: 600;
  color: var(--kiwi-purple);
  margin-bottom: 0.5rem;
  line-height: 1.3;
}

.doc-card-desc {
  font-size: 0.875rem;
  color: var(--kiwi-gray-600);
  line-height: 1.4;
  margin-top: auto;
}

.modal-apply {
  background: var(--kiwi-gray-50);
  padding: 1rem;
  border-radius: 0.5rem;
}

.modal-apply p {
  margin-bottom: 0.75rem;
  font-size: 1rem;
}

.modal-apply p:last-of-type {
  margin-bottom: 1rem;
}

.modal-apply-recipient {
  margin-bottom: 0.5rem;
  padding: 0.75rem;
  background: var(--kiwi-white);
  border-radius: 0.375rem;
  border: 1px solid var(--kiwi-gray-200);
}

.modal-apply-email {
  font-size: 0.9375rem;
  color: var(--kiwi-purple);
}

.modal-apply-note {
  font-size: 0.875rem;
  color: var(--kiwi-gray-600);
  font-style: italic;
}

.modal-cta {
  display: inline-block;
  margin-top: 0.25rem;
}

@media (max-width: 900px) {
  .doc-cards {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 480px) {
  .doc-cards {
    grid-template-columns: 1fr;
  }
}

.ffg-logo-link {
  display: inline-block;
  margin-bottom: 1rem;
}

.ffg-logo {
  max-height: 60px;
  width: auto;
  object-fit: contain;
  vertical-align: middle;
}

/* Contact Styles */
.contact-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2rem;
}

.contact-info h3 {
  color: var(--kiwi-purple);
  margin-bottom: 1.5rem;
}

.contact-details p {
  margin-bottom: 0.5rem;
}

.contact-link {
  color: var(--kiwi-purple);
  text-decoration: none;
}

.contact-link:hover {
  text-decoration: underline;
}

.funding-notice h3 {
  color: var(--kiwi-green);
  margin-bottom: 1rem;
}

/* Back to Top Button */
.back-to-top {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  width: 50px;
  height: 50px;
  background: var(--kiwi-purple);
  color: var(--kiwi-white);
  border: none;
  border-radius: 50%;
  font-size: 1.5rem;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(102, 45, 145, 0.3);
  transition: all 0.3s ease;
  opacity: 0;
  visibility: hidden;
  transform: translateY(20px);
  z-index: 1000;
}

.back-to-top.visible {
  opacity: 1;
  visibility: visible;
  transform: translateY(0);
}

.back-to-top:hover {
  background: var(--kiwi-orange);
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(102, 45, 145, 0.4);
}

.back-to-top:active {
  transform: translateY(0);
}

/* Footer Styles */
.footer {
  background: var(--kiwi-dark);
  color: var(--kiwi-white);
  padding: 2rem 0;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.footer-logo-img {
  height: 30px;
  width: auto;
  filter: brightness(0) invert(1);
}

.footer-logo-text {
  font-size: 1.25rem;
  font-weight: 700;
}

.footer-info {
  text-align: right;
}

.footer-info {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 0.5rem;
  text-align: right;
}

.footer-info p {
  margin-bottom: 0;
  font-size: 0.875rem;
  color: var(--kiwi-gray-300);
}

.footer-ffg-logo-link {
  display: inline-block;
  margin-top: 0.5rem;
}

.footer-ffg-logo {
  max-height: 36px;
  width: auto;
  object-fit: contain;
  filter: brightness(0) invert(1);
  opacity: 0.9;
}

/* Responsive Design */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-icon {
    width: 200px;
  }
  
  .tab-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .contact-content {
    grid-template-columns: 1fr;
  }
  
  .footer-content {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
  
  .footer-info {
    text-align: center;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 6rem 0 2rem;
  }
  
  .hero-buttons {
    flex-direction: column;
  }
  
  .project-details {
    grid-template-columns: 1fr;
  }
  
  .partners-grid {
    grid-template-columns: 1fr;
  }
}
</style>
