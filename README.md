# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>User Preferences + Animation</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }

    #animateBtn {
      padding: 10px 20px;
      background-color: #4CAF50;
      border: none;
      color: white;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      transition: background-color 0.3s ease;
    }

    #animateBtn:hover {
      background-color: #45a049;
    }

    /* CSS Animation */
    .animate {
      animation: bounce 0.5s;
    }

    @keyframes bounce {
      0%   { transform: scale(1); }
      50%  { transform: scale(1.2); }
      100% { transform: scale(1); }
    }

    input {
      padding: 8px;
      margin: 10px;
      font-size: 16px;
    }

    #saveBtn {
      padding: 8px 15px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h2 id="username">Welcome, Guest!</h2>

  <input type="text" id="nameInput" placeholder="Enter your name">
  <button id="saveBtn">Save Name</button>

  <br><br>
  <button id="animateBtn">Click to Animate!</button>

  <script>
    // Load saved username on page load
    window.onload = function() {
      let savedName = localStorage.getItem('username');
      let greeting = savedName ? `Welcome back, ${savedName}!` : 'Welcome, Guest!';
      document.getElementById('username').innerText = greeting;
    }

    // Save name to localStorage
    document.getElementById('saveBtn').addEventListener('click', function() {
      let name = document.getElementById('nameInput').value;
      localStorage.setItem('username', name);
      document.getElementById('username').innerText = `Welcome back, ${name}!`;
    });

    // Trigger animation
    document.getElementById('animateBtn').addEventListener('click', function() {
      this.classList.add('animate');

      // Remove animation class after it ends to make it reusable
      this.addEventListener('animationend', () => {
        this.classList.remove('animate');
      }, { once: true });
    });
  </script>

</body>
</html>


