# Happy-new-year
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy New Year ❤️</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        background: linear-gradient(135deg, #1f1c2c, #928dab);
        overflow: hidden;
        font-family: 'Segoe UI', sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        color: white;
    }

    .card {
        background: rgba(0,0,0,0.4);
        padding: 45px;
        border-radius: 20px;
        max-width: 540px;
        text-align: center;
        box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        animation: fadeIn 2s ease;
        z-index: 2;
    }

    h1 {
        font-size: 2.8em;
        margin-bottom: 15px;
        font-weight: 600;
    }

    p {
        font-size: 1.15em;
        line-height: 1.7;
        margin-bottom: 20px;
    }

    button {
        background: none;
        border: 2px solid white;
        color: white;
        padding: 12px 28px;
        font-size: 1em;
        border-radius: 30px;
        cursor: pointer;
        transition: all 0.3s ease;
    }

    button:hover {
        background: white;
        color: #1f1c2c;
    }

    .hidden {
        display: none;
        margin-top: 25px;
        animation: fadeIn 1.5s ease;
    }

    img {
        width: 100%;
        max-height: 300px;
        object-fit: cover;
        border-radius: 15px;
        margin-top: 20px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.4);
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(30px); }
        to { opacity: 1; transform: translateY(0); }
    }

    /* Soft floating hearts */
    .heart {
        position: absolute;
        bottom: -30px;
        font-size: 18px;
        opacity: 0.6;
        animation: float 7s linear infinite;
    }

    @keyframes float {
        from {
            transform: translateY(0) scale(1);
            opacity: 0.8;
        }
        to {
            transform: translateY(-110vh) scale(1.6);
            opacity: 0;
        }
    }
</style>
</head>

<body>

<!-- Background Music -->
<audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-tenderness.mp3" type="audio/mpeg">
</audio>

<div class="card">
    <h1>Happy New Year, Sarrah</h1>

    <p>
        Since 23rd February,<br>
        life has felt calmer, warmer,
        and more meaningful — because of you.
    </p>

    <p id="daysText"></p>

    <button onclick="showMessage()">One more thing</button>

    <div id="message" class="hidden">
        <img src="photo.jpg" alt="Us">

        <p>
            This new year isn’t about promises.<br>
            It’s about choosing each other —
            every day, without hesitation.
        </p>

        <p>
            — <b>Sahil</b>
        </p>
    </div>
</div>

<script>
    function showMessage() {
        document.getElementById("message").style.display = "block";
    }

    // Calculate days together since Feb 23
    const startDate = new Date("2025-02-23");
    const today = new Date();
    const diffTime = today - startDate;
    const daysTogether = Math.floor(diffTime / (1000 * 60 * 60 * 24));

    document.getElementById("daysText").innerHTML =
        `It’s been <b>${daysTogether}</b> days of togetherness —
        and I’m looking forward to many more.`;

    // Floating hearts
    function createHeart() {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (Math.random() * 3 + 6) + "s";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 8000);
    }

    setInterval(createHeart, 800);
</script>

</body>
</html>