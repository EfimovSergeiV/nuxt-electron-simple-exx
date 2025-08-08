# Nuxt3 + Electron expample


# Install
```zsh

npm install
npm run dev



npx tailwindcss-cli init




npm run build
npx electron-builder --linux deb


# Чистка RC перед переустановкой в Linux
dpkg --list |grep "^rc" | cut -d " " -f 3 | sudo xargs dpkg --purge



```