
# 🌐 **Web-Based Chinese Flashcard Quiz**  

Here’s a **simple, self-contained web-based version** of the Chinese flashcard quiz you can run in any browser—no server, no installation, just one HTML file. It uses **vanilla JavaScript** (no frameworks) so it’s easy to understand, modify, and share with students.

### Version deployed
[https://www.taojai.com/flashcards/](https://www.taojai.com/flashcards/)


### Full code


---


*(Save this as `chinese-quiz.html` and open in a browser)*

```html
<!-- DOCTYPE html   REMOVE COMMENT TAGS ON THIS LINE BEFORE DEPLOYMENT -->
<html lang="zh-Hans">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>汉字小测验 | Chinese Quiz</title>
  <style>
    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      max-width: 600px;
      margin: 40px auto;
      padding: 20px;
      background: #f9f9f9;
      color: #333;
      text-align: center;
    }
    h1 {
      color: #2c3e50;
      margin-bottom: 30px;
    }
    #chinese {
      font-size: 48px;
      margin: 30px 0;
      color: #e74c3c;
      font-family: "Microsoft Yahei", "PingFang SC", sans-serif;
    }
    input {
      padding: 10px;
      font-size: 18px;
      width: 80%;
      margin: 10px 0;
      border: 2px solid #ccc;
      border-radius: 8px;
    }
    button {
      background: #3498db;
      color: white;
      border: none;
      padding: 12px 24px;
      font-size: 18px;
      border-radius: 8px;
      cursor: pointer;
      margin-top: 10px;
    }
    button:hover {
      background: #2980b9;
    }
    #feedback {
      margin: 20px 0;
      font-size: 20px;
      min-height: 30px;
    }
    .correct { color: #27ae60; }
    .incorrect { color: #e74c3c; }
    #score {
      font-size: 20px;
      font-weight: bold;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>汉字小测验</h1>
  <div id="chinese">?</div>
  <input type="text" id="answer" placeholder="Enter English meaning..." autocomplete="off" />
  <br>
  <button onclick="checkAnswer()">Submit</button>
  <button onclick="skipWord()">Skip</button>
  <div id="feedback"></div>
  <div id="score">Score: 0/0</div>

  <script>
    // Vocabulary: [Chinese, Pinyin, English]
    const flashcards = [
      ["你好", "nǐ hǎo", "hello"],
      ["谢谢", "xiè xie", "thank you"],
      ["电脑", "diàn nǎo", "computer"],
      ["游戏", "yóu xì", "game"],
      ["朋友", "péng you", "friend"],
      ["水", "shuǐ", "water"],
      ["饭", "fàn", "rice / meal"],
      ["学校", "xué xiào", "school"]
      // 👉 Students can add more here!
    ];

    let currentCard = null;
    let score = 0;
    let total = 0;

    function getRandomCard() {
      return flashcards[Math.floor(Math.random() * flashcards.length)];
    }

    function displayNewCard() {
      currentCard = getRandomCard();
      document.getElementById('chinese').textContent = currentCard[0];
      document.getElementById('answer').value = '';
      document.getElementById('feedback').textContent = '';
    }

    function checkAnswer() {
      const userAnswer = document.getElementById('answer').value.trim().toLowerCase();
      const correctAnswer = currentCard[2].toLowerCase();

      total++;
      if (userAnswer === correctAnswer) {
        score++;
        document.getElementById('feedback').innerHTML = '✅ Correct!';
        document.getElementById('feedback').className = 'correct';
      } else {
        document.getElementById('feedback').innerHTML = `❌ It means "<b>${currentCard[2]}</b>".`;
        document.getElementById('feedback').className = 'incorrect';
      }

      document.getElementById('score').textContent = `Score: ${score}/${total}`;
      setTimeout(displayNewCard, 1500);
    }

    function skipWord() {
      document.getElementById('feedback').innerHTML = `It means "<b>${currentCard[2]}</b>".`;
      document.getElementById('feedback').className = 'incorrect';
      setTimeout(displayNewCard, 1000);
    }

    // Start first card
    displayNewCard();

    // Allow Enter key to submit
    document.getElementById('answer').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') checkAnswer();
    });
  </script>
</body>
</html>
```

---

### ✅ **Features**
- **Instant feedback** with color-coded responses (✅/❌).
- Shows correct answer if wrong or skipped.
- Tracks live score.
- Works **offline**—just open the file in Chrome/Firefox/Safari.
- **Easy to customize**: Add/remove words in the `flashcards` array.
- **Mobile-friendly**: Works on phones and tablets.
- **Bilingual**: Title in Chinese + English; uses Chinese fonts.

---

### 🛠️ **How Students Can Extend It**
1. **Add their own vocabulary** (e.g., gaming terms, K-drama phrases):
   ```js
   ["胜利", "shèng lì", "victory"],
   ["英雄", "yīng xióng", "hero"]
   ```
2. **Switch to Pinyin-to-Chinese mode** by changing which array index is shown.
3. **Add sound** later using the Web Audio API (advanced).
4. **Save high scores** with `localStorage` (for next lesson!).

---

### 📥 **How to Use**
1. Copy all the code above.
2. Paste into a text editor (Notepad, VS Code, etc.).
3. Save as `chinese-quiz.html`.
4. Double-click the file → opens in browser → play!

> 🔐 **Privacy note**: Everything runs locally—no data leaves the device.

---

Ideas:
- A version that **loads words from a separate text file** (for easier editing)?
- A **dark mode** toggle?
- Support for **traditional characters** or **HSK levels**?

 
