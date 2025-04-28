🎯 JavaScript Event Handling & Interactive Elements Assignment
Welcome to the ultimate JavaScript playground! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, alive experiences. Get ready to master event handling, build interactive components, and validate forms like a pro! 💪

📁 Assignment Structure
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
🧪 What to Build
Here’s what your interactive bundle of joy should include:

1. Event Handling 🎈
Button click ✅
Hover effects ✅
Keypress detection ✅
Bonus: A secret action for a double-click or long press 🤫
2. Interactive Elements 🎮
A button that changes text or color
An image gallery or slideshow
Tabs or accordion-style content
Bonus: Add some animation using JS or CSS ✨
3. Form Validation 📋✅
Required field checks
Email format validation
Password rules (e.g., min 8 characters)
Bonus: Real-time feedback while typing
🧙‍♂️ Pro Tips
Keep your code clean and commented – your future self will thank you!
Think about user experience – what makes your site more fun to use?
Don’t be afraid to Google and experiment – that’s how real developers roll!
🎉 Now Go Make It Fun!
Remember – this isn't just code. It's your first step toward creating magical user experiences. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨




1. Event Handling
JavaScript for Event Handling:

// Button click
document.getElementById('clickMeButton').onclick = function() {
  this.innerHTML = 'Clicked!';
  this.style.backgroundColor = 'lightblue';
  setTimeout(function() {
    this.innerHTML = 'Click Me!';
    this.style.backgroundColor = 'blue';
  }.bind(this), 2000);
};

// Hover effects
document.querySelectorAll('.hoverEffect').forEach(element => {
  element.addEventListener('mouseover', function() {
    this.style.fontSize = '24px';
  });
  element.addEventListener('mouseout', function() {
    this.style.fontSize = '16px';
  });
});

// Keypress detection
document.addEventListener('keydown', function(event) {
  if (event.code === 'KeyD') {
    alert('You pressed D!');
  }
});

// Secret action (double-click)
document.addEventListener('dblclick', function() {
  alert('Secret action detected!');
});

// Long press (requires Touch Events for mobile devices and user interaction)
document.addEventListener('pointerdown', function(event) {
  let timer = setTimeout(() => {
    alert('Long press detected after 2 seconds!');
    clearTimeout(timer);
  }, 2000);
});
2. Interactive Elements
HTML and CSS for Interactive Elements:

<!-- Button that changes text or color -->
<button id="colorfulButton">Change Color</button>

<!-- Image Gallery using Slider -->
<div id="gallery">
  <img src="image1.jpg" alt="Image 1">
  <img src="image2.jpg" alt="Image 2">
  <!-- Additional images -->
</div>

// JavaScript to control image gallery
let gallery = document.getElementById('gallery');
let images = gallery.querySelectorAll('img');
let currentImageIndex = 0;

function changeImage() {
  currentImageIndex = (currentImageIndex + 1) % images.length;
  images[currentImageIndex].style.display = 'block';
}

changeImage(); // Initial display

// Tabs and accordion using CSS and JS
<div class="tab-container">
  <button class="tab" onClick="showContent(1)">Tab 1</button>
  <button class="tab" onClick="showContent(2)">Tab 2</button>
  <div class="tab-content" id="content1">Content 1</div>
  <div class="tab-content" id="content2">Content 2</div>
</div>

function showContent(index) {
  document.querySelectorAll('.tab-content').forEach(content => {
    content.style.display = 'none';
  });
  document.getElementById('content' + index).style.display = 'block';
}

// Animation using CSS
.animatedElement {
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }
  40%, 60% {
    transform: translateY(15px);
  }
}

<!-- Apply class to elements you want to animate -->
<div class="animatedElement">Hover over me for animation!</div>
3. Form Validation
HTML and JavaScript for Form Validation:

<form id="userForm">
  <label for="username">Username:</label>
  <input type="text" id="username" required>
  <span class="error" style="display: none">Username is required.</span>
  <label for="email">Email:</label>
  <input type="email" id="email" required>
  <span class="error" style="display: none">Please enter a valid email.</span>
  <label for="password">Password:</label>
  <input type="password" id="password" minlength="8" required>
  <span class="error" style="display: none">Password must be at least 8 characters.</span>
  <input type="submit" value="Submit">
</form>

// JavaScript for real time feedback
let usernameField = document.getElementById('username');
let emailField = document.getElementById('email');
let passwordField = document.getElementById('password');

usernameField.oninput = function() {
  let error = document.getElementById('errorUsername');
  if (!this.value) {
    error.style.display = 'block';
  } else {
    error.style.display = 'none';
  }
};

emailField.oninput = function() {
  let error = document.getElementById('errorEmail');
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailRegex.test(this.value)) {
    error.style.display = 'block';
  } else {
    error.style.display = 'none';
  }
};

passwordField.oninput = function() {
  let error = document.getElementById('errorPassword');
  if (this.value.length < 8) {
    error.style.display = 'block';
  } else {
    error.style.display = 'none';
  }
};

// Form submission validation
document.getElementById('userForm').onsubmit = function(event) {
  event.preventDefault();
  // Perform validation here before actual form submission
};
