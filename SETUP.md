# Setup — kahan kaunsi image lagani hai

Is repo ka naam GitHub par **`nandubodra`** hona chahiye (same as username) tabhi README profile par dikhega.

## 1. Photo -> `assets/source/photo.png` (done: tumhari photo add ho chuki hai)

Ye banner ke left wale **VISUAL.MAP** panel mein dotted portrait banti hai.

- File ka naam exactly `photo.png` (ya `photo.jpg`) rakho.
- Best result: **transparent background wali PNG** (head + shoulders, face seedha). Phone ke "remove background" ya remove.bg se ban jaati hai.
- Normal photo bhi chalegi, script khud edges soft kar deti hai.

Phir:

```bash
pip install -r scripts/banner/requirements.txt
python scripts/banner/generate.py
```

Isse ye files ban jaayengi: `assets/banner-dark.v9.svg` aur `assets/banner-light.v9.svg`.

## 2. Certificates -> `assets/certificates/` (done: 2 certificates add ho chuke hain)

`cert-1.png`, `cert-2.png`, ... rakho, phir README mein **My Certificates** section ke comment wali lines uncomment karo.

## 3. Project screenshot (optional) -> `assets/portfolio-preview.png`

README mein **Featured Projects** ke neeche comment wali `<img>` line uncomment karo.

## 4. Socials

README mein (top) LinkedIn / Instagram / X ke links comment mein ready hain: apna link daalo aur uncomment karo.
Banner mein `Grid.LinkedIn` aur `Grid.Mail` abhi `—` hain: `scripts/banner/generate.py` ke `ROWS` mein edit karke banner dobara generate karo.

## 5. Auto-generated files (khud mat banao)

Push karne ke baad GitHub Actions ye bana dega:

- `assets/card-stats-*.svg`, `assets/card-PORTFOLIO-*.svg` (workflow **Charts and cards**)
- `assets/metrics.languages.svg` (workflow **Metrics**, repo secret `METRICS_TOKEN` chahiye)

Actions tab mein jaake dono workflows ko ek baar **Run workflow** karo.
`assets/projects.json` mein `repo` ka naam GitHub par repo ke naam se bilkul same hona chahiye (abhi `PORTFOLIO`).

## 6. Local preview

`preview.html` browser mein kholo: saari images dark aur light dono card par dikhengi.

## Photo ya banner dobara badalna ho

Naya `assets/source/photo.png` rakho (transparent background best) aur `python scripts/banner/generate.py` dobara chalao.
README mein banner ke link ke aage `?v=2` jaisa cache-bust laga dena taaki GitHub purana banner na dikhaye.
