<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Happy Birthday, isra!</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background-color: #fff5f5;
            color: #333;
            overflow-x: hidden;
            position: relative;
        }
        
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 10;
        }
        
        .love-note {
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transform: scale(0);
            transition: transform 0.3s;
            position: relative;
            margin: 15px 0;
        }
        
        .love-note.active {
            transform: scale(1);
        }
        
        .heart-btn {
            background: #ff6b6b;
            color: white;
            border: none;
            padding: 15px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(255,107,107,0.4);
            display: block;
            margin: 20px auto;
            width: 80%;
            max-width: 300px;
        }
        
        .heart-btn:hover {
            background: #ff5252;
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(255,107,107,0.5);
        }
        
        header {
            background: linear-gradient(135deg, #ff758c 0%, #ff7eb3 100%);
            color: white;
            text-align: center;
            padding: 50px 20px;
            border-radius: 0 0 30% 30%;
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(255, 117, 140, 0.3);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        h2 {
            font-size: 1.8rem;
        }
        
        p {
            font-size: 1rem;
        }
        
        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 20px 15px;
        }
        
        .photo-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        
        .photo-card {
            position: relative;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s;
            aspect-ratio: 1;
        }
        
        .photo-card:hover {
            transform: translateY(-10px);
        }
        
        .photo-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .photo-card:hover img {
            transform: scale(1.05);
        }
        
        .countdown {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 40px 0;
        }
        
        .countdown-box {
            background: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            min-width: 60px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        
        .countdown-value {
            font-size: 2rem;
            font-weight: bold;
            color: #ff6b6b;
        }
        
        .countdown-label {
            font-size: 0.8rem;
            color: #666;
            text-transform: uppercase;
        }
        
        .love-notes {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }
        
        footer {
            text-align: center;
            padding: 20px;
            background: linear-gradient(135deg, #ff758c 0%, #ff7eb3 100%);
            color: white;
            margin-top: 40px;
        }
        
        @media (max-width: 768px) {
            header {
                padding: 30px 15px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .countdown {
                flex-wrap: wrap;
                gap: 10px;
            }
            
            .love-notes {
                grid-template-columns: 1fr;
                gap: 15px;
            }
            
            .photo-gallery {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 480px) {
            .photo-gallery {
                grid-template-columns: 1fr;
            }
            
            .countdown-box {
                padding: 10px;
                min-width: 50px;
            }
            
            .countdown-value {
                font-size: 1.5rem;
            }
        }
        
        /* Animation classes */
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        .floating {
            animation: float 3s ease-in-out infinite;
        }
        
        .pulse {
            animation: pulse 2s ease-in-out infinite;
        }
        
        /* Confetti */
        .confetti {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 20;
            display: none;
        }
    </style>
</head>
<body>
    <!-- Floating aliens background -->
    <div class="hearts" id="hearts"></div>
    
    <!-- Confetti container -->
    <div class="confetti" id="confetti"></div>
    
    <header>
        <div class="container floating">
            <h1>Happy Birthday, <span id="name">isra!</span>!</h1>
            <p>Every day with you is a migraine</p>
        </div>
    </header>
    
    <div class="container">
        <section class="intro pulse">
            <h2>This Day Is All About an Alien</h2>
            <p>Today we celebrate the birthday of an alien, mean you, the talks and gossips we bring to our life every single day. You're my best friend, and an alien with red hair and owner of my kiko.</p>
            
            <div class="countdown">
                <div class="countdown-box">
                    <div class="countdown-value" id="days">00</div>
                    <div class="countdown-label">Days</div>
                </div>
                <div class="countdown-box">
                    <div class="countdown-value" id="hours">00</div>
                    <div class="countdown-label">Hours</div>
                </div>
                <div class="countdown-box">
                    <div class="countdown-value" id="minutes">00</div>
                    <div class="countdown-label">Minutes</div>
                </div>
                <div class="countdown-box">
                    <div class="countdown-value" id="seconds">00</div>
                    <div class="countdown-label">Seconds</div>
                </div>
            </div>
            
            <button class="heart-btn" id="surpriseBtn">Click for a Surprise!</button>
        </section>
        
        <section class="messages">
            <h2>Reasons Why You're an Alien</h2>
            <p>I don't know but...</p>
            
            <div class="love-notes">
                <div class="love-note">
                    <h3>You always support me</h3>
                    <p>Even in my worst to best, you support me.</p>
                </div>
                <div class="love-note">
                    <h3>Your Kindness</h3>
                    <p>You never dismotivate me, and when I feel bad, you always motivate and talk with kindness.</p>
                </div>
                <div class="love-note">
                    <h3>Your Laugh</h3>
                    <p>Ahh, I don't have to tell you how you laugh.</p>
                </div>
                <div class="love-note">
                    <h3>Our Bond</h3>
                    <p>I don't know how we maintain this strong bond even when we fight too much like hell.</p>
                </div>
                <div class="love-note">
                    <h3>Your Memory</h3>
                    <p>From the first time I saw you to the last time we hugged, those memories are so good.</p>
                </div>
                <div class="love-note">
                    <h3>Your Jealousness</h3>
                    <p>Whenever I talk about other girls, you really get jealous. Hahaha!</p>
                </div>
            </div>
        </section>
    </div>
    
    <footer>
        <p>Made for an alien, for the most stupid person I know.</p>
    </footer>
    
    <script>
        // Floating aliens background
        function createHearts() {
            const heartsContainer = document.getElementById('hearts');
            const colors = ['#ff6b6b', '#ff8e8e', '#ffb3b3', '#ffd8d8'];
            
            for (let i = 0; i < 15; i++) {
                const heart = document.createElement('div');
                heart.innerHTML = '👽'; // Alien emoji
                heart.style.position = 'absolute';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.top = Math.random() * 100 + 'vh';
                heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
                heart.style.color = colors[Math.floor(Math.random() * colors.length)];
                heart.style.opacity = Math.random() * 0.6 + 0.2;
                heart.style.animation = `float ${Math.random() * 5 + 5}s ease-in-out infinite`;
                heart.style.animationDelay = Math.random() * 5 + 's';
                heartsContainer.appendChild(heart);
            }
        }
        
        // Countdown timer
        function updateCountdown() {
            // Set the birthday date to August 11, 2025, at 12:00 AM London time
            const birthdayDate = new Date('2025-08-11T00:00:00Z'); // UTC time
            
            const now = new Date();
            const diff = birthdayDate - now;
            
            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days.toString().padStart(2, '0');
            document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
            document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
            document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
        }
        
        // Confetti effect
        function createConfetti() {
            const confettiContainer = document.getElementById('confetti');
            confettiContainer.style.display = 'block';
            
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.style.position = 'absolute';
                confetti.style.width = '10px';
                confetti.style.height = '10px';
                confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 50%)`;
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-10px';
                confetti.style.borderRadius = '50%';
                confetti.style.animation = `fall ${Math.random() * 3 + 2}s linear forwards`;
                confetti.style.animationDelay = Math.random() * 2 + 's';
                
                // Create keyframes for falling animation
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes fall {
                        to {
                            transform: translateY(100vh) rotate(${Math.random() * 360}deg);
                            opacity: 0;
                        }
                    }
                `;
                document.head.appendChild(style);
                
                confettiContainer.appendChild(confetti);
            }
            
            setTimeout(() => {
                confettiContainer.style.display = 'none';
                confettiContainer.innerHTML = '';
            }, 5000);
        }
        
        // Animate love notes on scroll
        function animateNotesOnScroll() {
            const loveNotes = document.querySelectorAll('.love-note');
            
            function checkVisibility() {
                loveNotes.forEach((note, index) => {
                    const notePosition = note.getBoundingClientRect().top;
                    const screenPosition = window.innerHeight / 1.3;
                    
                    if (notePosition < screenPosition) {
                        setTimeout(() => {
                            note.classList.add('active');
                        }, index * 200);
                    }
                });
            }
            
            window.addEventListener('scroll', checkVisibility);
            checkVisibility(); // Check on load
        }
        
        // Initialize everything when page loads
        window.onload = function() {
            createHearts();
            updateCountdown();
            animateNotesOnScroll();
            
            // Update countdown every second
            setInterval(updateCountdown, 1000);
            
            // Surprise button
            document.getElementById('surpriseBtn').addEventListener('click', createConfetti);
            
            // Optional: Prompt for name customization
            const name = prompt("Enter your name birthday girl", "");
            if (name && name.trim() !== "") {
                document.getElementById('name').textContent = name;
            }
        };
    </script>
</body>
</html>
