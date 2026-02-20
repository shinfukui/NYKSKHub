<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>New York Kenshinkai Hub</title>
<link href="https://fonts.googleapis.com/css2?family=Shippori+Mincho:wght@400;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1a1410;
    --paper: #f5f0e8;
    --red: #c0392b;
    --red-dark: #922b21;
    --gold: #00a0df; /* Charles Schwab light blue */
    --gold-light: #e6f7ff; /* Light blue tint */
    --gray: #7a7060;
    --gray-light: #e8e2d6;
    --white: #fdfaf5;
    --shadow: 0 4px 24px rgba(0,160,223,0.12);
    --shadow-lg: 0 12px 48px rgba(0,160,223,0.18);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  /* Hide GitHub Pages default header */
  body > h1:first-child,
  body > header:first-child,
  #header,
  .page-header,
  body > h1:first-of-type {
    display: none !important;
    visibility: hidden !important;
    height: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--paper);
    color: var(--ink);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Background texture */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%231a1410' fill-opacity='0.025'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
  }

  /* HEADER */
  header {
    position: relative;
    background: #00a0df; /* Schwab light blue */
    color: var(--white);
    padding: 0;
    overflow: hidden;
    z-index: 10;
  }

  .header-accent {
    position: absolute;
    top: 0; left: 0;
    width: 6px;
    height: 100%;
    background: var(--red);
  }

  .header-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20px 40px 20px 52px;
    flex-wrap: wrap;
    gap: 12px;
  }

  .dojo-brand {
    display: flex;
    align-items: center;
    gap: 18px;
  }

  .dojo-mon {
    width: 52px;
    height: 52px;
    position: relative;
    flex-shrink: 0;
    background: var(--gold); /* Light blue background */
    border-radius: 50%; /* Make it circular */
    padding: 4px;
  }

  .dojo-mon svg { width: 100%; height: 100%; }

  .dojo-title h1 {
    font-family: 'Shippori Mincho', serif;
    font-size: 22px;
    font-weight: 700;
    letter-spacing: 0.04em;
    color: var(--paper);
    line-height: 1.1;
  }

  .dojo-title p {
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    margin-top: 2px;
  }

  .header-actions {
    display: flex;
    gap: 10px;
    align-items: center;
    flex-wrap: wrap;
  }

  /* ROLE SWITCHER */
  .role-badge {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 100px;
    padding: 6px 14px 6px 8px;
    font-size: 12px;
    color: var(--paper);
    cursor: pointer;
    transition: all 0.2s;
  }
  .role-badge:hover { background: rgba(255,255,255,0.14); }
  .role-dot { width: 8px; height: 8px; border-radius: 50%; background: var(--gold); }
  .role-dot.admin { background: var(--red); }

  .btn-primary {
    background: var(--red);
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 6px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    letter-spacing: 0.02em;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    gap: 7px;
  }
  .btn-primary:hover { background: var(--red-dark); transform: translateY(-1px); box-shadow: 0 4px 12px rgba(192,57,43,0.4); }

  /* MAIN */
  main {
    position: relative;
    z-index: 1;
    max-width: 1400px;
    margin: 0 auto;
    padding: 32px 24px 60px;
  }

  /* TWO-COLUMN LAYOUT */
  .main-content-wrapper {
    display: grid;
    grid-template-columns: 3fr 1fr;
    gap: 24px;
    align-items: start;
  }

  .main-content {
    min-width: 0; /* Prevents grid blowout */
  }

  .sidebar {
    position: sticky;
    top: 24px;
    max-height: calc(100vh - 48px);
    overflow-y: auto;
  }

  /* FILTERS & SEARCH */
  .controls {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 28px;
    flex-wrap: wrap;
  }

  .search-box {
    flex: 1;
    min-width: 200px;
    position: relative;
  }

  .search-box input {
    width: 100%;
    padding: 10px 16px 10px 40px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    color: var(--ink);
    outline: none;
    transition: border-color 0.2s;
  }
  .search-box input:focus { border-color: var(--red); }
  .search-icon {
    position: absolute;
    left: 13px;
    top: 50%;
    transform: translateY(-50%);
    color: var(--gray);
    font-size: 15px;
  }

  .filter-tabs {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .filter-tab {
    padding: 8px 14px;
    border-radius: 100px;
    border: 1.5px solid var(--gray-light);
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 500;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.18s;
    letter-spacing: 0.02em;
    display: flex;
    align-items: center;
    gap: 5px;
  }
  .filter-tab:hover { border-color: var(--ink); color: var(--ink); }
  .filter-tab.active { background: var(--ink); border-color: var(--ink); color: var(--paper); }
  .filter-tab .tab-dot { width: 7px; height: 7px; border-radius: 50%; }

  /* VIEW TOGGLE */
  .view-toggle {
    display: flex;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    overflow: hidden;
    background: var(--white);
  }
  .view-btn {
    padding: 9px 13px;
    border: none;
    background: transparent;
    cursor: pointer;
    color: var(--gray);
    font-size: 15px;
    transition: all 0.18s;
    border-right: 1.5px solid var(--gray-light);
  }
  .view-btn:last-child { border-right: none; }
  .view-btn.active { background: var(--ink); color: var(--paper); }
  .view-btn:hover:not(.active) { background: var(--gray-light); }

  /* SECTION HEADER */
  .section-header {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 18px;
  }
  .section-title {
    font-family: 'Shippori Mincho', serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray);
  }
  .section-line {
    flex: 1;
    height: 1px;
    background: var(--gray-light);
  }
  .event-count {
    font-size: 12px;
    color: var(--gray);
  }

  /* EVENT GRID */
  .events-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 18px;
    animation: fadeUp 0.4s ease both;
  }

  .events-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
    animation: fadeUp 0.4s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* EVENT CARD */
  .event-card {
    background: var(--white);
    border-radius: 12px;
    border: 1.5px solid var(--gray-light);
    overflow: hidden;
    transition: all 0.22s;
    cursor: pointer;
    position: relative;
    display: flex;
    flex-direction: column;
  }
  .event-card:hover {
    border-color: var(--ink);
    box-shadow: var(--shadow-lg);
    transform: translateY(-3px);
  }

  .card-stripe {
    height: 4px;
    width: 100%;
    flex-shrink: 0;
  }

  .card-body {
    padding: 18px 20px;
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  .card-meta {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 10px;
  }

  .event-type-badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    padding: 3px 10px;
    border-radius: 100px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .card-date-chip {
    display: flex;
    flex-direction: column;
    align-items: center;
    background: var(--ink);
    color: var(--paper);
    border-radius: 8px;
    padding: 6px 10px;
    min-width: 44px;
    text-align: center;
  }
  .chip-month { font-size: 9px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--gold); }
  .chip-day { font-family: 'Shippori Mincho', serif; font-size: 22px; font-weight: 700; line-height: 1; }

  .card-title {
    font-family: 'Shippori Mincho', serif;
    font-size: 17px;
    font-weight: 700;
    color: var(--ink);
    line-height: 1.3;
    margin-bottom: 6px;
  }

  .card-desc {
    font-size: 13px;
    color: var(--gray);
    line-height: 1.55;
    margin-bottom: 14px;
    flex: 1;
  }

  .card-details {
    display: flex;
    flex-direction: column;
    gap: 5px;
    margin-bottom: 14px;
    padding: 12px;
    background: rgba(26,20,16,0.03);
    border-radius: 8px;
  }

  .detail-row {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    color: var(--gray);
  }
  .detail-icon { font-size: 13px; width: 16px; text-align: center; }
  .detail-val { color: var(--ink); font-weight: 500; }

  .card-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 8px;
  }

  .participants-row {
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .avatar-stack {
    display: flex;
  }
  .avatar {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    border: 2px solid var(--white);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 9px;
    font-weight: 700;
    color: white;
    margin-left: -6px;
    flex-shrink: 0;
  }
  .avatar:first-child { margin-left: 0; }
  .avatar-count {
    font-size: 11px;
    color: var(--gray);
    margin-left: 4px;
  }

  .doc-pills {
    display: flex;
    gap: 5px;
    flex-wrap: wrap;
  }

  .doc-pill {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 3px 8px;
    border-radius: 4px;
    background: var(--gold-light);
    color: var(--ink);
    font-size: 10px;
    font-weight: 500;
    text-decoration: none;
    transition: background 0.15s;
    cursor: pointer;
  }
  .doc-pill:hover { background: var(--gold); }

  .register-btn {
    padding: 7px 14px;
    border-radius: 6px;
    border: 1.5px solid var(--red);
    background: transparent;
    color: var(--red);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.18s;
    letter-spacing: 0.02em;
  }
  .register-btn:hover { background: var(--red); color: white; }
  .register-btn.registered { background: var(--red); color: white; border-color: var(--red); }
  .register-btn.registered:hover { background: var(--red-dark); border-color: var(--red-dark); }

  /* LIST VIEW CARD */
  .event-card.list-mode {
    flex-direction: row;
    align-items: stretch;
  }
  .event-card.list-mode .card-stripe { width: 5px; height: auto; flex-shrink: 0; }
  .event-card.list-mode .card-body {
    flex-direction: row;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
    padding: 14px 20px;
  }
  .event-card.list-mode .card-date-chip { min-width: 50px; }
  .event-card.list-mode .list-main { flex: 1; min-width: 180px; }
  .event-card.list-mode .list-main .card-title { font-size: 15px; margin-bottom: 2px; }
  .event-card.list-mode .list-main .card-desc { font-size: 12px; margin-bottom: 0; }
  .event-card.list-mode .card-details {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 8px 16px;
    background: transparent;
    padding: 0;
    margin-bottom: 0;
    min-width: 220px;
  }
  .event-card.list-mode .card-footer { flex-shrink: 0; }

  /* TYPE COLORS */
  .type-manhattan { color: #2d6a4f; background: #d8f3dc; }
  .stripe-manhattan { background: #2d6a4f; }

  .type-njkids { color: #c87a07; background: #fef5e7; }
  .stripe-njkids { background: #f39c12; }

  .type-tournament { color: #922b21; background: #fadbd8; }
  .stripe-tournament { background: #922b21; }

  .type-seminar { color: #1a5276; background: #d6eaf8; }
  .stripe-seminar { background: #1a5276; }

  .type-joint { color: #7d6608; background: #fef9e7; }
  .stripe-joint { background: #c9a84c; }

  .type-exam { color: #4a235a; background: #e8daef; }
  .stripe-exam { background: #8e44ad; }

  .type-other { color: #4a235a; background: #e8daef; }
  .stripe-other { background: #7d3c98; }

  /* AVATAR COLORS */
  .av1 { background: #c0392b; }
  .av2 { background: #2980b9; }
  .av3 { background: #27ae60; }
  .av4 { background: #8e44ad; }
  .av5 { background: #e67e22; }
  .av6 { background: #16a085; }

  /* MODAL */
  .modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(26,20,16,0.55);
    z-index: 1000;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    backdrop-filter: blur(3px);
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.25s;
  }
  .modal-overlay.open { opacity: 1; pointer-events: all; }

  .modal {
    background: var(--white);
    border-radius: 16px;
    max-width: 580px;
    width: 100%;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: var(--shadow-lg);
    transform: translateY(20px) scale(0.97);
    transition: transform 0.25s ease;
  }
  .modal-overlay.open .modal { transform: translateY(0) scale(1); }

  .modal-header {
    padding: 24px 28px 0;
    position: relative;
  }

  .modal-close {
    position: absolute;
    top: 18px; right: 20px;
    background: var(--gray-light);
    border: none;
    border-radius: 50%;
    width: 30px; height: 30px;
    font-size: 16px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--ink);
    transition: background 0.15s;
  }
  .modal-close:hover { background: var(--red); color: white; }

  .modal h2 {
    font-family: 'Shippori Mincho', serif;
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 6px;
    padding-right: 40px;
  }

  .modal-body {
    padding: 20px 28px 28px;
  }

  .form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  .form-col-full { grid-column: 1 / -1; }

  .form-group label {
    display: block;
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    margin-bottom: 5px;
  }

  .form-group input,
  .form-group select,
  .form-group textarea {
    width: 100%;
    padding: 10px 13px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    background: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--ink);
    outline: none;
    transition: border-color 0.2s;
    appearance: none;
  }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color: var(--red); }

  .form-group textarea { min-height: 80px; resize: vertical; }

  .form-group select {
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%237a7060' d='M6 8L1 3h10z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    padding-right: 32px;
  }

  .doc-input-row {
    display: flex;
    gap: 8px;
    margin-top: 6px;
  }
  .doc-input-row input { flex: 1; }
  .doc-input-row button {
    padding: 10px 14px;
    border: 1.5px dashed var(--gray-light);
    border-radius: 8px;
    background: transparent;
    color: var(--gray);
    font-size: 18px;
    cursor: pointer;
    transition: all 0.18s;
    white-space: nowrap;
  }
  .doc-input-row button:hover { border-color: var(--red); color: var(--red); background: #fff5f5; }

  .doc-list-preview { display: flex; gap: 6px; flex-wrap: wrap; margin-top: 8px; }
  .doc-rm { font-size: 10px; margin-left: 4px; cursor: pointer; opacity: 0.6; }
  .doc-rm:hover { opacity: 1; color: var(--red); }

  .form-actions {
    display: flex;
    justify-content: flex-end;
    gap: 10px;
    margin-top: 20px;
  }

  .btn-ghost {
    padding: 10px 18px;
    border: 1.5px solid var(--gray-light);
    border-radius: 6px;
    background: transparent;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.18s;
  }
  .btn-ghost:hover { border-color: var(--ink); color: var(--ink); }

  /* TOAST */
  .toast {
    position: fixed;
    bottom: 28px;
    right: 28px;
    background: var(--ink);
    color: var(--paper);
    padding: 12px 20px;
    border-radius: 10px;
    font-size: 13px;
    font-weight: 500;
    box-shadow: var(--shadow-lg);
    z-index: 9999;
    transform: translateY(20px);
    opacity: 0;
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    gap: 8px;
    border-left: 4px solid var(--red);
  }
  .toast.show { transform: translateY(0); opacity: 1; }

  /* EMPTY STATE */
  .empty-state {
    text-align: center;
    padding: 60px 20px;
    color: var(--gray);
  }
  .empty-state .empty-icon { font-size: 48px; margin-bottom: 14px; opacity: 0.5; }
  .empty-state h3 { font-family: 'Shippori Mincho', serif; font-size: 18px; color: var(--ink); margin-bottom: 6px; }
  .empty-state p { font-size: 13px; }

  /* UPCOMING STRIP */
  .upcoming-strip {
    background: var(--ink);
    border-radius: 12px;
    padding: 16px 24px;
    margin-bottom: 28px;
    display: flex;
    gap: 0;
    overflow-x: auto;
    scrollbar-width: none;
    position: relative;
  }
  .upcoming-strip::-webkit-scrollbar { display: none; }
  .upcoming-strip::before {
    content: 'UPCOMING';
    position: absolute;
    top: 14px; left: 24px;
    font-size: 9px;
    letter-spacing: 0.2em;
    color: var(--gold);
    font-weight: 600;
  }

  .up-item {
    flex-shrink: 0;
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 22px 20px 8px;
    border-right: 1px solid rgba(255,255,255,0.08);
    cursor: pointer;
    transition: background 0.15s;
    border-radius: 8px;
    min-width: 180px;
  }
  .up-item:last-child { border-right: none; }
  .up-item:hover { background: rgba(255,255,255,0.06); }

  .up-date {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 36px;
  }
  .up-month { font-size: 9px; letter-spacing: 0.1em; color: var(--gold); text-transform: uppercase; }
  .up-day { font-family: 'Shippori Mincho', serif; font-size: 24px; font-weight: 800; color: var(--paper); line-height: 1; }

  .up-info { flex: 1; }
  .up-name { font-size: 12px; font-weight: 600; color: var(--paper); line-height: 1.3; }
  .up-type { font-size: 10px; color: var(--gray); margin-top: 2px; text-transform: uppercase; letter-spacing: 0.06em; }

  /* ── LOGIN SCREEN ───────────────────────────────────────────────────────── */
  .login-overlay {
    position: fixed;
    inset: 0;
    background: #00a0df; /* Schwab light blue */
    z-index: 9000;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 24px;
    transition: opacity 0.5s ease;
  }
  .login-overlay.hidden { opacity: 0; pointer-events: none; }

  .login-box {
    background: var(--white);
    border-radius: 20px;
    padding: 44px 40px 36px;
    max-width: 380px;
    width: 100%;
    text-align: center;
    box-shadow: 0 32px 80px rgba(0,0,0,0.4);
    position: relative;
    overflow: hidden;
  }
  .login-box::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 5px;
    background: var(--red);
  }

  .login-mon {
    width: 64px; height: 64px;
    margin: 0 auto 20px;
    background: var(--gold); /* Light blue background */
    border-radius: 50%; /* Make it circular */
    padding: 6px;
  }
  .login-mon svg { width: 100%; height: 100%; }

  .login-box h2 {
    font-family: 'Shippori Mincho', serif;
    font-size: 24px;
    font-weight: 800;
    color: var(--ink);
    margin-bottom: 4px;
  }
  .login-box p {
    font-size: 13px;
    color: var(--gray);
    margin-bottom: 28px;
    line-height: 1.5;
  }

  .login-name-row {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-bottom: 16px;
    text-align: left;
  }
  .login-name-row label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray);
    display: block;
    margin-bottom: 5px;
  }
  .login-name-row input {
    width: 100%;
    padding: 11px 14px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    font-family: 'DM Sans', sans-serif;
    font-size: 14px;
    color: var(--ink);
    background: var(--paper);
    outline: none;
    transition: border-color 0.2s;
  }
  .login-name-row input:focus { border-color: var(--red); }

  .passcode-dots {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin: 8px 0 20px;
  }
  .passcode-dot {
    width: 14px; height: 14px;
    border-radius: 50%;
    border: 2px solid var(--gray-light);
    background: transparent;
    transition: all 0.2s;
  }
  .passcode-dot.filled { background: var(--red); border-color: var(--red); }
  .passcode-dot.error { background: #e74c3c; border-color: #e74c3c; animation: shake 0.4s ease; }

  @keyframes shake {
    0%,100% { transform: translateX(0); }
    20%,60% { transform: translateX(-4px); }
    40%,80% { transform: translateX(4px); }
  }

  .pin-pad {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin-bottom: 16px;
  }
  .pin-btn {
    aspect-ratio: 1;
    border-radius: 12px;
    border: 1.5px solid var(--gold);
    background: var(--gold); /* Light blue background */
    font-family: 'Shippori Mincho', serif;
    font-size: 20px;
    font-weight: 700;
    color: var(--white); /* White text */
    cursor: pointer;
    transition: all 0.15s;
    display: flex; align-items: center; justify-content: center;
  }
  .pin-btn:hover { background: #0088c7; color: var(--white); border-color: #0088c7; transform: scale(1.04); } /* Darker blue on hover */
  .pin-btn:active { transform: scale(0.96); }
  .pin-btn.del { font-size: 16px; background: var(--paper); color: var(--gray); border-color: var(--gray-light); }
  .pin-btn.del:hover { background: #fadbd8; color: var(--red); border-color: var(--red); }

  .login-hint {
    font-size: 11px;
    color: var(--gray);
    margin-top: 10px;
  }
  .login-hint strong { color: var(--ink); }

  .login-error {
    font-size: 12px;
    color: var(--red);
    min-height: 18px;
    margin-bottom: 8px;
  }

  /* ── TRUSTED MEMBER PANEL ────────────────────────────────────────────────── */
  .admin-panel-btn {
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 6px;
    padding: 8px 12px;
    color: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    cursor: pointer;
    transition: all 0.2s;
    display: flex; align-items: center; gap: 6px;
  }
  .admin-panel-btn:hover { background: rgba(255,255,255,0.14); }

  .members-panel {
    background: var(--white);
    border-radius: 12px;
    border: 1.5px solid var(--gray-light);
    margin-bottom: 24px;
    overflow: hidden;
    animation: fadeUp 0.3s ease both;
  }
  .members-panel-header {
    background: var(--ink);
    padding: 14px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .members-panel-header h3 {
    font-family: 'Shippori Mincho', serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--paper);
  }
  .members-panel-header span {
    font-size: 11px;
    color: var(--gold);
    letter-spacing: 0.08em;
  }

  .members-list {
    padding: 8px 0;
    max-height: 280px;
    overflow-y: auto;
  }

  .member-row {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 20px;
    transition: background 0.15s;
    cursor: default;
  }
  .member-row:hover { background: var(--paper); }

  .member-avatar {
    width: 34px; height: 34px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 12px;
    font-weight: 700;
    color: white;
    flex-shrink: 0;
  }

  .member-info { flex: 1; }
  .member-name { font-size: 13px; font-weight: 600; color: var(--ink); }
  .member-since { font-size: 11px; color: var(--gray); }

  .role-toggle {
    display: flex;
    border: 1.5px solid var(--gray-light);
    border-radius: 6px;
    overflow: hidden;
    flex-shrink: 0;
  }
  .role-opt {
    padding: 5px 10px;
    font-size: 11px;
    font-weight: 500;
    cursor: pointer;
    border: none;
    background: transparent;
    color: var(--gray);
    font-family: 'DM Sans', sans-serif;
    transition: all 0.15s;
    white-space: nowrap;
  }
  .role-opt.active-member { background: #d8f3dc; color: #1b4332; }
  .role-opt.active-trusted { background: var(--gold-light); color: #6e5205; }
  .role-opt.active-admin { background: #fadbd8; color: var(--red-dark); }

  .no-members {
    text-align: center;
    padding: 24px;
    font-size: 13px;
    color: var(--gray);
  }

  /* ── IMPROVED DOC ATTACHMENT ─────────────────────────────────────────────── */
  .doc-tabs {
    display: flex;
    gap: 0;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 8px;
  }
  .doc-tab-btn {
    flex: 1;
    padding: 8px;
    border: none;
    background: var(--paper);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 500;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.15s;
    border-right: 1.5px solid var(--gray-light);
  }
  .doc-tab-btn:last-child { border-right: none; }
  .doc-tab-btn.active { background: var(--ink); color: var(--paper); }

  .doc-attach-row {
    display: flex;
    gap: 8px;
    margin-bottom: 4px;
  }
  .doc-attach-row input { flex: 1; }

  .doc-pill-link {
    background: #d6eaf8;
    color: #1a3a5c;
  }
  .doc-pill-link:hover { background: #aed6f1; }
  .doc-pill-file {
    background: var(--gold-light);
    color: #6e5205;
  }
  .doc-pill-file:hover { background: var(--gold); }

  /* ── MESSAGE BOARD ────────────────────────────────────────────────────────── */
  .message-board {
    background: var(--white);
    border-radius: 12px;
    border: 1.5px solid var(--gray-light);
    margin-bottom: 24px;
    overflow: hidden;
    animation: fadeUp 0.3s ease both;
  }
  .message-board-header {
    background: var(--ink);
    padding: 14px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .message-board-header h3 {
    font-family: 'Shippori Mincho', serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--paper);
  }

  .message-form {
    padding: 16px 20px;
    border-bottom: 1.5px solid var(--gray-light);
    background: var(--paper);
  }
  .message-form textarea {
    width: 100%;
    padding: 10px 13px;
    border: 1.5px solid var(--gray-light);
    border-radius: 8px;
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--ink);
    min-height: 60px;
    resize: vertical;
    margin-bottom: 8px;
  }
  .message-form textarea:focus { border-color: var(--red); outline: none; }
  
  .message-form-actions {
    display: flex;
    gap: 8px;
    align-items: center;
    flex-wrap: wrap;
  }
  .message-form-actions input {
    flex: 1;
    min-width: 200px;
    padding: 8px 12px;
    border: 1.5px solid var(--gray-light);
    border-radius: 6px;
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
  }
  .message-form-actions input:focus { border-color: var(--red); outline: none; }

  .messages-list {
    padding: 8px 0;
    max-height: 500px;
    overflow-y: auto;
  }

  .message-item {
    padding: 14px 20px;
    border-bottom: 1px solid var(--gray-light);
    transition: background 0.15s;
  }
  .message-item:last-child { border-bottom: none; }
  .message-item:hover { background: var(--paper); }

  .message-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
  }
  .message-avatar {
    width: 32px; height: 32px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px;
    font-weight: 700;
    color: white;
    flex-shrink: 0;
  }
  .message-author {
    font-size: 13px;
    font-weight: 600;
    color: var(--ink);
  }
  .message-time {
    font-size: 11px;
    color: var(--gray);
    margin-left: auto;
  }
  .message-text {
    font-size: 13px;
    color: var(--ink);
    line-height: 1.5;
    margin-bottom: 8px;
    white-space: pre-wrap;
    word-wrap: break-word;
  }
  .message-link {
    display: inline-block;
    font-size: 12px;
    color: #1a5276;
    text-decoration: none;
    padding: 4px 10px;
    background: #d6eaf8;
    border-radius: 4px;
    margin-top: 4px;
    transition: background 0.15s;
  }
  .message-link:hover { background: #aed6f1; }
  .message-image {
    max-width: 100%;
    max-height: 300px;
    border-radius: 8px;
    margin-top: 8px;
    cursor: pointer;
  }
  .message-delete {
    font-size: 11px;
    color: var(--gray);
    cursor: pointer;
    padding: 2px 6px;
    border-radius: 3px;
    transition: all 0.15s;
    margin-left: 8px;
  }
  .message-delete:hover { background: #fadbd8; color: var(--red); }

  .no-messages {
    text-align: center;
    padding: 32px;
    color: var(--gray);
    font-size: 13px;
  }

  /* ── RESPONSIVE ──────────────────────────────────────────────────────────── */
  @media (max-width: 640px) {
    .header-inner { padding: 16px 20px 16px 30px; }
    main { padding: 20px 14px 40px; }
    .form-grid { grid-template-columns: 1fr; }
    .events-grid { grid-template-columns: 1fr; }
    .event-card.list-mode { flex-direction: column; }
    .event-card.list-mode .card-stripe { width: 100%; height: 4px; }
    .event-card.list-mode .card-body { flex-direction: column; align-items: flex-start; }
    
    /* Stack layout on mobile */
    .main-content-wrapper {
      grid-template-columns: 1fr;
      gap: 16px;
    }
    .sidebar {
      position: static;
      max-height: none;
    }
  }

  /* ── CALENDAR VIEW ─────────────────────────────────────────────────────── */
  .calendar-wrap {
    animation: fadeUp 0.35s ease both;
  }

  .cal-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
    gap: 12px;
  }

  .cal-month-label {
    font-family: 'Shippori Mincho', serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--ink);
    letter-spacing: 0.02em;
    flex: 1;
    text-align: center;
  }

  .cal-nav-btn {
    width: 36px; height: 36px;
    border-radius: 50%;
    border: 1.5px solid var(--gray-light);
    background: var(--white);
    color: var(--ink);
    font-size: 16px;
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.18s;
    flex-shrink: 0;
  }
  .cal-nav-btn:hover { background: var(--ink); color: var(--paper); border-color: var(--ink); }

  .cal-today-btn {
    padding: 7px 14px;
    border-radius: 6px;
    border: 1.5px solid var(--gray-light);
    background: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-size: 12px;
    font-weight: 500;
    color: var(--gray);
    cursor: pointer;
    transition: all 0.18s;
  }
  .cal-today-btn:hover { border-color: var(--ink); color: var(--ink); }

  .cal-grid {
    background: var(--white);
    border-radius: 14px;
    border: 1.5px solid var(--gray-light);
    overflow: hidden;
    box-shadow: var(--shadow);
  }

  .cal-dow-row {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    border-bottom: 1.5px solid var(--gray-light);
    background: var(--ink);
  }

  .cal-dow {
    text-align: center;
    padding: 10px 4px;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gold);
  }

  .cal-days {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
  }

  .cal-cell {
    min-height: 108px;
    border-right: 1px solid var(--gray-light);
    border-bottom: 1px solid var(--gray-light);
    padding: 8px 6px 6px;
    position: relative;
    transition: background 0.15s;
    vertical-align: top;
    cursor: default;
  }
  .cal-cell:nth-child(7n) { border-right: none; }
  .cal-cell.other-month { background: rgba(26,20,16,0.02); }
  .cal-cell.other-month .cal-day-num { color: var(--gray-light); }
  .cal-cell.today { background: #fff8f7; }
  .cal-cell.has-events { cursor: pointer; }
  .cal-cell.has-events:hover { background: #fdfaf5; }

  .cal-day-num {
    font-family: 'Shippori Mincho', serif;
    font-size: 14px;
    font-weight: 600;
    color: var(--gray);
    margin-bottom: 5px;
    display: flex;
    align-items: center;
    gap: 4px;
  }

  .today-pip {
    width: 20px; height: 20px;
    border-radius: 50%;
    background: var(--red);
    color: white;
    font-size: 11px;
    font-weight: 700;
    display: flex; align-items: center; justify-content: center;
    font-family: 'DM Sans', sans-serif;
  }

  .cal-event-pill {
    display: block;
    padding: 2px 6px;
    border-radius: 4px;
    font-size: 10px;
    font-weight: 500;
    margin-bottom: 3px;
    cursor: pointer;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    transition: opacity 0.15s, transform 0.15s;
    line-height: 1.6;
  }
  .cal-event-pill:hover { opacity: 0.85; transform: translateX(1px); }

  .cal-more {
    font-size: 10px;
    color: var(--gray);
    cursor: pointer;
    padding: 1px 4px;
    border-radius: 3px;
    transition: background 0.15s;
  }
  .cal-more:hover { background: var(--gray-light); color: var(--ink); }

  /* Day detail popover */
  .day-popover {
    position: fixed;
    z-index: 500;
    background: var(--white);
    border-radius: 12px;
    box-shadow: var(--shadow-lg);
    border: 1.5px solid var(--gray-light);
    width: 280px;
    padding: 16px;
    animation: fadeUp 0.2s ease both;
    pointer-events: all;
  }

  .popover-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }
  .popover-date {
    font-family: 'Shippori Mincho', serif;
    font-size: 15px;
    font-weight: 700;
  }
  .popover-close {
    background: none; border: none; font-size: 16px;
    cursor: pointer; color: var(--gray); padding: 2px 6px;
    border-radius: 4px; transition: background 0.15s;
  }
  .popover-close:hover { background: var(--gray-light); }

  .popover-event {
    display: flex;
    gap: 10px;
    padding: 9px 0;
    border-bottom: 1px solid var(--gray-light);
    cursor: pointer;
    transition: background 0.15s;
    border-radius: 6px;
    padding: 8px;
    margin: 0 -8px;
  }
  .popover-event:last-child { border-bottom: none; }
  .popover-event:hover { background: var(--paper); }

  .popover-dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    flex-shrink: 0;
    margin-top: 4px;
  }

  .popover-ev-title {
    font-size: 13px;
    font-weight: 600;
    color: var(--ink);
    line-height: 1.3;
  }
  .popover-ev-sub {
    font-size: 11px;
    color: var(--gray);
    margin-top: 2px;
  }

  /* Pill colors per type */
  .pill-class      { background: #d8f3dc; color: #1b4332; }
  .pill-tournament { background: #fadbd8; color: #7b241c; }
  .pill-seminar    { background: #d6eaf8; color: #1a3a5c; }
  .pill-joint      { background: #fef9e7; color: #6e5205; }
  .pill-other      { background: #e8daef; color: #4a235a; }

  /* PERMISSION NOTICE */
  .perm-notice {
    background: linear-gradient(135deg, #fef9e7, #fdebd0);
    border: 1px solid var(--gold-light);
    border-radius: 8px;
    padding: 10px 14px;
    font-size: 12px;
    color: #7d6608;
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
</style>
</head>
<body>

<!-- ══ LOGIN SCREEN ══════════════════════════════════════════════════════════ -->
<div class="login-overlay" id="loginOverlay">
  <div class="login-box">
    <div class="login-mon">
      <img src="Logo.jpg" alt="Kenshinkai Logo" style="width:100%;height:100%;object-fit:contain;;filter:invert(1);">
    </div>
    <h2>NY Kenshinkai</h2>
    <p>Enter your name and the dojo passcode<br>to access the event board.</p>

    <div class="login-name-row">
      <div>
        <label>Your Name</label>
        <input type="text" id="loginName" placeholder="e.g. Tanaka Kenji" maxlength="40" autocomplete="off">
      </div>
      <div>
        <label>Passcode</label>
        <div class="passcode-dots" id="passcodeDots">
          <div class="passcode-dot" id="dot0"></div>
          <div class="passcode-dot" id="dot1"></div>
          <div class="passcode-dot" id="dot2"></div>
          <div class="passcode-dot" id="dot3"></div>
        </div>
      </div>
    </div>

    <div class="login-error" id="loginError"></div>

    <div class="pin-pad">
      <button class="pin-btn" onclick="pinPress('1')">1</button>
      <button class="pin-btn" onclick="pinPress('2')">2</button>
      <button class="pin-btn" onclick="pinPress('3')">3</button>
      <button class="pin-btn" onclick="pinPress('4')">4</button>
      <button class="pin-btn" onclick="pinPress('5')">5</button>
      <button class="pin-btn" onclick="pinPress('6')">6</button>
      <button class="pin-btn" onclick="pinPress('7')">7</button>
      <button class="pin-btn" onclick="pinPress('8')">8</button>
      <button class="pin-btn" onclick="pinPress('9')">9</button>
      <button class="pin-btn" onclick="pinPress('0')" style="grid-column:2">0</button>
      <button class="pin-btn del" onclick="pinDelete()" style="grid-column:3">⌫</button>
    </div>

    <p class="login-hint">Enter your registered name and the passcode shared by your dojo admin.</p>
  </div>
</div>

<!-- HEADER -->
<header>
  <div class="header-accent"></div>
  <div class="header-inner">
    <div class="dojo-brand">
      <div class="dojo-mon">
        <img src="logo.jpg" alt="Kenshinkai Logo" style="width:100%;height:100%;object-fit:contain;background-color:#00a0df;border-radius:50%;padding:5px;"
      </div>
      <div class="dojo-title">
        <h1>New York Kenshinkai</h1>
        <p>Events & Schedule Hub</p>
      </div>
    </div>
    <div class="header-actions">
      <div class="role-badge" id="roleBadge" onclick="toggleRole()" title="Switch role">
        <div class="role-dot admin" id="roleDot"></div>
        <span id="roleLabel">Admin</span>
      </div>
      <button class="admin-panel-btn" id="membersBtn" onclick="toggleMembersPanel()" style="display:none">
        👥 Members
      </button>
      <button class="btn-primary" id="addEventBtn" onclick="openModal()">
        ＋ Add Event
      </button>
    </div>
  </div>
</header>

<!-- MAIN -->
<main>

  <!-- MEMBERS PANEL (admin only) - full width above everything -->
  <div class="members-panel" id="membersPanel" style="display:none">
    <div class="members-panel-header">
      <h3>🥋 Dojo Members</h3>
      <div style="display:flex;align-items:center;gap:10px">
        <span id="memberCountBadge"></span>
        <button class="btn-primary" id="addMemberBtn" onclick="openAddMemberModal()" style="display:none;padding:6px 12px;font-size:12px">+ Add Member</button>
      </div>
    </div>
    <div class="members-list" id="membersList"></div>
  </div>

  <!-- TWO-COLUMN LAYOUT: Main content + Sidebar -->
  <div class="main-content-wrapper">
    
    <!-- LEFT: Main content -->
    <div class="main-content">

  <!-- UPCOMING STRIP -->
  <div class="upcoming-strip" id="upcomingStrip"></div>

  <!-- CONTROLS -->
  <div class="controls">
    <div class="search-box">
      <span class="search-icon">⌕</span>
      <input type="text" id="searchInput" placeholder="Search events, venues, notes…" oninput="renderEvents()">
    </div>
    <div class="filter-tabs" id="filterTabs">
      <button class="filter-tab active" data-type="all" onclick="setFilter('all', this)">All</button>
      <button class="filter-tab" data-type="manhattan" onclick="setFilter('manhattan', this)"><span class="tab-dot" style="background:#2d6a4f"></span>Manhattan</button>
      <button class="filter-tab" data-type="njkids" onclick="setFilter('njkids', this)"><span class="tab-dot" style="background:#f39c12"></span>NJ Kids</button>
      <button class="filter-tab" data-type="tournament" onclick="setFilter('tournament', this)"><span class="tab-dot" style="background:#922b21"></span>Tournament</button>
      <button class="filter-tab" data-type="seminar" onclick="setFilter('seminar', this)"><span class="tab-dot" style="background:#1a5276"></span>Seminar</button>
      <button class="filter-tab" data-type="joint" onclick="setFilter('joint', this)"><span class="tab-dot" style="background:#c9a84c"></span>Joint</button>
      <button class="filter-tab" data-type="exam" onclick="setFilter('exam', this)"><span class="tab-dot" style="background:#8e44ad"></span>Exam</button>
      <button class="filter-tab" data-type="other" onclick="setFilter('other', this)"><span class="tab-dot" style="background:#7d3c98"></span>Other</button>
    </div>
    <div class="view-toggle">
      <button class="view-btn active" id="gridViewBtn" onclick="setView('grid')" title="Grid view">⊞</button>
      <button class="view-btn" id="listViewBtn" onclick="setView('list')" title="List view">☰</button>
      <button class="view-btn" id="calViewBtn" onclick="setView('calendar')" title="Calendar view">▦</button>
    </div>
  </div>

  <!-- SECTION HEADER -->
  <div class="section-header">
    <span class="section-title">Events</span>
    <div class="section-line"></div>
    <span class="event-count" id="eventCountLabel"></span>
  </div>

  <!-- EVENTS CONTAINER -->
  <div id="eventsContainer"></div>

    </div><!-- end main-content -->

    <!-- RIGHT: Sidebar -->
    <div class="sidebar">
      
      <!-- MESSAGE BOARD -->
      <div class="message-board" id="messageBoard">
        <div class="message-board-header">
          <h3>💬 Message Board</h3>
          <span style="font-size:11px;color:var(--gold);letter-spacing:0.08em" id="messageCount"></span>
        </div>
        <div class="message-form">
          <textarea id="messageText" placeholder="Share a message, announcement, or question..."></textarea>
          <div class="message-form-actions">
            <input type="url" id="messageLink" placeholder="Paste a link (optional)">
            <input type="url" id="messageImage" placeholder="Paste image URL (optional)">
            <button class="btn-primary" onclick="postMessage()" style="padding:8px 16px;font-size:12px">Post</button>
          </div>
        </div>
        <div class="messages-list" id="messagesList"></div>
      </div>

    </div><!-- end sidebar -->

  </div><!-- end main-content-wrapper -->

</main>

<!-- ADD/EDIT MODAL -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal">
    <div class="modal-header">
      <h2 id="modalTitle">New Event</h2>
      <button class="modal-close" onclick="closeModal()">✕</button>
    </div>
    <div class="modal-body">
      <div class="perm-notice" id="permNotice">
        🛡️ You're posting as <strong id="permRole">Admin</strong>. This event will be visible to all members.
      </div>
      <div class="form-grid">
        <div class="form-group form-col-full">
          <label>Event Title</label>
          <select id="fTitleSelect" onchange="handleTitleSelect()">
            <option value="">— Select a common title —</option>
            <option value="Regular Manhattan Practice">Regular Manhattan Practice</option>
            <option value="Regular NJ Kids Class">Regular NJ Kids Class</option>
            <option value="Tournament">Tournament</option>
            <option value="Seminar">Seminar</option>
            <option value="Shinsa (Exam)">Shinsa (Exam)</option>
            <option value="CUSTOM">✏️ Custom (type your own)</option>
          </select>
          <input type="text" id="fTitle" placeholder="Enter custom event title" style="margin-top:8px;display:none">
        </div>
        <div class="form-group">
          <label>Type</label>
          <select id="fType">
            <option value="manhattan">Manhattan Practice</option>
            <option value="njkids">NJ Kids Class</option>
            <option value="tournament">Tournament</option>
            <option value="seminar">Seminar</option>
            <option value="joint">Joint Practice</option>
            <option value="exam">Exam</option>
            <option value="other">Other</option>
          </select>
        </div>
        <div class="form-group">
          <label>Date</label>
          <input type="date" id="fDate">
        </div>
        <div class="form-group">
          <label>Time</label>
          <input type="time" id="fTime">
        </div>
        <div class="form-group">
          <label>End Time (optional)</label>
          <input type="time" id="fTimeEnd">
        </div>
        <div class="form-group form-col-full">
          <label>Venue / Location</label>
          <select id="fVenueSelect" onchange="handleVenueSelect()">
            <option value="">— Select a venue —</option>
            <option value="500 8th Ave, New York, NY 10018">500 8th Ave, New York, NY 10018</option>
            <option value="534 Old Bergen Blvd, Palisades Park, NJ 07650">534 Old Bergen Blvd, Palisades Park, NJ 07650</option>
            <option value="CUSTOM">✏️ Custom (type your own)</option>
          </select>
          <input type="text" id="fVenue" placeholder="Enter custom venue" style="margin-top:8px;display:none">
        </div>
        <div class="form-group">
          <label>Floor (optional)</label>
          <select id="fFloor">
            <option value="">— None —</option>
            <option value="3F">3F</option>
            <option value="4F">4F</option>
            <option value="12F">12F</option>
            <option value="OTHER">Other</option>
          </select>
        </div>
        <div class="form-group">
          <label>Custom Floor</label>
          <input type="text" id="fFloorCustom" placeholder="e.g. B1, 5F" style="display:none">
        </div>
        <div class="form-group">
          <label>Cost / Fee</label>
          <input type="text" id="fCost" placeholder="e.g. Free, $25, ¥3000">
        </div>
        <div class="form-group">
          <label>Registration Deadline</label>
          <input type="date" id="fRegDeadline">
        </div>
        <div class="form-group form-col-full">
          <label>Notes / Description</label>
          <textarea id="fNotes" placeholder="Details, requirements, what to bring…"></textarea>
        </div>
        <div class="form-group form-col-full">
          <label>Documents &amp; Links</label>
          <div class="doc-tabs">
            <button class="doc-tab-btn active" id="docTabLink" onclick="switchDocTab('link')">🔗 Paste a Link</button>
            <button class="doc-tab-btn" id="docTabFile" onclick="switchDocTab('file')">📎 Attach File Name</button>
          </div>
          <div id="docLinkRow" class="doc-attach-row">
            <input type="text" id="fDocName" placeholder="Label (e.g. Entry Form)">
            <input type="url" id="fDocUrl" placeholder="https://drive.google.com/…" style="flex:2">
            <button onclick="addDoc()" style="padding:10px 14px;border:1.5px dashed var(--gray-light);border-radius:8px;background:transparent;color:var(--gray);font-size:16px;cursor:pointer;transition:all 0.18s;white-space:nowrap;" onmouseover="this.style.borderColor='var(--red)';this.style.color='var(--red)'" onmouseout="this.style.borderColor='var(--gray-light)';this.style.color='var(--gray)'">＋</button>
          </div>
          <div id="docFileRow" class="doc-attach-row" style="display:none">
            <input type="text" id="fDocFileName" placeholder="File name (e.g. schedule.pdf)">
            <button onclick="addDocFile()" style="padding:10px 14px;border:1.5px dashed var(--gray-light);border-radius:8px;background:transparent;color:var(--gray);font-size:16px;cursor:pointer;transition:all 0.18s;white-space:nowrap;" onmouseover="this.style.borderColor='var(--red)';this.style.color='var(--red)'" onmouseout="this.style.borderColor='var(--gray-light)';this.style.color='var(--gray)'">＋ Add</button>
          </div>
          <div class="doc-list-preview" id="docListPreview"></div>
        </div>
      </div>
      <div class="form-actions">
        <button class="btn-ghost" onclick="closeModal()">Cancel</button>
        <button class="btn-primary" onclick="saveEvent()">Save Event</button>
      </div>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
// ═══════════════════════════════════════════════════════════════════════════
// GOOGLE SHEETS BACKEND — your data syncs between all users!
// ═══════════════════════════════════════════════════════════════════════════
const GOOGLE_SHEET_URL = 'https://script.google.com/macros/s/AKfycbzx7TiDGzrFp3KEMUQmtp1-raRV-xbUVooGeDDTQrPwBQf-wbeUkMkw13teymtPVBfR/exec';

// ═══════════════════════════════════════════════════════════════════════════
// PASSCODES — change these before sharing with your dojo!
// ═══════════════════════════════════════════════════════════════════════════
const PASSCODE_MEMBER  = '1726';   // share with all members
const PASSCODE_TRUSTED = '2172';   // share with editors only  
const PASSCODE_ADMIN   = '8558';   // keep to yourself, Sensei!

// ─── LOGIN STATE ──────────────────────────────────────────────────────────
let currentUser = null;
let pinBuffer = '';

function pinPress(digit) {
  if (pinBuffer.length >= 4) return;
  pinBuffer += digit;
  updateDots();
  if (pinBuffer.length === 4) setTimeout(tryLogin, 200);
}
function pinDelete() {
  pinBuffer = pinBuffer.slice(0,-1);
  updateDots();
  document.getElementById('loginError').textContent = '';
}
function updateDots() {
  for (let i=0;i<4;i++) {
    const d = document.getElementById('dot'+i);
    d.classList.toggle('filled', i < pinBuffer.length);
    d.classList.remove('error');
  }
}
function tryLogin() {
  const name = document.getElementById('loginName').value.trim();
  if (!name) {
    document.getElementById('loginError').textContent = 'Please enter your name first.';
    pinBuffer = ''; updateDots(); return;
  }
  // Prevent numbers-only names
  if (/^\d+$/.test(name)) {
    document.getElementById('loginError').textContent = 'Please enter your actual name, not a number.';
    pinBuffer = ''; updateDots(); return;
  }
  
  let role = null;
  if (pinBuffer === PASSCODE_ADMIN)        role = 'admin';
  else if (pinBuffer === PASSCODE_TRUSTED) role = 'trusted';
  else if (pinBuffer === PASSCODE_MEMBER)  role = 'member';
  
  if (!role) {
    document.getElementById('loginError').textContent = 'Incorrect passcode. Try again.';
    for (let i=0;i<4;i++) document.getElementById('dot'+i).classList.add('error');
    setTimeout(() => { pinBuffer=''; updateDots(); }, 700);
    return;
  }
  
  // Check if member exists (EXACT match, case-sensitive)
  const existingMember = members.find(m => m.name === name);
  
  // ALL USERS: Must be pre-registered (no auto-registration for anyone)
  if (!existingMember) {
    // Check for similar names and suggest correction
    const similarNames = members.filter(m => m.name.toLowerCase() === name.toLowerCase());
    if (similarNames.length > 0) {
      document.getElementById('loginError').textContent = `Name not found. Did you mean "${similarNames[0].name}"? (case-sensitive)`;
    } else {
      document.getElementById('loginError').textContent = 'Your name is not registered. Contact the admin.';
    }
    pinBuffer = ''; updateDots(); return;
  }
  
  // Verify the passcode matches their registered role
  let expectedPasscode = '';
  if (existingMember.role === 'admin') expectedPasscode = PASSCODE_ADMIN;
  else if (existingMember.role === 'trusted') expectedPasscode = PASSCODE_TRUSTED;
  else if (existingMember.role === 'member') expectedPasscode = PASSCODE_MEMBER;
  
  if (pinBuffer !== expectedPasscode) {
    document.getElementById('loginError').textContent = 'Wrong passcode for your role. Contact admin.';
    pinBuffer = ''; updateDots(); return;
  }
  
  // Success - log them in
  currentUser = { name, role: existingMember.role };
  currentRole = existingMember.role;
  
  document.getElementById('loginOverlay').classList.add('hidden');
  setTimeout(() => document.getElementById('loginOverlay').style.display='none', 500);
  updateHeaderForRole();
  
  // Load data from Google Sheets and then render
  loadData().then(() => {
    renderUpcoming();
    renderEvents();
    renderMessages();
    showToast('⚔️ Welcome, ' + name + '!');
  });
}
document.addEventListener('keydown', function(e) {
  if (!currentUser && e.key >= '0' && e.key <= '9') pinPress(e.key);
  if (!currentUser && e.key === 'Backspace') pinDelete();
});

// ─── APP STATE ────────────────────────────────────────────────────────────
let currentRole   = 'member';
let currentFilter = 'all';
let currentView   = 'grid';
let editingId     = null;
let tempDocs      = [];
let docTabMode    = 'link';
let membersPanelOpen = false;

const ROLES = { admin:'Admin', trusted:'Editor', member:'Member' };
const TYPE_META = {
  manhattan:  { label:'Manhattan Practice', css:'manhattan',  icon:'🗽' },
  njkids:     { label:'NJ Kids Class',      css:'njkids',     icon:'👶' },
  tournament: { label:'Tournament',         css:'tournament', icon:'🏆' },
  seminar:    { label:'Seminar',            css:'seminar',    icon:'📖' },
  joint:      { label:'Joint Practice',     css:'joint',      icon:'🤝' },
  exam:       { label:'Exam',               css:'exam',       icon:'📝' },
  other:      { label:'Other',              css:'other',      icon:'📌' },
};
const TYPE_COLORS = { manhattan:'#2d6a4f', njkids:'#f39c12', tournament:'#922b21', seminar:'#1a5276', joint:'#b8860b', exam:'#8e44ad', other:'#7d3c98' };
const AV_COLORS = ['av1','av2','av3','av4','av5','av6'];
function avColor(i) { return AV_COLORS[i % AV_COLORS.length]; }
function initials(name) { return name.split(' ').map(w=>w[0]).join('').slice(0,2).toUpperCase(); }

// ─── MEMBERS LIST ─────────────────────────────────────────────────────────
let members = [
  { name: 'Shin', role: 'admin', joined: 'Feb 2026' }
];
// Only pre-registered members can log in
// Admins can add new members through the Members panel

// ─── MESSAGE BOARD ────────────────────────────────────────────────────────
let messages = [];

// ─── PERSISTENT STORAGE (GOOGLE SHEETS) ──────────────────────────────────
async function saveData() {
  try {
    // Save to Google Sheets using POST with form data to avoid CORS
    const saveMembers = fetch(GOOGLE_SHEET_URL, {
      method: 'POST',
      body: new URLSearchParams({
        action: 'saveMembers',
        data: JSON.stringify(members)
      })
    }).catch(e => console.log('Members saved'));
    
    const saveEvents = fetch(GOOGLE_SHEET_URL, {
      method: 'POST',
      body: new URLSearchParams({
        action: 'saveEvents',
        data: JSON.stringify(events)
      })
    }).catch(e => console.log('Events saved'));
    
    const saveMessages = fetch(GOOGLE_SHEET_URL, {
      method: 'POST',
      body: new URLSearchParams({
        action: 'saveMessages',
        data: JSON.stringify(messages)
      })
    }).catch(e => console.log('Messages saved'));
    
    await Promise.all([saveMembers, saveEvents, saveMessages]);
  } catch (e) {
    console.error('Failed to save data:', e);
  }
}

async function loadData() {
  try {
    // Load members
    const membersRes = await fetch(GOOGLE_SHEET_URL + '?action=getMembers');
    const loadedMembers = await membersRes.json();
    if (loadedMembers && loadedMembers.length > 0) {
      members = loadedMembers;
    }
    
    // Load events
    const eventsRes = await fetch(GOOGLE_SHEET_URL + '?action=getEvents');
    const loadedEvents = await eventsRes.json();
    if (loadedEvents && loadedEvents.length > 0) {
      events = loadedEvents;
    }
    
    // Load messages
    const messagesRes = await fetch(GOOGLE_SHEET_URL + '?action=getMessages');
    const loadedMessages = await messagesRes.json();
    if (loadedMessages && loadedMessages.length > 0) {
      messages = loadedMessages;
    }
  } catch (e) {
    console.error('Failed to load data:', e);
  }
}

// Load data on startup
loadData().then(() => {
  // Render after data is loaded
  if (currentUser) {
    renderMessages();
    renderEvents();
    renderUpcoming();
  }
});

function postMessage() {
  if (!currentUser) return;
  const text = document.getElementById('messageText').value.trim();
  const link = document.getElementById('messageLink').value.trim();
  const imageUrl = document.getElementById('messageImage').value.trim();
  
  if (!text && !link && !imageUrl) {
    showToast('⚠️ Please enter a message, link, or image');
    return;
  }
  
  messages.unshift({
    id: Date.now(),
    author: currentUser.name,
    text: text,
    link: link,
    imageUrl: imageUrl,
    timestamp: new Date().toISOString(),
  });
  
  document.getElementById('messageText').value = '';
  document.getElementById('messageLink').value = '';
  document.getElementById('messageImage').value = '';
  
  saveData(); // Save to localStorage
  renderMessages();
  showToast('✅ Message posted');
}

function deleteMessage(id) {
  const msg = messages.find(m => m.id === id);
  if (!msg) return;
  
  // Only author or admin can delete
  if (msg.author !== currentUser?.name && currentRole !== 'admin') {
    showToast('⚠️ You can only delete your own messages');
    return;
  }
  
  if (!confirm('Delete this message?')) return;
  
  messages = messages.filter(m => m.id !== id);
  saveData(); // Save to localStorage
  renderMessages();
  showToast('✅ Message deleted');
}

function renderMessages() {
  document.getElementById('messageCount').textContent = messages.length + ' message' + (messages.length !== 1 ? 's' : '');
  const list = document.getElementById('messagesList');
  
  if (!messages.length) {
    list.innerHTML = '<div class="no-messages">No messages yet. Be the first to post!</div>';
    return;
  }
  
  list.innerHTML = messages.map(m => {
    const time = new Date(m.timestamp);
    const timeStr = time.toLocaleDateString('en-US', {month:'short', day:'numeric'}) + ' ' + 
                    time.toLocaleTimeString('en-US', {hour:'numeric', minute:'2-digit'});
    
    const canDelete = (m.author === currentUser?.name || currentRole === 'admin');
    const deleteBtn = canDelete ? `<span class="message-delete" onclick="deleteMessage(${m.id})">✕ Delete</span>` : '';
    
    return `
      <div class="message-item">
        <div class="message-header">
          <div class="message-avatar ${avColor(messages.indexOf(m))}">${initials(m.author)}</div>
          <span class="message-author">${m.author}</span>
          <span class="message-time">${timeStr}</span>
          ${deleteBtn}
        </div>
        ${m.text ? `<div class="message-text">${m.text}</div>` : ''}
        ${m.link ? `<a href="${m.link}" target="_blank" rel="noopener" class="message-link">🔗 ${m.link.length > 50 ? m.link.substring(0,50)+'...' : m.link}</a>` : ''}
        ${m.imageUrl ? `<img src="${m.imageUrl}" class="message-image" alt="Posted image" onclick="window.open('${m.imageUrl}','_blank')">` : ''}
      </div>
    `;
  }).join('');
}

function updateHeaderForRole() {
  const role = currentUser ? currentUser.role : 'member';
  currentRole = role;
  document.getElementById('roleLabel').textContent = currentUser ? currentUser.name + ' (' + ROLES[role] + ')' : ROLES[role];
  document.getElementById('roleDot').className = 'role-dot' + (role==='admin' ? ' admin' : '');
  document.getElementById('membersBtn').style.display = ''; // Show for everyone
  document.getElementById('addEventBtn').style.display = (role==='admin'||role==='trusted') ? '' : 'none';
  document.getElementById('roleBadge').style.cursor = 'default';
  document.getElementById('roleBadge').onclick = null;
}

function toggleMembersPanel() {
  membersPanelOpen = !membersPanelOpen;
  document.getElementById('membersPanel').style.display = membersPanelOpen ? '' : 'none';
  document.getElementById('addMemberBtn').style.display = (membersPanelOpen && currentRole==='admin') ? '' : 'none';
  if (membersPanelOpen) renderMembersPanel();
}

function renderMembersPanel() {
  document.getElementById('memberCountBadge').textContent = members.length + ' member' + (members.length!==1?'s':'');
  const list = document.getElementById('membersList');
  const isAdmin = currentRole === 'admin';
  
  if (!members.length) {
    list.innerHTML = '<div class="no-members">No members yet. ' + (isAdmin ? 'Click "+ Add Member" to register people.' : 'They appear here after admin registers them.') + '</div>';
    return;
  }
  
  list.innerHTML = members.map((m,i) => `
    <div class="member-row">
      <div class="member-avatar ${avColor(i)}">${initials(m.name)}</div>
      <div class="member-info">
        <div class="member-name">${m.name}</div>
        <div class="member-since">Joined ${m.joined}</div>
      </div>
      ${isAdmin ? `<div class="role-toggle">
        <button class="role-opt ${m.role==='member'?'active-member':''}" onclick="setMemberRole(${i},'member')">Member</button>
        <button class="role-opt ${m.role==='trusted'?'active-trusted':''}" onclick="setMemberRole(${i},'trusted')">Editor</button>
        <button class="role-opt ${m.role==='admin'?'active-admin':''}"   onclick="setMemberRole(${i},'admin')">Admin</button>
      </div>
      <button class="btn-ghost" style="font-size:11px;padding:4px 8px;margin-left:8px" onclick="removeMember(${i})">✕</button>` : `<div style="font-size:11px;color:var(--gray);text-transform:uppercase;letter-spacing:0.08em">${ROLES[m.role]}</div>`}
    </div>`).join('');
}

function setMemberRole(idx, role) {
  members[idx].role = role;
  saveData(); // Save to localStorage
  renderMembersPanel();
  showToast('✅ ' + members[idx].name + ' is now ' + ROLES[role]);
}

function removeMember(idx) {
  if (members[idx].name === currentUser?.name) {
    showToast('⚠️ You cannot remove yourself!');
    return;
  }
  if (!confirm('Remove ' + members[idx].name + ' from the dojo?')) return;
  const name = members[idx].name;
  members.splice(idx, 1);
  saveData(); // Save to localStorage
  renderMembersPanel();
  showToast('✅ ' + name + ' removed');
}

function openAddMemberModal() {
  const name = prompt('Enter the new member\'s full name:\n(They will use this exact name to log in)');
  if (!name || !name.trim()) return;
  const trimmed = name.trim();
  
  // Check for duplicate (exact match)
  if (members.find(m => m.name === trimmed)) {
    showToast('⚠️ A member with that exact name already exists');
    return;
  }
  
  // Prevent numbers-only
  if (/^\d+$/.test(trimmed)) {
    showToast('⚠️ Name cannot be only numbers');
    return;
  }
  
  // Ask for role
  const roleChoice = prompt('Assign role for ' + trimmed + ':\n1 = Member\n2 = Editor\n3 = Admin', '1');
  let role = 'member';
  if (roleChoice === '2') role = 'trusted';
  else if (roleChoice === '3') role = 'admin';
  
  members.push({ 
    name: trimmed, 
    role, 
    joined: new Date().toLocaleDateString('en-US', {month:'short', year:'numeric'})
  });
  
  saveData(); // Save to localStorage
  renderMembersPanel();
  showToast('✅ ' + trimmed + ' added as ' + ROLES[role]);
}

// ─── EVENTS DATA ──────────────────────────────────────────────────────────
function futureDateStr(days) {
  const d = new Date(); d.setDate(d.getDate()+days);
  return d.toISOString().split('T')[0];
}

let events = [
  { id:1, title:'Tuesday Evening Class', type:'manhattan', date:futureDateStr(3), time:'19:00', timeEnd:'21:00', venue:'Main Dojo — 45 Sakura Ave', cost:'Members Free', regDeadline:'', notes:'Regular keiko. Beginners welcome. Please arrive 10 min early to prepare bogu.', docs:[], participants:['KT','RS','MA','YB','TN'], participantNames:['Kenji Tanaka','Robert Smith','Maria Anderson','Yuki Brown','Tom Nakamura'], registeredByMe:true, postedBy:'Admin' },
  { id:2, title:'Spring Shiai — Regional Tournament', type:'tournament', date:futureDateStr(18), time:'09:00', timeEnd:'17:00', venue:'Prefectural Gymnasium, 2 Oak St', cost:'¥3,000 / member', regDeadline:futureDateStr(10), notes:'Individual and team shiai. Bring valid ZNKR membership card. Men and bogu mandatory.', docs:[{name:'Entry Form',url:'https://drive.google.com',type:'link'},{name:'Schedule',url:'',type:'file'}], participants:['KT','RS','MA'], participantNames:['Kenji Tanaka','Robert Smith','Maria Anderson'], registeredByMe:false, postedBy:'Admin' },
  { id:3, title:'Seminar with Nakamura Sensei (7-dan)', type:'seminar', date:futureDateStr(26), time:'10:00', timeEnd:'15:00', venue:'East Community Hall, Room B', cost:'$40 per person', regDeadline:futureDateStr(20), notes:'Focus on kamae and suburi fundamentals. Open to all grades. Max 30 participants.', docs:[{name:'Seminar Flyer',url:'https://docs.google.com',type:'link'}], participants:['KT','YB','TN','MA','RS'], participantNames:['Kenji Tanaka','Yuki Brown','Tom Nakamura','Maria Anderson','Robert Smith'], registeredByMe:true, postedBy:'Editor' },
  { id:4, title:'Joint Practice — Riverside Dojo', type:'joint', date:futureDateStr(7), time:'14:00', timeEnd:'16:30', venue:'Riverside Kendo Club, 88 River Rd', cost:'Free', regDeadline:futureDateStr(5), notes:'Friendly joint keiko. Jigeiko format. Carpooling available — contact admin.', docs:[], participants:['KT','RS','TN'], participantNames:['Kenji Tanaka','Robert Smith','Tom Nakamura'], registeredByMe:false, postedBy:'Admin' },
  { id:5, title:'Saturday Morning Class', type:'njkids', date:futureDateStr(5), time:'09:00', timeEnd:'11:00', venue:'Main Dojo — 45 Sakura Ave', cost:'Members Free', regDeadline:'', notes:'All levels. Focus on kihon waza this session.', docs:[], participants:['KT','MA','YB'], participantNames:['Kenji Tanaka','Maria Anderson','Yuki Brown'], registeredByMe:true, postedBy:'Admin' },
  { id:6, title:'Grading Assessment (Ikkyu & Shodan)', type:'exam', date:futureDateStr(35), time:'13:00', timeEnd:'16:00', venue:'Main Dojo — 45 Sakura Ave', cost:'$50 examination fee', regDeadline:futureDateStr(28), notes:'ZNKR grading for Ikkyu and Shodan candidates. Sensei approval required.', docs:[{name:'Grading Requirements',url:'https://drive.google.com',type:'link'},{name:'Application Form',url:'',type:'file'}], participants:['MA','TN'], participantNames:['Maria Anderson','Tom Nakamura'], registeredByMe:false, postedBy:'Admin' },
];

// ─── HELPERS ──────────────────────────────────────────────────────────────
function formatDate(str) {
  if(!str) return '—';
  return new Date(str+'T00:00:00').toLocaleDateString('en-US',{weekday:'short',month:'short',day:'numeric',year:'numeric'});
}
function formatMonth(str) {
  if(!str) return '';
  return new Date(str+'T00:00:00').toLocaleDateString('en-US',{month:'short'}).toUpperCase();
}
function formatDay(str) {
  if(!str) return '';
  return new Date(str+'T00:00:00').getDate();
}
function formatTime(t) {
  if(!t) return '';
  const [h,m]=t.split(':').map(Number);
  return (h%12||12)+':'+(m<10?'0':'')+m+(h>=12?' PM':' AM');
}
function nextId() { return Math.max(0,...events.map(e=>e.id))+1; }
function stripeColor(css) { return {class:'#2d6a4f',tournament:'#922b21',seminar:'#1a5276',joint:'#c9a84c',other:'#7d3c98'}[css]||'#999'; }

// ─── FILTER / VIEW ────────────────────────────────────────────────────────
function setFilter(type,btn) {
  currentFilter=type;
  document.querySelectorAll('.filter-tab').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderEvents();
}

function setView(v) {
  currentView=v;
  ['grid','list','cal'].forEach(k => document.getElementById(k+'ViewBtn').classList.toggle('active', k===v||(k==='cal'&&v==='calendar')));
  const secHeader=document.querySelector('.section-header');
  const searchBox=document.querySelector('.search-box');
  const filterTabs=document.querySelector('.filter-tabs');
  if(v==='calendar'){
    secHeader.style.display='none'; searchBox.style.display='none'; filterTabs.style.display='none';
    renderCalendar();
  } else {
    secHeader.style.display=''; searchBox.style.display=''; filterTabs.style.display='';
    renderEvents();
  }
}

// ─── UPCOMING STRIP ───────────────────────────────────────────────────────
function renderUpcoming() {
  const sorted = [...events].filter(e=>e.date).sort((a,b)=>a.date.localeCompare(b.date)).slice(0,6);
  document.getElementById('upcomingStrip').innerHTML = sorted.map(e=>`
    <div class="up-item" onclick="highlightCard(${e.id})">
      <div class="up-date"><span class="up-month">${formatMonth(e.date)}</span><span class="up-day">${formatDay(e.date)}</span></div>
      <div class="up-info"><div class="up-name">${e.title}</div><div class="up-type">${TYPE_META[e.type]?.label||'Event'}</div></div>
    </div>`).join('');
}

// ─── RENDER EVENTS ────────────────────────────────────────────────────────
function renderEvents() {
  const q = document.getElementById('searchInput').value.toLowerCase();
  const filtered = events.filter(e=>{
    const matchType   = currentFilter==='all'||e.type===currentFilter;
    const matchSearch = !q||[e.title,e.venue,e.notes,e.type].some(f=>f&&f.toLowerCase().includes(q));
    return matchType&&matchSearch;
  }).sort((a,b)=>(a.date||'').localeCompare(b.date||''));
  document.getElementById('eventCountLabel').textContent = filtered.length+' event'+(filtered.length!==1?'s':'');
  const container = document.getElementById('eventsContainer');
  if(!filtered.length){
    container.innerHTML='<div class="empty-state"><div class="empty-icon">⚔️</div><h3>No events found</h3><p>Try a different filter or search.</p></div>';
    return;
  }
  const cls = currentView==='grid'?'events-grid':'events-list';
  container.innerHTML = '<div class="'+cls+'">'+filtered.map(e=>renderCard(e)).join('')+'</div>';
}

function renderCard(e) {
  const tm = TYPE_META[e.type]||TYPE_META.other;
  const isList = currentView==='list';
  const shown = e.participants.slice(0,4);
  const extra = e.participants.length-shown.length;
  const timeStr = e.time?(e.timeEnd?formatTime(e.time)+' – '+formatTime(e.timeEnd):formatTime(e.time)):'—';
  const avatars = shown.map((p,i)=>'<div class="avatar '+avColor(i)+'">'+p+'</div>').join('');
  const extraChip = extra>0?'<div class="avatar" style="background:var(--gray)">+'+extra+'</div>':'';
  const canEdit = currentRole==='admin'||currentRole==='trusted';
  const editBtn = canEdit?'<button class="btn-ghost" style="font-size:11px;padding:5px 10px" onclick="event.stopPropagation();editEvent('+e.id+')">✎ Edit</button>':'';
  const deleteBtn = canEdit?'<button class="btn-ghost" style="font-size:11px;padding:5px 10px;color:var(--red);border-color:#fadbd8" onclick="event.stopPropagation();deleteEvent('+e.id+')" onmouseover="this.style.background=\'#fadbd8\'" onmouseout="this.style.background=\'transparent\'">🗑 Delete</button>':'';
  const regBtn  = '<button class="register-btn '+(e.registeredByMe?'registered':'')+'" onclick="event.stopPropagation();toggleRegister('+e.id+')">'+(e.registeredByMe?'✓ Registered':'Register')+'</button>';

  const docPills = e.docs.length?'<div class="doc-pills">'+e.docs.map(d=>{
    if(d.type==='link'&&d.url) return '<a class="doc-pill doc-pill-link" href="'+d.url+'" target="_blank" rel="noopener" onclick="event.stopPropagation()">🔗 '+d.name+'</a>';
    return '<span class="doc-pill doc-pill-file" onclick="event.stopPropagation()">📎 '+d.name+'</span>';
  }).join('')+'</div>':'';

  const viewAttendeesBtn = e.participants.length > 0 
    ? '<button class="btn-ghost" style="font-size:11px;padding:5px 10px;margin-right:8px" onclick="event.stopPropagation();viewAttendees('+e.id+')">👥 View All</button>'
    : '';

  const details = isList?`
    <div class="card-details">
      <div class="detail-row"><span class="detail-icon">📍</span><span class="detail-val">${e.venue||'—'}</span></div>
      <div class="detail-row"><span class="detail-icon">⏰</span><span class="detail-val">${timeStr}</span></div>
      ${e.cost?'<div class="detail-row"><span class="detail-icon">💴</span><span class="detail-val">'+e.cost+'</span></div>':''}
    </div>` : `
    <div class="card-details">
      <div class="detail-row"><span class="detail-icon">📅</span><span>${formatDate(e.date)}</span></div>
      <div class="detail-row"><span class="detail-icon">⏰</span><span class="detail-val">${timeStr}</span></div>
      <div class="detail-row"><span class="detail-icon">📍</span><span class="detail-val">${e.venue||'—'}</span></div>
      ${e.cost?'<div class="detail-row"><span class="detail-icon">💴</span><span class="detail-val">'+e.cost+'</span></div>':''}
      ${e.regDeadline?'<div class="detail-row"><span class="detail-icon">⏳</span><span>Register by <strong>'+formatDate(e.regDeadline)+'</strong></span></div>':''}
    </div>`;

  if(isList) return `
    <div class="event-card list-mode" id="card-${e.id}">
      <div class="card-stripe" style="background:${stripeColor(tm.css)};width:5px;height:auto;flex-shrink:0"></div>
      <div class="card-body">
        <div class="card-date-chip" style="min-width:50px"><span class="chip-month">${formatMonth(e.date)}</span><span class="chip-day">${formatDay(e.date)}</span></div>
        <div class="list-main"><div class="card-title">${e.title}</div><div class="card-desc" style="font-size:12px">${(e.notes||'').slice(0,80)}${(e.notes||'').length>80?'…':''}</div></div>
        ${details}
        <div class="card-footer" style="flex-shrink:0">
          <div class="participants-row" style="margin-right:8px"><div class="avatar-stack">${avatars}${extraChip}</div><span class="avatar-count">${e.participants.length}</span></div>
          ${docPills}${viewAttendeesBtn}${editBtn}${deleteBtn}${regBtn}
        </div>
      </div>
    </div>`;

  return `
    <div class="event-card" id="card-${e.id}">
      <div class="card-stripe stripe-${tm.css}"></div>
      <div class="card-body">
        <div class="card-meta">
          <span class="event-type-badge type-${tm.css}">${tm.icon} ${tm.label}</span>
          <div class="card-date-chip"><span class="chip-month">${formatMonth(e.date)}</span><span class="chip-day">${formatDay(e.date)}</span></div>
        </div>
        <div class="card-title">${e.title}</div>
        <p class="card-desc">${e.notes||''}</p>
        ${details}${docPills}
        <div class="card-footer">
          <div class="participants-row"><div class="avatar-stack">${avatars}${extraChip}</div><span class="avatar-count">${e.participants.length} going</span></div>
          <div style="display:flex;gap:6px;align-items:center">${viewAttendeesBtn}${editBtn}${deleteBtn}${regBtn}</div>
        </div>
      </div>
    </div>`;
}

function highlightCard(id) {
  if(currentView==='calendar'){setView('grid');setTimeout(()=>_doHighlight(id),380);}
  else _doHighlight(id);
}
function _doHighlight(id) {
  const el=document.getElementById('card-'+id);
  if(!el) return;
  el.scrollIntoView({behavior:'smooth',block:'center'});
  el.style.outline='3px solid var(--red)';
  setTimeout(()=>el.style.outline='',1800);
}

// ─── REGISTER ─────────────────────────────────────────────────────────────
function toggleRegister(id) {
  const e = events.find(ev=>ev.id===id); if(!e) return;
  const myInit = currentUser ? initials(currentUser.name) : 'ME';
  const myName = currentUser ? currentUser.name : 'Guest';
  
  e.registeredByMe = !e.registeredByMe;
  if(e.registeredByMe){ 
    e.participants.push(myInit);
    // Store full name for attendee list
    if (!e.participantNames) e.participantNames = [];
    e.participantNames.push(myName);
    
    showToast('✅ Registered for "'+e.title+'"');
    
    // Notify admin/trusted members
    if (currentRole !== 'admin' && currentRole !== 'trusted') {
      // In a real app, this would send a notification to admin
      // For now, just log it (admin will see the updated count)
      console.log('📢 New registration:', myName, 'registered for', e.title);
    }
  } else { 
    e.participants=e.participants.filter(p=>p!==myInit);
    if (e.participantNames) e.participantNames = e.participantNames.filter(n => n !== myName);
    showToast('↩ Registration cancelled'); 
  }
  saveData(); // Save to localStorage
  if(currentView==='calendar') renderCalendar(); else renderEvents();
  renderUpcoming();
}

function viewAttendees(id) {
  const e = events.find(ev => ev.id === id);
  if (!e) return;
  
  // Fallback if participantNames doesn't exist (old events)
  const names = e.participantNames || e.participants || [];
  if (!names.length) {
    alert('No one has registered yet.');
    return;
  }
  
  const list = names.map((name, i) => `${i+1}. ${name}`).join('\n');
  alert(`Attendees for "${e.title}":\n\n${list}\n\nTotal: ${names.length}`);
}

// ─── DOC TAB SWITCH ───────────────────────────────────────────────────────
function switchDocTab(mode) {
  docTabMode = mode;
  document.getElementById('docTabLink').classList.toggle('active', mode==='link');
  document.getElementById('docTabFile').classList.toggle('active', mode==='file');
  document.getElementById('docLinkRow').style.display = mode==='link'?'':'none';
  document.getElementById('docFileRow').style.display = mode==='file'?'':'none';
}

function handleTitleSelect() {
  const sel = document.getElementById('fTitleSelect');
  const txt = document.getElementById('fTitle');
  if (sel.value === 'CUSTOM') {
    txt.style.display = '';
    txt.focus();
  } else {
    txt.style.display = 'none';
    txt.value = sel.value;
  }
}

function handleVenueSelect() {
  const sel = document.getElementById('fVenueSelect');
  const txt = document.getElementById('fVenue');
  if (sel.value === 'CUSTOM') {
    txt.style.display = '';
    txt.focus();
  } else {
    txt.style.display = 'none';
    txt.value = sel.value;
  }
}

function handleFloorSelect() {
  const sel = document.getElementById('fFloor');
  const txt = document.getElementById('fFloorCustom');
  if (sel.value === 'OTHER') {
    txt.style.display = '';
    txt.focus();
  } else {
    txt.style.display = 'none';
    txt.value = '';
  }
}

// Add onchange handler for floor dropdown
document.addEventListener('DOMContentLoaded', function() {
  const floorSel = document.getElementById('fFloor');
  if (floorSel) floorSel.onchange = handleFloorSelect;
});

// ─── MODAL ────────────────────────────────────────────────────────────────
function openModal(prefill) {
  if(!currentUser) return;
  editingId = prefill?prefill.id:null;
  tempDocs  = prefill?[...(prefill.docs||[])]:[];
  document.getElementById('modalTitle').textContent = prefill?'Edit Event':'New Event';
  document.getElementById('permRole').textContent   = ROLES[currentRole];
  
  // Handle title dropdown
  const titleSel = document.getElementById('fTitleSelect');
  const titleTxt = document.getElementById('fTitle');
  if (prefill?.title) {
    const presetTitles = ['Regular Manhattan Practice','Regular NJ Kids Class','Tournament','Seminar','Shinsa (Exam)'];
    if (presetTitles.includes(prefill.title)) {
      titleSel.value = prefill.title;
      titleTxt.style.display = 'none';
      titleTxt.value = prefill.title;
    } else {
      titleSel.value = 'CUSTOM';
      titleTxt.style.display = '';
      titleTxt.value = prefill.title;
    }
  } else {
    titleSel.value = '';
    titleTxt.style.display = 'none';
    titleTxt.value = '';
  }
  
  // Handle venue dropdown
  const venueSel = document.getElementById('fVenueSelect');
  const venueTxt = document.getElementById('fVenue');
  const floorSel = document.getElementById('fFloor');
  const floorTxt = document.getElementById('fFloorCustom');
  
  if (prefill?.venue) {
    const presetVenues = ['500 8th Ave, New York, NY 10018','534 Old Bergen Blvd, Palisades Park, NJ 07650'];
    if (presetVenues.includes(prefill.venue)) {
      venueSel.value = prefill.venue;
      venueTxt.style.display = 'none';
      venueTxt.value = prefill.venue;
    } else {
      venueSel.value = 'CUSTOM';
      venueTxt.style.display = '';
      venueTxt.value = prefill.venue;
    }
  } else {
    venueSel.value = '';
    venueTxt.style.display = 'none';
    venueTxt.value = '';
  }
  
  // Handle floor dropdown
  if (prefill?.floor) {
    const presetFloors = ['3F','4F','12F'];
    if (presetFloors.includes(prefill.floor)) {
      floorSel.value = prefill.floor;
      floorTxt.style.display = 'none';
      floorTxt.value = '';
    } else {
      floorSel.value = 'OTHER';
      floorTxt.style.display = '';
      floorTxt.value = prefill.floor;
    }
  } else {
    floorSel.value = '';
    floorTxt.style.display = 'none';
    floorTxt.value = '';
  }
  
  document.getElementById('fType').value        = prefill?.type||'class';
  document.getElementById('fDate').value        = prefill?.date||'';
  document.getElementById('fTime').value        = prefill?.time||'';
  document.getElementById('fTimeEnd').value     = prefill?.timeEnd||'';
  document.getElementById('fCost').value        = prefill?.cost||'';
  document.getElementById('fRegDeadline').value = prefill?.regDeadline||'';
  document.getElementById('fNotes').value       = prefill?.notes||'';
  document.getElementById('fDocName').value     = '';
  document.getElementById('fDocUrl').value      = '';
  document.getElementById('fDocFileName').value = '';
  switchDocTab('link');
  renderDocPreview();
  document.getElementById('modalOverlay').classList.add('open');
}
function closeModal() {
  document.getElementById('modalOverlay').classList.remove('open');
  editingId=null; tempDocs=[];
}
function editEvent(id) { const e=events.find(ev=>ev.id===id); if(e) openModal(e); }

function addDoc() {
  const name=document.getElementById('fDocName').value.trim();
  const url =document.getElementById('fDocUrl').value.trim();
  if(!name){showToast('⚠️ Enter a label for the link');return;}
  tempDocs.push({name,url,type:'link'});
  document.getElementById('fDocName').value='';
  document.getElementById('fDocUrl').value='';
  renderDocPreview();
}
function addDocFile() {
  const name=document.getElementById('fDocFileName').value.trim();
  if(!name){showToast('⚠️ Enter a file name');return;}
  tempDocs.push({name,url:'',type:'file'});
  document.getElementById('fDocFileName').value='';
  renderDocPreview();
}
function removeDoc(i){tempDocs.splice(i,1);renderDocPreview();}
function renderDocPreview() {
  document.getElementById('docListPreview').innerHTML = tempDocs.map((d,i)=>{
    const cls = d.type==='link'?'doc-pill-link':'doc-pill-file';
    const ico = d.type==='link'?'🔗':'📎';
    return '<span class="doc-pill '+cls+'">'+ico+' '+d.name+'<span class="doc-rm" onclick="removeDoc('+i+')">✕</span></span>';
  }).join('');
}
function saveEvent() {
  const title=document.getElementById('fTitle').value.trim();
  if(!title){showToast('⚠️ Please enter an event title');return;}
  
  // Get floor info
  const floorSel = document.getElementById('fFloor').value;
  const floorCustom = document.getElementById('fFloorCustom').value.trim();
  const floor = floorSel === 'OTHER' ? floorCustom : floorSel;
  
  // Combine venue with floor if floor is specified
  let venue = document.getElementById('fVenue').value.trim();
  if (floor && venue) {
    venue = venue + ', ' + floor;
  }
  
  const data={
    title, type:document.getElementById('fType').value,
    date:document.getElementById('fDate').value,
    time:document.getElementById('fTime').value,
    timeEnd:document.getElementById('fTimeEnd').value,
    venue: venue,
    floor: floor, // Store separately for editing
    cost:document.getElementById('fCost').value.trim(),
    regDeadline:document.getElementById('fRegDeadline').value,
    notes:document.getElementById('fNotes').value.trim(),
    docs:[...tempDocs],
    postedBy:currentUser?.name||ROLES[currentRole],
  };
  if(editingId){
    const idx=events.findIndex(e=>e.id===editingId);
    events[idx]={...events[idx],...data};
    saveData(); // Save to localStorage
    showToast('✅ Event updated');
  } else {
    events.push({id:nextId(),participants:[],registeredByMe:false,...data});
    saveData(); // Save to localStorage
    showToast('✅ Event added to the board');
  }
  closeModal();
  if(currentView==='calendar') renderCalendar(); else renderEvents();
  renderUpcoming();
}

function deleteEvent(id) {
  if (!confirm('Delete this event? This cannot be undone.')) return;
  
  events = events.filter(e => e.id !== id);
  saveData(); // Save to localStorage
  
  if(currentView==='calendar') renderCalendar(); else renderEvents();
  renderUpcoming();
  showToast('✅ Event deleted');
}

// ─── CALENDAR ─────────────────────────────────────────────────────────────
let calYear,calMonth;
(function(){const n=new Date();calYear=n.getFullYear();calMonth=n.getMonth();})();

function renderCalendar() {
  const container=document.getElementById('eventsContainer');
  const today=new Date();
  const firstDay=new Date(calYear,calMonth,1);
  const daysInMonth=new Date(calYear,calMonth+1,0).getDate();
  const startDow=firstDay.getDay();
  const monthName=firstDay.toLocaleDateString('en-US',{month:'long',year:'numeric'});
  const evMap={};
  events.forEach(e=>{if(e.date){if(!evMap[e.date])evMap[e.date]=[];evMap[e.date].push(e);}});
  let cells='';
  for(let i=0;i<startDow;i++) cells+=calCell(new Date(calYear,calMonth,-startDow+i+1),evMap,today,true);
  for(let d=1;d<=daysInMonth;d++) cells+=calCell(new Date(calYear,calMonth,d),evMap,today,false);
  const total=startDow+daysInMonth;
  const trailing=total%7===0?0:7-(total%7);
  for(let i=1;i<=trailing;i++) cells+=calCell(new Date(calYear,calMonth+1,i),evMap,today,true);
  container.innerHTML=`
    <div class="calendar-wrap">
      <div class="cal-nav">
        <button class="cal-nav-btn" onclick="calPrev()">&#8592;</button>
        <span class="cal-month-label">${monthName}</span>
        <button class="cal-today-btn" onclick="calToday()">Today</button>
        <button class="cal-nav-btn" onclick="calNext()">&#8594;</button>
      </div>
      <div class="cal-grid">
        <div class="cal-dow-row">${['Sun','Mon','Tue','Wed','Thu','Fri','Sat'].map(d=>'<div class="cal-dow">'+d+'</div>').join('')}</div>
        <div class="cal-days">${cells}</div>
      </div>
    </div>`;
}

function dateStr(d) {
  return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0');
}

function calCell(date,evMap,today,other) {
  const ds=dateStr(date);
  const dayEvs=evMap[ds]||[];
  const isToday=ds===dateStr(today);
  const shown=dayEvs.slice(0,3);
  const extra=dayEvs.length-shown.length;
  const pills=shown.map(e=>'<span class="cal-event-pill pill-'+e.type+'" onclick="event.stopPropagation();openEventPopover(event,\''+ds+'\')" title="'+e.title+'">'+e.title+'</span>').join('');
  const more=extra>0?'<span class="cal-more" onclick="event.stopPropagation();openEventPopover(event,\''+ds+'\')">+'+extra+' more</span>':'';
  const num=isToday?'<span class="today-pip">'+date.getDate()+'</span>':date.getDate();
  const cls=['cal-cell',other?'other-month':'',isToday?'today':'',dayEvs.length?'has-events':''].filter(Boolean).join(' ');
  const click=dayEvs.length?'onclick="openEventPopover(event,\''+ds+'\')"':'';
  return '<div class="'+cls+'" '+click+'><div class="cal-day-num">'+num+'</div>'+pills+more+'</div>';
}

function calPrev(){calMonth--;if(calMonth<0){calMonth=11;calYear--;}renderCalendar();}
function calNext(){calMonth++;if(calMonth>11){calMonth=0;calYear++;}renderCalendar();}
function calToday(){const n=new Date();calYear=n.getFullYear();calMonth=n.getMonth();renderCalendar();}

// ─── DAY POPOVER ──────────────────────────────────────────────────────────
let activePopover=null;
function openEventPopover(ev,ds) {
  closePopover();
  const dayEvs=events.filter(e=>e.date===ds);
  if(!dayEvs.length) return;
  const label=new Date(ds+'T00:00:00').toLocaleDateString('en-US',{weekday:'long',month:'long',day:'numeric'});
  const items=dayEvs.map(e=>{
    const t=e.time?formatTime(e.time):'';
    return '<div class="popover-event" onclick="openModal(events.find(x=>x.id==='+e.id+'))">'
      +'<div class="popover-dot" style="background:'+(TYPE_COLORS[e.type]||'#999')+'"></div>'
      +'<div><div class="popover-ev-title">'+e.title+'</div>'
      +'<div class="popover-ev-sub">'+t+(t&&e.venue?' · ':'')+( e.venue||'')+'</div></div></div>';
  }).join('');
  const pop=document.createElement('div');
  pop.className='day-popover';pop.id='dayPopover';
  pop.innerHTML='<div class="popover-header"><span class="popover-date">'+label+'</span><button class="popover-close" onclick="closePopover()">✕</button></div>'+items;
  document.body.appendChild(pop);
  activePopover=pop;
  const rect=ev.currentTarget?.getBoundingClientRect?.();
  let left=(rect?rect.left+rect.width/2-140:ev.clientX-140);
  let top=(rect?rect.bottom+8:ev.clientY+8);
  if(left+280>window.innerWidth-10) left=window.innerWidth-290;
  if(left<10) left=10;
  if(top+300>window.innerHeight-10) top=(rect?rect.top-310:ev.clientY-310);
  pop.style.left=left+'px';pop.style.top=top+'px';
  setTimeout(()=>document.addEventListener('click',outsidePopover),10);
}
function closePopover(){if(activePopover){activePopover.remove();activePopover=null;}document.removeEventListener('click',outsidePopover);}
function outsidePopover(e){if(activePopover&&!activePopover.contains(e.target))closePopover();}

// ─── TOAST ────────────────────────────────────────────────────────────────
let toastTimer;
function showToast(msg) {
  const t=document.getElementById('toast');
  t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer=setTimeout(()=>t.classList.remove('show'),3000);
}

// ─── INIT ─────────────────────────────────────────────────────────────────
document.getElementById('modalOverlay').addEventListener('click', function(e){if(e.target===this)closeModal();});
document.getElementById('fDocName').addEventListener('keydown',    e=>{if(e.key==='Enter'){e.preventDefault();addDoc();}});
document.getElementById('fDocFileName').addEventListener('keydown', e=>{if(e.key==='Enter'){e.preventDefault();addDocFile();}});
document.getElementById('loginName').addEventListener('keydown',    e=>{if(e.key==='Enter')document.querySelector('.pin-btn').focus();});
</script>
</body>
</html>
