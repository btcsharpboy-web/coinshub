<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Elite Trading Hub</title>
    <style>
        :root { --bg: #0b0c0d; --card: #151717; --accent: #ff444f; --text: #ffffff; --green: #4caf50; }
        body { background: var(--bg); color: var(--text); font-family: 'Arial', sans-serif; margin: 0; padding: 0; }
        .nav { height: 70px; background: var(--card); display: flex; justify-content: space-between; align-items: center; padding: 0 30px; border-bottom: 1px solid #2a2d2e; }
        .logo { font-weight: 900; color: var(--accent); font-size: 24px; }
        .container { max-width: 450px; margin: 60px auto; background: var(--card); padding: 30px; border-radius: 12px; border: 1px solid #333; text-align: center; }
        input { width: 100%; padding: 15px; margin: 20px 0; background: #000; border: 1px solid #444; color: #00ff41; border-radius: 5px; box-sizing: border-box; font-family: monospace; }
        .btn { width: 100%; padding: 15px; border: none; border-radius: 5px; font-weight: bold; cursor: pointer; font-size: 16px; margin-bottom: 10px; }
        .btn-connect { background: var(--accent); color: white; }
        .btn-start { background: var(--green); color: white; display: none; }
        .btn-stop { background: #555; color: white; display: none; }
        #console { background: #000; border: 1px solid #333; padding: 15px; height: 150px; overflow-y: auto; font-family: monospace; font-size: 12px; margin-top: 20px; text-align: left; color: #aaa; }
        .success { color: var(--green); }
        .error { color: var(--accent); }
    </style>
</head>
<body>

    <div class="nav">
        <div class="logo">ELITE HUB</div>
        <div id="display-balance">Balance: --</div>
    </div>

    <div class="container" id="setup-area">
        <h2>Enter Access Token</h2>
        <input type="text" id="api-token" placeholder="Paste your token here..." />
        <button class="btn btn-connect" id="main-connect-btn">CONNECT ACCOUNT</button>
    </div>

    <div class="container" id="trading-area" style="display:none;">
        <h3 id="acc-id">Account: --</h3>
        <button class="btn btn-start" id="start-bot-btn">START DOLLAR PRINTER</button>
        <button class="btn btn-stop" id="stop-bot-btn">STOP BOT</button>
    </div>

    <div style="max-width: 450px; margin: auto;">
        <div id="console">> System ready for connection...</div>
    </div>

<script>
    const APP_ID = '36544';
    let ws = null;
    let isRunning = false;
    let stake = 0.35;

    // Helper to log to our on-screen console
    function log(msg, color = "") {
        const consoleDiv = document.getElementById('console');
        const span = document.createElement('div');
        if (color) span.className = color;
        span.innerText = `[${new Date().toLocaleTimeString()}] ${msg}`;
        consoleDiv.appendChild(span);
        consoleDiv.scrollTop = consoleDiv.scrollHeight;
    }

    // Connect Button Logic
    document.getElementById('main-connect-btn').addEventListener('click', function() {
        const token = document.getElementById('api-token').value.trim();
        if (!token) return alert("Please paste a token first.");

        log("Attempting to connect to Deriv...");
        
        if (ws) ws.close();
        ws = new WebSocket(`wss://ws.derivws.com/websockets/v3?app_id=${APP_ID}`);

        ws.onopen = () => {
            log("Socket opened. Authorizing token...");
            ws.send(JSON.stringify({ authorize: token }));
        };

        ws.onmessage = (msg) => {
            const res = JSON.parse(msg.data);

            if (res.error) {
                log("ERROR: " + res.error.message, "error");
                return;
            }

            if (res.msg_type === 'authorize') {
                log("Authorized
