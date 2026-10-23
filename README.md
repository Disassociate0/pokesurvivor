# PokéSurvivor — Offline English Fork

An unofficial English and offline-focused adaptation of **PokéSurvivor: Mundo
Misterioso**, a Pokémon survival game for the browser. This fork starts directly
in the game, saves progress in the browser, and lets attacks and buffs activate
automatically.

This is a fan project. It is not an official Pokémon product and is not
affiliated with Nintendo, Creatures Inc., GAME FREAK, or the original game
author.

## Run locally

Requires Python 3. Open a terminal in this folder and run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000> in your browser. Keep the terminal open while
playing; stop the server with **Ctrl+C** when done. The game files are served
from your computer, so the game itself does not need an internet connection.

Use the same browser and address each time to keep the same save. Progress is
stored in that browser’s local storage, not in this folder. Clearing browser
site data will erase it. To reset only this game’s save, open the browser’s
developer console on the game page and run:

```js
localStorage.removeItem('ps.save.offline')
```

Reload the page to create a fresh save.

## Publish your own GitHub Pages copy

1. Create an empty repository on your GitHub account. Do not add a README,
   license, or `.gitignore`; this project already has them.
2. In this project folder, add your new repository as `origin` and push:

   ```sh
   git remote add origin https://github.com/YOUR-NAME/YOUR-REPOSITORY.git
   git push -u origin main
   ```

   This working copy keeps the original project remote under `upstream`. Never
   push your changes to that remote.
3. In your new repository, open **Settings → Pages**. Choose **Deploy from a
   branch**, select **main** and **/(root)**, then save.
4. GitHub will show your site address in the Pages settings. Open that address.

Pages users need internet to load the site. Saves stay in each visitor’s own
browser and do not transfer between devices or GitHub accounts.

If you downloaded a ZIP without its `.git` folder, initialize a repository
before step 2:

```sh
git init -b main
git add -A
git commit -m "Prepare PokéSurvivor offline fork"
```

## Editing and rebuilding

Edit `dev.html` and files in `js/` or `css/`. `index.html` and
`js/app.min.js` are generated. After changing game code, rebuild the bundle with
Node.js and npm:

```sh
node tools/build.js --sin-seo
```

The build downloads its minifier tools through npm. Normal play and serving the
already built game need only Python 3.

## License and credits

The game source is under the [PolyForm Noncommercial 1.0.0
license](LICENSE-NONCOMMERCIAL.md). Pokémon sprites are under **CC BY-NC 4.0**;
the font is under **OFL**. These terms restrict commercial use. Keep the
[credits](CREDITS.md) and license files when sharing this fork. Pokémon and
related marks belong to their respective owners.
