# rat-cursor-effect
rat-cursor-effect
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mouse Trail Effect</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: black;
            font-family: Arial, sans-serif;
        }
        .rat {
            position: absolute;
            font-size: 20px; /* Size of the mouse emoji */
            animation: fadeOut 0.5s ease-out forwards;
        }
        @keyframes fadeOut {
            to {
                opacity: 0;
                transform: scale(2);
            }
        }
    </style>
</head>
<body>
    <script>
        document.addEventListener("mousemove", function (e) {
            const rat = document.createElement("div");
            rat.classList.add("rat");
            rat.textContent = "🐀";  // Mouse emoji (gray rat)
            document.body.appendChild(rat);

            rat.style.left = `${e.clientX}px`;
            rat.style.top = `${e.clientY}px`;

            setTimeout(() => {
                rat.remove();
            }, 500); // Rat disappears after 0.5 seconds
        });
    </script>
</body>
</html>
