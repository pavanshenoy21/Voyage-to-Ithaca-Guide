# ⚓ Voyage to Ithaca: A Beginner's Guide to CTFs 🏛️

Welcome aboard, traveler! 🌊 This guide is for first-year students who have never played a CTF before. Read it before the event and you'll know what to expect, what to install, and where to start. Even Odysseus needed a map. 🗺️

---

# 🚩 What is a CTF?

A Capture The Flag (CTF) is a gamified cybersecurity competition where participants hunt for hidden strings of text called **flags** to earn points. To find them, you apply real-world cybersecurity techniques on a scaled-down, safe, legal playground built just for this.

Think of it as a treasure hunt 🏴‍☠️ where the treasure is a piece of text and the map is a puzzle made of files, websites, code, and clues.

# 🏁 What is a Flag?

A flag is the secret string that proves you solved a challenge. Once you find it, you submit it on the CTF platform and the points are yours. 🎉

For Voyage to Ithaca, every flag looks like this:

```
rvcectf{this_is_an_example_flag}
```

A few things to remember:

* 🔤 The flag format is always `rvcectf{...}`
* 🔠 Flags are **case sensitive**. Copy them exactly as you find them.
* 🤔 If what you found doesn't start with `rvcectf{`, you probably haven't finished the challenge yet. Keep going!

# 🧩 How a Challenge Works

Each challenge gives you a description, sometimes with files to download or a link to a service. Your job is to figure out what's hidden, decode or exploit it, and extract the flag. Harder challenges are worth more points ⭐. Some come with hints 💡, and it's worth reading them.

You don't need to know everything. Nobody does. Most of CTF is searching, experimenting, and learning on the fly. Googling is part of the game. 🔍

# 🛠️ Setup

If you are on Windows 🪟, install [**Windows Subsystem for Linux (WSL)**](https://www.youtube.com/watch?v=9gT6vO_W6x0) before the event. Many CTF tools are command-line utilities built for Linux, and WSL gives you a Linux terminal 🐧 without leaving Windows. Linux and macOS users are good to go.

Make sure you also have Python 🐍 installed, a modern browser, and a text editor.

---

# 🗡️ Verticals of Cybersecurity

Challenges are grouped into **verticals** (categories). Here's a quick tour of each one, with some tools to get you started.

## 🖼️ Steganography

### What is it?

Steganography is the art of hiding data inside another file, such as a secret message tucked inside an image, audio clip, or archive. The file looks completely normal, but there's more inside than meets the eye. 👀

### Tools

* `strings` (Ubuntu WSL: `sudo apt update && sudo apt install binutils -y`) - Extracts readable text from any file. Sometimes the secret is just sitting there in plaintext.
* `steghide` (Ubuntu WSL: `sudo apt-get install steghide`) - Extracts data hidden inside images and audio.
* `zsteg` (Ubuntu WSL: `sudo apt install ruby ruby-dev build-essential -y && sudo gem install zsteg`) - Finds data hidden in the color channels of PNG and BMP images.
* `binwalk` (Ubuntu WSL: `sudo apt-get install binwalk`) - Detects and extracts files embedded inside other files.
* [Audacity](https://www.audacityteam.org/download/) 🎧 - Lets you view an audio file's spectrogram, where data can be hidden visually.
* [7-Zip](https://7-zip.org/download.html) / [WinRAR](https://www.rarlab.com/download.htm) 📦 - For opening and extracting compressed archives.

## 🔐 Cryptography

### What is it?

Cryptography is the practice of hiding information by converting readable data into something that looks meaningless. In CTFs, you'll be given scrambled, encoded, or encrypted text and asked to work out how to reverse it. 🗝️

### Tools

* [CyberChef](https://www.cyberchef.org) and [dCode](https://www.dcode.fr) 🧪 - The Swiss Army knives of crypto. They handle a huge range of encodings, ciphers, and hashes.
* [CrackStation](https://crackstation.net/) - Looks up precomputed hashes of commonly used passwords.
* Python 🐍 - When the puzzle needs custom logic, a short script goes a long way.

## 🕵️ OSINT

### What is it?

OSINT stands for **Open Source Intelligence**: gathering information from publicly available sources. Picture following someone's public trail online, where one post leads to the next clue and eventually reveals something that wasn't obvious at first. 🧵

### Tools

* 🔎 Google Search, Google Lens, and Google Maps
* 📱 Social platforms such as [Instagram](https://www.instagram.com), [Reddit](https://www.reddit.com), and [Discord](https://www.discord.com)
* 🕰️ [Internet Archive / Wayback Machine](https://archive.org/) - Browse old versions of websites that have since changed or vanished.

## 📡 Network Security

### What is it?

Network security is about protecting a network's infrastructure, traffic, and data from unauthorized access or misuse. In CTFs, you'll usually be handed a recording of network traffic and asked to dig through it for something that shouldn't be there. 🕸️

### Tools

* [Wireshark](https://www.wireshark.org/download.html) 🦈 - Capture and inspect individual data packets.
* `tshark` (Ubuntu WSL: `sudo apt-get install wireshark tshark`) - Wireshark's command-line cousin.

## 🌐 Web Exploitation

### What is it?

Ever opened **Inspect Element** and edited a webpage? That's a tiny taste of web exploitation. It's about understanding how web applications work and spotting weaknesses in how they're built, such as pages that trust the user too much or expose things they shouldn't. 🚪

### Tools

Everything you need to start lives in your browser's Developer Tools (press F12):

* 💻 **Console** - Run JavaScript directly on the page.
* 📁 **Sources** - View the site's files, like `index.html`, `styles.css`, and `script.js`.
* 📶 **Network** - See every request your browser sends and every response it gets back.
* 🍪 **Application** - Inspect cookies, local storage, and other stored data.

## ⚙️ Reverse Engineering

### What is it?

Reverse engineering means taking apart a finished program to understand how it works without having the original source code. You'll study its structure and logic to figure out what it's doing and what it expects from you. 🔧

### Tools

* `uncompyle6` (`pip install uncompyle6`) and `decompyle3` (`pip install decompyle3`) - Decompile Python bytecode back into readable code.
* `dis` - Python's built-in disassembler.

## 🤖 AI / ML

### What is it?

These challenges involve machine learning models and the data around them. You might analyze a model's behavior, dig into its files, or reason about how it was built. A little curiosity and some Python go a long way here. 🧠

### Tools

* 🐍 Python, with libraries like `numpy` and `pandas`
* 📓 Jupyter Notebook or Google Colab

## 🏎️ Competitive Programming

### What is it?

Competitive programming is about solving problems with efficient code under constraints. In a CTF, it often shows up blended with another vertical, so expect to write a bit of code to get your flag. ⚡

### Tools

* ⌨️ Any language you're comfortable with. Python or C++ are great choices.

---

# 💡 Tips for Your First CTF

* 🍃 **Start with the easy ones.** Points add up, and early wins build confidence.
* 📖 **Read the description carefully.** Every word may be a clue.
* 👁️ **Check the obvious first.** File names, metadata, page source, and plain text.
* 📝 **Take notes.** Write down what you've already tried so you don't repeat it.
* 🤝 **Work as a team.** Split up challenges, then share ideas within your own team.
* 🧗 **Don't be afraid to get stuck.** Being stuck is where the learning happens.

Good luck, and fair winds on your voyage to Ithaca! ⛵🌅
