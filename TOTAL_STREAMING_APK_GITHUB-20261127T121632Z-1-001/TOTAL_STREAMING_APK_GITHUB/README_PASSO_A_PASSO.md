# TOTAL STREAMING V6.3 — Build de APK na Nuvem (GitHub Actions)

Este pacote transforma o `Index_V6.3.html` em um aplicativo Android (`.apk`) direto nos servidores do GitHub, sem precisar instalar Android Studio.

## 1. Estrutura de pastas no repositório GitHub

Suba exatamente esta estrutura na raiz do seu repositório (recomendado: **Privado**):

```text
seu-repositorio/
├── .github/
│   └── workflows/
│       └── build-apk.yml
├── www/
│   ├── index.html          (já copiado do Index_V6.3.html)
│   └── config.js           (modelo; preenchido automaticamente no build)
├── assets/                 (opcional: ícone e splash futuros)
├── package.json
└── capacitor.config.json
```

## 2. Cadastrar os Secrets (obrigatório e seguro)

No seu repositório do GitHub, acesse:
**Settings > Secrets and variables > Actions > New repository secret**

Crie exatamente estes 2 segredos:
1. **`TS_API_URL`** — cole a URL `/exec` da implantação atual do seu Google Apps Script.
2. **`TS_API_KEY`** — cole a chave definida em `TS_API_KEY` nas Propriedades do Script do Apps Script.

> **Segurança:** nunca digite a chave real diretamente nos arquivos do repositório. O robô injeta os Secrets na hora de compilar o APK.

## 3. Gerar e baixar o APK

1. Após subir os arquivos e cadastrar os 2 Secrets, abra a aba **Actions** no GitHub.
2. Clique no workflow **Build APK TOTAL STREAMING** e depois em **Run workflow** (ou faça qualquer commit na branch `main`).
3. Aguarde cerca de 3 a 4 minutos até aparecer o ícone verde.
4. Clique na execução concluída e role até **Artifacts** para baixar **`TOTAL-STREAMING-V6.3-APK`**.
5. Extraia o ZIP no celular/TV e instale o arquivo **`app-debug.apk`**.
