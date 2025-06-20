# Notes-App
A starter notes app that I created when I was 11. It was something that I was working on while learning the different concepts of Android Studio. It is an Android Notes application built with Java using Android Studio 2021 and API 30. The app allows users to create, view, edit, and delete text-based notes. Data persistence is handled using `SharedPreferences`.

## 🚀 Features

* View a list of saved notes.
* Create a new note via the options menu.
* Edit a note by tapping on it.
* Delete a note with a long press and confirmation dialog.
* Persist notes between app launches using `SharedPreferences`.

---

## 🛠 Technologies Used

* Java
* Android SDK
* AndroidX AppCompat Library
* SharedPreferences (for simple persistent storage)
* `ArrayAdapter` and `ListView` for note display

---

## 🔍 How It Works

* On app launch, notes are retrieved from `SharedPreferences` and shown in a `ListView`.
* Selecting a note starts `NoteEditorActivity` with the note ID passed via intent.
* Long-pressing a note opens a confirmation dialog to delete the note.
* A menu option in the action bar allows adding a new note.
* When notes are added or removed, the updated list is saved back to `SharedPreferences` using a `HashSet<String>`.

---

## 📦 Data Persistence

The app stores all notes locally using:

```java
SharedPreferences sharedPreferences = getApplicationContext().getSharedPreferences("com.example.notes", Context.MODE_PRIVATE);
sharedPreferences.edit().putStringSet("notes", set).apply();
```

> Note: `SharedPreferences` with `StringSet` does not guarantee order. This can lead to unpredictable behavior with note order.

---

## 📌 TODO

* Implement and include `NoteEditorActivity` for note editing functionality.
* Replace `SharedPreferences` with a more scalable solution like Room Database for larger datasets.
* Improve UI/UX with Material Design components.
* Add note timestamps and sorting options.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
