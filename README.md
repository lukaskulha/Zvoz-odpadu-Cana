# Zvoz odpadu Čaňa – moved

The waste collection app for Čaňa is now part of one app for several villages:

**https://zvoz-odpadu.netlify.app/cana/**

Source code: https://github.com/lukaskulha/zvoz-odpadu

This repository only keeps the old address (https://zvoz-odpadu-cana-kosit.netlify.app/) working: Netlify redirects every request
to the new app (see `netlify.toml`), and `sw.js` removes the old offline copy from phones
where the app was installed.
