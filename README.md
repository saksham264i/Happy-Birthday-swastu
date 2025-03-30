# Happy-Birthday-swastu
Surprise 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Swasti</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #ffebcd;
            overflow: hidden;
        }
        .container {
            margin-top: 50px;
        }
        .hidden {
            display: none;
        }
        .question {
            font-size: 24px;
            margin-bottom: 20px;
        }
        .button {
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            border: none;
            background-color: #ff69b4;
            color: white;
            border-radius: 5px;
            margin-top: 10px;
        }
        .envelope {
            margin: auto;
            width: 300px;
            height: 200px;
            background-color: #ffcccc;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
        }
        .celebration {
            font-size: 30px;
            font-weight: bold;
            color: #ff4500;
        }
        textarea {
            width: 80%;
            height: 100px;
            padding: 10px;
            font-size: 16px;
            border: 2px solid #ff69b4;
            border-radius: 5px;
            resize: none;
        }
        .floating-hearts {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 24px;
            animation: float 5s linear infinite;
        }
        @keyframes float {
            0% { transform: translateY(100vh) scale(1); opacity: 1; }
            100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
        }
    </style>
</head>
<body>

<div class="floating-hearts"></div>

<div id="welcome-screen" class="container">
    <h1>WELCOME</h1>
    <button class="button" onclick="startQuiz()">Start</button>
</div>

<div id="question-screen" class="container hidden">
    <p class="question" id="question-text">How do you feel, princess?</p>
    <button class="button" onclick="nextQuestion()">Amazing</button>
    <button class="button" onclick="nextQuestion()">Happy</button>
    <button class="button" onclick="nextQuestion()">Excited</button>
</div>

<div id="letter-screen" class="container hidden">
    <div class="envelope" onclick="showLetter()">Click to Open</div>
    <p id="letter" class="hidden">
        Hi Swasti,<br><br>
        First of all, very very happy returns of the day! I wish you a very happy birthday.<br>
        You are one of the most beautiful people in my life. You made my life so special,
        and every moment with you has been amazing.<br>
        Thanks for being in my life, and I hope my best friend remains my lifetime friend.<br><br>
        Once again, Happy Birthday!<br><br>
        Yours,<br>
        Saksham
    </p>
    <button class="button hidden" id="next-button" onclick="showFinalQuestion()">Next</button>
</div>

<div id="final-question-screen" class="container hidden">
    <p class="question">What are your thoughts today? I'm excited to listen! 😊</p>
    <form id="response-form" action="https://formsubmit.co/rathodsaksham1802@gmail.com" method="POST">
        <textarea id="response" name="message" placeholder="Write your thoughts here..." required></textarea>
        <input type="hidden" name="_captcha" value="false">
        <input type="hidden" name="_subject" value="Swasti's Response">
        <input type="hidden" name="_template" value="table">
        <button class="button" type="submit">Submit</button>
    </form>
</div>

<script>
    function startQuiz() {
        document.getElementById('welcome-screen').classList.add('hidden');
        document.getElementById('question-screen').classList.remove('hidden');
        createFloatingHearts();
    }

    function nextQuestion() {
        document.getElementById('question-screen').classList.add('hidden');
        document.getElementById('letter-screen').classList.remove('hidden');
    }

    function showLetter() {
        document.querySelector('.envelope').classList.add('hidden');
        document.getElementById('letter').classList.remove('hidden');
        document.getElementById('next-button').classList.remove('hidden');
    }

    function showFinalQuestion() {
        document.getElementById('letter-screen').classList.add('hidden');
        document.getElementById('final-question-screen').classList.remove('hidden');
    }

    function createFloatingHearts() {
        const container = document.querySelector(".floating-hearts");
        setInterval(() => {
            let heart = document.createElement("div");
            heart.innerHTML = "❤️";
            heart.classList.add("heart");
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 3 + 3 + "s";
            container.appendChild(heart);
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }, 500);
    }
</script>

</body>
</html>
