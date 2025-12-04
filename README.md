<!--  Floating Thumbnail Quiz Button (Right Middle) -->
<style>
  #quizLauncher {
    position: fixed;
    top: 50%;
    right: 20px;
    transform: translateY(-50%);
    background: transparent;
    border: none;
    cursor: pointer;
    z-index: 10000;
    padding: 0;
  }
  #quizLauncher img {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    box-shadow: 0 4px 8px rgba(0,0,0,0.3);
    object-fit: cover;
    transition: transform 0.2s ease-in-out;
  }
  #quizLauncher img:hover {
    transform: scale(1.1);
  }
</style>

<button id="quizLauncher" onclick="openQuiz()" title="Take Quiz">
  <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createavibranteye-catchingyoutubeblogthumbnailfeaturingafloatingquizpop-upicononadigitalblogpage5084708667809205788.jpg" alt="Take Quiz">
</button>

<!-- Quiz Modal -->
<style>
  .quiz-modal {
    display: none;
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.6);
    justify-content: center;
    align-items: center;
    z-index: 9999;
  }
  .quiz-content {
    background: #fff;
    padding: 20px;
    max-width: 500px;
    width: 90%;
    border-radius: 10px;
    font-family: sans-serif;
    position: relative;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    text-align: center;
  }
  .quiz-close {
    position: absolute;
    top: 10px; right: 15px;
    font-size: 20px;
    cursor: pointer;
  }
  .start-btn {
    background: #007bff;
    color: white;
    padding: 10px 15px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  .start-btn:hover {
    background: #0056b3;
  }
  #timer {
    font-weight: bold;
    color: #555;
  }
</style>

<div id="quizModal" class="quiz-modal">
  <div class="quiz-content">
    <span class="quiz-close" onclick="closeQuiz()">×</span>
    <!-- Thumbnail Preview in Modal -->
    <a href="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createavibranteye-catchingyoutubeblogthumbnailfeaturingafloatingquizpop-upicononadigitalblogpage5084708667809205788.jpg" target="_blank">
      <img src="https://debeatzgh.wordpress.com/wp-content/uploads/2025/08/createavibranteye-catchingyoutubeblogthumbnailfeaturingafloatingquizpop-upicononadigitalblogpage5084708667809205788.jpg" alt="Quiz Thumbnail" style="width:100%; border-radius:8px; margin-bottom:15px;">
    </a>
    <h3>🧠 Quick Quiz</h3>
    <div id="quizBody"></div>
    <button id="startBtn" class="start-btn" onclick="startQuiz()">Start Quiz</button>
    <p id="timer" style="display:none;">⏱ Time left: <span id="timeLeft">30</span>s</p>
    <p id="finalScore" style="font-weight:bold;"></p>
    <br>
    <button onclick="window.location.href='https://beatzde4.blogspot.com/'">Proceed to Blog</button>
    <button onclick="window.location.href='https://beatzde4.blogspot.com/p/htmlgenbtn-position-fixed-bottom-20px.html'">Take More Quizzes</button>
  </div>
</div>

<script>
  const quizQuestions = [
    { question: "What is Java?", answers: ["A coffee drink", "A programming language", "An island"], correct: [1] },
    { question: "Which tools are in 'Google Essentials'?", answers: ["Microsoft Office", "Apple iWork", "Gmail, Drive, Docs, Calendar"], correct: [2] },
    { question: "What does AI stand for?", answers: ["Automated Input", "Artificial Intelligence", "Applied Imaging"], correct: [1] },
    { question: "What is HTML?", answers: ["HyperText Markup Language", "HighText Machine Language", "Home Tool Markup Language"], correct: [0] },
    { question: "What is the focus of D Konsult’s blog?", answers: ["Cooking recipes", "AI, digital tools & online business", "Fashion trends"], correct: [1] },
    { question: "'Decoding AI' is about?", answers: ["Blockchain", "AI fundamentals, ML, ethics", "Vintage computing"], correct: [1] },
    { question: "Which service lets you hire freelancers from the blog?", answers: ["Uber", "Netflix", "Fiverr"], correct: [2] }
  ];

  let currentQuestion = 0, score = 0, timer, timeLeft = 30;

  function openQuiz() {
    document.getElementById("quizModal").style.display = "flex";
  }
  function closeQuiz() {
    document.getElementById("quizModal").style.display = "none";
    clearInterval(timer);
  }
  function startQuiz() {
    document.getElementById("startBtn").style.display = "none";
    showQuestion();
    startTimer();
    document.getElementById("timer").style.display = "block";
  }
  function showQuestion() {
    const q = quizQuestions[currentQuestion];
    let html = `<p><strong>Q${currentQuestion + 1}:</strong> ${q.question}</p>`;
    q.answers.forEach((ans, i) => {
      html += `<label><input type="checkbox" name="answer" value="${i}"> ${ans}</label><br>`;
    });
    html += `<br><button onclick="checkAnswer()" class="start-btn">Next</button>`;
    document.getElementById("quizBody").innerHTML = html;
  }
  function checkAnswer() {
    const selected = Array.from(document.querySelectorAll('input[name="answer"]:checked')).map(el => parseInt(el.value));
    const correct = quizQuestions[currentQuestion].correct;
    if (JSON.stringify(selected.sort()) === JSON.stringify(correct.sort())) score++;
    currentQuestion++;
    if (currentQuestion < quizQuestions.length) showQuestion();
    else endQuiz();
  }
  function startTimer() {
    timer = setInterval(() => {
      timeLeft--;
      document.getElementById("timeLeft").textContent = timeLeft;
      if (timeLeft <= 0) { clearInterval(timer); endQuiz(); }
    }, 1000);
  }
  function endQuiz() {
    clearInterval(timer);
    document.getElementById("quizBody").innerHTML = "";
    document.getElementById("finalScore").textContent = `You scored ${score} out of ${quizQuestions.length}`;
  }
</script>




> **Explore, Learn & Test Your Knowledge!**  
> Fun, challenging, and educational quizzes for **students, learners, and curious minds**.  
> Take part and **improve your knowledge online** — one quiz at a time!  

## 🧩 Choose Your Quiz

<div class="quiz-grid">

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/4248/4248757.png" alt="Accountancy Quiz">
  <h3>📘 Accountancy</h3>
  <p>Challenge your financial and accounting knowledge. Perfect for commerce students!</p>
  <a href="https://quizzory.in/id/60f309a3f264f969c42cea13" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" alt="Famous Personalities Quiz">
  <h3>🌟 Famous Personalities</h3>
  <p>How well do you know the world’s most famous icons? Test your general knowledge!</p>
  <a href="https://quizzory.in/id/60f3081695c1d3699de6d554" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/3703/3703430.png" alt="Sociology Quiz">
  <h3>📚 Sociology</h3>
  <p>Learn about society, culture, and human behavior through engaging quiz questions.</p>
  <a href="https://quizzory.in/id/60f3070a95c1d3699de6d218" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/2172/2172728.png" alt="Economics Quiz">
  <h3>💰 Economics</h3>
  <p>Explore your economic knowledge from markets to global finance.</p>
  <a href="https://quizzory.in/id/60f30571f944c2698774bb9b" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/4052/4052987.png" alt="Grammar Quiz">
  <h3>✍️ Grammar</h3>
  <p>Sharpen your English grammar and writing skills through interactive questions.</p>
  <a href="https://quizzory.in/id/60f3047995c1d3699de6cd1c" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/2329/2329986.png" alt="Agriculture Quiz">
  <h3>🌾 Agriculture</h3>
  <p>Dive into the world of crops, soil, and sustainable farming methods.</p>
  <a href="https://quizzory.in/id/60f2fc9f66f0bc69aa9c2b05" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/3039/3039433.png" alt="Inventions Quiz">
  <h3>💡 Inventions</h3>
  <p>Test your knowledge of innovations that shaped the modern world.</p>
  <a href="https://quizzory.in/id/60f30211f264f969c42cda12" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/3163/3163478.png" alt="General Quiz">
  <h3>🧠 General Knowledge</h3>
  <p>Challenge yourself with mixed questions across various topics!</p>
  <a href="https://beatzde4.blogspot.com/p/htmlgenbtn-position-fixed-bottom-20px.html" class="quiz-button">Start Quiz</a>
</div>

<div class="quiz-card">
  <img src="https://cdn-icons-png.flaticon.com/512/2891/2891491.png" alt="Flashcards">
  <h3>🎴 Flashcards</h3>
  <p>Revise quickly and learn smarter with our interactive flashcards.</p>
  <a href="https://beatzde4.blogspot.com/p/open-debeatzgh.html" class="quiz-button">Open Flashcards</a>
</div>

</div>

<a href="https://beatzde4.blogspot.com/p/htmlgenbtn-position-fixed-bottom-20px.html" class="floating-btn">🎯 View All Quizzes</a>

</div>

---

### 🧠 Why Take These Quizzes?
- ✅ Improve academic knowledge  
- ✅ Build confidence before exams  
- ✅ Engage in fun, interactive learning  
- ✅ Great for students, educators, and curious minds  

---

**© 2025 Debeatzgh Quizzes**  
*Designed for Learners, Students & Curious Minds 💡*
