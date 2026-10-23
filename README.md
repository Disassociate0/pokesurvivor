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

## License and credits

The game source is under the [PolyForm Noncommercial 1.0.0
license](LICENSE-NONCOMMERCIAL.md). Pokémon sprites are under **CC BY-NC 4.0**;
the font is under **OFL**. These terms restrict commercial use. Keep the
[credits](CREDITS.md) and license files when sharing this fork. Pokémon and
related marks belong to their respective owners.
