<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>instagram: @pythonlearnerr</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(135deg, #ffdee9, #b5fffc);
        font-family: Arial, sans-serif;
    }

    .container {
        width: 90vw;
        max-width: 400px;
        height: 90vw;
        max-height: 400px;
        background: white;
        border-radius: 15px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        position: relative;
        text-align: center;
        padding-top: 30px;
    }

    h2 {
        font-size: 1.4rem;
        margin-bottom: 30px;
    }

    button {
        padding: 12px 25px;
        font-size: 1rem;
        border: none;
        border-radius: 25px;
        cursor: pointer;
    }

    #yes {
        background-color: #4CAF50;
        color: white;
    }

    #no {
        background-color: #f44336;
        color: white;
        position: absolute;
        left: 50%;
        top: 60%;
        transform: translate(-50%, -50%);
    }

    /* Popup */
    .popup {
        display: none;
        position: fixed;
        inset: 0;
        background: rgba(0,0,0,0.5);
        justify-content: center;
        align-items: center;
    }

    .popup-box {
        background: white;
        padding: 20px;
        border-radius: 15px;
        width: 80%;
        max-width: 300px;
        text-align: center;
    }

    .popup-box button {
        margin-top: 15px;
        background: #4CAF50;
        color: white;
        width: 100%;
    }
</style>
</head>

<body>

<div class="container">
    <h2>Do you like me? ❤️</h2>
    <button id="yes" onclick="showPopup()">Yes</button>
    <button id="no">No</button>
</div>

<div class="popup" id="popup">
    <div class="popup-box">
        <p>Thanks for Accepting 😍</p>
        <button onclick="closePopup()">OK</button>
    </div>
</div>

<script>
    const noButton = document.getElementById("no");
    const container = document.querySelector(".container");

    function moveButton() {
        const maxX = container.clientWidth - noButton.offsetWidth;
        const maxY = container.clientHeight - noButton.offsetHeight;

        const x = Math.random() * maxX;
        const y = Math.random() * maxY;

        noButton.style.left = x + "px";
        noButton.style.top = y + "px";
        noButton.style.transform = "none";
    }

    // Desktop hover
    noButton.addEventListener("mouseenter", moveButton);

    // Mobile touch
    noButton.addEventListener("touchstart", moveButton);

    function showPopup() {
        document.getElementById("popup").style.display = "flex";
    }

    function closePopup() {
        document.getElementById("popup").style.display = "none";
    }
</script>

</body>
</html>
