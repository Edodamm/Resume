<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Eduardo Damm – Intelligence Officer</title>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
    background: #f9f9f7;
    color: #1a1a18;
    font-size: 15px;
    line-height: 1.6;
  }

  a { color: inherit; text-decoration: none; }

  /* ── Layout ── */
  .page {
    max-width: 780px;
    margin: 0 auto;
    padding: 48px 32px 80px;
  }

  /* ── Header ── */
  header {
    display: flex;
    align-items: flex-start;
    gap: 28px;
    padding-bottom: 36px;
    border-bottom: 1px solid #e4e4e0;
    margin-bottom: 40px;
  }

  .avatar {
    width: 68px;
    height: 68px;
    border-radius: 50%;
    background: #2c2c2a;
    color: #f9f9f7;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    font-weight: 500;
    letter-spacing: 1px;
    flex-shrink: 0;
  }

  .header-text h1 {
    font-size: 26px;
    font-weight: 600;
    letter-spacing: -0.5px;
    color: #1a1a18;
    line-height: 1.2;
  }

  .header-text .role {
    font-size: 14px;
    color: #5f5e5a;
    margin-top: 4px;
    font-weight: 400;
  }

  .header-text .summary {
    font-size: 14px;
    color: #444441;
    margin-top: 10px;
    max-width: 560px;
    line-height: 1.65;
  }

  .contact-row {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
    margin-top: 14px;
  }

  .contact-row a {
    font-size: 13px;
    color: #5f5e5a;
    display: flex;
    align-items: center;
    gap: 5px;
    transition: color 0.15s;
  }

  .contact-row a:hover { color: #1a1a18; }

  .contact-row .dot {
    width: 3px;
    height: 3px;
    background: #b4b2a9;
    border-radius: 50%;
    display: inline-block;
    margin: 0 2px;
  }

  /* ── Skills strip ── */
  .skills-strip {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-bottom: 40px;
  }

  .tag {
    font-size: 12px;
    font-weight: 500;
    color: #444441;
    background: #f1efe8;
    border: 0.5px solid #d3d1c7;
    border-radius: 4px;
    padding: 4px 10px;
    white-space: nowrap;
  }

  /* ── Section ── */
  section { margin-bottom: 44px; }

  .section-label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 1.2px;
    text-transform: uppercase;
    color: #888780;
    margin-bottom: 20px;
  }

  /* ── Experience ── */
  .job { display: flex; gap: 20px; margin-bottom: 28px; }
  .job:last-child { margin-bottom: 0; }

  .job-timeline {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-top: 4px;
    flex-shrink: 0;
    width: 16px;
  }

  .dot-outer {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    border: 1.5px solid #888780;
    background: #f9f9f7;
    flex-shrink: 0;
  }

  .line {
    width: 1px;
    flex: 1;
    background: #e4e4e0;
    margin-top: 4px;
  }

  .job:last-child .line { display: none; }

  .job-body { flex: 1; padding-bottom: 4px; }

  .job-header {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 4px;
    margin-bottom: 2px;
  }

  .job-title {
    font-size: 14px;
    font-weight: 600;
    color: #1a1a18;
  }

  .job-org {
    font-size: 13px;
    color: #5f5e5a;
    font-weight: 400;
  }

  .job-org a:hover { color: #1a1a18; text-decoration: underline; }

  .job-dates {
    font-size: 12px;
    color: #888780;
    white-space: nowrap;
  }

  .job-bullets {
    margin-top: 6px;
    padding-left: 0;
    list-style: none;
  }

  .job-bullets li {
    font-size: 13.5px;
    color: #444441;
    line-height: 1.6;
    padding-left: 14px;
    position: relative;
    margin-bottom: 3px;
  }

  .job-bullets li::before {
    content: '–';
    position: absolute;
    left: 0;
    color: #b4b2a9;
  }

  /* ── Education ── */
  .edu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 12px;
  }

  .edu-card {
    background: #fff;
    border: 0.5px solid #e4e4e0;
    border-radius: 8px;
    padding: 14px 16px;
  }

  .edu-degree {
    font-size: 13px;
    font-weight: 600;
    color: #1a1a18;
  }

  .edu-field {
    font-size: 12.5px;
    color: #5f5e5a;
    margin-top: 2px;
  }

  .edu-school {
    font-size: 12px;
    color: #888780;
    margin-top: 6px;
  }

  .edu-school a:hover { color: #444441; text-decoration: underline; }

  /* ── Certifications ── */
  .cert-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 8px;
  }

  .cert-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 13px;
    color: #444441;
    background: #fff;
    border: 0.5px solid #e4e4e0;
    border-radius: 6px;
    padding: 10px 14px;
  }

  .cert-icon {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #888780;
    flex-shrink: 0;
    margin-top: 5px;
  }

  .cert-issuer {
    font-size: 11.5px;
    color: #888780;
    margin-top: 1px;
  }

  /* ── Languages ── */
  .lang-row {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
  }

  .lang-tag {
    font-size: 13px;
    font-weight: 500;
    color: #2c2c2a;
    background: #fff;
    border: 0.5px solid #e4e4e0;
    border-radius: 6px;
    padding: 6px 14px;
  }

  /* ── Footer ── */
  footer {
    margin-top: 60px;
    padding-top: 24px;
    border-top: 1px solid #e4e4e0;
    font-size: 12px;
    color: #b4b2a9;
    text-align: center;
  }
</style>
</head>
<body>
<div class="page">

  <!-- Header -->
  <header>
    <div class="avatar">ED</div>
    <div class="header-text">
      <h1>Eduardo Damm</h1>
      <p class="role">Intelligence Officer &amp; Analyst</p>
      <p class="summary">
        Multilingual intelligence professional with expertise spanning cybersecurity, geopolitical risk, and regulatory intelligence. Experienced in open-source analysis, predictive reporting, and stakeholder briefings across government and private sector environments.
      </p>
      <div class="contact-row">
        <a href="mailto:damm@mail.com">damm@mail.com</a>
        <span class="dot"></span>
        <a href="https://github.com/Edodamm/Resume" target="_blank">GitHub</a>
      </div>
    </div>
  </header>

  <!-- Skills -->
  <div class="skills-strip">
    <span class="tag">Python</span>
    <span class="tag">R</span>
    <span class="tag">Linux CLI</span>
    <span class="tag">Power BI</span>
    <span class="tag">Tableau</span>
    <span class="tag">Gephi</span>
    <span class="tag">GIS</span>
    <span class="tag">OSINT</span>
    <span class="tag">Data visualisation</span>
    <span class="tag">Geopolitical risk</span>
    <span class="tag">Regulatory intelligence</span>
    <span class="tag">Safeguarding &amp; compliance</span>
  </div>

  <!-- Experience -->
  <section>
    <p class="section-label">Experience</p>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Officer – Remote Operations</span>
            <span class="job-org"> · <a href="https://www.gov.uk/government/organisations/home-office" target="_blank">UK Home Office</a></span>
          </div>
          <span class="job-dates">May 2026 – Present</span>
        </div>
        <ul class="job-bullets">
          <li>Assess cases for individuals entering the UK by clandestine means, conducting mandatory identity, biometric, and security checks against UK Home Office and policing systems.</li>
          <li>Create and manage case records, analyse domestic and international connections, and initiate safeguarding, detention, and removal referrals in line with statutory requirements.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Intelligence Officer</span>
            <span class="job-org"> · <a href="https://nmc.org.uk" target="_blank">NMC</a></span>
          </div>
          <span class="job-dates">Mar 2025 – Apr 2026</span>
        </div>
        <ul class="job-bullets">
          <li>Managed and assessed intelligence relating to regulatory concerns, safeguarding, whistleblowing, and risk — ensuring timely and proportionate sharing.</li>
          <li>Developed intelligence products and provided guidance on data use, aligned with legislation and operational objectives.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Intelligence Manager</span>
            <span class="job-org"> · <a href="https://global-weekly.com" target="_blank">Global Weekly</a></span>
          </div>
          <span class="job-dates">May 2024 – Oct 2024</span>
        </div>
        <ul class="job-bullets">
          <li>Provided intelligence support for ongoing analysis, reports, and investigations.</li>
          <li>Established standards for reporting, risk analysis, and intelligence frameworks.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Editorial Contributor</span>
            <span class="job-org"> · <a href="https://www.latinnews.com/" target="_blank">Latin News</a></span>
          </div>
          <span class="job-dates">May 2024 – Oct 2024</span>
        </div>
        <ul class="job-bullets">
          <li>Monitored and reported on political, economic, and security developments across Latin America.</li>
          <li>Produced analytical reports supporting editorial decision-making and regional coverage.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Intelligence Consultant</span>
            <span class="job-org"> · <a href="https://londonpolitica.com" target="_blank">London Politica</a></span>
          </div>
          <span class="job-dates">Dec 2023 – Present</span>
        </div>
        <ul class="job-bullets">
          <li>Crafted predictive intelligence reports for strategic decision-making, drawing on diverse open and closed data sources.</li>
          <li>Delivered targeted briefings on evolving international threat landscapes.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Intelligence Analyst</span>
            <span class="job-org"> · <a href="https://www.sibylline.co.uk" target="_blank">Sibylline</a></span>
          </div>
          <span class="job-dates">Sep 2022 – Dec 2023</span>
        </div>
        <ul class="job-bullets">
          <li>Produced detailed predictive intelligence reports utilising diverse data sources for strategic clients.</li>
          <li>Delivered targeted briefings on threat landscapes across Latin America.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Consular Agent</span>
            <span class="job-org"> · <a href="https://www.gov.br/mre/pt-br/consulado-londres/consulate-general" target="_blank">Consulate General of Brazil, London</a></span>
          </div>
          <span class="job-dates">Dec 2021 – Sep 2022</span>
        </div>
        <ul class="job-bullets">
          <li>Provided technical and administrative support across Military, Electoral, and Visa sectors; managed document processing and liaised with British entities.</li>
          <li>Conducted due diligence on individuals and companies, and facilitated information sharing with British institutions.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Intelligence Analyst</span>
            <span class="job-org"> · <a href="https://www.ueni.com" target="_blank">UENI</a></span>
          </div>
          <span class="job-dates">Aug 2019 – Oct 2020</span>
        </div>
        <ul class="job-bullets">
          <li>Led operations across Latin America, conducting market research and identifying business opportunities.</li>
          <li>Managed a cross-functional team of content specialists, customer service agents, and quality supervisors overseeing operations in Brazil.</li>
          <li>Assisted in e-commerce expansion and prepared strategic reports.</li>
        </ul>
      </div>
    </div>

    <div class="job">
      <div class="job-timeline"><div class="dot-outer"></div><div class="line"></div></div>
      <div class="job-body">
        <div class="job-header">
          <div>
            <span class="job-title">Intelligence Analyst</span>
            <span class="job-org"> · <a href="https://www.intelligencefusion.co.uk" target="_blank">Intelligence Fusion</a></span>
          </div>
          <span class="job-dates">Feb 2019 – Sep 2019</span>
        </div>
        <ul class="job-bullets">
          <li>Monitored and analysed political events in Latin America, producing regional awareness reports.</li>
          <li>Specialised in fact-checking and analysis of Brazilian affairs.</li>
        </ul>
      </div>
    </div>

  </section>

  <!-- Education -->
  <section>
    <p class="section-label">Education</p>
    <div class="edu-grid">
      <div class="edu-card">
        <p class="edu-degree">MA</p>
        <p class="edu-field">Global Security</p>
        <p class="edu-school"><a href="https://www.kcl.ac.uk/" target="_blank">King's College London</a></p>
      </div>
      <div class="edu-card">
        <p class="edu-degree">BA</p>
        <p class="edu-field">International Relations</p>
        <p class="edu-school"><a href="https://estacio.br/" target="_blank">Universidade Estácio de Sá</a></p>
      </div>
      <div class="edu-card">
        <p class="edu-degree">BSc</p>
        <p class="edu-field">Cyber Defence</p>
        <p class="edu-school"><a href="https://estacio.br/" target="_blank">Universidade Estácio de Sá</a></p>
      </div>
    </div>
  </section>

  <!-- Certifications -->
  <section>
    <p class="section-label">Certifications</p>
    <div class="cert-list">
      <div class="cert-item"><div class="cert-icon"></div><div><div>Google Advanced Data Analytics</div><div class="cert-issuer">Google</div></div></div>
      <div class="cert-item"><div class="cert-icon"></div><div><div>Google Cybersecurity</div><div class="cert-issuer">Google</div></div></div>
      <div class="cert-item"><div class="cert-icon"></div><div><div>International Security Management</div><div class="cert-issuer">Erasmus University Rotterdam</div></div></div>
      <div class="cert-item"><div class="cert-icon"></div><div><div>Intelligence &amp; Counterintelligence</div><div class="cert-issuer">ABEIC</div></div></div>
      <div class="cert-item"><div class="cert-icon"></div><div><div>International Relations Analyst</div><div class="cert-issuer">ESRI – School of International Relations</div></div></div>
      <div class="cert-item"><div class="cert-icon"></div><div><div>Open Source Intelligence (OSINT)</div><div class="cert-issuer">The Basel Institute on Governance</div></div></div>
    </div>
  </section>

  <!-- Languages -->
  <section>
    <p class="section-label">Languages</p>
    <div class="lang-row">
      <span class="lang-tag">English</span>
      <span class="lang-tag">Portuguese</span>
      <span class="lang-tag">Spanish</span>
      <span class="lang-tag">French</span>
    </div>
  </section>

  <footer>
    Eduardo Damm · <a href="mailto:damm@mail.com">damm@mail.com</a>
  </footer>

</div>
</body>
</html>
