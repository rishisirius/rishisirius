<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Jerry!</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: linear-gradient(to bottom, #ffcccb, #ffe4e1);
            color: #333;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        header {
            background: #ff69b4;
            padding: 20px;
            color: white;
        }

        h1 {
            font-size: 3em;
            margin: 0;
        }

        .birthday-message {
            padding: 20px;
        }

        .collage {
            width: 80%;
            border-radius: 10px;
            margin-top: 20px;
        }

        .promise, .fun-elements {
            background: #fff0f5;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
        }

        textarea {
            width: 80%;
            height: 100px;
            margin-top: 10px;
        }

        .call-to-action {
            margin: 20px 0;
        }

        button {
            background: #d900ff;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
        }

        footer {
            background: #ff69b4;
            color: white;
            padding: 10px;
            position: relative;
            bottom: 0;
            width: 100%;
        }

        .social-media a {
            margin: 0 10px;
            color: white;
            text-decoration: none;
        }

        .wish-card {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .quote {
            margin-top: 20px;
            font-style: italic;
            color: #555;
        }
    </style>
</head>
<body>
    <header>
        <h1>Happy Birthday, Jerry!</h1>
    </header>

    <section class="birthday-message">
        <p>On this special day, I want to celebrate you and all the joy you've brought into my life.</p>
        <img src="c:\Users\synta\OneDrive\Pictures\Screenshots\shino.jpg" alt="Collage of memories" class="collage">
    </section>

    <section class="promise">
        <h2>A Promise to You</h2>
        <p>As we celebrate another beautiful year of your life, I want to promise you this: I will be by your side through every moment, until the very end.</p>
    </section>

    <section class="fun-elements">
        <h2>Countdown to Your Next Birthday</h2>
        <div id="countdown"></div>
        <h2>Leave Your Birthday Wishes</h2>
        <textarea id="wishInput" placeholder="Write your wishes here..."></textarea>
        <button id="submitWishButton">Submit Wish</button>
        <div id="wishList"></div>
        <div id="quoteDisplay" class="quote"></div>
        <button id="createECardButton">Create E-Card</button>
        <button id="reminderButton">Set Birthday Reminder</button>
    </section>

    <section class="call-to-action">
        <h2>Let’s make more memories together!</h2>
        <button id="planAdventureButton">Plan Our Next Adventure!</button>
    </section>

    <footer>
        <p>Reach me anytime at syntaxsamurai13@gmail.com!</p>
        <div class="social-media">
            <a href="#">Facebook</a>
            <a href="#">Instagram</a>
            <a href="#">Twitter</a>
        </div>
    </footer>

    <script>
        // Countdown Timer
        const nextBirthday = new Date('2025-11-22T00:00:00'); // Jerry's next birthday
        const countdownElement = document.getElementById('countdown');

        function updateCountdown() {
 const now = new Date();
            const timeRemaining = nextBirthday - now;

            // Check if the countdown has finished
            if (timeRemaining < 0) {
                countdownElement.innerHTML = "Happy Birthday, Jerry! 🎉";
                clearInterval(countdownInterval); // Stop the countdown
                return;
            }

            const days = Math.floor(timeRemaining / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeRemaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeRemaining % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeRemaining % (1000 * 60)) / 1000);

            countdownElement.innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
        }

        const countdownInterval = setInterval(updateCountdown, 1000);

        // Function to submit wishes
        document.getElementById('submitWishButton').onclick = function() {
            const wish = document.getElementById('wishInput').value;
            if (wish) {
                const wishList = document.getElementById('wishList');
                const wishCard = document.createElement('div');
                wishCard.className = 'wish-card';
                wishCard.textContent = wish;
                wishList.appendChild(wishCard);
                document.getElementById('wishInput').value = '';
                const quotes = [
                    "Count your life by smiles, not tears. Count your age by friends, not years.",
                    "You are never too old to set another goal or to dream a new dream.",
                    "The more you praise and celebrate your life, the more there is in life to celebrate."
                ];
                const randomQuote = quotes[Math.floor(Math.random() * quotes.length)];
                document.getElementById('quoteDisplay').textContent = randomQuote;
            } else {
                alert("Please enter a wish.");
            }
        };

        // Function to create E-Card
        document.getElementById('createECardButton').onclick = function() {
            const wish = document.getElementById('wishInput').value;
            if (wish) {
                alert(`E-Card Created with your wish: "${wish}"`);
            } else {
                alert("Please enter a wish to create an E-Card.");
            }
        };

        // Function to set birthday reminder
        document.getElementById('reminderButton').onclick = function() {
            const reminderDate = prompt("Enter your birthday (YYYY-MM-DD):");
            if (reminderDate) {
                alert(`Birthday reminder set for ${reminderDate}.`);
            } else {
                alert("Please enter a valid date.");
            }
        };

        // Function to plan an adventure
        document.getElementById('planAdventureButton').onclick = function() {
            alert("Let's plan something special together!");
        };
    </script>
</body>
</html>
