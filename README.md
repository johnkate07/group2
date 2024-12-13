<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Group 2's Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #121212;
      margin: 0;
      padding: 0;
      color: white;
    }
    h1 {
      color: #ff9800;
      font-size: 36px;
      margin-top: 50px;
      text-align: center;
    }
    p {
      font-size: 18px;
      color: #ddd;
      text-align: center;
    }
    .button {
      background-color: #6200ea;
      color: white;
      padding: 15px 30px;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s;
      margin-top: 20px;
    }
    .button:hover {
      background-color: #3700b3;
    }
    .score {
      font-size: 24px;
      font-weight: bold;
      margin-top: 20px;
      color: #ddd;
      text-align: center;
    }
    #quiz-container, #result-container, #final-score-container {
      display: none;
      text-align: center;
    }
    #quiz-container {
      margin-top: 50px;
      background-image: url('bdquiz.jpg'); /* Add your background image URL */
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      padding: 40px;
      border-radius: 8px;
    }
    #dashboard {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #121212;
      color: white;
      height: 100vh;
      background-image: url('bdfunction.jpg'); /* Add your background image URL */
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
    }
    #dashboard h2 {
      font-size: 28px;
      margin-bottom: 30px;
    }
    #dashboard p {
      font-size: 20px;
      margin-bottom: 30px;
      text-align: center;
      max-width: 400px;
    }
    #dashboard .button {
      background-color: #ff9800;
      font-size: 22px;
      margin-top: 30px;
    }
    #members-dashboard {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh; /* Full viewport height */
  color: white;
  text-align: center;
  background-image: url('bdmember.jpg'); /* Replace with your image URL */
  background-size: cover; /* Ensure the image covers the entire section */
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Prevent repeating the image */
  margin: 0; /* Ensure there's no margin causing the black space */
  padding: 0; /* Remove padding if any */
}


#members-dashboard h2 {
  font-size: 28px;
  margin-bottom: 30px;
}

#members-dashboard ul {
  list-style-type: none;
  padding: 0;
}

#members-dashboard li {
  font-size: 1.2rem;
  margin: 5px 0;
}

#members-dashboard button {
  margin-top: 20px;
}


    #result-container button {
      margin-top: 20px;
    }
    .question-container {
      background-color: rgba(51, 51, 51, 0.8); /* Semi-transparent background */
      color: white;
      margin-bottom: 30px;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      max-width: 500px;
      margin-left: auto;
      margin-right: auto;
    }
    .answers {
      list-style-type: none;
      padding: 0;
      display: flex;
      justify-content: space-evenly;
      margin-top: 20px;
      flex-wrap: nowrap;
    }

    .answer-btn {
      flex-grow: 1;
      margin: 0 5px;
      padding: 10px 20px;
      font-size: 16px;
      text-align: center;
    }

    .answer-btn:hover {
      background-color: #3700b3;
    }
    .hint-btn, .pass-btn {
      background-color: #03a9f4;
      color: white;
      padding: 10px 20px;
      margin-top: 20px;
      border-radius: 5px;
      font-size: 18px;
    }
    .hint-btn:hover, .pass-btn:hover {
      background-color: #0288d1;
    }
    .exit-btn {
      background-color: #f44336;
      color: white;
      padding: 10px 20px;
      margin-top: 20px;
      border-radius: 5px;
    }
    .exit-btn:hover {
      background-color: #d32f2f;
    }
    .timer {
      font-size: 20px;
      font-weight: bold;
      margin-top: 20px;
      color: #ff5722;
      position: absolute;
      top: 10px;
      right: 20px;
    }
    /* Responsive Design */
    @media (max-width: 768px) {
      h1 {
        font-size: 28px;
      }
      .button {
        font-size: 16px;
        padding: 12px 25px;
      }
      .score {
        font-size: 18px;
      }
      .question-container {
        width: 90%;
      }
      .answer-btn {
        width: 48%;
        padding: 12px;
        font-size: 16px;
      }
      .timer {
        font-size: 16px;
        right: 10px;
        top: 10px;
      }
    }
  </style>
</head>
<body>

  <!-- Dashboard Section -->


  <div id="dashboard">
    <h1>Welcome to Group 2's Quiz Game!</h1>
    <h2>Test your knowledge of mathematical functions!</h2>
    <p>Before starting the quiz, make sure you're ready to answer questions about function properties, domains, and more. Click "Start Quiz" to begin.</p>
    <button class="button" id="start-button">Start Quiz</button>
    <button class="button" id="members-button">Members</button>
  </div>
  
  <div id="quiz-container" style="display: none;">
    <h1>Function Game</h1>
    <div id="quiz-question"></div>
    <div class="score" id="score-container">Score: 0</div>
    <button class="hint-btn" id="hint-button" onclick="showHint()">Hint</button>
    <button class="pass-btn" id="pass-button" onclick="passQuestion()">Pass</button>
  </div>
  
  <div id="members-dashboard" style="display: none;">
    <h2> Members</h2>
    <ul id="members-list">
      <li>Loren Rabino</li>
      <li>Eilyn Manire</li>
      <li>Richeal Garcia</li>
      <li>Rey Ubaldo</li>
      <li>Leny Mae Velasco</li>
    </ul>
    <button class="button" id="back-to-dashboard">Back to Dashboard</button>
  </div>
  

  <!-- Timer -->
  <div class="timer" id="timer" style="display: none;">Time Left: 05:00</div>

  <!-- Final Score Section -->
  <div id="final-score-container">
    <h2>Final Score</h2>
    <p id="final-score-message"></p>
    <p>Your final score is: <span id="final-score"></span> / 20</p>
    <button class="button" onclick="tryAgain()">Try Again</button>
    <button class="button" onclick="exitGame()">Exit to Menu</button>
  </div>

  <script>
    // Members Button Functionality
    const membersButton = document.getElementById('members-button');
    const backToDashboardButton = document.getElementById('back-to-dashboard');
    const dashboard = document.getElementById('dashboard');
    const membersDashboard = document.getElementById('members-dashboard');
    const startButton = document.getElementById('start-button');
    const quizContainer = document.getElementById('quiz-container');

    // Show Members Dashboard
    membersButton.addEventListener('click', () => {
      dashboard.style.display = 'none';
      membersDashboard.style.display = 'block';
    });

    // Back to Dashboard
    backToDashboardButton.addEventListener('click', () => {
      membersDashboard.style.display = 'none';
      dashboard.style.display = 'flex';
    });

    // Start Quiz Button Functionality
startButton.addEventListener('click', () => {
  dashboard.style.display = 'none';
  quizContainer.style.display = 'block';
  loadQuestion();
  document.getElementById('timer').style.display = 'block';  // Show the timer
});


    const questions = [
      { question: "What is the value of f(2) for the function f(x) = 3x + 1?", answers: ["a. 5", "b. 6", "c. 7", "d. 8"], correct: "b. 6", hint: "Think about substituting x = 2 into the equation." },
      { question: "What is the domain of the function f(x) = 1/(x-2)?", answers: ["a. x ≠ 2", "b. all real numbers", "c. x > 2", "d. x < 2"], correct: "a. x ≠ 2", hint: "Consider where the function is undefined." },
      { question: "Which of the following is a quadratic function?", answers: ["a. f(x) = x + 3", "b. f(x) = x^2 + 5", "c. f(x) = 1/x", "d. f(x) = √x"], correct: "b. f(x) = x^2 + 5", hint: "Look for the highest power of x." },
      { question: "What is the range of the function f(x) = x^2?", answers: ["a. all real numbers", "b. x ≥ 0", "c. x ≤ 0", "d. x > 0"], correct: "b. x ≥ 0", hint: "Consider the output values of a squared function." },
      { question: "What is the slope of the line represented by the function f(x) = 2x + 3?", answers: ["a. 1", "b. 2", "c. 3", "d. 0"], correct: "b. 2", hint: "The slope is the coefficient of x." },
      { question: "What is the intercept of the function f(x) = -4x + 10?", answers: ["a. (0, 10)", "b. (0, -4)", "c. (10, 0)", "d. (4, 0)"], correct: "a. (0, 10)", hint: "Set x = 0 and find the value of f(x)." },
      { question: "What is the range of f(x) = x^3?", answers: ["a. all real numbers", "b. x ≥ 0", "c. x ≤ 0", "d. x > 0"], correct: "a. all real numbers", hint: "Cubic functions have a range of all real numbers." },
      { question: "Which of the following is not a function?", answers: ["a. f(x) = 2x + 1", "b. f(x) = x^2", "c. f(x) = {1, 2, 3}", "d. f(x) = √x"], correct: "c. f(x) = {1, 2, 3}", hint: "A function should have one output for each input." },
      { question: "What is the derivative of f(x) = x^2?", answers: ["a. 2x", "b. x", "c. 2x^2", "d. 0"], correct: "a. 2x", hint: "Use the power rule for derivatives." },
      { question: "What is the limit of f(x) = 1/x as x approaches 0?", answers: ["a. 0", "b. ∞", "c. -∞", "d. does not exist"], correct: "d. does not exist", hint: "Consider the behavior of the function as x approaches 0." },
      { question: "What type of function is f(x) = e^x?", answers: ["a. linear", "b. quadratic", "c. exponential", "d. logarithmic"], correct: "c. exponential", hint: "Exponential functions grow at a rate proportional to their value." },
      { question: "Which function has a maximum value?", answers: ["a. f(x) = -x^2", "b. f(x) = x^2", "c. f(x) = x", "d. f(x) = 2^x"], correct: "a. f(x) = -x^2", hint: "Look for the shape of the graph." },
      { question: "What is the integral of f(x) = 1?", answers: ["a. x", "b. x + C", "c. 1/x", "d. 0"], correct: "b. x + C", hint: "Integration adds the variable." },
      { question: "Which of the following is an odd function?", answers: ["a. f(x) = x^2", "b. f(x) = x^3", "c. f(x) = 2^x", "d. f(x) = |x|"], correct: "b. f(x) = x^3", hint: "Odd functions have symmetry about the origin." },
      { question: "What is the period of the function f(x) = sin(x)?", answers: ["a. π", "b. 2π", "c. 1", "d. 0"], correct: "b. 2π", hint: "Consider the properties of the sine function." },
      { question: "What is the inverse of f(x) = 3x + 1?", answers: ["a. f^(-1)(x) = (x - 1)/3", "b. f^(-1)(x) = (3x - 1)", "c. f^(-1)(x) = x/3 - 1", "d. f^(-1)(x) = 3/(x - 1)"], correct: "a. f^(-1)(x) = (x - 1)/3", hint: "Swap x and y, then solve for y." },
      { question: "What is the asymptote of f(x) = 1/x?", answers: ["a. x = 0", "b. y = 0", "c. both x = 0 and y = 0", "d. none"], correct: "c. both x = 0 and y = 0", hint: "Consider where the function approaches infinity." },
      { question: "What type of function is f(x) = ln(x)?", answers: ["a. linear", "b. quadratic", "c. logarithmic", "d. polynomial"], correct: "c. logarithmic", hint: "Logarithmic functions have a specific base." },
      { question: "Which of the following is a periodic function?", answers: ["a. f(x) = x", "b. f(x) = e^x", "c. f(x) = sin(x)", "d. f(x) = 1/x"], correct: "c. f(x) = sin(x)", hint: "Periodic functions repeat their values." }
    ];

    let currentQuestionIndex = 0;
    let score = 0;

    function loadQuestion() {
      const questionContainer = document.getElementById('quiz-question');
      const currentQuestion = questions[currentQuestionIndex];
      questionContainer.innerHTML = `
        <div class="question-container">
          <p>${currentQuestion.question}</p>
          <ul class="answers">
            ${currentQuestion.answers.map(answer => `<li><button class="answer-btn" onclick="checkAnswer('${answer}')">${answer}</button></li>`).join('')}
          </ul>
        </div>
      `;
    }

    function checkAnswer(selectedAnswer) {
  const currentQuestion = questions[currentQuestionIndex];
  const answerButtons = document.querySelectorAll('.answer-btn');

  // Disable the buttons after the answer is selected
  answerButtons.forEach(button => button.disabled = true);

  // Check if the answer is correct and apply color
  answerButtons.forEach(button => {
    if (button.innerText === selectedAnswer) {
      if (selectedAnswer === currentQuestion.correct) {
        button.style.backgroundColor = 'green'; // Correct answer
        score++;
      } else {
        button.style.backgroundColor = 'red'; // Incorrect answer
        // Highlight the correct answer
        answerButtons.forEach(button => {
          if (button.innerText === currentQuestion.correct) {
            button.style.backgroundColor = 'green'; // Correct answer
          }
        });
      }
    }
  });

  // Move to the next question after 1 second
  setTimeout(() => {
    currentQuestionIndex++;
    if (currentQuestionIndex < questions.length) {
      loadQuestion();
      answerButtons.forEach(button => {
        button.style.backgroundColor = ''; // Reset button color
        button.disabled = false; // Enable buttons again
      });
    } else {
      showFinalScore();
    }
  }, 1000);
}


    function showHint() {
      const currentQuestion = questions[currentQuestionIndex];
      alert("Hint: " + currentQuestion.hint);
    }

    function passQuestion() {
      alert("You passed this question.");
      currentQuestionIndex++;
      if (currentQuestionIndex < questions.length) {
        loadQuestion();
      } else {
        showFinalScore();
      }
    }

    function showFinalScore() {
      quizContainer.style.display = 'none';
      const finalScoreContainer = document.getElementById('final-score-container');
      finalScoreContainer.style.display = 'block';
      document.getElementById('final-score').innerText = score;
      document.getElementById('final-score-message').innerText = score >= 15 ? "Congratulations! You did great!" : "Better luck next time!";
    }

    function tryAgain() {
      score = 0;
      currentQuestionIndex = 0;
      document.getElementById('final-score-container').style.display = 'none';
      quizContainer.style.display = 'block';
      loadQuestion();
    }

    function exitGame() {
      finalScoreContainer.style.display = 'none';
      dashboard.style.display = 'flex';
    }

    // Timer functionality
    let timeLeft = 300; // 5 minutes in seconds
const timerElement = document.getElementById('timer');
let timerInterval; // Global variable to store the interval

// Function to update the timer display
function updateTimer() {
  if (timeLeft > 0) {
    const minutes = Math.floor(timeLeft / 60);
    const seconds = timeLeft % 60;
    timerElement.innerText = `Time Left: ${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;
    timeLeft--;
  } else {
    alert("Time's up! Your score is: " + score);
    showFinalScore();
  }
}

// Function to start the timer
function startTimer() {
  // Reset the time
  timeLeft = 300; // 5 minutes
  // Clear any existing timer
  if (timerInterval) {
    clearInterval(timerInterval);
  }
  // Start a new timer
  timerInterval = setInterval(updateTimer, 1000);
}

// Modify the loadQuestion function to reset the timer
function loadQuestion() {
  // Reset and start the timer when a new question is loaded
  startTimer();
  
  const questionContainer = document.getElementById('quiz-question');
  const currentQuestion = questions[currentQuestionIndex];
  questionContainer.innerHTML = `
    <div class="question-container">
      <p>${currentQuestion.question}</p>
      <ul class="answers">
        ${currentQuestion.answers.map(answer => `<li><button class="answer-btn" onclick="checkAnswer('${answer}')">${answer}</button></li>`).join('')}
      </ul>
    </div>
  `;
}

  </script>
</body>
</html>
![bdquiz](https://github.com/user-attachments/assets/d444f619-f64d-4651-bc4f-383f87d98c0d)
![bdmember](https://github.com/user-attachments/assets/32467e99-898c-44c4-831a-0c83d8461cd6)
![bdfunction](https://github.com/user-attachments/assets/bdb37e0b-b729-4206-af80-92cc3ea6bb92)
