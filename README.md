# Tauri + Svelte + Vite

This template shows cross-platform app dev.  
for Mobile devices. iOS, Android.

## Setup note

- npm create vite@latest here-for-app-name
- select svelte and java
- cd here-for-app-name
- npm install three (and what you want)
- npm install -D @tauri-apps/cli
- npx tauri init
  - Make url and port are same to the vite
  - like... http://localhost:5173/
  - if you test on lan, make front dev command 'npm run dev -- --host'
- edit package.json command "tauri": "tauri"
- edit tauri confs
  - src-tauri/tauri.conf.json
    - identifier to com.YourComp.appName
    - frontendDist to ../dist
  - src-tauri/capabilities/default.json
    - permissions
- edit vite.config.js's base path
  - base: './'

## mobile setup
- init devives.
  - npm run tauri android init
    - then src-tauri/gen/android/ is created.
    - __optionanl__ rustup target add aarch64-linux-android armv7-linux-androideabi i686-linux-android x86_64-linux-android
  - npm run tauri ios init
  - npm run tauri ios build
    - maybe build fails at first.
    - open src-tauri/gen/apple xcode proj
    - set your team and signing profiles.
    - set npm command to xcode
      - in terminal "which npm"
    - or set edit scheme... debug to release.
      - comment build phase > rust code
      - like # npm run -- tauri...
      - then ⌘+R to run proj.
    - if install succeeded but coudnt launch the app, open ios setting App > General > VPN and Devices > developer app
- then some folders are created.

## commands...  
> - npm run tauri dev
>   - if not work well, try npm run build first.
> - npm run tauri build

> - npm run tauri android dev
> - npm run tauri android build

> - npm run tauri ios dev
> - npm run tauri ios build