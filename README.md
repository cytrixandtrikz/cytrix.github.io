    #loading-screen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: radial-gradient(ellipse at bottom, #000 0%, #111 100%);
      z-index: 1000;
      animation: fadeOut 1s ease 3s forwards;
    }

    @keyframes fadeOut {
      to {
        opacity: 0;
        visibility: hidden;
      }
    }

    .rocket {
      position: absolute;
      bottom: 100px;
      left: 50%;
      transform: translateX(-50%);
      width: 40px;
      height: 80px;
      background: white;
      border-radius: 20px 20px 5px 5px;
      z-index: 10;
      animation: rocket-launch 3s ease forwards;
    }

    .rocket .window {
      position: absolute;
      top: 20px;
      left: 50%;
      transform: translateX(-50%);
      width: 15px;
      height: 15px;
      background: #3cf;
      border-radius: 50%;
      border: 2px solid #0cf;
    }

    .rocket .flame {
      position: absolute;
      top: 100%;
      left: 50%;
      transform: translateX(-50%);
      width: 14px;
      height: 80px;
      background: orange;
      border-radius: 50%;
      animation: flame-flicker 0.3s infinite;
    }

    @keyframes flame-flicker {
      0%, 100% { background: orange; height: 80px; }
      50% { background: red; height: 60px; }
    }

    @keyframes rocket-launch {
      0% { transform: translateX(-50%) translateY(0); }
      100% { transform: translateX(-50%) translateY(-200px); }
    }

    .sidebar {
      width: 200px;
      background-color: #111;
      padding: 20px;
      border-right: 1px solid #333;
      height: 100vh;
      z-index: 10;
    }

    .sidebar h1 {
      color: #ff66cc;
    }

    .sidebar a {
      display: block;
      color: white;
      text-decoration: none;
      margin: 20px 0;
    }

    .sidebar a:hover {
      color: #ff66cc;
    }

    .content {
      flex-grow: 1;
      padding: 40px;
      overflow-y: auto;
    }

    .section {
      display: none;
    }

    .section.active {
      display: block;
    }

    #output-container {
      margin-top: 20px;
      background: #111;
      border: 1px solid #333;
      height: calc(100vh - 280px);
    }

    #output-frame {
      width: 100%;
      height: 100%;
      border: none;
    }

    input, button {
      background: #222;
      color: white;
      border: 1px solid #555;
      padding: 6px 10px;
      margin: 5px 0;
    }

    button:hover {
      background: #333;
      cursor: pointer;
    }

    <div id="code-editor" class="section">
      <h2>Select Your Language and Code</h2>
      <button onclick="setLanguage('html')">HTML</button>
      <button onclick="setLanguage('css')">CSS</button>
      <button onclick="setLanguage('javascript')">JavaScript</button>
      <textarea id="code-area" style="width:100%;height:300px;background:#111;color:white;border:1px solid #333;margin-top:10px;"></textarea>
      <button onclick="runCode()">Run Code</button>
      <div id="output-container">
        <iframe id="output-frame"></iframe>
      </div>
      <div id="error-msg" style="color:red;margin-top:10px;"></div>
    </div>

    <div id="hackit" class="section">
      <h2>HackIt! Level 1</h2>
      <p>Can you deencrypt the password from the HTML source code?</p>
      <!-- Encrypted password (Base64): dHJpY2t6X21hc3Rlcg== -->
      <input type="text" id="hackit-answer" placeholder="Enter password...">
      <button onclick="checkHackitLevel1()">Submit</button>
      <div id="hackit-result" style="margin-top:10px;"></div>
    </div>

    <div id="hackit-level2" class="section">
      <h2>HackIt! Level 2</h2>
      <p>Encrypt the following password and enter the result.</p>
      <p><strong>Password:</strong> phantom_gate</p>
      <input type="text" id="level2-answer" placeholder="Enter encrypted password...">
      <button onclick="checkHackitLevel2()">Submit</button>
      <div id="level2-result" style="margin-top:10px;"></div>
    </div>

    <div id="recon" class="section">
      <h2>🕵️ Reconnaissance</h2>
      <p>Once you hack the account and get the encrypted password, you win. To win, you must paste both the encrypted password and the real password below:</p>
      <input type="text" id="encrypted" placeholder="Encrypted password (Base64)">
      <br>
      <input type="text" id="realpass" placeholder="Real password">
      <br>
      <button onclick="checkRecon()">Submit</button>
      <div id="recon-result" style="margin-top:10px;"></div>
      <br><br>
      <button onclick="window.open('https://cytrixandtrikz.github.io/instawam.github.io/', '_blank')">Start</button>
    </div>
