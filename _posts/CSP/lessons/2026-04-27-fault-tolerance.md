---
layout: none
permalink: /csp/fault-tolerance/p3/lessons/
title: Fault Tolerance Lesson
---

<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fault Tolerance Lesson</title>
<style>
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  background: linear-gradient(180deg, #08101f 0%, #0f1a33 100%);
  color: #f5f8ff;
  padding: 24px;
}
.wrap {
  max-width: 900px;
  margin: 0 auto;
  background: rgba(15, 26, 51, 0.96);
  border: 1px solid rgba(138, 232, 255, 0.18);
  border-radius: 20px;
  padding: 24px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.35);
}
.badge {
  display: inline-block;
  padding: 8px 12px;
  border-radius: 999px;
  background: rgba(0, 194, 255, 0.16);
  color: #8ae8ff;
  font-weight: 700;
  font-size: 0.92rem;
}
h1, h2 { text-align: center; }
h1 { margin: 10px 0 8px; font-size: 2.4rem; }
p { line-height: 1.55; }
.section { margin: 20px 0; }
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 14px;
}
.card, .box {
  background: linear-gradient(180deg, #172447 0%, #13203f 100%);
  border: 1px solid rgba(138, 232, 255, 0.12);
  border-radius: 14px;
  padding: 16px;
}
.card strong, .box strong { color: #8ae8ff; }
.mini { color: #9eb8ff; font-size: 0.8rem; letter-spacing: 0.08em; text-transform: uppercase; margin-bottom: 8px; }
.network {
  display: flex;
  justify-content: center;
  gap: 14px;
  flex-wrap: wrap;
  margin: 16px 0;
}
.node {
  width: 92px;
  height: 92px;
  border: none;
  border-radius: 18px;
  background: linear-gradient(180deg, #2de2ff 0%, #00a9d6 100%);
  color: #001018;
  font-weight: 700;
  cursor: pointer;
  box-shadow: 0 10px 24px rgba(0, 194, 255, 0.18);
}
.node.off { background: linear-gradient(180deg, #5d6780 0%, #434d64 100%); color: white; }
.buttons { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; }
button.choice, button.reset {
  border: none;
  border-radius: 12px;
  padding: 12px 14px;
  font-weight: 700;
  cursor: pointer;
}
button.choice { width: 100%; margin-top: 10px; background: #f7fbff; color: #101b38; }
button.choice.correct { background: #b7ffd6; }
button.choice.wrong { background: #ffd5d5; }
button.reset { background: #8ae8ff; color: #001018; }
#msg, #quizMsg, #score { text-align: center; font-weight: 700; min-height: 24px; }
#score { color: #8ae8ff; margin-top: 10px; }
.tip {
  background: rgba(255, 255, 255, 0.05);
  border-left: 4px solid #8ae8ff;
  border-radius: 10px;
  padding: 12px 14px;
}
.code {
  background: #071223;
  border: 1px solid rgba(138, 232, 255, 0.16);
  border-radius: 12px;
  padding: 14px;
  overflow-x: auto;
  color: #d8f0ff;
  line-height: 1.55;
  font-family: Menlo, Consolas, Monaco, monospace;
  font-size: 0.92rem;
}
@media (max-width: 640px) {
  body { padding: 12px; }
  .wrap { padding: 18px; border-radius: 16px; }
  h1 { font-size: 1.9rem; }
  .node { width: 78px; height: 78px; }
}
</style>
</head>
<body>
<div class="wrap">
  <div class="badge">AP CSP Mini Lesson - 5 to 10 minutes</div>
  <h1>Fault Tolerance</h1>

  <div class="tip">
    <strong>Goal:</strong> understand fault tolerance, learn why redundancy matters, and answer the AP CSP idea correctly.
  </div>

  <div class="section">
    <h2>How to use this lesson</h2>
    <div class="grid">
      <div class="card">
        <div class="mini">Step 1</div>
        Read the definition and look for the clue words: backup, redundancy, and still works.
      </div>
      <div class="card">
        <div class="mini">Step 2</div>
        Try the server game and notice what happens when one part fails.
      </div>
      <div class="card">
        <div class="mini">Step 3</div>
        Use the code example to connect the idea to a real system design.
      </div>
    </div>
    <div class="box" style="margin-top: 12px;">
      <strong>Quick reminder:</strong> if the system can lose one part and still keep going, it is showing fault tolerance.
    </div>
  </div>

  <div class="section">
    <h2>Code example</h2>
    <div class="box">
      Here is a simple idea in pseudocode:
      <pre class="code">if server_A fails:
    use server_B as backup
else:
    keep serving users</pre>
      This shows redundancy because there is a backup path ready if the first one breaks.
    </div>
  </div>

  <div class="section">
    <h2>What it means</h2>
    <div class="grid">
      <div class="card">
        <div class="mini">Simple definition</div>
        <strong>Fault tolerance</strong> means a system keeps working even when part of it fails.
      </div>
      <div class="card">
        <div class="mini">Kid example</div>
        If one bus breaks, a backup bus can still bring everyone home.
      </div>
      <div class="card">
        <div class="mini">AP clue words</div>
        Look for <strong>backup</strong>, <strong>redundancy</strong>, and <strong>still works</strong>.
      </div>
    </div>
    <div class="box" style="margin-top: 12px;">
      <strong>Exam-friendly version:</strong> fault tolerance is the ability of a system to keep operating after a failure.
    </div>
  </div>

  <div class="section">
    <h2>Why redundancy matters</h2>
    <div class="box">
      <strong>Redundancy</strong> means extra parts or extra paths so there is a backup if something breaks.
      <br><br>
      Redundancy is the design choice. Fault tolerance is the result.
    </div>
  </div>

  <div class="section">
    <h2>Quick game</h2>
    <div class="box">Click a server to make it fail. If the app can keep going, that is fault tolerance.</div>
    <div class="network">
      <button class="node" id="A" onclick="fail('A')">Server A</button>
      <button class="node" id="B" onclick="fail('B')">Server B</button>
      <button class="node" id="C" onclick="fail('C')">Server C</button>
    </div>
    <div id="msg"></div>
    <div class="buttons" style="margin-top: 10px;">
      <button class="reset" onclick="resetGame()">Reset</button>
    </div>

    <div class="grid" style="margin-top: 14px;">
      <div class="card">
        <strong>Scenario 1:</strong> one server dies, but the app still works.
        <button class="choice" onclick="pickAnswer('quiz1', true, this)">Add a backup server</button>
        <button class="choice" onclick="pickAnswer('quiz1', false, this)">Remove the extra server</button>
      </div>
      <div class="card">
        <strong>Scenario 2:</strong> there are two internet paths.
        <button class="choice" onclick="pickAnswer('quiz2', true, this)">This is more fault tolerant</button>
        <button class="choice" onclick="pickAnswer('quiz2', false, this)">One failure will always stop it</button>
      </div>
      <div class="card">
        <strong>Scenario 3:</strong> one power cord runs everything.
        <button class="choice" onclick="pickAnswer('quiz3', false, this)">That is redundant</button>
        <button class="choice" onclick="pickAnswer('quiz3', true, this)">That is a single point of failure</button>
      </div>
    </div>

    <div id="score">Score: 0 / 3</div>
    <div id="quizMsg"></div>
  </div>

  <div class="section">
    <h2>AP check</h2>
    <div class="box">
      If a system still works when one part fails, that system has:
      <br><br>
      A. Compression<br>
      B. Fault tolerance<br>
      C. Encryption<br>
      D. Sorting
    </div>

    <div class="grid" style="margin-top: 14px;">
      <div class="card">
        <strong>Question 2:</strong> What helps a system keep working after one part breaks?
        <button class="choice" onclick="pickAnswer('quiz4', true, this)">Redundancy</button>
        <button class="choice" onclick="pickAnswer('quiz4', false, this)">Compression</button>
        <button class="choice" onclick="pickAnswer('quiz4', false, this)">Encryption</button>
        <button class="choice" onclick="pickAnswer('quiz4', false, this)">Sorting</button>
      </div>
      <div class="card">
        <strong>Question 3:</strong> A website has two servers. One fails, and the other takes over. What is this an example of?
        <button class="choice" onclick="pickAnswer('quiz5', true, this)">Fault tolerance</button>
        <button class="choice" onclick="pickAnswer('quiz5', false, this)">A single point of failure</button>
        <button class="choice" onclick="pickAnswer('quiz5', false, this)">Data compression</button>
        <button class="choice" onclick="pickAnswer('quiz5', false, this)">Pattern matching</button>
      </div>
      <div class="card">
        <strong>Question 4:</strong> Which design choice is the best way to make a system more reliable?
        <button class="choice" onclick="pickAnswer('quiz6', true, this)">Add backup parts</button>
        <button class="choice" onclick="pickAnswer('quiz6', false, this)">Remove all extra parts</button>
        <button class="choice" onclick="pickAnswer('quiz6', false, this)">Use one cable for everything</button>
        <button class="choice" onclick="pickAnswer('quiz6', false, this)">Turn off the network</button>
      </div>
    </div>
  </div>
</div>

<script>
let score = 0;
const solved = { quiz1: false, quiz2: false, quiz3: false, quiz4: false, quiz5: false, quiz6: false };

function fail(node) {
  document.getElementById(node).classList.add('off');
  document.getElementById('msg').innerText = node === 'B'
    ? 'This system failed because B was a single point of failure.'
    : 'This system still works. That is fault tolerance through redundancy.';
}

function pickAnswer(quizName, isCorrect, button) {
  if (solved[quizName]) {
    document.getElementById('quizMsg').innerText = 'That round is already solved. Try another one or reset the game.';
    return;
  }

  if (isCorrect) {
    score += 1;
    solved[quizName] = true;
    button.classList.add('correct');
    document.getElementById('quizMsg').innerText = 'Correct. That choice adds redundancy and improves fault tolerance.';
  } else {
    button.classList.add('wrong');
    document.getElementById('quizMsg').innerText = 'Not quite. Look for the choice with a backup or extra path.';
  }

  document.getElementById('score').innerText = 'Score: ' + score + ' / 3';
}

function resetGame() {
  ['A', 'B', 'C'].forEach(function(node) {
    document.getElementById(node).classList.remove('off');
  });
  score = 0;
  solved.quiz1 = false;
  solved.quiz2 = false;
  solved.quiz3 = false;
  solved.quiz4 = false;
  solved.quiz5 = false;
  solved.quiz6 = false;
  document.getElementById('msg').innerText = '';
  document.getElementById('quizMsg').innerText = '';
  document.getElementById('score').innerText = 'Score: 0 / 3';
  document.querySelectorAll('.choice').forEach(function(button) {
    button.classList.remove('correct', 'wrong');
  });
}
</script>
</body>
</html>
