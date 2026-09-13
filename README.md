[README.md.md](https://github.com/user-attachments/files/32159858/README.md.md)
# 📱 Practical 2 — Android Activity Life Cycle & Basic UI

## 🎯 Aim

Develop an Android application that demonstrates **Basic UI components** and the different stages of the **Activity Life Cycle** using Logcat, Toast, and Snackbar messages.

---

## 📌 Objective

This practical focuses on the following Android concepts:

- Creating a basic Activity
- Using `TextView`
- Setting TextView properties
- Working with `ConstraintLayout`
- Generating and using a View ID
- Understanding Activity Life Cycle callbacks
- Printing messages in Logcat
- Showing Toast notifications
- Showing Snackbar notifications
- Using Android built-in color resources

---

## 🧰 Requirements

- Android Studio
- Android SDK
- Android Emulator / Android Smartphone
- Java or Kotlin
- Gradle

---

# 🖥️ 1. Basic User Interface

The application contains a `TextView` placed at the center of the Activity.

The Activity background is set to **yellow**, while the TextView displays **Hello World** with the required formatting.

### TextView Configuration

| Property | Setting |
|---|---|
| Text | `Hello World` |
| Background | `#FFFF00` |
| Text Color | `@android:color/holo_blue_bright` |
| Text Size | `27sp` |
| Text Style | Bold + Italic |
| Alignment | Center |
| ID | Generated using `@+id/...` |

### Example XML

```xml
<TextView
    android:id="@+id/textView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Hello World"
    android:textColor="@android:color/holo_blue_bright"
    android:textSize="27sp"
    android:textStyle="bold|italic"
    app:layout_constraintTop_toTopOf="parent"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintEnd_toEndOf="parent" />
```

The root `ConstraintLayout` uses:

```xml
android:background="#FFFF00"
```

This gives the Activity a yellow background.

---

# 🔄 2. Activity Life Cycle

An Activity changes its state depending on how the user interacts with the application.

The important callback methods demonstrated in this practical are:

```text
onCreate()
onStart()
onResume()
onPause()
onStop()
onRestart()
onDestroy()
```

### Life Cycle Sequence

```text
             onCreate()
                 ↓
              onStart()
                 ↓
             onResume()
                 ↓
          Activity Running
                 ↓
              onPause()
                 ↓
              onStop()
              ↙     ↘
        onRestart()  onDestroy()
             ↓
          onStart()
             ↓
          onResume()
```

The exact sequence may change depending on whether the Activity is paused, stopped, restarted, or destroyed.

---

# 📝 3. Logcat Demonstration

Each Activity Life Cycle method prints a message using Android's `Log` class.

Example:

```java
Log.d("LIFE_CYCLE", "onCreate() executed");
```

These messages can be viewed in **Android Studio → Logcat**.

### Sample Logcat Messages

```text
D/LIFE_CYCLE: onCreate() executed
D/LIFE_CYCLE: onStart() executed
D/LIFE_CYCLE: onResume() executed
D/LIFE_CYCLE: onPause() executed
D/LIFE_CYCLE: onStop() executed
D/LIFE_CYCLE: onRestart() executed
D/LIFE_CYCLE: onDestroy() executed
```

> **📸 Screenshot — Logcat Output**
>
> Add your own screenshot here after running the application.
>
> `![Logcat Output](images/logcat.png)`

---

# 🍞 4. Toast Message

A Toast displays a short temporary message on the screen.

Example:

```java
Toast.makeText(
    this,
    "onCreate() executed",
    Toast.LENGTH_SHORT
).show();
```

Toast messages are useful for giving quick feedback to the user without changing the current Activity.

> **📸 Screenshot — Toast Output**
>
> Add your Toast screenshot here.
>
> `![Toast Message](images/toast.png)`

---

# 🟫 5. Snackbar Message

A Snackbar displays a message near the bottom of the Activity.

Example:

```java
Snackbar.make(
    findViewById(android.R.id.content),
    "onResume() executed",
    Snackbar.LENGTH_SHORT
).show();
```

Unlike a Toast, a Snackbar can also contain an action button.

> **📸 Screenshot — Snackbar Output**
>
> Add your Snackbar screenshot here.
>
> `![Snackbar Message](images/snackbar.png)`

---

# 🧩 6. ConstraintLayout

`ConstraintLayout` is used as the main layout for arranging the TextView.

The TextView is centered by applying constraints to the four sides of the parent:

```xml
app:layout_constraintTop_toTopOf="parent"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintStart_toStartOf="parent"
app:layout_constraintEnd_toEndOf="parent"
```

This allows the TextView to remain in the center of the Activity.

---

# 🆔 7. TextView ID

An ID is assigned to the TextView so that it can be accessed from the Activity code.

Example:

```xml
android:id="@+id/textView"
```

The `@+id` syntax creates a new ID resource.

The View can then be accessed in Java/Kotlin using its generated resource ID.

---

# 🛠️ 8. Practical Workflow

1. Create a new Android Studio project.
2. Create the Activity layout.
3. Add a `ConstraintLayout`.
4. Add a `TextView`.
5. Generate an ID for the TextView.
6. Set the text to `Hello World`.
7. Apply the required color, size, bold, and italic properties.
8. Set the Activity background to yellow.
9. Override the Activity Life Cycle methods.
10. Add Logcat messages to each callback.
11. Add Toast messages.
12. Add Snackbar messages.
13. Run the application on an emulator or Android device.
14. Perform Activity transitions and observe the Life Cycle messages.

---

# 📸 9. Output Screenshots

`img1.png`
`img2.png`

# 📚 10. Concepts Learned

| Concept | Purpose |
|---|---|
| TextView | Displays text on the Activity |
| ConstraintLayout | Arranges UI elements using constraints |
| TextView ID | Provides a unique reference to the View |
| `textSize` | Controls the size of text |
| `textColor` | Changes text color |
| `textStyle` | Applies bold and italic formatting |
| Activity | Represents an Android application screen |
| `onCreate()` | Initializes the Activity |
| `onStart()` | Called when the Activity becomes visible |
| `onResume()` | Called when the Activity becomes active |
| `onPause()` | Called when the Activity starts losing focus |
| `onStop()` | Called when the Activity is no longer visible |
| `onRestart()` | Called when a stopped Activity starts again |
| `onDestroy()` | Called before the Activity is destroyed |
| Logcat | Displays application log messages |
| Toast | Displays a short temporary notification |
| Snackbar | Displays a message at the bottom of the screen |

---

# ▶️ 11. How to Run

1. Open the project in Android Studio.
2. Wait for Gradle synchronization to finish.
3. Select an emulator or connect an Android device.
4. Build the project.
5. Click **Run**.
6. Verify the Hello World UI.
7. Open and close/minimize the Activity to trigger life-cycle callbacks.
8. Open **Logcat** and filter using the application's log tag.
9. Observe the Toast and Snackbar messages.
10. Capture screenshots of the outputs.

---

# ✅ Result

The Android application was successfully implemented to demonstrate **Basic UI and Activity Life Cycle**. The application displays the required TextView and demonstrates Activity Life Cycle callbacks through **Logcat, Toast, and Snackbar messages**.

