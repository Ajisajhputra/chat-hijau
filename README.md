<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chat App - Tutorial</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #e8f5e9 0%, #ffffff 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .tutorial-section {
            background: linear-gradient(135deg, #4caf50 0%, #66bb6a 100%);
            color: white;
            padding: 30px;
            overflow-y: auto;
            max-height: 80vh;
        }

        .tutorial-section h2 {
            font-size: 28px;
            margin-bottom: 20px;
            text-align: center;
            border-bottom: 2px solid white;
            padding-bottom: 15px;
        }

        .tutorial-step {
            background: rgba(255, 255, 255, 0.2);
            padding: 20px;
            margin-bottom: 15px;
            border-radius: 10px;
            backdrop-filter: blur(10px);
        }

        .tutorial-step h3 {
            font-size: 20px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .step-number {
            background: white;
            color: #4caf50;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .tutorial-step p {
            line-height: 1.6;
            font-size: 14px;
        }

        .chat-section {
            display: flex;
            flex-direction: column;
            background: white;
        }

        .chat-header {
            background: linear-gradient(135deg, #4caf50 0%, #66bb6a 100%);
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
        }

        .chat-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            min-height: 400px;
            max-height: 500px;
            background: #f5f5f5;
        }

        .message {
            margin-bottom: 15px;
            display: flex;
            flex-direction: column;
        }

        .message.user {
            align-items: flex-end;
        }

        .message.bot {
            align-items: flex-start;
        }

        .message-content {
            max-width: 70%;
            padding: 12px 16px;
            border-radius: 18px;
            word-wrap: break-word;
        }

        .message.user .message-content {
            background: linear-gradient(135deg, #4caf50 0%, #66bb6a 100%);
            color: white;
            border-bottom-right-radius: 4px;
        }

        .message.bot .message-content {
            background: white;
            color: #333;
            border: 2px solid #4caf50;
            border-bottom-left-radius: 4px;
        }

        .message-time {
            font-size: 11px;
            color: #666;
            margin-top: 5px;
            padding: 0 5px;
        }

        .chat-input-container {
            padding: 20px;
            background: white;
            border-top: 2px solid #e0e0e0;
        }

        .chat-input-wrapper {
            display: flex;
            gap: 10px;
        }

        .chat-input {
            flex: 1;
            padding: 12px 16px;
            border: 2px solid #4caf50;
            border-radius: 25px;
            font-size: 14px;
            outline: none;
            transition: all 0.3s;
        }

        .chat-input:focus {
            border-color: #66bb6a;
            box-shadow: 0 0 0 3px rgba(76, 175, 80, 0.1);
        }

        .send-button {
            background: linear-gradient(135deg, #4caf50 0%, #66bb6a 100%);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            transition: all 0.3s;
        }

        .send-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(76, 175, 80, 0.3);
        }

        .send-button:active {
            transform: translateY(0);
        }

        .typing-indicator {
            display: none;
            padding: 10px 20px;
            color: #666;
            font-style: italic;
        }

        .typing-indicator.active {
            display: block;
        }

        @media (max-width: 768px) {
            .container {
                grid-template-columns: 1fr;
                max-height: 90vh;
            }

            .tutorial-section {
                max-height: 300px;
            }
        }

        .welcome-message {
            text-align: center;
            color: #4caf50;
            padding: 20px;
            background: #e8f5e9;
            border-radius: 10px;
            margin-bottom: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="tutorial-section">
            <h2>📚 Tutorial Chat App</h2>
            
            <div class="tutorial-step">
                <h3>
                    <span class="step-number">1</span>
                    Mulai Chat
                </h3>
                <p>Ketik pesan Anda di kotak input di bagian bawah, lalu klik tombol "Kirim" atau tekan Enter untuk mengirim pesan.</p>
            </div>

            <div class="tutorial-step">
                <h3>
                    <span class="step-number">2</span>
                    Format Pesan
                </h3>
                <p>Pesan Anda akan muncul di sisi kanan dengan latar hijau, sedangkan balasan bot akan muncul di sisi kiri dengan latar putih.</p>
            </div>

            <div class="tutorial-step">
                <h3>
                    <span class="step-number">3</span>
                    Fitur Chat
                </h3>
                <p>Aplikasi ini mendukung percakapan real-time. Bot akan merespons pesan Anda dengan berbagai balasan yang relevan.</p>
            </div>

            <div class="tutorial-step">
                <h3>
                    <span class="step-number">4</span>
                    Tips Penggunaan
                </h3>
                <p>Gunakan bahasa yang jelas dan sopan. Coba tanyakan hal-hal seperti "Halo", "Apa kabar?", atau "Bantu saya" untuk memulai percakapan.</p>
            </div>

            <div class="tutorial-step">
                <h3>
                    <span class="step-number">5</span>
                    Navigasi
                </h3>
                <p>Gulir ke atas untuk melihat riwayat pesan sebelumnya. Aplikasi ini otomatis menyimpan percakapan selama sesi berlangsung.</p>
            </div>
        </div>

        <div class="chat-section">
            <div class="chat-header">
                💬 Chat App
            </div>
            
            <div class="chat-messages" id="chatMessages">
                <div class="welcome-message">
                    <h3>Selamat Datang! 👋</h3>
                    <p>Mulai percakapan dengan mengetik pesan di bawah ini.</p>
                </div>
            </div>

            <div class="typing-indicator" id="typingIndicator">
                Bot sedang mengetik...
            </div>

            <div class="chat-input-container">
                <div class="chat-input-wrapper">
                    <input 
                        type="text" 
                        class="chat-input" 
                        id="chatInput" 
                        placeholder="Ketik pesan Anda di sini..."
                        autocomplete="off"
                    >
                    <button class="send-button" id="sendButton">Kirim</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        const chatMessages = document.getElementById('chatMessages');
        const chatInput = document.getElementById('chatInput');
        const sendButton = document.getElementById('sendButton');
        const typingIndicator = document.getElementById('typingIndicator');
        const welcomeMessage = document.querySelector('.welcome-message');

        // Respon bot
        const botResponses = [
            "Halo! Senang bertemu dengan Anda. Ada yang bisa saya bantu?",
            "Terima kasih atas pesan Anda! Saya di sini untuk membantu.",
            "Wah, menarik sekali! Bisa ceritakan lebih detail?",
            "Saya mengerti. Mari kita diskusikan lebih lanjut.",
            "Bagus sekali! Apakah ada hal lain yang ingin Anda tanyakan?",
            "Saya siap membantu Anda. Silakan lanjutkan.",
            "Terima kasih sudah menggunakan chat app ini!",
            "Pesan Anda sudah saya terima. Ada yang bisa saya bantu lagi?"
        ];

        // Kata kunci untuk respon khusus
        const keywordResponses = {
            "halo": "Halo! Selamat datang di Chat App. Bagaimana saya bisa membantu Anda hari ini?",
            "hai": "Hai! Senang bertemu dengan Anda. Ada yang bisa saya bantu?",
            "terima kasih": "Sama-sama! Senang bisa membantu. Ada hal lain yang ingin ditanyakan?",
            "makasih": "Sama-sama! Jika ada pertanyaan lain, jangan ragu untuk bertanya.",
            "bantu": "Tentu saja! Saya di sini untuk membantu. Silakan jelaskan apa yang Anda butuhkan.",
            "help": "Saya siap membantu! Silakan tanyakan apa yang ingin Anda ketahui.",
            "apa kabar": "Saya baik-baik saja, terima kasih! Bagaimana dengan Anda?",
            "selamat pagi": "Selamat pagi! Semoga hari Anda menyenangkan. Ada yang bisa saya bantu?",
            "selamat siang": "Selamat siang! Semoga aktivitas Anda berjalan lancar.",
            "selamat malam": "Selamat malam! Semoga Anda beristirahat dengan baik nanti."
        };

        function getCurrentTime() {
            const now = new Date();
            return now.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' });
        }

        function addMessage(text, isUser) {
            // Hapus welcome message jika ada
            if (welcomeMessage && welcomeMessage.parentNode) {
                welcomeMessage.remove();
            }

            const messageDiv = document.createElement('div');
            messageDiv.className = `message ${isUser ? 'user' : 'bot'}`;

            const contentDiv = document.createElement('div');
            contentDiv.className = 'message-content';
            contentDiv.textContent = text;

            const timeDiv = document.createElement('div');
            timeDiv.className = 'message-time';
            timeDiv.textContent = getCurrentTime();

            messageDiv.appendChild(contentDiv);
            messageDiv.appendChild(timeDiv);
            chatMessages.appendChild(messageDiv);

            // Scroll ke bawah
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }

        function getBotResponse(userMessage) {
            const lowerMessage = userMessage.toLowerCase().trim();

            // Cek kata kunci
            for (const [keyword, response] of Object.entries(keywordResponses)) {
                if (lowerMessage.includes(keyword)) {
                    return response;
                }
            }

            // Respon random jika tidak ada kata kunci yang cocok
            return botResponses[Math.floor(Math.random() * botResponses.length)];
        }

        function sendMessage() {
            const message = chatInput.value.trim();
            
            if (message === '') {
                return;
            }

            // Tambahkan pesan user
            addMessage(message, true);
            chatInput.value = '';

            // Tampilkan typing indicator
            typingIndicator.classList.add('active');
            chatMessages.scrollTop = chatMessages.scrollHeight;

            // Simulasi delay bot
            setTimeout(() => {
                typingIndicator.classList.remove('active');
                const botResponse = getBotResponse(message);
                addMessage(botResponse, false);
            }, 1000 + Math.random() * 1000);
        }

        // Event listeners
        sendButton.addEventListener('click', sendMessage);

        chatInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                sendMessage();
            }
        });

        // Focus pada input saat halaman dimuat
        chatInput.focus();
    </script>
</body>
</html>
