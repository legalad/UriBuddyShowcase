# UriBuddy - showcase ![logo](https://github.com/legalad/UriBuddyShowcase/assets/109519711/abb6ed62-5be6-49bf-8ec8-e1cc68519249)

A mobile application that I am currently developing. The goal is to facilitate the collection, presentation and generation of data needed in the treatment of patients with urological problems. It supports activities performed both by the patient and the work of doctors. It is created in cooperation with renowned urologists. The application will be available on the Play Store at the turn of the 2nd and 3rd quarter of 2024.

## Tech Stack

**Application consists of three layers:**
  - The UI layer that displays application data on the screen.
  - The domain layer that that simplifies and reuses the interactions between the UI and data layers and cointains complex business logic.
  - The data layer that contains the business logic of your app and exposes application data.

***UI layer:***
  - User Interface built with **Jetpack Compose** and **Material Design 3**,
  - UI state is hoisted in **ViewModels** classes that holds data, expose it to the UI, and handle logic,
  - UDF pattern helps enforce separation of resposibility:
    - viewModels product UI state, contain necessary logic, handles user action and update the state,
    - UI components consume UI state and notify viewModels of user events
  - A single-activity architecture using Navigation Compose
  - Reactive UIs using Flow and coroutines for asynchronous operations

***Domain layer:***
  - ex. PDF services (generate various pdf with itext),
  - delegates common functionalities to delegate classes (in accordance with the principle of composition over inheritance)
  - and other
    
***Data layer:***
  - data layer with **repositories** each contain at the momemnt **local data source** (depending on business requirements and legal regulations, an external data source may also appear),
  - local data sources use:
    - SQLite with **Room** library,
    - **DataStore**,
  - repositories expose data using **Kotlin Coroutines** and **Kotlin Flows**

**Managing dependencies between components:**
  - Dependency injection using **Hilt** library,
  - Make dependencies easy to replace. ex., use interfaces instead of concrete implementations.


**Deffered tasks:**
  - schedules tasks with **WorkManager**,

**Ads:**
  - Displaying ads with AdMob
  - Ad types in app:
    - banner (also collapsing)
    - rewarded
    - native

**Testing:**
  - Local tests:
     - Unit tests (viewModels, repositories, datasources, daos, utility classes, domain layer use cases -> JUNIT5, Mockito)
  - Instrumented tests:
    - Integration tests (screen UI, user flow, navigation test -> JUNIT4, Mockito, Espresso)
    - End-to-end tests
  - depending on test variuos types of test doubles are used (fakes, mocks, dummies, stubs)

## Demo
(TO DO)

## Roadmap
(TO DO)

## Authors
- [@legalad](https://www.github.com/legalad)
