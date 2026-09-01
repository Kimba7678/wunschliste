<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<title>Wunschliste</title>
<style>
  :root {
    --bg: #16141a;
    --bg-raised: #1e1b24;
    --ink: #e8e3da;
    --ink-dim: #9c95a8;
    --line: #322d3a;
    --accent: #b0492f;
    --taken: #4a5240;
    --taken-ink: #a9b494;
  }
  * { box-sizing: border-box; }
  body {
    margin: 0;
    background: var(--bg);
    color: var(--ink);
    font-family: Georgia, 'Iowan Old Style', 'Palatino Linotype', serif;
    padding: 32px 16px 64px;
  }
  .wrap { max-width: 640px; margin: 0 auto; }
  h1 {
    font-size: 28px;
    font-weight: 400;
    letter-spacing: 0.01em;
    margin: 0 0 4px;
    color: var(--ink);
  }
  .sub {
    color: var(--ink-dim);
    font-size: 15px;
    margin: 0 0 36px;
    line-height: 1.5;
    max-width: 46ch;
  }
  ul { list-style: none; margin: 0; padding: 0; }
  li {
    border-top: 1px solid var(--line);
    padding: 20px 0;
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }
  li:last-child { border-bottom: 1px solid var(--line); }
  .info { flex: 1; min-width: 0; }
  .name {
    font-size: 17px;
    line-height: 1.4;
    margin: 0 0 4px;
  }
  .name a { color: var(--ink); text-decoration: none; border-bottom: 1px solid var(--line); }
  .name a:hover { border-bottom-color: var(--accent); }
  .note {
    font-size: 13px;
    color: var(--ink-dim);
    margin: 0;
    font-style: italic;
  }
  button {
    flex-shrink: 0;
    font-family: inherit;
    font-size: 14px;
    padding: 9px 16px;
    border-radius: 3px;
    border: 1px solid var(--accent);
    background: transparent;
    color: var(--accent);
    cursor: pointer;
    transition: background 0.15s ease, color 0.15s ease;
    align-self: center;
  }
  button:hover:not(:disabled) { background: var(--accent); color: #16141a; }
  button:disabled {
    border-color: var(--taken);
    color: var(--taken-ink);
    cursor: default;
    background: transparent;
  }
  button.loading { opacity: 0.5; cursor: wait; }
  .foot {
    margin-top: 40px;
    font-size: 13px;
    color: var(--ink-dim);
    text-align: center;
  }
  .error {
    color: #c96a4f;
    font-size: 13px;
    text-align: center;
    margin-top: 20px;
    display: none;
  }
</style>
</head>
<body>
<div class="wrap">
  <h1>Meine Wunschliste</h1>
  <p class="sub">Auf „Ich nehme das" klicken reserviert das Geschenk für dich – es verschwindet dann für alle anderen. Wer was genommen hat, wird nicht angezeigt.</p>
  <ul id="list"></ul>
  <p class="foot">Jedes Geschenk kann nur einmal reserviert werden.</p>
  <p class="error" id="error">Verbindung zur Datenbank fehlgeschlagen. Bitte Seite neu laden.</p>
</div>

<!-- Firebase SDK (compat-Version, funktioniert direkt per <script>-Tag ohne npm) -->
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.2/firebase-database-compat.js"></script>

<script>
const firebaseConfig = {
  apiKey: "AIzaSyB0HynRXBTR8ei8t_7fw6w6z7TjZYpxspU",
  authDomain: "wunschliste-6873e.firebaseapp.com",
  databaseURL: "https://wunschliste-6873e-default-rtdb.firebaseio.com",
  projectId: "wunschliste-6873e",
  storageBucket: "wunschliste-6873e.firebasestorage.app",
  messagingSenderId: "1007973909587",
  appId: "1:1007973909587:web:2e71cd459152ff498fb2a6",
  measurementId: "G-1KMLVR75BD"
};

firebase.initializeApp(firebaseConfig);
const db = firebase.database();
const reservationsRef = db.ref("reservations");

const items = [
  { id: "item1", name: "This Place Will Become Your Tomb – Blue/Green Marbled Vinyl (Sleep Token LP)", price: "36,99 €", url: "https://vinyl-galore.de/produkt/this-place-will-become-your-tomb-blue-green-marbled-vinyl-sleep-token-lp/" },
  { id: "item2", name: "Sundowning – Clear Vinyl (Sleep Token LP)", price: "36,99 €", url: "https://vinyl-galore.de/produkt/sundowning-clear-vinyl-sleep-token-lp/" },
  { id: "item3", name: "Take Me Back to Eden – Glow in the Dark Vinyl, Limited Edition (Sleep Token LP)", price: "37,99 €", url: "https://vinyl-galore.de/produkt/take-me-back-to-eden-limited-edition-glow-in-the-dark-vinyl-sleep-token-lp/" },
  { id: "item4", name: "Shapeshifter – Signed, Inkblot Vinyl", price: "$50.00 USD", url: "https://deadrabbitts.com/products/signed-shapeshifter-clear-w-black-splatter-vinyl" },
  { id: "item5", name: "UGREEN FineTrack Duo GPS Tracker – 4er Pack", price: "28,49 €", url: "https://www.amazon.de/dp/B0FRLWSGPW" }
];

const listEl = document.getElementById("list");
const errorEl = document.getElementById("error");

function render(reserved) {
  listEl.innerHTML = "";
  items.forEach(item => {
    const li = document.createElement("li");
    const isTaken = !!reserved[item.id];
    li.innerHTML = `
      <div class="info">
        <p class="name"><a href="${item.url}" target="_blank" rel="noopener">${item.name}</a></p>
        <p class="note">${item.price}</p>
      </div>
      <button data-id="${item.id}" ${isTaken ? "disabled" : ""}>${isTaken ? "Vergeben" : "Ich nehme das"}</button>
    `;
    listEl.appendChild(li);
  });

  listEl.querySelectorAll("button:not(:disabled)").forEach(btn => {
    btn.addEventListener("click", async () => {
      btn.disabled = true;
      btn.classList.add("loading");
      btn.textContent = "Moment...";
      try {
        const result = await reservationsRef.child(btn.dataset.id).transaction(current => {
          if (current) return;
          return true;
        });
        if (!result.committed) {
          btn.classList.remove("loading");
          btn.disabled = true;
          btn.textContent = "Vergeben";
        }
      } catch (e) {
        btn.classList.remove("loading");
        btn.disabled = false;
        btn.textContent = "Ich nehme das";
        alert("Da ist etwas schiefgelaufen, bitte nochmal versuchen.");
      }
    });
  });
}

reservationsRef.on("value", snapshot => {
  const reserved = snapshot.val() || {};
  render(reserved);
}, err => {
  errorEl.style.display = "block";
  console.error(err);
});
</script>
</body>
</html>
