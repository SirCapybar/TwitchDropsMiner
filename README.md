# Twitch Drops Miner – Docker Edition 🐳

> Dockerized version of [DevilXD’s Twitch Drops Miner](https://github.com/DevilXD/TwitchDropsMiner), with zero-UI overhead and everything you need to AFK farm Twitch drops from inside a container.

---

### ✅ Synced with Upstream

This Docker project includes **all the latest updates** from [`DevilXD/TwitchDropsMiner`](https://github.com/DevilXD/TwitchDropsMiner).

Upstream commits are regularly merged, and new Docker images are built and published automatically — so you're always running the most current version, just containerized.

---

## 📌 Purpose

This container wraps **Twitch Drops Miner**, the well-loved desktop drop farming tool by [DevilXD](https://github.com/DevilXD/TwitchDropsMiner), to make it effortless to run on **servers, VPSs, NAS setups, headless devices**, or anything else that supports Docker.

It's entirely streamless — no video or audio is fetched — so you save bandwidth while still progressing active Twitch drop campaigns ✅

You just log in with your Twitch account, choose which games you want drops from, and let it run.

---

## 🔗 Links

- 🌐 Website: [twitchdropsminer.com](https://twitchdropsminer.com)
- 🧑‍💻 Github: [TwitchDropsMiner](https://nokodo.net/github/twitchdropsminer)
- 🐙 Original Project: [github.com/DevilXD/TwitchDropsMiner](https://github.com/DevilXD/TwitchDropsMiner)
- 🐳 Docker Hub: [`nokodo/twitchdropsminer`](https://nokodo.net/dockerhub/twitchdropsminer)
- 💻 Powered by: [nokodo](https://nokodo.net)

---

## 🧰 Usage (Quickstart with Docker Compose)

```yaml
services:
  twitchdropsminer:
    container_name: twitchdropsminer
    image: nokodo/twitchdropsminer:latest
    restart: on-failure
    pull_policy: always
    user: "568:568"
    ports:
      - "5800:5800"
    environment:
      - DARK_MODE=1
      - USER_ID=568
      - GROUP_ID=568
    volumes:
      - ./config:/config
      - cache:/cache

volumes:
  cache:
```

Then run:

```bash
docker compose up -d
```

Your container will start the miner with a web interface accessible at `http://localhost:5800`.

On first launch, you'll be prompted to log in using the Twitch device-code flow. Simply follow the instructions shown in the web interface.

---

## 🔒 Login & Account Linking

You need to have your Twitch account linked to the games you want drops for:  
👉 [https://www.twitch.tv/drops/campaigns](https://www.twitch.tv/drops/campaigns)

This container keeps your login persistent via a `cookies.jar` file inside your mounted `./config` folder.

**⚠️ Do not share your cookies file. It can be used to access your Twitch account.**

---

## ⚙️ Features

These are inherited directly from the base project:

- ✅ Streamless drop progress (bandwidth-friendly)
- ✅ Smart priority/exclusion system per game
- ✅ Always picks the best stream for each campaign
- ✅ Auto-restarts drop progress as new campaigns go live
- ✅ Up to 199 streams tracked via sharded websocket
- ✅ Runs completely headless – no GUI needed

---

## 🧠 Credits

All core mining logic and functionality comes from [DevilXD/TwitchDropsMiner](https://github.com/DevilXD/TwitchDropsMiner).

The Docker implementation and containerization work is based on [fireph/TwitchDropsMiner](https://github.com/fireph/TwitchDropsMiner).

This repo combines both efforts to provide a **Docker-focused build** that runs efficiently in headless environments 💖

Massive shoutout to:

- [@DevilXD](https://github.com/DevilXD) for the original application and ongoing development
- [@fireph](https://github.com/fireph) for the Alpine/Docker adaptation
- All translators, maintainers, and contributors 🙏

If you want to support the original author — [Buy Me A Coffee](https://www.buymeacoffee.com/DevilXD) / [Patreon](https://www.patreon.com/bePatron?u=26937862)

---

## ⚠️ Disclaimer

This image is unofficial and unaffiliated with Twitch.  
It simply automates what a real user could do — no scraping, spoofing, or abuse is involved.

Still: use at your own risk.

Note: When adding a new credits line below, please add two trailing spaces at the end
of the previous line, if they aren't already there. Doing so ensures proper markdown
rendering on Github. In short: Each credits line should end with two trailing spaces,
placed past the period character at the end.

• Last line can have the two trailing spaces omitted.
• Please ensure your editor won't trim the trailing spaces upon saving the file.
• Please ensure to leave a single empty new line at the end of the file.
-->

@guihkx - For the CI script, CI maintenance, and everything related to Linux builds.  
@kWAYTV - For the implementation of the dark mode theme.  
@crocchetto - For the macOS port.  

@Bamboozul - For the entirety of the Arabic (العربية) translation.  
@Suz1e - For the entirety of the Chinese (简体中文) translation and revisions.  
@wwj010, @zhangminghao1989, @Self4215 - For the Chinese (简体中文) translation corrections and revisions.  
@Ricky103403 - For the entirety of the Traditional Chinese (繁體中文) translation.  
@LusTerCsI - For the Traditional Chinese (繁體中文) translation corrections and revisions.  
@nwvh - For the entirety of the Czech (Čeština) translation.  
@Kjerne - For the entirety of the Danish (Dansk) translation.  
@lmdpocus - For the entirety of the Dutch (Nederlandse) translation.  
@Rensoraa - For the Traditional Dutch (Nederlandse) translation corrections and revisions.  
@roobini-gamer - For the entirety of the French (Français) translation.  
@Calvineries - For the French (Français) translation revisions.  
@ThisIsCyreX - For the entirety of the German (Deutsch) translation.  
@Nagyhoho1234 - For the entirety of the Hungarian (Magyar) translation.  
@Eriza-Z - For the entirety of the Indonesian translation.  
@casungo - For the entirety of the Italian (Italiano) translation.  
@ShimadaNanaki - For the entirety of the Japanese (日本語) translation.  
@biroman -  For the entirety of the Norwegian (Norsk) translation.  
@Patriot99 - For the Polish (Polski) translation and revisions (co-authored with @DevilXD).  
@zarigata - For the entirety of the Portuguese (Português) translation.  
@Sergo1217 - For the entirety of the Russian (Русский) translation.  
@kilroy98, @flamesv - For the Russian (Русский) translation corrections and revisions.  
@Shofuu - For the entirety of the Spanish (Español) translation and revisions.  
@Forero-0 - For the Spanish (Español) translation revisions.  
@alikdb - For the entirety of the Turkish (Türkçe) translation.  
@DogancanYr, @Elderly-Emre, @Hweord - For the Turkish (Türkçe) translation corrections and revisions.  
@Nollasko - For the entirety of the Ukrainian (Українська) translation and revisions.  
@kilroy98 - For the Ukrainian (Українська) translation corrections and revisions.  
