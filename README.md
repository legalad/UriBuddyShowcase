# UriBuddy - showcase ![logo](https://github.com/legalad/UriBuddyShowcase/assets/109519711/abb6ed62-5be6-49bf-8ec8-e1cc68519249)

A mobile application that I am currently developing. The goal is to facilitate the collection, presentation and generation of data needed in the treatment of patients with urological problems. It supports activities performed both by the patient and the work of doctors. It is created in cooperation with renowned urologists. The application will be available on the Play Store at the turn of the 2nd and 3rd quarter of 2024.

#### Current dev stage - *during internal tests*

## Demo (tech stack below)
<img src="https://github.com/legalad/UriBuddyShowcase/assets/109519711/6a81afe1-7adc-4f62-bfc0-85f697ee64f2" height="400"/>
<img src="https://github.com/legalad/UriBuddyShowcase/assets/109519711/a55a9c59-1b01-49d3-812d-cebb2d7f4ac7" height="400"/>
<img src="https://github.com/legalad/UriBuddyShowcase/assets/109519711/444bf792-d95e-42b1-a95b-5db50a7d53f6" height="400"/>
<img src="https://github.com/legalad/UriBuddyShowcase/assets/109519711/3f152025-bf7d-4302-b504-51631f0001fb" height="400"/>
<img src="https://github.com/legalad/UriBuddyShowcase/assets/109519711/cba16d2c-ab74-422a-8e95-bae03f31654a" height="400"/>

## Features
- Quick overview:
  - urination diary (pees, leaks, intakes)
  - psa,
  - questionnaires (IPSS, IIEF5),
  - medicines,
  - medical interviews,
  - documents
- Common functionalities (for each modules mentioned above):
  - forms (validation, user friendly)
  - dashboards (display data in bar chart, line chart, and list views, data could be filtered fe. by date, grouped, etc.)
  - data could be shared or exported to pdf reports
- Settings:
  - multi-language support (english, french, german, polish, indonesian, portuguese, spanish, russian, arabic, chinese)
  - multi-display modes (light, dark, dynamic)
  - units of measure (metric, imperial)
- Animations:
  - content,
  - loading state (ex. shimmer effect)
  - etc.

## Tech Stack

**Application consists of three layers:**
  - The UI layer that displays application data on the screen.
  - The domain layer that simplifies and reuses the interactions between the UI and data layers and contains complex business logic.
  - The data layer that contains the business logic of your app and exposes application data.

***UI layer:***
  - User Interface built with **Jetpack Compose** and **Material Design 3**,
  - UI state is hoisted in **ViewModels** classes that hold data, expose it to the UI, and handle logic,
  - UDF pattern helps enforce separation of resposibility:
    - viewModels product UI state, contain necessary logic, handles user action and updates the state,
    - UI components consume UI state and notify viewModels of user events
  - A single-activity architecture using Navigation Compose
  - Reactive UIs using Flow and coroutines for asynchronous operations

***Domain layer:***
  - ex. PDF services (generate various pdf with itext),
  - delegates common functionalities to delegate classes (in accordance with the principle of composition over inheritance)
  - and other
    
***Data layer:***
  - data layer with **repositories** each contain at the moment **local data source** (depending on business requirements and legal regulations, an external data source may also appear),
  - local data sources use:
    - SQLite with **Room** library,
    - **DataStore**,
  - repositories expose data using **Kotlin Coroutines** and **Kotlin Flows**

**Managing dependencies between components:**
  - Dependency injection using **Hilt** library,
  - Make dependencies easy to replace. ex., use interfaces instead of concrete implementations.


**Deferred tasks:**
  - schedules tasks with **WorkManager**,

**Ads:**
  - Displaying ads with AdMob
  - Ad types in app:
    - banner (also collapsing)
    - rewarded
    - native

**Testing:**
  - Local tests:
     - Unit tests (viewModels, repositories, data sources, daos, utility classes, domain layer use cases -> JUNIT5, Mockito)
  - Instrumented tests:
    - Integration tests (screen UI, user flow, navigation test -> JUNIT4, Mockito, Espresso)
    - End-to-end tests
  - depending on test various types of test doubles are used (fakes, mocks, dummies, stubs)

## Generated PDF example
<embed src="https://github.com/legalad/UriBuddyShowcase/files/15313161/QUESTIONNAIRES_URI_BUDDY.pdf" width="800px" height="1600px"/>

[QUESTIONNAIRES_URI_BUDDY.pdf](https://github.com/legalad/UriBuddyShowcase/files/15313161/QUESTIONNAIRES_URI_BUDDY.pdf)


## Roadmap
- perform closed test of app
- perform open test of app
- publish app on Play Store

## Authors
- [@legalad](https://www.github.com/legalad)
