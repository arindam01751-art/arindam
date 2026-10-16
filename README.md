
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hadi's Surprise 😂</title>

<style>
    * {
        box-sizing: border-box;
    }

    body {
        margin: 0;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        font-family: Arial, sans-serif;
        color: white;
        background: linear-gradient(135deg, #141e30, #4b134f);
        overflow: hidden;
    }

    .box {
        padding: 30px 20px;
        width: 90%;
        max-width: 450px;
        border-radius: 25px;
        background: rgba(255,255,255,0.12);
        box-shadow: 0 0 30px rgba(0,0,0,0.3);
    }

    h1 {
        font-size: 30px;
    }

    p {
        font-size: 19px;
    }

    button {
        padding: 14px 22px;
        margin: 10px 5px;
        border: none;
        border-radius: 12px;
        font-size: 17px;
        font-weight: bold;
        cursor: pointer;
        transition: 0.2s;
    }

    button:hover {
        transform: scale(1.08);
    }

    #leftBtn {
        background: #ffca28;
        color: #222;
    }

    #rightBtn {
        background: #ff416c;
        color: white;
    }

    #surprise {
        display: none;
    }

    .emoji {
        font-size: 75px;
        animation: bounce 0.6s infinite alternate;
    }

    .shake {
        animation: shake 0.35s infinite;
    }

    .hidden {
        display: none;
    }

    @keyframes bounce {
        from { transform: translateY(0) rotate(-10deg); }
        to { transform: translateY(-20px) rotate(10deg); }
    }

    @keyframes shake {
        0%, 100% { transform: translateX(0); }
        25% { transform: translateX(-8px); }
        75% { transform: translateX(8px); }
    }

    .confetti {
        position: fixed;
        top: -30px;
        font-size: 25px;
        animation: fall 3s linear forwards;
        pointer-events: none;
    }

    @keyframes fall {
        to {
            transform: translateY(110vh) rotate(720deg);
            opacity: 0;
        }
    }
</style>
</head>

<body>

<div class="box" id="mainBox">
    <div id="question">
        <div class="emoji">🤨</div>
        <h1>এই হাদি শোন! 😂</h1>
        <p>তোর জন্য একটা সারপ্রাইজ আছে!</p>
        <p><b>যেকোনো একটা বাটনে ক্লিক কর! 👇</b></p>

        <button id="leftBtn" onclick="leftClick()">
            বাঁ বাটন 👈
        </button>

        <button id="rightBtn" onclick="rightClick()">
            ডান বাটন 👉
        </button>
    </div>

    <div id="surprise">
        <div class="emoji">🤡🤣</div>
        <h1>হাহাহা হাদি!</h1>
        <p style="font-size:24px">
            😂 তুই একটা আস্ত বোকাচোদা! 😂
        </p>
        <p>এত পড়াশোনা করিস, তাও এই ফাঁদে পা দিলি! 📚🤓</p>
        <h2>MISSION SUCCESSFUL! 💀</h2>
        <button onclick="location.reload()">আবার খেল 😈</button>
    </div>
</div>

<script>
    function leftClick() {
        alert("আবে সালা! 😂 ডান বাটনে ক্লিক কর!");
    }

    function rightClick() {
        document.getElementById("question").style.display = "none";
        document.getElementById("surprise").style.display = "block";
        document.body.classList.add("shake");

        setTimeout(() => {
            document.body.classList.remove("shake");
        }, 1500);

        const emojis = ["😂", "🤣", "🤡", "💀", "📚", "😭"];

        for (let i = 0; i < 60; i++) {
            const item = document.createElement("div");
            item.className = "confetti";
            item.textContent =
                emojis[Math.floor(Math.random() * emojis.length)];

            item.style.left = Math.random() * 100 + "vw";
            item.style.animationDelay = Math.random() * 2 + "s";

            document.body.appendChild(item);

            setTimeout(() => item.remove(), 5000);
        }
    }
</script>

</body>
</html>
