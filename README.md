<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Love - Keyshia Cole Lyrics (2006)</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Roboto:wght@300;400&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Roboto', sans-serif;
            background: linear-gradient(135deg, #ff9a9e, #fecfef, #ffecd2, #a8edea);
            color: #d63384;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            position: relative;
        }
        .container {
            max-width: 900px;
            margin: 50px auto;
            padding: 30px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            text-align: center;
            backdrop-filter: blur(10px);
        }
        h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3em;
            margin-bottom: 10px;
            color: #e91e63;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            animation: fadeIn 2s ease-in-out;
        }
        h2 {
            font-size: 1.5em;
            margin-bottom: 30px;
            color: #ad1457;
            animation: fadeIn 2s ease-in-out 0.5s both;
        }
        #lyrics {
            font-size: 1.3em;
            line-height: 1.8;
            margin: 30px 0;
            text-align: left;
            max-width: 700px;
            margin: 30px auto;
        }
        .word {
            display: inline-block;
            margin-right: 8px; /* Added spacing between words */
            animation: floatPop 0.8s ease-in-out forwards;
            opacity: 0;
            text-shadow: 0 0 5px rgba(233, 30, 99, 0.5);
        }
        .word:last-child {
            margin-right: 0;
        }
        @keyframes floatPop {
            0% {
                opacity: 0;
                transform: translateY(30px) scale(0.5) rotate(-10deg);
            }
            50% {
                opacity: 1;
                transform: translateY(-10px) scale(1.2) rotate(5deg);
            }
            100% {
                opacity: 1;
                transform: translateY(0) scale(1) rotate(0deg);
            }
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .heart {
            position: absolute;
            color: #ff4081;
            font-size: 2.5em;
            animation: float 8s ease-in-out infinite;
            opacity: 0.8;
        }
        .heart:nth-child(odd) {
            animation-delay: -4s;
        }
        .heart:nth-child(3n) {
            color: #e91e63;
        }
        .heart:nth-child(5n) {
            color: #f48fb1;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(180deg); }
        }
        .sparkle {
            position: absolute;
            color: #ffd700;
            font-size: 1.5em;
            animation: sparkleFloat 5s ease-in-out infinite;
        }
        @keyframes sparkleFloat {
            0%, 100% { transform: translateY(0px) scale(1); opacity: 0.5; }
            50% { transform: translateY(-20px) scale(1.5); opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>💖 Love 💖</h1>
        <h2>By Keyshia Cole (2006)</h2>
        <div id="lyrics"></div>
    </div>

    <script>
        const lyricsText = `[Intro]
Love, love, love, love
Love, love, love, love
Love, love, love, love
Love, love, love, love

[Verse 1]
I used to think that I wasn't fine enough
And I used to think that I wasn't wild enough
You brought the sunshine into my life
You took me and you made me your wife
And now I know that I am fine enough
And I know that I am wild enough
You brought the sunshine into my life
You took me and you made me your wife

[Chorus]
Love, love, love, love
Love, love, love, love
Love, love, love, love
Love, love, love, love

[Verse 2]
I used to think that I wasn't fine enough
And I used to think that I wasn't wild enough
You brought the sunshine into my life
You took me and you made me your wife
And now I know that I am fine enough
And I know that I am wild enough
You brought the sunshine into my life
You took me and you made me your wife

[Chorus]
Love, love, love, love
Love, love, love, love
Love, love, love, love
Love, love, love, love

[Outro]
Love, love, love, love
Love, love, love, love
Love, love, love, love
Love, love, love, love`;

        function animateLyrics() {
            const lyricsContainer = document.getElementById('lyrics');
            lyricsContainer.innerHTML = '';
            const lines = lyricsText.split('\n');
            let totalDelay = 0;

            lines.forEach((line, lineIndex) => {
                const lineDiv = document.createElement('div');
                lineDiv.style.marginBottom = '15px';
                lyricsContainer.appendChild(lineDiv);

                const words = line.split(' ');
                words.forEach((word, wordIndex) => {
                    const span = document.createElement('span');
                    span.textContent = word;
                    span.className = 'word';
                    span.style.animationDelay = `${totalDelay + wordIndex * 0.2}s`;
                    lineDiv.appendChild(span);
                    // Add space after each word except the last
                    if (wordIndex < words.length - 1) {
                        lineDiv.appendChild(document.createTextNode(' '));
                    }
                });

                totalDelay += words.length * 0.2 + 1; // Delay for next line
            });
        }

        // Start animation on page load
        window.onload = animateLyrics;

        // Create floating hearts animation
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 4 + 4 + 's';
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 8000);
        }

        // Create floating sparkles
        function createSparkle() {
            const sparkle = document.createElement('div');
            sparkle.className = 'sparkle';
            sparkle.innerHTML = '✨';
            sparkle.style.left = Math.random() * 100 + 'vw';
            sparkle.style.animationDuration = Math.random() * 3 + 3 + 's';
            document.body.appendChild(sparkle);

            setTimeout(() => {
                sparkle.remove();
            }, 5000);
        }

        // Generate hearts every 600ms
        setInterval(createHeart, 600);
        // Generate sparkles every 800ms
        setInterval(createSparkle, 800);
    </script>
</body>
</html>
