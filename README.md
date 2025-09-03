# stopwatch
Vimala Rani A

212223040240

III-year(CSE)

## Question:

Create a Stopwatch Application using HTML, CSS, and JavaScript.

## Requirements:

The stopwatch should have buttons to Start, Pause, and Reset.

Display time in the format: MM : SS : MS (minutes, seconds, milliseconds).

The time should update dynamically without page refresh.

## code:
index.html:
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Stopwatch App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="stopwatch">
    <div id="display">00 : 00 : 000</div>
    <button class="start" onclick="startTimer()">Start</button>
    <button class="pause" onclick="pauseTimer()">Pause</button>
    <button class="reset" onclick="resetTimer()">Reset</button>
  </div>

  <!-- Load JavaScript at the end of body -->
  <script src="script.js"></script>
</body>
</html>

```


style.css:
```
body {
  font-family: Arial, sans-serif;
  background: #f5f5f5;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.stopwatch {
  background: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  text-align: center;
}

#display {
  font-size: 2.5rem;
  margin-bottom: 20px;
  font-weight: bold;
}

button {
  padding: 10px 20px;
  margin: 5px;
  font-size: 1rem;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: 0.2s;
}

button:hover {
  opacity: 0.8;
}

.start { background: #28a745; color: white; }
.pause { background: #ffc107; color: white; }
.reset { background: #dc3545; color: white; }

```

script.js:
```
let startTime = 0;
let updatedTime = 0;
let difference = 0;
let tInterval;
let running = false;

function startTimer() {
  if (!running) {
    startTime = new Date().getTime() - difference;
    tInterval = setInterval(updateDisplay, 10);
    running = true;
  }
}

function pauseTimer() {
  if (running) {
    clearInterval(tInterval);
    difference = new Date().getTime() - startTime;
    running = false;
  }
}

function resetTimer() {
  clearInterval(tInterval);
  running = false;
  difference = 0;
  document.getElementById("display").innerHTML = "00 : 00 : 000";
}

function updateDisplay() {
  updatedTime = new Date().getTime() - startTime;
  let minutes = Math.floor((updatedTime % (1000 * 60 * 60)) / (1000 * 60));
  let seconds = Math.floor((updatedTime % (1000 * 60)) / 1000);
  let milliseconds = Math.floor((updatedTime % 1000));

  minutes = (minutes < 10) ? "0" + minutes : minutes;
  seconds = (seconds < 10) ? "0" + seconds : seconds;
  milliseconds = milliseconds.toString().padStart(3, '0');

  document.getElementById("display").innerHTML =
    `${minutes} : ${seconds} : ${milliseconds}`;
}

```
## output:

start:
<img width="1919" height="1078" alt="Screenshot 2025-09-03 102634" src="https://github.com/user-attachments/assets/b1e99d0f-09d8-4e61-a9be-d1c1d902395f" />

pause:
<img width="1915" height="1075" alt="Screenshot 2025-09-03 102648" src="https://github.com/user-attachments/assets/f87bc62a-a61d-465c-bb9a-4a54d156be5f" />

reset:

<img width="1919" height="1078" alt="Screenshot 2025-09-03 102634" src="https://github.com/user-attachments/assets/bd415992-c03c-40d6-9eb9-328cfa89d61d" />







