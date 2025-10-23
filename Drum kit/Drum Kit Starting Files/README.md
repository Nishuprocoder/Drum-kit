# 🥁 Drum Kit

> A fun and interactive web project that lets you play drum sounds using your keyboard or mouse clicks.  
> Press the keys **w, a, s, d, j, k, l** to make some beats!

---

## 🎯 Demo / Preview

Open `index.html` in your browser — or serve the project using a simple local server — to see the Drum Kit in action.

---

## 🌟 Features

✅ Play drum sounds via **keyboard** or **mouse clicks**  
✅ Smooth **button animation** when pressed  
✅ Clean UI with **Arvo Google Font**  
✅ Easy-to-customize sound and image files  

---

## 📂 Project Structure

drum-kit/
├── index.html
├── styles.css
├── index.js
├── README.md
├── images/
│ ├── crash.png
│ ├── kick.png
│ ├── snare.png
│ ├── tom-1.png
│ ├── tom-2.png
│ ├── tom-3.png
│ └── tom-4.png
└── sounds/
├── tom-1.mp3
├── tom-2.mp3
├── tom-3.mp3
├── tom-4.mp3
├── snare.mp3
├── crash.mp3
└── kick-bass.mp3


> ⚠️ Make sure your **file names match exactly** (case-sensitive on some systems).

---

## 🚀 How to Run (Locally)

### 🅰️ Option 1 — Quick Method
Just double-click on the `index.html` file.  
If the sounds don’t load properly, try Option 2 below.

### 🅱️ Option 2 — Using a Local Server

#### Using Python
```bash
python -m http.server 8000
# Visit http://localhost:8000/

Using Node.js
npm install -g http-server
http-server -p 8000
# Visit http://localhost:8000/

🕹️ Controls / Keyboard Map
Key	Sound
w	tom-1
a	tom-2
s	tom-3
d	tom-4
j	snare
k	crash
l	kick-bass

You can also click on the on-screen buttons.

⚙️ How It Works

Each .drum button listens for a click event.

The document listens for keypress events.

Depending on the key/button pressed:

A new Audio() object plays the correct sound.

The button briefly gets a .pressed class for animation.

Example core logic:

document.querySelectorAll(".drum").forEach(button => {
  button.addEventListener("click", function() {
    const key = this.innerHTML;
    makeSound(key);
    buttonAnimation(key);
  });
});

document.addEventListener("keypress", event => {
  makeSound(event.key);
  buttonAnimation(event.key);
});

🧰 Common Issues & Fixes
1. ❌ Sound Doesn’t Play

Click anywhere on the page before pressing keys (browser policy blocks auto audio).

Make sure sound files exist and are named correctly.

Run via local server if CORS/audio issues appear.

2. ⚠️ Unmapped Keys Cause Errors

Add a safety check in buttonAnimation:

function buttonAnimation(currentKey) {
  const activeButton = document.querySelector("." + currentKey);
  if (!activeButton) return;
  activeButton.classList.add("pressed");
  setTimeout(() => activeButton.classList.remove("pressed"), 100);
}

3. 🧩 Script Loading Issues

Move the <script> tag before the closing </body> or use:

<script src="index.js" defer></script>

💡 Future Enhancements

🎚️ Volume and mute controls

🧠 Record and replay your beats

📱 Mobile/touch support

🌈 Animated visualizer

🎵 Switch between multiple drum kits

🤝 Contributing

Fork the repository

Create a new branch

git checkout -b feature/your-feature


Commit your changes

git commit -m "Add new feature"


Push and create a pull request

🪪 License & Credits

License: MIT

Font: Google Fonts - Arvo

Author: Made with ❤️ in India by [Your Name]

🎶 "When in doubt… just hit the drums!" 🥁


---

Would you like me to **personalize this README** by:
- Replacing “Your Name” with **Nishant Kumar Rai**,  
- Adding your GitHub profile link,  
- And adding a small preview image section at the top (e.g., `preview.png`)?
