<div align="center">
  <img src="assets/app-icon.png" alt="World Rank Challenge app icon" width="160" />

  # World Rank Challenge — App Showcase

  **A geography strategy game for iPhone where country knowledge, ranking intuition, and careful category choices determine your score.**

  [View on the App Store](https://apps.apple.com/tr/app/world-rank-challenge/id6798357229)
</div>

> This public repository is a product and engineering showcase. The production source code remains private and proprietary.

## Overview

World Rank Challenge turns real-world country rankings into a strategic eight-round game. A country is drawn each round and must be placed into one unused category. The country's real ranking becomes the score for that slot, and the lowest final total wins.

Players can compete with all 193 UN member countries in World Mode or focus on 45 European countries in Europe Mode.

## App Store Screenshots — English

<p align="center">
  <img src="screenshots/en/01-Where-Does-It-Rank.png" alt="World Rank Challenge gameplay in English" width="31%" />
  <img src="screenshots/en/02-Three-Ways-To-Play.png" alt="Free, Daily, and Weekly game modes" width="31%" />
  <img src="screenshots/en/03-The-Lower-The-Better.png" alt="Eight-round score summary" width="31%" />
</p>

<p align="center">
  <img src="screenshots/en/04-Compete-Around-The-World.png" alt="Global rankings and leaderboards" width="31%" />
  <img src="screenshots/en/05-Track-Your-Progress.png" alt="Player profile and medals" width="31%" />
</p>

## App Store Screenshots — Türkçe

<p align="center">
  <img src="screenshots/tr/01-Sence-Kacinci-Sirada.png" alt="World Rank Challenge Türkçe oyun ekranı" width="31%" />
  <img src="screenshots/tr/02-Uc-Farkli-Oyun-Modu.png" alt="Serbest, Günlük ve Haftalık oyun modları" width="31%" />
  <img src="screenshots/tr/03-En-Dusuk-Puani-Topla.png" alt="Sekiz turluk puan özeti" width="31%" />
</p>

<p align="center">
  <img src="screenshots/tr/04-Dunya-Siralamasinda-Yaris.png" alt="Dünya sıralaması ve liderlik tablosu" width="31%" />
  <img src="screenshots/tr/05-Gelisimini-Takip-Et.png" alt="Oyuncu profili ve madalyalar" width="31%" />
</p>

## Product Highlights

- World Mode with 193 UN member countries
- Europe Mode with 45 European countries
- Free Play, Daily Challenge, and Weekly Challenge modes
- Eight ranking categories per game with one-time slot usage
- Global World and Europe leaderboards
- Player profiles, best scores, statistics, and medal history
- Separate World and Europe challenge attempts and achievements
- Guest play plus Google and Apple authentication
- English and Turkish localization
- Premium subscription and purchase restoration
- Consent-aware advertising and configurable game audio

## How It Works

1. Choose World or Europe and select Free, Daily, or Weekly play.
2. Receive a randomly drawn country in each of eight rounds.
3. Place the country into one remaining ranking category.
4. Earn points equal to the country's real position in that category.
5. Finish all eight rounds with the lowest total score possible.
6. Compare results on leaderboards and track medals in the player profile.

## Engineering Overview

The app combines a local ranking-based game engine with cloud-backed identity, profiles, competitive challenges, and scheduled medal awards.

```mermaid
flowchart LR
    UI[Expo / React Native UI] --> GAME[Ranking Game Engine]
    GAME --> DATA[World & Europe Ranking Data]
    GAME --> LOCAL[AsyncStorage]
    UI --> AUTH[Firebase Authentication]
    AUTH --> DB[Cloud Firestore]
    DB --> RANK[Leaderboards & Profiles]
    DB --> CHALLENGE[Daily & Weekly Challenges]
    FUNCTIONS[Cloud Functions] --> CHALLENGE
    FUNCTIONS --> MEDALS[Scheduled Medal Awards]
    IAP[StoreKit / React Native IAP] --> PREMIUM[Premium Entitlement]
    ADS[Google Mobile Ads] --> PREMIUM
```

### Selected Engineering Challenges

- Modeling rankings whose scoring direction differs by category
- Supporting separate World and Europe datasets and statistics
- Preserving legacy player data while introducing mode-specific profiles
- Enforcing challenge attempts and score integrity with Firestore rules
- Awarding Daily and Weekly medals through scheduled Cloud Functions
- Supporting guest, Google, and Apple authentication flows
- Localizing the full experience in English and Turkish
- Coordinating subscriptions, purchase restoration, ads, and consent flows
- Preparing native iOS builds and App Store releases with Expo EAS

## Technology Stack

- TypeScript
- React Native
- Expo
- Firebase Authentication
- Cloud Firestore
- Firebase Cloud Functions
- Async Storage
- React Native IAP / StoreKit
- Google Mobile Ads
- Expo EAS Build

## Availability

World Rank Challenge is available on the Turkish App Store:

**[Download World Rank Challenge on the App Store](https://apps.apple.com/tr/app/world-rank-challenge/id6798357229)**

The app interface supports both English and Turkish.

## Developer

Built by [Harun İlker Kaya](https://github.com/HarunIlkerKaya), a Software Engineering student focused on mobile, frontend, and cloud-connected product development.

## Source Code and Rights

The production source code is maintained in a private repository. This showcase contains promotional images and high-level technical documentation only. It does not grant permission to reproduce the application, branding, datasets, or visual assets.

See [NOTICE.md](NOTICE.md) for details.
