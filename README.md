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
  - src-tauri/capabilities/default.json
    - permissions

## mobile setup
- init devives.
  - npm run tauri android init
  - then src-tauri/gen/android/ is created.
  - __optionanl__ rustup target add aarch64-linux-android armv7-linux-androideabi i686-linux-android x86_64-linux-android
  - npm run tauri ios init
- then some folders are created.

## commands...  
> - npm run tauri dev
> - npm run tauri build

> - npm run tauri android dev
> - npm run tauri android build