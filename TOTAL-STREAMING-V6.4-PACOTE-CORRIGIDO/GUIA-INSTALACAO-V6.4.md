# GUIA DE INSTALAÇÃO E ATUALIZAÇÃO — TOTAL STREAMING V6.4

## Ordem exata dos arquivos na raiz do repositório `TOTAL_STREAMING`

1. `www/index.html` (arquivo da interface — dentro da pasta `www`)
2. `package.json` (na raiz do repositório)
3. `capacitor.config.json` (na raiz do repositório)
4. `.github/workflows/build-apk.yml` (dentro das pastas `.github/workflows/`)

## O que foi corrigido nesta versão (V6.4)

- **Proteção contra tela branca ao abrir o APK:** o `loginOverlay` exibe a interface imediatamente com fallback automático caso a verificação de sessão demore ou não tenha endpoint configurado ainda, evitando tela branca silenciosa.
- **Correção de aspas e classes CSS no `www/index.html`:** corrigidos conflitos de aspas nos atributos `onerror` das rádios e canais e padronizada a classe `hud-lock-clean`.
- **Workflow limpo (`build-apk.yml`):** removido `sed` frágil com quebra de linha, atualizado `setup-java@v5` e garantida permissão `INTERNET` e `usesCleartextTraffic="true"` no `AndroidManifest.xml`.

## Como aplicar sem errar

1. Extraia o pacote ZIP no computador.
2. No GitHub (`TOTAL_STREAMING`), clique em **Add file > Upload files** e envie `package.json`, `capacitor.config.json`, a pasta `www` (com `index.html` dentro) e a pasta `.github` (com `workflows/build-apk.yml` dentro).
3. Clique em **Commit changes**.
4. Vá na aba **Actions**, aguarde o build ficar verde (ou clique em **Run workflow**).
5. Role até o final da página da execução verde, abra a seção **Artifacts**, baixe **`TOTAL-STREAMING-V6.4-APK`**, extraia o `.zip` e instale **`app-debug.apk`** no Android.
