

## Adicionar as Dependências

```
npm install
```

Gerar o Executável

npm run package

Isso criará uma pasta dist/ contendo o executável.

Extras

Para Mac: Adicione --platform=darwin

Para Linux: Adicione --platform=linux

Para Ícone: Use --icon=icon.png (substitua icon.png pelo caminho do ícone)

Para criar um instalador para sua aplicação desktop, você pode usar o Electron Forge ou o Electron Builder. O Electron Builder é mais recomendado porque suporta pacotes para Windows (.exe), Mac (.dmg) e Linux (.AppImage ou .deb).

Instalar o Electron Builder

No terminal, dentro do seu projeto Electron, execute:

npm install --save-dev electron-builder

Configurar o package.json

Abra o arquivo package.json e adicione a configuração do electron-builder:


"build": {
  "appId": "com.seuapp.desktop",
  "productName": "Meu App",
  "win": {
    "target": "nsis",
    "icon": "icon.ico"
  },
  "mac": {
    "target": "dmg",
    "icon": "icon.icns"
  },
  "linux": {
    "target": "AppImage",
    "icon": "icon.png"
  }
},
"scripts": {
  "start": "electron .",
  "dist": "electron-builder"
}

Substitua icon.ico, icon.icns e icon.png pelo caminho do ícone da sua aplicação.

Gerar o Instalador

Agora, no terminal, execute:


npm run dist

Isso criará uma pasta dist/ contendo os instaladores:

Windows: .exe

Mac: .dmg

Linux: .AppImage ou .deb
