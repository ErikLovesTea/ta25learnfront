# Front-endi harjutus: JavaScripti moodulid

Õppeprojekt, mis kasutab Vite'i, `mathjs` teeki ja CSS-i animatsiooni.

Leht kuvab tehte `4 + 5` tulemuse animeeritud värviüleminekuga taustal.

## Käivitamine

Vaja on Node.js-i ja npm-i. Lukufailis oleva Vite'i Node.js-i nõue on `^20.19.0 || >=22.12.0`.

```sh
npm ci
npx vite
```

Ava Vite'i kuvatud kohalik aadress. Lehe keskel ja brauseri konsoolis peaks olema tulemus `9`.

Tootmisversiooni koostamiseks:

```sh
npx vite build
```

Väljund tekib kausta `dist/`. Projektis puuduvad npm-i `dev` ja `build` skriptid, seetõttu kutsutakse Vite'i otse.

## Failid

- [index.html](index.html) — lehe struktuur ja tulemuse kuvamine.
- [index.js](index.js) — liitmine `mathjs` abil ja tulemuse eksport.
- [style.css](style.css) — paigutus ja taustaanimatsioon.
