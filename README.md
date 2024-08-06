# DrumKit
Overview
The Drum Kit project is a web-based application that simulates a virtual drum set. Users can interact with the drum kit by clicking on the buttons displayed on the screen or by pressing specific keys on their keyboard. Each button corresponds to a different drum sound, allowing users to create their own rhythms and beats.

It's an online Drum Set. No matter if you are a beginner or a pro, let's beat some drums and enjoy. LET'S Beat it.

Features
Interactive Buttons: Each drum sound is mapped to a specific button on the screen, which users can click to play the corresponding sound.
Keyboard Interaction: Users can also play drum sounds by pressing keys on their keyboard. Each key ('w', 'a', 's', 'd', 'j', 'k', 'l') corresponds to a different drum sound.
Visual Feedback: When a drum sound is played, the corresponding button provides visual feedback by animating (e.g., changing opacity and adding a shadow).
Custom Styles: The application features a visually appealing design with custom styles for buttons and background.
Technical Details
HTML: The structure of the webpage, including the buttons for the drum kit and other static elements, is defined in the index.html file.
CSS: The styles for the application are provided in the styles.css file. This includes the layout, colors, fonts, and animations for the drum buttons.
JavaScript: The index.js file contains the logic for handling user interactions. This includes adding event listeners for button clicks and key presses, playing the appropriate drum sounds, and applying visual effects.

Files


index.html

HTML CODE ->

<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
  <title>Drum Kit</title>
  <link rel="stylesheet" href="styles.css">
  <link href="https://fonts.googleapis.com/css?family=Arvo" rel="stylesheet">
</head>
<body>
  <h1 id="title">Drum 🥁 Kit</h1>
  <div class="set">
    <button class="w drum">w</button>
    <button class="a drum">a</button>
    <button class="s drum">s</button>
    <button class="d drum">d</button>
    <button class="j drum">j</button>
    <button class="k drum">k</button>
    <button class="l drum">l</button>
  </div>
  <script src="index.js"></script>
  <footer>🥁 Lets Beat it 🥁</footer>
</body>
</html>


index.js

javascript CODE ->


var len = document.querySelectorAll(".drum").length;

for (var i = 0; i < len; i++) {
    document.querySelectorAll(".drum")[i].addEventListener("click", function() {
        var buttonInnerHTML = this.innerHTML;
        makeSound(buttonInnerHTML);
        buttonAnimation(buttonInnerHTML);
    });
}

document.addEventListener("keypress", function(event) {
    buttonAnimation(event.key);
    makeSound(event.key);
});

function makeSound(key) {
    switch (key) {
        case "w": var audio = new Audio("sounds/tom-1.mp3"); audio.play(); break;
        case "a": var audio = new Audio("sounds/tom-2.mp3"); audio.play(); break;
        case "s": var audio = new Audio("sounds/tom-3.mp3"); audio.play(); break;
        case "d": var audio = new Audio("sounds/tom-4.mp3"); audio.play(); break;
        case "j": var audio = new Audio("sounds/snare.mp3"); audio.play(); break;
        case "k": var audio = new Audio("sounds/crash.mp3"); audio.play(); break;
        case "l": var audio = new Audio("sounds/kick-bass.mp3"); audio.play(); break;
        default: break;
    }
}

function buttonAnimation(currentKey) {
    document.querySelector("." + currentKey).classList.add("pressed");
    setTimeout(function() {
        document.querySelector("." + currentKey).classList.remove("pressed");
    }, 100);
}






styles.css

CSS CODE->

body {
  text-align: center;
  background-color: #283149;
}

h1 {
  font-size: 5rem;
  color: #DBEDF3;
  font-family: "Arvo", cursive;
  text-shadow: 3px 0 #DA0463;
}

footer {
  color: #DBEDF3;
  font-family: sans-serif;
}

.w { background-image: url(images/tom1.png); }
.a { background-image: url(images/tom2.png); }
.s { background-image: url(images/tom3.png); }
.d { background-image: url(images/tom4.png); }
.j { background-image: url(images/snare.png); }
.k { background-image: url(images/crash.png); }
.l { background-image: url(images/kick.png); }

.set {
  margin: 10% auto;
}

.pressed {
  box-shadow: 0 3px 4px 0 #DBEDF3;
  opacity: 0.5;
}

.drum {
  outline: none;
  border: 10px solid #404B69;
  font-size: 5rem;
  font-family: 'Arvo', cursive;
  line-height: 2;
  font-weight: 900;
  color: #DA0463;
  text-shadow: 3px 0 #DBEDF3;
  border-radius: 15px;
  display: inline-block;
  width: 150px;
  height: 150px;
  text-align: center;
  margin: 10px;
  background-color: white;
}

How to Use-
Open index.html in a web browser: This will display the drum kit interface.
Click on the buttons or press keys: Interact with the drum kit by clicking the buttons or pressing the keys ('w', 'a', 's', 'd', 'j', 'k', 'l') to play different drum sounds.
Experience the visual feedback: Notice the animations and changes in button appearance when a sound is played.
This project serves as an interactive and engaging way to simulate a drum kit using web technologies, making it a fun tool for both learning and entertainment.
