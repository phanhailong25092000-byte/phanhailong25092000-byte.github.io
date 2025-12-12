<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trò chơi Cờ Caro (Tic-Tac-Toe)</title>
    <style>
        /* --- CSS: Làm đẹp giao diện --- */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f2f5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .game-container {
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            text-align: center;
        }

        h1 {
            color: #2c3e50;
            margin: 0 0 20px 0;
        }

        /* Khu vực hiển thị trạng thái (Lượt ai, Ai thắng) */
        #status {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #555;
            font-weight: bold;
            height: 1.5em; /* Giữ chiều cao cố định để không bị nhảy layout */
        }

        /* Lưới bàn cờ 3x3 */
        .board {
            display: grid;
            grid-template-columns: repeat(3, 100px);
            grid-template-rows: repeat(3, 100px);
            gap: 5px;
            margin: 0 auto 25px auto;
            background-color: #dfe6e9; /* Màu nền của các khe hở */
            border: 5px solid #dfe6e9;
            border-radius: 5px;
        }

        /* Ô cờ */
        .cell {
            background-color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 4rem;
            font-weight: bold;
            cursor: pointer;
            user-select: none; /* Không cho bôi đen chữ */
            transition: background 0.2s;
        }

        /* Hiệu ứng khi di chuột vào ô trống */
        .cell:not(.x):not(.o):hover {
            background-color: #f1f2f6;
        }

        /* Màu sắc riêng cho X và O */
        .cell.x { color: #e74c3c; } /* Màu đỏ cho X */
        .cell.o { color: #3498db; } /* Màu xanh cho O */

        /* Nút chơi lại */
        #restartBtn {
            padding: 12px 24px;
            font-size: 1.1rem;
            background-color: #2c3e50;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            transition: background 0.3s;
            display: none; /* Ẩn đi khi mới vào game */
            margin: 0 auto;
        }

        #restartBtn:hover {
            background-color: #34495e;
        }
    </style>
</head>
<body>

    <div class="game-container">
        <h1>Cờ Caro</h1>
        <div id="status">Lượt của X</div>
        
        <div class="board">
            <div class="cell" data-index="0"></div>
            <div class="cell" data-index="1"></div>
            <div class="cell" data-index="2"></div>
            <div class="cell" data-index="3"></div>
            <div class="cell" data-index="4"></div>
            <div class="cell" data-index="5"></div>
            <div class="cell" data-index="6"></div>
            <div class="cell" data-index="7"></div>
            <div class="cell" data-index="8"></div>
        </div>

        <button id="restartBtn">Chơi lại ván mới</button>
    </div>

    <script>
        // 1. Khởi tạo các biến trạng thái
        const statusDisplay = document.querySelector('#status');
        const restartBtn = document.querySelector('#restartBtn');
        const cells = document.querySelectorAll('.cell');

        let gameActive = true; // Trò chơi đang diễn ra hay đã kết thúc
        let currentPlayer = "X"; // Người chơi hiện tại
        // Mảng lưu trạng thái của 9 ô cờ (ban đầu là chuỗi rỗng)
        let gameState = ["", "", "", "", "", "", "", "", ""];

        // Các trường hợp thắng (các dòng, cột, đường chéo)
        const winningConditions = [
            [0, 1, 2], [3, 4, 5], [6, 7, 8], // Hàng ngang
            [0, 3, 6], [1, 4, 7], [2, 5, 8], // Hàng dọc
            [0, 4, 8], [2, 4, 6]             // Đường chéo
        ];

        // --- Các hàm xử lý ---

        // Hàm hiển thị lượt đi
        const currentPlayerTurnHtml = () => `Lượt của <span style="color: ${currentPlayer === 'X' ? '#e74c3c' : '#3498db'}">${currentPlayer}</span>`;

        // Hàm xử lý khi click vào một ô
        function handleCellClick(clickedCellEvent) {
            const clickedCell = clickedCellEvent.target;
            // Lấy chỉ số (index) của ô vừa click (từ 0 đến 8)
            const clickedCellIndex = parseInt(clickedCell.getAttribute('data-index'));

            // Nếu ô đã được đánh hoặc game đã kết thúc thì bỏ qua
            if (gameState[clickedCellIndex] !== "" || !gameActive) {
                return;
            }

            // Cập nhật ô đã đánh
            handleCellPlayed(clickedCell, clickedCellIndex);
            // Kiểm tra kết quả sau khi đánh
            handleResultValidation();
        }

        // Hàm cập nhật giao diện và trạng thái ô cờ
        function handleCellPlayed(clickedCell, clickedCellIndex) {
            gameState[clickedCellIndex] = currentPlayer;
            clickedCell.innerHTML = currentPlayer;
            // Thêm class để đổi màu chữ (class 'x' hoặc 'o')
            clickedCell.classList.add(currentPlayer.toLowerCase());
        }

        // Hàm kiểm tra thắng/thua/hòa
        function handleResultValidation() {
            let roundWon = false;
            // Duyệt qua tất cả các điều kiện thắng
            for (let i = 0; i < winningConditions.length; i++) {
                const winCondition = winningConditions[i];
                let a = gameState[winCondition[0]];
                let b = gameState[winCondition[1]];
                let c = gameState[winCondition[2]];

                // Nếu có ô trống trong dòng này thì chưa thắng
                if (a === '' || b === '' || c === '') {
                    continue;
                }
                // Nếu 3 ô giống nhau (XXX hoặc OOO) thì thắng
                if (a === b && b === c) {
                    roundWon = true;
                    break;
                }
            }

            if (roundWon) {
                statusDisplay.innerHTML = `🎉 Chúc mừng! Người chơi ${currentPlayer} đã thắng!`;
                gameActive = false; // Dừng game
                restartBtn.style.display = "block"; // Hiện nút chơi lại
                return;
            }

            // Kiểm tra hòa (Nếu không còn ô trống nào trong mảng gameState)
            let roundDraw = !gameState.includes("");
            if (roundDraw) {
                statusDisplay.innerHTML = `🤝 Ván đấu Hòa!`;
                gameActive = false;
                restartBtn.style.display = "block";
                return;
            }

            // Nếu chưa thắng và chưa hòa, đổi lượt người chơi
            handlePlayerChange();
        }

        // Hàm đổi người chơi
        function handlePlayerChange() {
            currentPlayer = currentPlayer === "X" ? "O" : "X";
            statusDisplay.innerHTML = currentPlayerTurnHtml();
        }

        // Hàm chơi lại (Reset game)
        function handleRestartGame() {
            gameActive = true;
            currentPlayer = "X";
            gameState = ["", "", "", "", "", "", "", "", ""];
            statusDisplay.innerHTML = currentPlayerTurnHtml();
            restartBtn.style.display = "none";
            
            // Xóa nội dung và class màu sắc trên bàn cờ
            cells.forEach(cell => {
                cell.innerHTML = "";
                cell.classList.remove('x', 'o');
            });
        }

        // --- Gán sự kiện (Event Listeners) ---
        // Gán sự kiện click cho từng ô cờ
        cells.forEach(cell => cell.addEventListener('click', handleCellClick));
        // Gán sự kiện cho nút chơi lại
        restartBtn.addEventListener('click', handleRestartGame);

        // Hiển thị trạng thái ban đầu
        statusDisplay.innerHTML = currentPlayerTurnHtml();
    </script>
</body>
</html>
