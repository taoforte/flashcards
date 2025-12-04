<!DOCTYPE html>
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
    #score, #final {
      font-size: 20px;
      font-weight: bold;
      margin-top: 20px;
    }
    #final {
      display: none;
    }
    #question-counter {
      font-size: 16px;
      color: #7f8c8d;
    }
  </style>
</head>
<body>
  <h1>汉字小测验</h1>
  <div id="question-counter">Question <span id="current">1</span> of <span id="total-questions">5</span></div>
  <div id="chinese">?</div>
  <input type="text" id="answer" placeholder="Enter English meaning..." autocomplete="off" />
  <br>
  <button onclick="checkAnswer()">Submit</button>
  <button onclick="skipWord()">Skip</button>
  <div id="feedback"></div>
  <div id="score">Score: 0/0</div>

  <div id="final">
    <h2>🎉 Quiz Complete!</h2>
    <p>Your final score: <span id="final-score">0</span> / 5</p>
    <button onclick="restartQuiz()">Play Again</button>
  </div>

  <script>
    // === CONFIG ===
    const QUIZ_LENGTH = 5; // ← Change this to set number of questions

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
    ];

    let currentCard = null;
    let score = 0;
    let questionNumber = 0;

    function getRandomCard() {
      if (flashcards.length === 0) {
        alert("No flashcards available!");
        return ["⚠️", "", "error"];
      }
      return flashcards[Math.floor(Math.random() * flashcards.length)];
    }

    function displayNewCard() {
      if (questionNumber >= QUIZ_LENGTH) return;

      currentCard = getRandomCard();
      document.getElementById('chinese').textContent = currentCard[0];
      document.getElementById('answer').value = '';
      document.getElementById('feedback').textContent = '';
      document.getElementById('current').textContent = questionNumber + 1;
    }

    function checkAnswer() {
      if (questionNumber >= QUIZ_LENGTH) return;

      const userAnswer = document.getElementById('answer').value.trim().toLowerCase();
      const correctAnswer = currentCard[2].toLowerCase();

      questionNumber++;
      if (userAnswer === correctAnswer) {
        score++;
        document.getElementById('feedback').innerHTML = '✅ Correct!';
        document.getElementById('feedback').className = 'correct';
      } else {
        document.getElementById('feedback').innerHTML = `❌ It means "<b>${currentCard[2]}</b>".`;
        document.getElementById('feedback').className = 'incorrect';
      }

      document.getElementById('score').textContent = `Score: ${score}/${questionNumber}`;

      if (questionNumber >= QUIZ_LENGTH) {
        // Show final screen
        setTimeout(() => {
          document.getElementById('final-score').textContent = score;
          document.getElementById('final').style.display = 'block';
          document.getElementById('chinese').style.display = 'none';
          document.getElementById('answer').style.display = 'none';
          document.querySelector('button[onclick="checkAnswer()"]').style.display = 'none';
          document.querySelector('button[onclick="skipWord()"]').style.display = 'none';
          document.getElementById('score').style.display = 'none';
          document.getElementById('question-counter').style.display = 'none';
        }, 1500);
      } else {
        setTimeout(displayNewCard, 1500);
      }
    }

    function skipWord() {
      if (questionNumber >= QUIZ_LENGTH) return;
      document.getElementById('feedback').innerHTML = `It means "<b>${currentCard[2]}</b>".`;
      document.getElementById('feedback').className = 'incorrect';
      questionNumber++;
      document.getElementById('score').textContent = `Score: ${score}/${questionNumber}`;
      
      if (questionNumber >= QUIZ_LENGTH) {
        setTimeout(() => {
          document.getElementById('final-score').textContent = score;
          document.getElementById('final').style.display = 'block';
          document.getElementById('chinese').style.display = 'none';
          document.getElementById('answer').style.display = 'none';
          document.querySelector('button[onclick="checkAnswer()"]').style.display = 'none';
          document.querySelector('button[onclick="skipWord()"]').style.display = 'none';
          document.getElementById('score').style.display = 'none';
          document.getElementById('question-counter').style.display = 'none';
        }, 1000);
      } else {
        setTimeout(displayNewCard, 1000);
      }
    }

    function restartQuiz() {
      score = 0;
      questionNumber = 0;
      document.getElementById('final').style.display = 'none';
      document.getElementById('chinese').style.display = 'block';
      document.getElementById('answer').style.display = 'inline-block';
      document.querySelector('button[onclick="checkAnswer()"]').style.display = 'inline-block';
      document.querySelector('button[onclick="skipWord()"]').style.display = 'inline-block';
      document.getElementById('score').style.display = 'block';
      document.getElementById('question-counter').style.display = 'block';
      document.getElementById('score').textContent = 'Score: 0/0';
      displayNewCard();
    }

    // Allow Enter key to submit
    document.getElementById('answer').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') checkAnswer();
    });

    // Initialize
    document.getElementById('total-questions').textContent = QUIZ_LENGTH;
    displayNewCard();
  </script>
</body>
</html>
