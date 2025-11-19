<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>⏱️ Penghitung Waktu Mundur</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #6a1b9a, #4a148c);
            color: white;
            text-align: center;
            margin: 0;
            padding-top: 100px;
            min-height: 100vh;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .timer {
            font-size: 5rem;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            margin-bottom: 40px;
        }

        .controls {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        button {
            background-color: #9c27b0;
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 8px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: background-color 0.3s ease;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
        }

        button:hover {
            background-color: #ab47bc;
        }

        #resetBtn {
            background-color: #f44336;
        }

        #resetBtn:hover {
            background-color: #e53935;
        }
    </style>
</head>

<body>
    <h1>⏱️ Waktu Sampai Tahun Baru!</h1>
    <div class="timer" id="countdown">00:00:00</div>
    <div class="controls">
        <button id="startBtn"><i class="fas fa-play"></i> Mulai</button>
        <button id="pauseBtn"><i class="fas fa-pause"></i> Jeda</button>
        <button id="resetBtn"><i class="fas fa-undo"></i> Reset</button>
    </div>

    <script>
        // Set tanggal tujuan (Tahun Baru)
        const targetDate = new Date("Jan 1, 2026 00:00:00").getTime();
        let countdownInterval;

        function updateCountdown() {
            const now = new Date().getTime();
            const timeLeft = targetDate - now;

            const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            document.getElementById("countdown").innerHTML =
                ${String(hours).padStart(2, '0')}:${String(minutes).padStart(2, '0')}:${String(seconds).padStart(2, '0')};

            if (timeLeft < 0) {
                clearInterval(countdownInterval);
                document.getElementById("countdown").innerHTML = "🎉 Selamat Tahun Baru!";
            }
        }

        // Tombol Kontrol
        const startBtn = document.getElementById("startBtn");
        const pauseBtn = document.getElementById("pauseBtn");
        const resetBtn = document.getElementById("resetBtn");

        startBtn.addEventListener("click", () => {
            if (!countdownInterval) {
                countdownInterval = setInterval(updateCountdown, 1000);
            }
        });

        pauseBtn.addEventListener("click", () => {
            clearInterval(countdownInterval);
            countdownInterval = null;
        });

        resetBtn.addEventListener("click", () => {
            clearInterval(countdownInterval);
            countdownInterval = null;
            document.getElementById("countdown").innerHTML = "00:00:00";
        });

        // Inisialisasi
        updateCountdown();
    </script>
</body>

</html>
