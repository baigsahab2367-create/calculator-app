# My Calculator App (Kotlin + XML) — Offline

A beginner-friendly Android app with:
- Full calculator (add, subtract, multiply, divide, percentage, backspace, clear)
- Income & Expense Tracker (add entries, see totals + balance, history list)
- 100% offline — data saved locally using SharedPreferences (JSON)

## How to open in Android Studio

1. Open **Android Studio**.
2. Choose **File > Open**, then select this `MyCalculatorApp` folder.
3. Wait for Gradle to sync (it will download dependencies — do this once while online).
4. Click **Run ▶** to install on an emulator or a connected phone.

After the first Gradle sync, the app works completely offline — no internet needed to use it.

## Project structure

```
MyCalculatorApp/
├─ app/
│  ├─ build.gradle
│  └─ src/main/
│     ├─ AndroidManifest.xml
│     ├─ java/com/example/mycalculator/
│     │    ├─ MainActivity.kt        -> Calculator logic
│     │    ├─ TrackerActivity.kt     -> Income/Expense logic + save/load
│     │    └─ TrackerAdapter.kt      -> RecyclerView list adapter
│     └─ res/
│        ├─ layout/
│        │    ├─ activity_main.xml       -> Calculator UI
│        │    ├─ activity_tracker.xml    -> Tracker UI
│        │    └─ item_transaction.xml    -> One row in history list
│        ├─ values/
│        │    ├─ colors.xml
│        │    ├─ strings.xml
│        │    ├─ styles.xml
│        │    └─ themes.xml
│        └─ mipmap-anydpi-v26/ -> app icon
├─ build.gradle
├─ settings.gradle
└─ gradle.properties
```

## How it works

- **Calculator (MainActivity.kt):** Number buttons build up the current value as text.
  Tapping +, −, ×, ÷ stores the first number + operator; tapping "=" computes the result.
  "%" divides the current number by 100. "C" clears everything, "⌫" deletes last digit.

- **Tracker (TrackerActivity.kt):** Enter a title + amount, tap "Add Income" or
  "Add Expense". Every entry is stored in a list and shown via RecyclerView.
  All entries are converted to JSON and saved in SharedPreferences, so your data
  is still there next time you open the app — no internet required.

- Tap **"Income/Expense Tracker"** button on the calculator screen to switch screens.

Enjoy! 🎉
