<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pagina cu Lacăt</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            font-family: Arial, sans-serif;
        }
        .lock {
            font-size: 100px;
            transition: transform 0.5s ease;
        }
        .unlocked {
            transform: rotate(20deg);
            color: green;
        }
        input, button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
        }
        #startAdventure {
            display: none;
        }
    </style>
</head>
<body>
    <div id="lock" class="lock">🔒</div>
    <input type="text" id="codeInput" placeholder="Introdu codul">
    <button id="submitButton">Enter</button>
    <button id="startAdventure" onclick="nextPage()">Să înceapă aventura</button>

    <script>
        const correctCode = "1234";
        document.getElementById("submitButton").addEventListener("click", function() {
            const inputValue = document.getElementById("codeInput").value;
            if (inputValue === correctCode) {
                document.getElementById("lock").classList.add("unlocked");
                document.getElementById("lock").textContent = "🔓";
                document.getElementById("startAdventure").style.display = "block";
            }
        });

        function nextPage() {
            window.location.href = "blocuri.html";
        }
    </script>
</body>
</html>
