# Oscillab — oscilații și unde

Prezentare interactivă în română pentru clasa a VIII-a, după secțiunile 1.1–1.3 ale manualului de Fizică furnizat (pp. 6–13).

Cinci capitole: pendul gravitațional, pendul elastic, energia oscilațiilor, fir elastic interactiv și lungimea de undă. Fiecare simulare are controale, grafic sincronizat, formule și explicații. Trage corpul sau capătul firului; poți folosi și săgețile când simularea are focus. Modelele și aproximațiile sunt explicate în fiecare capitol.

## Pornire locală

Nu sunt necesare pachete npm, chei API sau compilare. Cu Python 3:

```sh
cd /workspace/oscilatii-8
python3 -m http.server 8000 --bind 0.0.0.0
```

Deschide serverul în browser. Poți deschide și `index.html` direct. Fișierele aplicației sunt `index.html`, `style.css`, `app.js`; nu există dependențe externe.

## Publicare pe GitHub Pages

1. Salvează fișierele acestui proiect în repository-ul `bitalyk/oscilatii-8`, pe ramura `main` (commit și push).
2. În GitHub: **Settings → Pages → Build and deployment → Source → GitHub Actions**.
3. Workflow-ul **Deploy static content to Pages** rulează la fiecare push pe `main`. Dacă ai activat Pages după push, pornește-l manual din **Actions → Deploy static content to Pages → Run workflow**.
4. După finalizarea cu succes, adresa este `https://bitalyk.github.io/oscilatii-8/` (sau adresa afișată de GitHub în Pages).

Workflow-ul existent în `.github/workflows/static.yml` publică conținutul repository-ului. Toate căile sunt relative, compatibile cu subdirectorul repository-ului pe GitHub Pages. Nu este nevoie de server backend.

Alternativ, selectează **Deploy from a branch**, ramura `main`, directorul `/ (root)` în Settings → Pages; în acest caz poți elimina workflow-ul pentru a evita două metode de publicare.

## Verificare

```sh
node --check app.js
```

În browser: parcurge cele cinci capitole; testează pauza, reluarea, parametrii, tragerea pendulelor și impulsul pe fir. Graficul trebuie să urmărească simularea; la energie, suma Ep + Ec rămâne constantă în limita erorii numerice.
