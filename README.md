# 📝 Vue Task Tracker

This is a simple task management app built with **Vue 3 Composition API**, designed as part of my personal learning journey. It uses `script setup`, component communication via `props` and `emits`, `reactive` state management, and persists data with **localStorage**.

> ⚠️ This project is built purely for educational purposes and exploration of Vue 3. It’s not meant for production use (yet 😉).

---

## 🚀 Features

- Add tasks dynamically
- Track completion with checkboxes
- Dynamically update task status (`Pending` / `Done`)
- Remove individual tasks
- Store tasks in localStorage (data persists on refresh)
- Reactive rendering without reloading all elements
- Simple, component-based structure

---

## 🛠 Tech Stack

- [Vue 3](https://vuejs.org/) — Composition API + `<script setup>`
- [Vite](https://vitejs.dev/) — fast dev server
- JavaScript (ES6+)
- HTML & CSS
- LocalStorage

---

## 📁 Project Structure

```bash
 simp/
├── public/
│   └── vite.svg
├── src/
│   ├── assets/
│   │   └── vue.svg
│   ├── components/
│   │   ├── MyDate.vue        # (optional UI widget for date display)
│   │   ├── Todo.vue          # main task manager logic
│   │   ├── TodoItem.vue      # reusable task item
│   │   └── UserInput.vue     # input field for new tasks
│   ├── App.vue               # root app shell
│   └── main.js               # app entry point
├── style.css                 # global styles
├── index.html                # app entry
├── package.json              # dependencies & scripts
├── vite.config.js            # vite config
└── README.md                 # you're here 👋
```

## 🧠 What I Learned

- Basics of Vue 3's Composition API  
- Building reusable components  
- State management using `reactive` and `ref`  
- Watching state changes using `watch()`  
- Emitting and listening to custom events  
- Saving and loading data from `localStorage`  
- Dynamic class binding  

---

## 🙏 A Note

This app is a sandbox for learning, so expect the code to be readable but not yet optimized for scale.  
The purpose is to **learn by doing**, not to perfect the UI/UX.

---

## 📬 Feedback & Contact

If you’re also learning Vue and want to chat, feel free to fork the repo or hit me up via GitHub Issues.

