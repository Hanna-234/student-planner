<!DOCTYPE html>
<html>
<head>
  <title>Student Planner - Home</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header><h1>Welcome to Your Academic Planner</h1></header>
  <section>
    <h2 id="quote">"Loading quote..."</h2>
    <button onclick="changeQuote()">New Quote</button>
  </section>
  <nav>
    <a href="subjects.html">Subjects</a>
    <a href="todo.html">To-Do List</a>
    <a href="calendar.html">Calendar</a>
    <a href="timer.html">Study Timer</a>
  </nav>
  <script src="script.js"></script>
</body>
</html>
const quotes = [
  "Success is the sum of small efforts, repeated.",
  "The secret of getting ahead is getting started.",
  "Push yourself, because no one else is going to do it.",
  "Dream big. Start small. Act now."
];

function changeQuote() {
  const index = Math.floor(Math.random() * quotes.length);
  document.getElementById("quote").textContent = quotes[index];
}

window.onload = changeQuote;
<!DOCTYPE html>
<html>
<head>
  <title>Subjects</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Your Subjects & Grades</h1>
  <ul id="subjectList"></ul>
  <script>
    fetch('subjects.json')
      .then(response => response.json())
      .then(data => {
        const list = document.getElementById('subjectList');
        data.subjects.forEach(subj => {
          const li = document.createElement('li');
          li.textContent = `${subj.name} - Grade: ${subj.grade}`;
          list.appendChild(li);
        });
      });
  </script>
</body>
</html>
{
  "subjects": [
    { "name": "Math", "grade": "A" },
    { "name": "English", "grade": "B+" },
    { "name": "Science", "grade": "A-" }
  ]
}
<!DOCTYPE html>
<html>
<head>
  <title>To-Do List</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>To-Do List</h1>
  <input type="text" id="taskInput" placeholder="New task..." />
  <button onclick="addTask()">Add</button>
  <ul id="taskList"></ul>
  <script src="todo.js"></script>
</body>
</html>
function addTask() {
  const taskInput = document.getElementById('taskInput');
  if (taskInput.value.trim() === "") return;

  const li = document.createElement('li');
  li.textContent = taskInput.value;

  li.addEventListener('click', () => {
    li.classList.toggle('done');
  });

  const removeBtn = document.createElement('button');
  removeBtn.textContent = 'X';
  removeBtn.onclick = () => li.remove();
  li.appendChild(removeBtn);

  document.getElementById('taskList').appendChild(li);
  taskInput.value = '';
}
<!DOCTYPE html>
<html>
<head>
  <title>Calendar</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Monthly Calendar</h1>
  <table border="1">
    <tr><th>Sun</th><th>Mon</th><th>Tue</th>...<th>Sat</th></tr>
    <tr><td></td><td></td><td>1</td>...<td>7</td></tr>
    <!-- Continue layout manually or generate using JS -->
  </table>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Pomodoro Timer</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Study Timer</h1>
  <div id="timer">25:00</div>
  <button onclick="startTimer()">Start</button>
  <button onclick="resetTimer()">Reset</button>
  <script src="timer.js"></script>
</body>
</html>
let time = 25 * 60;
let timer;
let running = false;

function updateDisplay() {
  const minutes = Math.floor(time / 60);
  const seconds = time % 60;
  document.getElementById("timer").textContent =
    `${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')}`;
}

function startTimer() {
  if (running) return;
  running = true;
  timer = setInterval(() => {
    if (time > 0) {
      time--;
      updateDisplay();
    } else {
      clearInterval(timer);
      alert("Time's up!");
      running = false;
    }
  }, 1000);
}

function resetTimer() {
  clearInterval(timer);
  time = 25 * 60;
  updateDisplay();
  running = false;
}

updateDisplay();
body {
  font-family: 'Arial', sans-serif;
  margin: 20px;
  padding: 0;
  background-color: #f2f2f2;
}

h1, h2 {
  color: #333;
}

nav a {
  margin: 10px;
  text-decoration: none;
  color: #0077cc;
}

button {
  margin-left: 5px;
  padding: 5px 10px;
  cursor: pointer;
}

#taskList li {
  margin: 5px 0;
  list-style: none;
}

#taskList li.done {
  text-decoration: line-through;
  color: gray;
}
