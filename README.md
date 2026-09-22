<div align="center">

# Nexory Store

**App Android para baixar e instalar APKs/APKMs direto do APKMirror — Free Fire e qualquer app da loja, com atualizações pelo GitHub.**

[![Release](https://img.shields.io/github/v/release/RD7Void/NexoryStore?include_prereleases&style=for-the-badge&label=RELEASE)](https://github.com/RD7Void/NexoryStore/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/RD7Void/NexoryStore/total?style=for-the-badge)](https://github.com/RD7Void/NexoryStore/releases)
[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)](#licença)

**[⬇️ BAIXAR APK](https://github.com/RD7Void/NexoryStore/releases/latest)** ·
[📋 Releases](https://github.com/RD7Void/NexoryStore/releases) ·
[issues](https://github.com/RD7Void/NexoryStore/issues)

<img src="assets/icon/app_icon.png" width="120" alt="Nexory Store icon" />

</div>

---

## Sobre o app

Nexory Store é um cliente Android (Flutter) que consulta o **APKMirror** e instala pacotes **`.apk`** e **`.apkm`** (bundle de splits) pelo `PackageInstaller` nativo — sem root, sem ADB.

| | |
|---|---|
| **Pacote** | `com.rd7.update` |
| **Nome** | Nexory Store |
| **Plataforma** | Android 7.0+ (minSdk 24) |
| **Stack** | Flutter · Kotlin · APKMirror |
| **Idiomas** | Português, English |

### Recursos

- **Atualizador** — Free Fire (`.apkm`) com escolha de versão e arquitetura (V7A / V8A)
- **Store** — busca e vitrine de apps; chips de dispositivo (Android TV, Celular, Wear OS, Tablet, Chromebook) e formato (APK / APKM)
- **Downloads** — fila em segundo plano com notificação de progresso; **Instalar** e **Excluir** em arquivos já baixados
- **Ajustes** — idioma PT/EN, download em segundo plano, limpar cache
- **Atualização automática** — checa [Releases](https://github.com/RD7Void/NexoryStore/releases) no GitHub e avisa quando sai versão nova

---

## Download

> **[⬇️ Baixar a última versão](https://github.com/RD7Void/NexoryStore/releases/latest)**

1. Abre a página da release mais recente
2. Baixa o `.apk` do asset (ex.: `app-release.apk`)
3. Instala (ativo “Fontes desconhecidas” se o Android pedir)

<p align="center">
  <a href="https://github.com/RD7Void/NexoryStore/releases/latest">
    <img src="https://img.shields.io/badge/Download-APK-e5322d?style=for-the-badge&logo=android&logoColor=white" alt="Download APK" />
  </a>
</p>

---

## Como publicar uma atualização

Para o app avisar os usuários (notificação + popup):

1. Bump da versão no `pubspec.yaml`:
   ```yaml
   version: 1.1.0+2   # major.minor.patch+buildNumber
   ```
2. Build do release:
   ```bash
   flutter build apk --release
   ```
3. No GitHub: **Releases → Draft a new release**
   - Tag: `v1.1.0` (aceita `v` ou não)
   - Título livre
   - Anexa o `app-release.apk` como asset
4. **Publish release**

O app na próxima abertura compara a tag com a versão instalada (`package_info`) e, se for mais nova, mostra notificação e popup **Atualização disponível**.

---

## Desenvolvimento

```bash
git clone https://github.com/RD7Void/NexoryStore.git
cd NexoryStore
flutter pub get
flutter run
```

Requisitos: Flutter SDK 3.x, Android SDK (API 24+), JDK 17.

### Estrutura (resumo)

```
lib/
  app.dart                 # gate de idioma/onboarding
  main.dart                # boot
  screens/                 # Home, Store, Downloads, Ajustes, Créditos
  services/
    apk_mirror_service.dart      # scraping APKMirror + tags
    apkm_installer_service.dart  # extrai .apkm / instala splits
    download_manager.dart        # fila de downloads
    download_notification_service.dart
    github_update_service.dart   # checa Releases no GitHub
  theme/app_strings.dart   # PT/EN (todos os textos)
```

---

## Permissões

- **Notificações** — progresso de download e aviso de atualização  
- **Instalar apps** — `REQUEST_INSTALL_PACKAGES` (instalação de APK/APKM)  
- **Internet** — APKMirror e API do GitHub  

O app **não** pede armazenamento externo (usa o diretório de documents do app).

---

## Avisos

- APKMirror é fonte de terceiros; Nexory Store não hospeda binários.
- Apps de terceiros podem exigir conta Google / Cloudflare dependendo da rede.
- Instale apenas APKs em que você confia.

---

## Créditos

- **rd7void** — desenvolvimento  
- [APKMirror](https://www.apkmirror.com/) — fonte dos pacotes  
- [Flutter](https://flutter.dev) — framework  

---

## Licença

MIT — veja [LICENSE](LICENSE) se existir no repositório.  
© RD7Void · GameFF: Garena International I Pte. Ltd. (marca do jogo é de seus donos).

---

<div align="center">
  <sub>Nexory Store · feito com Flutter · releases no GitHub</sub>
</div>
