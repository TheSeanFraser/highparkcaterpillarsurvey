---
layout: null
title: Checklist
permalink: /checklist/
sitemap: false
---

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
<meta name="color-scheme" content="dark">
<title>Caterpillar Checklist</title>
<style>
  :root{
    --bg: #000000;
    --text: #ffffff;
    --text-soft: #d6d6d6;
    --muted: #9b9b9b;
    --border: #2e2e2e;
    --border-strong: #707070;
    --accent: #3fa570;
    --accent-soft: #12301f;
    --danger: #e07a5f;
    --focus: #6fb1e8;
    --radius: 4px;
  }

  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing:antialiased;
    min-height:100vh;
    line-height:1.4;
  }
  ::selection{background:var(--accent-soft); color:var(--text);}

  button{font-family:inherit; cursor:pointer;}
  input{font-family:inherit;}
  a{color:inherit;}

  .app{
    max-width:640px;
    margin:0 auto;
    min-height:100vh;
    display:flex;
    flex-direction:column;
  }

  /* ---------- Header ---------- */
  header.top{
    position:sticky;
    top:0;
    z-index:30;
    background:var(--bg);
    border-bottom:1px solid var(--border);
    padding:16px 16px 0 16px;
  }
  .title-row{
    display:flex;
    align-items:baseline;
    justify-content:space-between;
    gap:12px;
    flex-wrap:wrap;
  }
  h1{
    font-size:20px;
    font-weight:600;
    margin:0;
    letter-spacing:-0.01em;
    line-height:1.2;
  }
  h1 em{
    font-style:normal;
    font-weight:600;
    color:var(--text);
  }
  .session-meta{
    display:flex;
    gap:10px;
    align-items:center;
    font-size:12px;
    color:var(--muted);
  }
  .new-session-btn{
    background:none;
    border:1px solid var(--border);
    color:var(--muted);
    font-size:11px;
    padding:4px 9px;
    border-radius:var(--radius);
  }
  .new-session-btn:hover{border-color:var(--text); color:var(--text);}

  .search-wrap{
    position:relative;
    margin:12px 0 12px 0;
  }
  #search{
    width:100%;
    padding:11px 12px;
    font-size:16px;
    border:1px solid var(--border-strong);
    background:var(--bg);
    color:var(--text);
    border-radius:var(--radius);
  }
  #search:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 2px rgba(47,111,166,0.12);}
  #search::placeholder{color:var(--muted);}

  .dropdown{
    position:absolute;
    left:0; right:0; top:calc(100% + 4px);
    background:var(--bg);
    border:1px solid var(--border-strong);
    border-radius:var(--radius);
    max-height:60vh;
    overflow-y:auto;
    box-shadow:0 4px 12px rgba(0,0,0,0.08);
    z-index:40;
  }
  .dd-item{
    display:flex;
    justify-content:space-between;
    align-items:baseline;
    gap:10px;
    padding:9px 12px;
    border-bottom:1px solid var(--border);
  }
  .dd-item:last-child{border-bottom:none;}
  .dd-item:hover, .dd-item.active{background:var(--accent-soft);}
  .dd-main{min-width:0;}
  .dd-common{font-size:14px; font-weight:500; color:var(--text);}
  .dd-sci{
    font-style:italic;
    font-size:12px;
    color:var(--muted);
    margin-top:1px;
  }
  .dd-fam{
    font-size:11px;
    color:var(--muted);
    white-space:nowrap;
    flex-shrink:0;
  }
  .dd-custom{
    padding:11px 12px;
    font-size:14px;
    color:var(--accent);
    display:flex;
    align-items:center;
    gap:8px;
  }
  .dd-custom:hover, .dd-custom.active{background:var(--accent-soft);}
  .dd-empty{padding:12px; font-size:13px; color:var(--muted);}

  /* ---------- Session notes ---------- */
  .notes-wrap{
    padding:0 16px 0 16px;
  }
  .notes-label{
    display:block;
    font-size:11px;
    color:var(--muted);
    margin:12px 0 4px 0;
  }
  #notes{
    width:100%;
    padding:10px 12px;
    font-size:14px;
    line-height:1.45;
    background:var(--bg);
    color:var(--text);
    border:1px solid var(--border);
    border-radius:var(--radius);
    resize:vertical;
    min-height:44px;
  }
  #notes:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 2px rgba(111,177,232,0.15);}
  #notes::placeholder{color:var(--muted);}

  /* ---------- Summary strip ---------- */
  .summary{
    display:flex;
    gap:20px;
    padding:0 16px 12px 16px;
    font-size:12px;
    color:var(--text-soft);
  }
  .summary b{
    font-size:14px;
    color:var(--text);
    margin-right:4px;
  }

  /* ---------- List ---------- */
  main{
    flex:1;
    padding:4px 16px 90px 16px;
  }
  .group-label{
    font-size:11px;
    color:var(--muted);
    margin:16px 0 4px 0;
    padding-bottom:4px;
    border-bottom:1px solid var(--border);
  }
  .empty-state{
    text-align:center;
    padding:56px 20px;
    color:var(--muted);
  }
  .empty-state .moth-mark{
    font-size:28px;
    display:block;
    margin-bottom:10px;
    color:var(--border-strong);
  }
  .empty-state p{font-size:14px; line-height:1.5; max-width:280px; margin:0 auto;}

  .row{
    display:flex;
    flex-wrap:wrap;
    align-items:center;
    gap:10px;
    padding:11px 0;
    border-bottom:1px solid var(--border);
  }
  .row-info{flex:1; min-width:0;}
  .row-common{
    font-size:15px;
    font-weight:500;
    color:var(--text);
    display:flex;
    align-items:center;
    gap:6px;
  }
  .custom-dot{
    width:6px; height:6px;
    border-radius:50%;
    background:var(--accent);
    flex-shrink:0;
    display:inline-block;
  }
  .row-sci{
    font-style:italic;
    font-size:12.5px;
    color:var(--muted);
    margin-top:1px;
  }
  .row-fam{
    font-size:10.5px;
    color:var(--muted);
    margin-top:2px;
  }
  .cmt-btn{
    background:none;
    border:none;
    padding:6px 0 0 0;
    font-size:12px;
    color:var(--accent);
    text-decoration:underline;
    text-underline-offset:2px;
    -webkit-tap-highlight-color:transparent;
  }
  .row-cmt-text{
    flex-basis:100%;
    font-size:13px;
    line-height:1.4;
    color:var(--text-soft);
    white-space:pre-wrap;
    overflow-wrap:anywhere;
    padding-left:10px;
    border-left:2px solid var(--border-strong);
  }
  .row-cmt-edit{flex-basis:100%;}
  .row-cmt-edit textarea{
    width:100%;
    padding:9px 11px;
    font-size:16px;
    line-height:1.4;
    font-family:inherit;
    background:var(--bg);
    color:var(--text);
    border:1px solid var(--border-strong);
    border-radius:var(--radius);
    resize:vertical;
    min-height:44px;
  }
  .row-cmt-edit textarea:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 2px rgba(111,177,232,0.15);}
  .row-cmt-edit textarea::placeholder{color:var(--muted);}

  .counter{
    display:flex;
    align-items:center;
    gap:0;
    flex-shrink:0;
    border:1px solid var(--border-strong);
    border-radius:var(--radius);
    overflow:hidden;
  }
  .ctr-btn{
    background:var(--bg);
    border:none;
    width:32px;
    height:36px;
    font-size:16px;
    color:var(--text-soft);
    display:flex; align-items:center; justify-content:center;
    -webkit-tap-highlight-color:transparent;
  }
  .ctr-btn:active{background:var(--border);}
  .ctr-minus{border-right:1px solid var(--border);}
  .ctr-count{
    min-width:42px;
    height:36px;
    display:flex; align-items:center; justify-content:center;
    font-size:16px;
    font-weight:600;
    background:var(--accent);
    color:#ffffff;
    border-left:1px solid var(--border);
    border-right:1px solid var(--border);
    -webkit-tap-highlight-color:transparent;
  }
  .ctr-count:active{opacity:0.85;}
  .ctr-plus{color:var(--accent);}

  .row-del{
    background:none;
    border:none;
    color:var(--muted);
    font-size:15px;
    width:24px;
    height:24px;
    flex-shrink:0;
    -webkit-tap-highlight-color:transparent;
  }
  .row-del:hover{color:var(--danger);}

  /* ---------- Footer ---------- */
  footer{
    position:sticky;
    bottom:0;
    background:var(--bg);
    border-top:1px solid var(--border);
    padding:10px 16px calc(10px + env(safe-area-inset-bottom)) 16px;
    font-size:11.5px;
    color:var(--muted);
  }
  .footer-row{
    display:flex;
    justify-content:space-between;
    align-items:center;
  }
  footer .foot-actions{display:flex; gap:14px;}
  footer button{
    background:none;
    border:none;
    color:var(--text-soft);
    font-size:11.5px;
    text-decoration:underline;
    text-underline-offset:2px;
    padding:4px 0;
  }
  footer button:hover{color:var(--accent);}
  #exportBtn{
    background:var(--accent);
    color:#ffffff;
    border:1px solid var(--accent);
    border-radius:var(--radius);
    text-decoration:none;
    font-size:12px;
    font-weight:600;
    padding:7px 12px;
    white-space:nowrap;
  }
  #exportBtn:hover{background:var(--accent); opacity:0.9; color:#ffffff;}

  .toast{
    position:fixed;
    left:50%;
    bottom:64px;
    transform:translateX(-50%) translateY(10px);
    background:#1f1f1f;
    border:1px solid #3a3a3a;
    color:#ffffff;
    font-size:13px;
    padding:9px 16px;
    border-radius:var(--radius);
    opacity:0;
    pointer-events:none;
    transition:opacity 0.2s ease, transform 0.2s ease;
    z-index:60;
    display:flex;
    align-items:center;
    gap:10px;
  }
  .toast.show{opacity:1; transform:translateX(-50%) translateY(0);}
  .toast button{
    background:none; border:none; color:#ffffff;
    text-decoration:underline; font-size:12px;
  }

  .credit{
    margin:8px 0 0 0;
    padding-top:8px;
    border-top:1px solid var(--border);
    font-size:10.5px;
    line-height:1.4;
    color:var(--muted);
  }
  .credit em{font-style:italic;}

  @media (max-width:400px){
    h1{font-size:18px;}
    .row-common{font-size:14px;}
  }

  :focus-visible{outline:2px solid var(--focus); outline-offset:1px;}
</style>
</head>
<body>
<div class="app">
  <header class="top">
    <div class="title-row">
      <!-- <h1>Field <em>Checklist</em></h1> -->
      <h1>iCat</h1>
      <div class="session-meta">
        <span id="dateLabel"></span>
        <button class="new-session-btn" id="newSessionBtn" title="Start a fresh checklist">New session</button>
      </div>
    </div>
    <div class="search-wrap">
      <input type="text" id="search" placeholder="Search species to add&hellip;" autocomplete="off" spellcheck="false">
      <div class="dropdown" id="dropdown" hidden></div>
    </div>
  </header>

  <div class="notes-wrap">
    <label class="notes-label" for="notes">Session notes</label>
    <textarea id="notes" rows="3" placeholder="General comments for this session &mdash; included in the export."></textarea>
  </div>

  <div class="summary" id="summary"></div>

  <main>
    <div id="list"></div>
  </main>

  <footer>
    <div class="footer-row">
      <span id="footNote">Tap a species to add it, then tap its count each time you spot another.</span>
      <div class="foot-actions">
        <button id="exportBtn">Copy table</button>
      </div>
    </div>
    <p class="credit">Moth list: David Beadle and Alan Macnaughton, <em>TEA Checklist of Ontario Moths</em> (13 September 2026)</p>
  </footer>
</div>

<div class="toast" id="toast"></div>

<script src="/https://highparkcaterpillars.ca/checklist/species-list.js"></script>
<script>
/* ---- Reference data: loaded from /checklist-species.js (defines MOTHS) ----  */
const SPECIES = (typeof MOTHS !== 'undefined') ? MOTHS : [];
if(!SPECIES.length) console.error('checklist-species.js did not load \u2014 species search will be empty.');
/* ---- State ---- */
const STORAGE_KEY = 'caterpillarWatchSession_v1';
let session = loadSession();

function defaultSession(){
  return {
    date: new Date().toISOString().slice(0,10),
    notes: '',
    entries: [] // {id, common, sci, fam, count, custom}
  };
}

function loadSession(){
  try{
    const raw = localStorage.getItem(STORAGE_KEY);
    if(!raw) return defaultSession();
    const parsed = JSON.parse(raw);
    if(!parsed.entries) return defaultSession();
    return parsed;
  }catch(e){
    return defaultSession();
  }
}

function saveSession(){
  try{ localStorage.setItem(STORAGE_KEY, JSON.stringify(session)); }catch(e){}
}

/* ---- DOM refs ---- */
const searchEl = document.getElementById('search');
const dropdownEl = document.getElementById('dropdown');
const listEl = document.getElementById('list');
const summaryEl = document.getElementById('summary');
const dateLabel = document.getElementById('dateLabel');
const newSessionBtn = document.getElementById('newSessionBtn');
const exportBtn = document.getElementById('exportBtn');
const toastEl = document.getElementById('toast');
const notesEl = document.getElementById('notes');

notesEl.value = session.notes || '';
notesEl.addEventListener('input', () => {
  session.notes = notesEl.value;
  saveSession();
});

dateLabel.textContent = formatDate(session.date);

function formatDate(iso){
  const d = new Date(iso + 'T00:00:00');
  if(isNaN(d)) return iso;
  return d.toLocaleDateString(undefined, {month:'short', day:'numeric'});
}

/* ---- Search / autocomplete ---- */
let activeIndex = -1;
let currentMatches = [];

function normalize(s){
  return s.toLowerCase().replace(/[-\u2010-\u2015]/g, ' ').replace(/\s+/g, ' ').trim();
}

function searchMoths(q){
  const nq = normalize(q);
  if(!nq) return [];
  const starts = [];
  const contains = [];
  for(const m of SPECIES){
    const c = normalize(m.common || '');
    const s = normalize(m.sci);
    if(c.startsWith(nq) || s.startsWith(nq)) starts.push(m);
    else if(c.includes(nq) || s.includes(nq)) contains.push(m);
    if(starts.length >= 30) break;
  }
  return starts.concat(contains).slice(0, 8);
}

function renderDropdown(q){
  const matches = searchMoths(q);
  currentMatches = matches;
  activeIndex = -1;
  dropdownEl.innerHTML = '';

  if(!q.trim()){
    dropdownEl.hidden = true;
    return;
  }

  if(matches.length === 0){
    const empty = document.createElement('div');
    empty.className = 'dd-empty';
    empty.textContent = 'No matches in the Ontario checklist.';
    dropdownEl.appendChild(empty);
  } else {
    matches.forEach((m, i) => {
      const item = document.createElement('div');
      item.className = 'dd-item';
      item.dataset.index = i;
      item.innerHTML = `
        <div class="dd-main">
          <div class="dd-common">${escapeHtml(m.common || m.sci)}</div>
          <div class="dd-sci">${escapeHtml(m.sci)}</div>
        </div>
        <div class="dd-fam">${escapeHtml(m.fam || '')}</div>
      `;
      item.addEventListener('click', () => addSpecies(m));
      dropdownEl.appendChild(item);
    });
  }

  const customRow = document.createElement('div');
  customRow.className = 'dd-custom';
  customRow.dataset.custom = '1';
  customRow.innerHTML = `<span>+</span> Add "${escapeHtml(q.trim())}" as a custom entry`;
  customRow.addEventListener('click', () => addCustom(q.trim()));
  dropdownEl.appendChild(customRow);

  dropdownEl.hidden = false;
}

function escapeHtml(str){
  return String(str).replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}

searchEl.addEventListener('input', () => renderDropdown(searchEl.value));
searchEl.addEventListener('focus', () => { if(searchEl.value.trim()) renderDropdown(searchEl.value); });

searchEl.addEventListener('keydown', (e) => {
  const rows = Array.from(dropdownEl.children);
  if(dropdownEl.hidden || rows.length === 0) return;

  if(e.key === 'ArrowDown'){
    e.preventDefault();
    activeIndex = Math.min(activeIndex + 1, rows.length - 1);
    updateActive(rows);
  } else if(e.key === 'ArrowUp'){
    e.preventDefault();
    activeIndex = Math.max(activeIndex - 1, 0);
    updateActive(rows);
  } else if(e.key === 'Enter'){
    e.preventDefault();
    if(activeIndex >= 0 && rows[activeIndex]){
      rows[activeIndex].click();
    } else if(currentMatches.length === 1){
      addSpecies(currentMatches[0]);
    } else if(searchEl.value.trim()){
      addCustom(searchEl.value.trim());
    }
  } else if(e.key === 'Escape'){
    dropdownEl.hidden = true;
    searchEl.blur();
  }
});

function updateActive(rows){
  rows.forEach(r => r.classList.remove('active'));
  if(rows[activeIndex]) rows[activeIndex].classList.add('active');
}

document.addEventListener('click', (e) => {
  if(!e.target.closest('.search-wrap')) dropdownEl.hidden = true;
});

/* ---- Session entry actions ---- */
function findEntry(sci, common, custom){
  return session.entries.find(en => en.custom === custom && en.sci === sci && en.common === common);
}

function addSpecies(m){
  let entry = findEntry(m.sci, m.common || '', false);
  if(entry){
    entry.count += 1;
    bumpToast(`${m.common || m.sci} \u00B7 already on list, now ${entry.count}`);
  } else {
    entry = {
      id: 'sp_' + Date.now() + '_' + Math.random().toString(36).slice(2,7),
      common: m.common || '',
      sci: m.sci,
      fam: m.fam || '',
      count: 1,
      custom: false,
      comment: '',
      h: (typeof m.h === 'number') ? m.h : null
    };
    session.entries.push(entry);
    bumpToast(`Added ${m.common || m.sci}`);
  }
  finishAdd(entry.id);
}

function addCustom(text){
  if(!text) return;
  let entry = findEntry('', text, true);
  if(entry){
    entry.count += 1;
    bumpToast(`${text} \u00B7 already on list, now ${entry.count}`);
  } else {
    entry = {
      id: 'cu_' + Date.now() + '_' + Math.random().toString(36).slice(2,7),
      common: text,
      sci: '',
      fam: '',
      count: 1,
      custom: true,
      comment: '',
      h: null
    };
    session.entries.push(entry);
    bumpToast(`Added custom entry: ${text}`);
  }
  finishAdd(entry.id);
}

function finishAdd(id){
  saveSession();
  searchEl.value = '';
  dropdownEl.hidden = true;
  renderList(id);
  searchEl.focus();
}

function incrementEntry(id, delta){
  const entry = session.entries.find(e => e.id === id);
  if(!entry) return;
  entry.count = Math.max(0, entry.count + delta);
  saveSession();
  renderList();
  const pill = document.querySelector(`.ctr-count[data-id="${id}"]`);
  if(pill && delta > 0){
    pill.classList.remove('pulse');
    void pill.offsetWidth;
    pill.classList.add('pulse');
  }
}

function removeEntry(id){
  const entry = session.entries.find(e => e.id === id);
  if(!entry) return;
  if(!confirm(`Remove ${entry.common || entry.sci} from the list?`)) return;
  session.entries = session.entries.filter(e => e.id !== id);
  saveSession();
  renderList();
  bumpToast(`Removed ${entry.common || entry.sci}`);
}

/* ---- Per-species comments ---- */
const openComments = new Set();

function toggleComment(id){
  const entry = session.entries.find(e => e.id === id);
  if(!entry) return;
  if(openComments.has(id)){
    openComments.delete(id);
    entry.comment = (entry.comment || '').trim();
    saveSession();
    renderList();
  } else {
    openComments.add(id);
    renderList();
    const ta = listEl.querySelector(`.row-cmt-edit textarea[data-id="${id}"]`);
    if(ta){ ta.focus(); ta.setSelectionRange(ta.value.length, ta.value.length); }
  }
}

/* ---- Rendering ---- */
function renderList(highlightId){
  listEl.innerHTML = '';

  if(session.entries.length === 0){
    listEl.innerHTML = `
      <div class="empty-state">
        <span class="moth-mark">&#10022;</span>
        <p>Nothing logged yet. Search above for a species from the Ontario checklist, or add your own custom entry &mdash; like "unknown geometer on ash."</p>
      </div>`;
    updateSummary();
    return;
  }

  const sorted = [...session.entries].sort((a,b) => {
    const an = (a.common || a.sci).toLowerCase();
    const bn = (b.common || b.sci).toLowerCase();
    return an.localeCompare(bn);
  });

  sorted.forEach(entry => {
    const row = document.createElement('div');
    row.className = 'row';
    row.innerHTML = `
      <div class="row-info">
        <div class="row-common">${entry.custom ? '<span class="custom-dot" title="custom entry"></span>' : ''}${escapeHtml(entry.common || entry.sci)}</div>
        ${entry.sci ? `<div class="row-sci">${escapeHtml(entry.sci)}</div>` : ''}
        ${entry.fam ? `<div class="row-fam">${escapeHtml(entry.fam)}</div>` : ''}
        <button class="cmt-btn" data-id="${entry.id}" data-action="comment">${openComments.has(entry.id) ? 'Done' : (entry.comment ? 'Edit comment' : 'Add comment')}</button>
      </div>
      <div class="counter">
        <button class="ctr-btn ctr-minus" aria-label="Decrease count" data-id="${entry.id}" data-action="minus">&minus;</button>
        <button class="ctr-count" data-id="${entry.id}" aria-label="Increase count, currently ${entry.count}">${entry.count}</button>
        <button class="ctr-btn ctr-plus" aria-label="Increase count" data-id="${entry.id}" data-action="plus">+</button>
      </div>
      <button class="row-del" data-id="${entry.id}" aria-label="Remove ${escapeHtml(entry.common || entry.sci)}">&times;</button>
      ${openComments.has(entry.id)
        ? `<div class="row-cmt-edit"><textarea rows="2" data-id="${entry.id}" placeholder="Comment (host plant, location, stage&hellip;)" aria-label="Comment for ${escapeHtml(entry.common || entry.sci)}">${escapeHtml(entry.comment || '')}</textarea></div>`
        : (entry.comment ? `<div class="row-cmt-text">${escapeHtml(entry.comment)}</div>` : '')}
    `;
    listEl.appendChild(row);
  });

  listEl.querySelectorAll('[data-action="comment"]').forEach(btn => {
    btn.addEventListener('click', () => toggleComment(btn.dataset.id));
  });
  listEl.querySelectorAll('.row-cmt-edit textarea').forEach(ta => {
    ta.addEventListener('input', () => {
      const entry = session.entries.find(e => e.id === ta.dataset.id);
      if(!entry) return;
      entry.comment = ta.value;
      saveSession();
    });
  });

  listEl.querySelectorAll('.ctr-count').forEach(btn => {
    btn.addEventListener('click', () => incrementEntry(btn.dataset.id, 1));
  });
  listEl.querySelectorAll('[data-action="plus"]').forEach(btn => {
    btn.addEventListener('click', () => incrementEntry(btn.dataset.id, 1));
  });
  listEl.querySelectorAll('[data-action="minus"]').forEach(btn => {
    btn.addEventListener('click', () => incrementEntry(btn.dataset.id, -1));
  });
  listEl.querySelectorAll('.row-del').forEach(btn => {
    btn.addEventListener('click', () => removeEntry(btn.dataset.id));
  });

  updateSummary();
}

function updateSummary(){
  const speciesCount = session.entries.length;
  const individualCount = session.entries.reduce((sum, e) => sum + e.count, 0);
  summaryEl.innerHTML = `
    <span><b>${speciesCount}</b>species</span>
    <span><b>${individualCount}</b>individuals</span>
  `;
}

/* ---- Toast ---- */
let toastTimer = null;
function bumpToast(msg, undoOpts){
  clearTimeout(toastTimer);
  toastEl.innerHTML = '';
  const text = document.createElement('span');
  text.textContent = msg;
  toastEl.appendChild(text);
  if(undoOpts){
    const btn = document.createElement('button');
    btn.textContent = undoOpts.label;
    btn.addEventListener('click', () => { undoOpts.action(); toastEl.classList.remove('show'); });
    toastEl.appendChild(btn);
  }
  toastEl.classList.add('show');
  toastTimer = setTimeout(() => toastEl.classList.remove('show'), 2600);
}

/* ---- Header actions ---- */
newSessionBtn.addEventListener('click', () => {
  if(session.entries.length && !confirm('Start a new session? This clears the current checklist.')) return;
  session = defaultSession();
  dateLabel.textContent = formatDate(session.date);
  notesEl.value = '';
  saveSession();
  renderList();
});

const commentFor = e => (e.comment || '').trim().replace(/\s*\n\s*/g, ' ').replace(/\t/g, ' ');
const anyComments = () => session.entries.some(e => commentFor(e));

const notesForExport = () => (session.notes || '').trim().replace(/\s*\n\s*/g, ' ');

function sortedForExport(){
  return [...session.entries].sort((a, b) => {
    return (a.common || a.sci).toLowerCase().localeCompare((b.common || b.sci).toLowerCase());
  });
}

function buildExportPlain(){
  const withCmt = anyComments();
  const headerCells = ['Qty', 'Common name', 'Scientific name'].concat(withCmt ? ['Comments'] : []);
  const lines = [];
  const notes = notesForExport();
  if(notes){
    lines.push('Notes: ' + notes);
    lines.push('');
  }
  lines.push(headerCells.join('\t'));
  sortedForExport().forEach(e => lines.push([e.count, e.common || e.sci, e.sci].concat(withCmt ? [commentFor(e)] : []).join('\t')));
  return lines.join('\n');
}

function buildExportHtml(){
  const withCmt = anyComments();
  const headerCells = ['Qty', 'Common name', 'Scientific name'].concat(withCmt ? ['Comments'] : []);
  const notes = notesForExport();
  let html = '';
  if(notes){
    html += '<p><b>Notes:</b> ' + escapeHtml(notes) + '</p>';
  }
  html += '<table><thead><tr>' +
    headerCells.map(h => `<th>${h}</th>`).join('') +
    '</tr></thead><tbody>' +
    sortedForExport().map(e => `<tr><td>${e.count}</td><td>${escapeHtml(e.common || e.sci)}</td><td>${escapeHtml(e.sci)}</td>${withCmt ? `<td>${escapeHtml(commentFor(e))}</td>` : ''}</tr>`).join('') +
    '</tbody></table>';
  return html;
}

async function copyExport(){
  const notes = notesForExport();
  if(session.entries.length === 0 && !notes){ bumpToast('Nothing to export yet'); return; }
  const plain = buildExportPlain();
  const html = buildExportHtml();
  try{
    if(navigator.clipboard && window.ClipboardItem){
      await navigator.clipboard.write([new ClipboardItem({
        'text/plain': new Blob([plain], {type:'text/plain'}),
        'text/html': new Blob([html], {type:'text/html'})
      })]);
      bumpToast('Table copied \u2014 paste into a spreadsheet or doc');
    } else if(navigator.clipboard && navigator.clipboard.writeText){
      await navigator.clipboard.writeText(plain);
      bumpToast('Table copied as text');
    } else {
      throw new Error('Clipboard API unavailable');
    }
  } catch(err){
    const ta = document.createElement('textarea');
    ta.value = plain;
    ta.style.position = 'fixed';
    ta.style.top = '0';
    ta.style.opacity = '0';
    document.body.appendChild(ta);
    ta.focus();
    ta.select();
    let ok = false;
    try{ ok = document.execCommand('copy'); }catch(e2){}
    document.body.removeChild(ta);
    bumpToast(ok ? 'Table copied \u2014 paste into a spreadsheet or doc' : 'Copy failed \u2014 please copy manually');
  }
}

exportBtn.addEventListener('click', copyExport);

/* ---- Init ---- */
renderList();
</script>
</body>
</html>
