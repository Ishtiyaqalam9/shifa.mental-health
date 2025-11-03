<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shifa – মানসিক আরোগ্যের ডিজিটাল সঙ্গী</title>
<style>
  * { box-sizing: border-box; }
  body {
    font-family: "Segoe UI", sans-serif;
    margin: 0;
    background: linear-gradient(135deg, #cce4f7, #e9f3ff);
    color: #222;
    transition: background 0.3s ease;
  }

  header {
    background: linear-gradient(90deg, #007acc, #0099cc);
    color: white;
    text-align: center;
    padding: 50px 40px;
    font-size: 26px;
    font-weight: bold;
    letter-spacing: 1px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    position: relative;
  }

  .header-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url('https://picsum.photos/seed/shifa-header/1200/300.jpg');
    background-size: cover;
    background-position: center;
    opacity: 0.2;
    z-index: -1;
  }

  section {
    display: none;
    background: white;
    max-width: 900px;
    margin: 40px auto;
    padding: 30px;
    border-radius: 18px;
    box-shadow: 0 8px 18px rgba(0,0,0,0.1);
    animation: fadeIn 0.4s ease;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
  }

  h2 {
    color: #007acc;
    margin-bottom: 20px;
    text-align: center;
  }

  p { text-align: center; }

  button {
    margin: 8px;
    padding: 10px 20px;
    border-radius: 30px;
    border: none;
    background: #007acc;
    color: white;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: 0.3s;
  }

  button:hover {
    background: #005f99;
    transform: scale(1.05);
  }

  input, textarea, select {
    width: 100%;
    padding: 10px;
    border-radius: 10px;
    border: 1px solid #007acc;
    margin-top: 8px;
    margin-bottom: 16px;
    font-size: 15px;
  }

  .feature-btn {
    width: 100%;
    background: #f0f8ff;
    color: #007acc;
    text-align: left;
    padding: 15px;
    margin: 8px 0;
    border: 1px solid #cce4f7;
    border-radius: 12px;
    transition: all 0.3s ease;
    font-weight: 500;
  }

  .feature-btn:hover {
    background: #007acc;
    color: white;
    transform: scale(1.02);
  }

  .back-btn {
    background: #ff6b6b;
  }

  .back-btn:hover {
    background: #c0392b;
  }

  /* Sub-feature CSS */
  .sub-feature {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 8px;
    margin: 20px 0;
  }

  .sub-feature button {
    background: #e7f5ff;
    color: #007acc;
    border: 1px solid #cce4f7;
    border-radius: 10px;
    padding: 8px 15px;
    font-size: 14px;
    cursor: pointer;
    transition: 0.3s;
  }

  .sub-feature button:hover {
    background: #007acc;
    color: white;
  }

  /* Chatbot styles */
  .chatbot-container {
    position: fixed;
    bottom: 20px;
    right: 20px;
    width: 300px;
    height: 400px;
    background: white;
    border-radius: 15px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    display: none;
    flex-direction: column;
    z-index: 1000;
  }

  .chatbot-header {
    background: #007acc;
    color: white;
    padding: 10px;
    border-radius: 15px 15px 0 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .chatbot-messages {
    flex: 1;
    padding: 10px;
    overflow-y: auto;
  }

  .chatbot-input {
    display: flex;
    padding: 10px;
  }

  .chatbot-input input {
    flex: 1;
    margin-right: 5px;
  }

  .chatbot-toggle {
    position: fixed;
    bottom: 20px;
    right: 20px;
    width: 60px;
    height: 60px;
    background: #007acc;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-size: 24px;
    cursor: pointer;
    box-shadow: 0 3px 10px rgba(0,0,0,0.2);
    z-index: 999;
  }

  .message {
    margin-bottom: 10px;
    padding: 8px;
    border-radius: 10px;
    max-width: 80%;
  }

  .bot-message {
    background: #e7f5ff;
    align-self: flex-start;
  }

  .user-message {
    background: #007acc;
    color: white;
    align-self: flex-end;
    margin-left: auto;
  }

  /* Content area styles */
  .content-area {
    background: #f9f9f9;
    padding: 20px;
    border-radius: 10px;
    margin: 20px 0;
  }

  .mood-tracker {
    display: flex;
    justify-content: space-around;
    margin: 20px 0;
  }

  .mood-option {
    text-align: center;
    cursor: pointer;
    transition: transform 0.2s;
  }

  .mood-option:hover {
    transform: scale(1.1);
  }

  .mood-emoji {
    font-size: 30px;
  }

  .chart-container {
    height: 200px;
    background: white;
    border-radius: 10px;
    padding: 15px;
    margin: 20px 0;
    position: relative;
  }

  .chart-bar {
    position: absolute;
    bottom: 30px;
    width: 40px;
    background: #007acc;
    border-radius: 5px 5px 0 0;
    transition: height 0.5s;
  }

  .symptom-checker {
    background: #f9f9f9;
    padding: 15px;
    border-radius: 10px;
    margin: 20px 0;
  }

  .checkbox-group {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin: 15px 0;
  }

  .checkbox-item {
    display: flex;
    align-items: center;
    background: white;
    padding: 8px 12px;
    border-radius: 20px;
    border: 1px solid #cce4f7;
  }

  .checkbox-item input {
    width: auto;
    margin-right: 5px;
  }

  .assessment-question {
    margin: 20px 0;
  }

  .assessment-options {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 10px;
  }

  .assessment-option {
    background: white;
    padding: 10px;
    border-radius: 10px;
    border: 1px solid #cce4f7;
    cursor: pointer;
    transition: all 0.2s;
  }

  .assessment-option:hover {
    background: #e7f5ff;
  }

  .assessment-option.selected {
    background: #007acc;
    color: white;
  }

  .progress-bar {
    height: 10px;
    background: #e7f5ff;
    border-radius: 5px;
    margin: 20px 0;
    overflow: hidden;
  }

  .progress {
    height: 100%;
    background: #007acc;
    width: 0%;
    transition: width 0.3s;
  }

  .forum-post {
    background: white;
    padding: 15px;
    border-radius: 10px;
    margin-bottom: 15px;
    border-left: 4px solid #007acc;
  }

  .forum-post-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
    font-weight: bold;
  }

  .forum-post-content {
    margin-bottom: 10px;
  }

  .forum-post-actions {
    display: flex;
    gap: 10px;
    font-size: 14px;
    color: #666;
  }

  .forum-post-actions span {
    cursor: pointer;
  }

  .forum-post-actions span:hover {
    color: #007acc;
  }

  .reminder-item {
    display: flex;
    align-items: center;
    background: white;
    padding: 15px;
    border-radius: 10px;
    margin-bottom: 10px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  }

  .reminder-icon {
    font-size: 24px;
    margin-right: 15px;
  }

  .reminder-content {
    flex: 1;
  }

  .reminder-time {
    color: #666;
    font-size: 14px;
  }

  .reminder-toggle {
    background: none;
    border: none;
    color: #007acc;
    font-size: 20px;
    cursor: pointer;
    margin: 0;
  }

  .tab-container {
    margin: 20px 0;
  }

  .tab-buttons {
    display: flex;
    border-bottom: 1px solid #cce4f7;
  }

  .tab-button {
    background: none;
    border: none;
    padding: 10px 15px;
    cursor: pointer;
    color: #666;
    font-weight: 500;
    border-bottom: 2px solid transparent;
    margin: 0;
  }

  .tab-button.active {
    color: #007acc;
    border-bottom: 2px solid #007acc;
  }

  .tab-content {
    padding: 20px 0;
  }

  .tab-pane {
    display: none;
  }

  .tab-pane.active {
    display: block;
  }

  .tracker-form {
    background: #f9f9f9;
    padding: 15px;
    border-radius: 10px;
    margin: 20px 0;
  }

  .form-group {
    margin-bottom: 15px;
  }

  .form-group label {
    display: block;
    margin-bottom: 5px;
    font-weight: 500;
  }

  .form-group input, .form-group select, .form-group textarea {
    margin: 0;
  }

  .anonymous-message {
    background: #f9f9f9;
    padding: 15px;
    border-radius: 10px;
    margin: 20px 0;
  }

  .anonymous-message textarea {
    min-height: 100px;
  }

  .voice-player {
    background: #f9f9f9;
    padding: 15px;
    border-radius: 10px;
    margin: 20px 0;
    text-align: center;
  }

  .voice-controls {
    display: flex;
    justify-content: center;
    gap: 15px;
    margin: 15px 0;
  }

  .voice-control-btn {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
  }

  .voice-progress {
    height: 6px;
    background: #e7f5ff;
    border-radius: 3px;
    margin: 15px 0;
    overflow: hidden;
  }

  .voice-progress-bar {
    height: 100%;
    background: #007acc;
    width: 0%;
    transition: width 0.1s linear;
  }

  .voice-title {
    font-weight: 500;
    margin-bottom: 10px;
  }

  .voice-time {
    color: #666;
    font-size: 14px;
  }
</style>
</head>
<body>

<header>
  <div class="header-image"></div>
  Shifa – মানসিক আরোগ্যের ডিজিটাল সঙ্গী
</header>

<!-- Home Page -->
<section id="home" style="display:block; text-align:center;">
  <img src="https://cdn-icons-png.flaticon.com/512/2966/2966486.png" 
       alt="Healthcare Illustration" 
       style="width:130px; margin-bottom:25px;">
  <h2>স্বাগতম!</h2>
  <p>আপনার মানসিক আরোগ্যের পথে Shifa সঙ্গে আছে 💙</p>
  <button onclick="showLogin()">Login</button>
  <button onclick="showSignUp()">Sign Up</button>
</section>

<!-- Login Page -->
<section id="login">
  <h2>Login করুন</h2>
  <input type="text" id="login-username" placeholder="Username">
  <input type="password" id="login-password" placeholder="Password">
  <button onclick="login()">Login</button>
  <p id="login-msg" style="color:red;"></p>
  <p>নতুন ব্যবহারকারী? <button style="background:none; color:#007acc;" onclick="showSignUp()">Sign Up</button></p>
</section>

<!-- Sign Up Page -->
<section id="signup">
  <h2>একাউন্ট তৈরি করুন</h2>
  <input type="text" id="signup-username" placeholder="Username">
  <input type="email" id="signup-email" placeholder="Email">
  <input type="password" id="signup-password" placeholder="Password">
  <button onclick="signup()">Sign Up</button>
  <p id="signup-msg" style="color:red;"></p>
  <p>Already have account? <button style="background:none; color:#007acc;" onclick="showLogin()">Login</button></p>
</section>

<!-- Features Menu -->
<section id="menu">
  <h2>✨ SHIFA Features</h2>
  <button class="feature-btn" onclick="openFeature('dashboard')">📊 ড্যাশবোর্ড</button>
  <button class="feature-btn" onclick="openFeature('monpulse')">🧠 মনের পরীক্ষা</button>
  <button class="feature-btn" onclick="openFeature('rogradar')">⚕ রোগরাডার</button>
  <button class="feature-btn" onclick="openFeature('chupline')">🕊 চুপলাইন</button>
  <button class="feature-btn" onclick="openFeature('rituboost')">☀ ঋতুবসুতি</button>
  <button class="feature-btn" onclick="openFeature('mababybuddy')">👩‍👧 মা ও শিশুর ট্র্যাকার</button>
  <button class="feature-btn" onclick="openFeature('voicecare')">🎙 VoiceCare</button>
  <button class="feature-btn" onclick="openFeature('forum')">💬 Community Forum</button>
  <button class="feature-btn" onclick="openFeature('reminder')">⏰ Daily Reminder</button>
  <button class="feature-btn" onclick="openChatbot()">🤖 Shifa Assistant</button>
</section>

<!-- Dashboard Section with Sub-features -->
<section id="dashboard">
  <h2>📊 ড্যাশবোর্ড</h2>
  <p>এখানে আপনি আপনার সাম্প্রতিক কার্যক্রম ও মানসিক স্বাস্থ্যের সারসংক্ষেপ দেখতে পারবেন।</p>

  <div class="tab-container">
    <div class="tab-buttons">
      <button class="tab-button active" onclick="openTab('mood-summary', this)">মানসিক সারসংক্ষেপ</button>
      <button class="tab-button" onclick="openTab('progress-chart', this)">অগ্রগতি চার্ট</button>
      <button class="tab-button" onclick="openTab('daily-log', this)">দৈনিক লগ</button>
    </div>

    <div class="tab-content">
      <div id="mood-summary" class="tab-pane active">
        <div class="content-area">
          <h3>আজকের মানসিক অবস্থা</h3>
          <div class="mood-tracker">
            <div class="mood-option" onclick="selectMood(this, 'very-happy')">
              <div class="mood-emoji">😄</div>
              <p>খুব ভালো</p>
            </div>
            <div class="mood-option" onclick="selectMood(this, 'happy')">
              <div class="mood-emoji">😊</div>
              <p>ভালো</p>
            </div>
            <div class="mood-option" onclick="selectMood(this, 'neutral')">
              <div class="mood-emoji">😐</div>
              <p>স্বাভাবিক</p>
            </div>
            <div class="mood-option" onclick="selectMood(this, 'sad')">
              <div class="mood-emoji">😔</div>
              <p>খারাপ</p>
            </div>
            <div class="mood-option" onclick="selectMood(this, 'very-sad')">
              <div class="mood-emoji">😢</div>
              <p>খুব খারাপ</p>
            </div>
          </div>
          <div id="mood-note" style="display:none; margin-top:20px;">
            <h4>আপনার আজকের অনুভূতি সম্পর্কে লিখুন:</h4>
            <textarea id="mood-note-text" placeholder="আপনি কেমন অনুভব করছেন এবং কেন?"></textarea>
            <button onclick="saveMoodNote()">সংরক্ষণ করুন</button>
          </div>
        </div>
      </div>

      <div id="progress-chart" class="tab-pane">
        <div class="content-area">
          <h3>মানসিক স্বাস্থ্য অগ্রগতি</h3>
          <div class="chart-container">
            <div class="chart-bar" style="left: 20px; height: 60%;"></div>
            <div class="chart-bar" style="left: 80px; height: 70%;"></div>
            <div class="chart-bar" style="left: 140px; height: 50%;"></div>
            <div class="chart-bar" style="left: 200px; height: 80%;"></div>
            <div class="chart-bar" style="left: 260px; height: 75%;"></div>
            <div class="chart-bar" style="left: 320px; height: 85%;"></div>
            <div class="chart-bar" style="left: 380px; height: 90%;"></div>
          </div>
          <div style="display: flex; justify-content: space-between; margin-top: 10px; font-size: 12px; color: #666;">
            <span>সোম</span>
            <span>মঙ্গল</span>
            <span>বুধ</span>
            <span>বৃহস্পতি</span>
            <span>শুক্র</span>
            <span>শনি</span>
            <span>রবি</span>
          </div>
          <p style="margin-top: 20px; text-align: center;">এই সপ্তাহে আপনার মানসিক স্বাস্থ্য ১৫% উন্নতি হয়েছে।</p>
        </div>
      </div>

      <div id="daily-log" class="tab-pane">
        <div class="content-area">
          <h3>দৈনিক লগ</h3>
          <div class="tracker-form">
            <div class="form-group">
              <label>আজকের তারিখ</label>
              <input type="date" id="log-date" value="">
            </div>
            <div class="form-group">
              <label>আপনি আজ কী কী করেছেন?</label>
              <textarea id="log-activities" placeholder="আজকের কার্যক্রম লিখুন..."></textarea>
            </div>
            <div class="form-group">
              <label>আপনি কেমন অনুভব করেছেন?</label>
              <select id="log-mood">
                <option value="very-happy">খুব ভালো</option>
                <option value="happy">ভালো</option>
                <option value="neutral">স্বাভাবিক</option>
                <option value="sad">খারাপ</option>
                <option value="very-sad">খুব খারাপ</option>
              </select>
            </div>
            <button onclick="saveDailyLog()">লগ সংরক্ষণ করুন</button>
          </div>
          <div id="daily-logs" style="margin-top: 20px;">
            <h4>পূর্ববর্তী লগসমূহ</h4>
            <div class="forum-post">
              <div class="forum-post-header">
                <span>১৫ মে, ২০২৩</span>
                <span>মেজাজ: 😊</span>
              </div>
              <div class="forum-post-content">
                আজ সকালে হাঁটা শেষে ভালো লাগছে। কাজে মনোযোগ বেশি ছিল।
              </div>
            </div>
            <div class="forum-post">
              <div class="forum-post-header">
                <span>১৪ মে, ২০২৩</span>
                <span>মেজাজ: 😐</span>
              </div>
              <div class="forum-post-content">
                আজ কিছুটা চাপ অনুভব করছি। কাজের চাপ বেশি।
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Mind Test Section -->
<section id="monpulse">
  <h2>🧠 মনের পরীক্ষা</h2>
  <p>একটা ছোট সার্ভে নিন, জানুন আপনার বর্তমান মুড কেমন।</p>
  
  <div class="content-area">
    <div class="progress-bar">
      <div class="progress" id="assessment-progress"></div>
    </div>
    <p style="text-align: right; font-size: 14px; color: #666;">প্রশ্ন <span id="current-question">1</span> / <span id="total-questions">5</span></p>
    
    <div id="assessment-container">
      <div class="assessment-question">
        <h3>আপনি গত সপ্তাহে কতবার মনে হয়েছে যে আপনি নিজেকে নিয়ন্ত্রণ করতে পারছেন না?</h3>
        <div class="assessment-options">
          <div class="assessment-option" onclick="selectOption(this, 0)">কখনোই না</div>
          <div class="assessment-option" onclick="selectOption(this, 1)">খুব কমই</div>
          <div class="assessment-option" onclick="selectOption(this, 2)">কখনো কখনো</div>
          <div class="assessment-option" onclick="selectOption(this, 3)">বেশিরভাগ সময়</div>
          <div class="assessment-option" onclick="selectOption(this, 4)">প্রায় সব সময়</div>
        </div>
      </div>
    </div>
    
    <div id="assessment-result" style="display:none; text-align: center;">
      <h3>আপনার মানসিক স্বাস্থ্য পরীক্ষার ফলাফল</h3>
      <div style="font-size: 60px; margin: 20px 0;">😊</div>
      <p>আপনার মানসিক স্বাস্থ্য ভালো অবস্থায় আছে। আপনি নিজের আবেগগুলোকে ভালোভাবে ব্যবস্থাপনা করতে পারছেন।</p>
      <p style="margin-top: 20px;">আপনার স্কোর: <span id="score-value" style="font-weight: bold; color: #007acc;">৭/১০</span></p>
      <div style="margin-top: 30px;">
        <h4>সুপারিশ:</h4>
        <p>আপনার মানসিক স্বাস্থ্য ভালো রাখতে নিয়মিত ব্যায়াম এবং ধ্যান করুন।</p>
      </div>
      <button onclick="restartAssessment()">আবার পরীক্ষা দিন</button>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Disease Radar Section -->
<section id="rogradar">
  <h2>⚕ রোগরাডার</h2>
  <p>আপনার উপসর্গ দিন, সম্ভাব্য স্বাস্থ্য সমস্যা জানুন।</p>
  
  <div class="symptom-checker">
    <h3>আপনার উপসর্গগুলো নির্বাচন করুন:</h3>
    <div class="checkbox-group">
      <div class="checkbox-item">
        <input type="checkbox" id="symptom1" value="headache">
        <label for="symptom1">মাথাব্যথা</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom2" value="fatigue">
        <label for="symptom2">ক্লান্তি</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom3" value="anxiety">
        <label for="symptom3">উদ্বেগ</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom4" value="insomnia">
        <label for="symptom4">অনিদ্রা</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom5" value="appetite-loss">
        <label for="symptom5">ক্ষুধামন্দা</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom6" value="sadness">
        <label for="symptom6">বিষণ্ণতা</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom7" value="irritability">
        <label for="symptom7">বিরক্তিভাব</label>
      </div>
      <div class="checkbox-item">
        <input type="checkbox" id="symptom8" value="concentration">
        <label for="symptom8">মনোযোগ সমস্যা</label>
      </div>
    </div>
    
    <div class="form-group">
      <label>আপনার উপসর্গ কতদিন ধরে চলছে?</label>
      <select id="symptom-duration">
        <option value="less-than-week">এক সপ্তাহের কম</option>
        <option value="one-to-two-weeks">এক থেকে দুই সপ্তাহ</option>
        <option value="two-to-four-weeks">দুই থেকে চার সপ্তাহ</option>
        <option value="more-than-month">এক মাসের বেশি</option>
      </select>
    </div>
    
    <button onclick="analyzeSymptoms()">উপসর্গ বিশ্লেষণ করুন</button>
    
    <div id="symptom-result" style="display:none; margin-top: 20px;">
      <h3>বিশ্লেষণ ফলাফল</h3>
      <div class="content-area">
        <p>আপনার উপসর্গগুলোর উপর ভিত্তি করে, আপনি হয়তো নিচের স্বাস্থ্য সমস্যাগুলোর মুখোমুখি হচ্ছেন:</p>
        <div style="margin: 20px 0;">
          <div style="background: #e7f5ff; padding: 15px; border-radius: 10px; margin-bottom: 10px;">
            <h4>সম্ভাব্য সমস্যা: হালকা ডিপ্রেশন</h4>
            <p>আপনার উপসর্গগুলো হালকা ডিপ্রেশনের সাথে মিলে যাচ্ছে। এটি একটি সাধারণ মানসিক স্বাস্থ্য সমস্যা যা চিকিৎসাযোগ্য।</p>
          </div>
          <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
            <h4>সুপারিশ:</h4>
            <ul style="text-align: left; padding-left: 20px;">
              <li>নিয়মিত ব্যায়াম করুন</li>
              <li>পর্যাপ্ত ঘুমান</li>
              <li>স্বাস্থ্যকর খাবার খান</li>
              <li>বন্ধুবান্ধব ও পরিবারের সাথে সময় কাটান</li>
              <li>প্রয়োজনে একজন মানসিক স্বাস্থ্য পেশাজীবীর সাথে কথা বলুন</li>
            </ul>
          </div>
        </div>
        <p style="font-size: 14px; color: #666; text-align: center;">এটি শুধুমাত্র একটি প্রাথমিক বিশ্লেষণ। সঠিক রোগ নির্ণয়ের জন্য একজন ডাক্তারের সাথে পরামর্শ করুন।</p>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- ChupLine Section -->
<section id="chupline">
  <h2>🕊 চুপলাইন</h2>
  <p>গোপনে সাহায্য চান, কেউ জানবে না — আমরা আছি পাশে।</p>
  
  <div class="anonymous-message">
    <h3>আপনার মনের কথা গোপনে শেয়ার করুন</h3>
    <p style="font-size: 14px; color: #666; margin-bottom: 20px;">আপনার পরিচয় সম্পূর্ণ গোপন থাকবে। আমরা আপনার সমস্যা শুনে সাহায্য করব।</p>
    
    <div class="form-group">
      <label>আপনি কী ধরনের সাহায্য চান?</label>
      <select id="help-type">
        <option value="emotional">আবেগগত সাহায্য</option>
        <option value="advice">পরামর্শ</option>
        <option value="information">তথ্য</option>
        <option value="resources">সম্পদ</option>
        <option value="other">অন্যান্য</option>
      </select>
    </div>
    
    <div class="form-group">
      <label>আপনার বার্তা লিখুন (বিস্তারিতভাবে)</label>
      <textarea id="anonymous-message-text" placeholder="আপনার সমস্যা বা প্রশ্নটি এখানে লিখুন..."></textarea>
    </div>
    
    <div class="form-group">
      <label>আপনি কি উত্তর পেতে চান?</label>
      <select id="response-preference">
        <option value="yes">হ্যাঁ, আমি উত্তর পেতে চাই</option>
        <option value="no">না, শুধু শেয়ার করতে চাই</option>
      </select>
    </div>
    
    <button onclick="sendAnonymousMessage()">বার্তা পাঠান</button>
    
    <div id="anonymous-message-sent" style="display:none; margin-top: 20px; text-align: center;">
      <div style="font-size: 50px; margin-bottom: 15px;">✅</div>
      <h3>আপনার বার্তা সফলভাবে পাঠানো হয়েছে</h3>
      <p>আমরা আপনার বার্তা পেয়েছি এবং খুব শীঘ্রই আপনাকে সাহায্য করব। আপনার পরিচয় সম্পূর্ণ গোপন রাখা হবে।</p>
      <p style="margin-top: 15px; font-size: 14px; color: #666;">আপনি যদি তাৎক্ষণিক সাহায্য প্রয়োজন হয়, অনুগ্রহ করে আমাদের হটলাইনে কল করুন: ১৬২৬৩</p>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Rituboost Section -->
<section id="rituboost">
  <h2>☀ ঋতুবসুতি</h2>
  <p>প্রতিটি মৌসুমে নিজের যত্ন নেওয়ার টিপস জানুন।</p>
  
  <div class="tab-container">
    <div class="tab-buttons">
      <button class="tab-button active" onclick="openTab('season-tips', this)">ঋতু ভিত্তিক টিপস</button>
      <button class="tab-button" onclick="openTab('seasonal-mood', this)">ঋতু ভিত্তিক মেজাজ</button>
      <button class="tab-button" onclick="openTab('seasonal-food', this)">ঋতু ভিত্তিক খাবার</button>
    </div>

    <div class="tab-content">
      <div id="season-tips" class="tab-pane active">
        <div class="content-area">
          <h3>বর্তমান ঋতু: গ্রীষ্মকাল</h3>
          <div style="background: #fff9e6; padding: 15px; border-radius: 10px; margin-bottom: 20px;">
            <h4>গ্রীষ্মকালে মানসিক স্বাস্থ্য রক্ষার টিপস:</h4>
            <ul style="text-align: left; padding-left: 20px;">
              <li>পর্যাপ্ত পানি পান করুন - প্রতিদিন কমপক্ষে ৮ গ্লাস</li>
              <li>সূর্যের তীব্রতা এড়িয়ে চলুন, বিশেষ করে দুপুরে</li>
              <li>হালকা ও আরামদায়ক পোশাক পরুন</li>
              <li>শীতল পরিবেশে সময় কাটান</li>
              <li>ধ্যান এবং শ্বাসক্রিয়া অনুশীলন করুন</li>
              <li>ফলমূল এবং সবজি বেশি খান</li>
            </ul>
          </div>
          
          <h4>অন্যান্য ঋতুর টিপস:</h4>
          <div class="sub-feature">
            <button onclick="showSeasonTips('spring')">বসন্তকাল</button>
            <button onclick="showSeasonTips('monsoon')">বর্ষাকাল</button>
            <button onclick="showSeasonTips('autumn')">শরৎকাল</button>
            <button onclick="showSeasonTips('late-autumn')">হেমন্তকাল</button>
            <button onclick="showSeasonTips('winter')">শীতকাল</button>
          </div>
          
          <div id="season-tips-content" style="margin-top: 20px;"></div>
        </div>
      </div>

      <div id="seasonal-mood" class="tab-pane">
        <div class="content-area">
          <h3>ঋতু ভিত্তিক মেজাজ পরিবর্তন</h3>
          <p>ঋতু পরিবর্তনের সাথে সাথে আমাদের মেজাজও পরিবর্তিত হয়। এটি একটি স্বাভাবিক প্রক্রিয়া।</p>
          
          <div style="display: flex; flex-wrap: wrap; gap: 15px; margin: 20px 0;">
            <div style="flex: 1; min-width: 200px; background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>বসন্তকাল</h4>
              <p>সাধারণত আনন্দময় ও উদ্যমী মেজাজ</p>
            </div>
            <div style="flex: 1; min-width: 200px; background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>গ্রীষ্মকাল</h4>
              <p>ক্লান্তি ও জিডিসন অনুভূতি হতে পারে</p>
            </div>
            <div style="flex: 1; min-width: 200px; background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>বর্ষাকাল</h4>
              <p>কিছুটা নিস্তেজ ও বিষণ্ণ মেজাজ</p>
            </div>
            <div style="flex: 1; min-width: 200px; background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>শরৎকাল</h4>
              <p>স্থিতিশীল ও সুখী মেজাজ</p>
            </div>
            <div style="flex: 1; min-width: 200px; background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>হেমন্তকাল</h4>
              <p>সতর্ক ও কিছুটা উদ্বিগ্ন মেজাজ</p>
            </div>
            <div style="flex: 1; min-width: 200px; background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>শীতকাল</h4>
              <p>কিছুটা বিষণ্ণ ও অলস মেজাজ</p>
            </div>
          </div>
          
          <div style="background: #fff9e6; padding: 15px; border-radius: 10px; margin-top: 20px;">
            <h4>ঋতু ভিত্তিক মেজাজ পরিবর্তন মোকাবেলার উপায়:</h4>
            <ul style="text-align: left; padding-left: 20px;">
              <li>নিয়মিত ব্যায়াম করুন</li>
              <li>সূর্যালোকের সংস্পর্শে আসুন</li>
              <li>সামাজিক যোগাযোগ বজায় রাখুন</li>
              <li>সুষম খাবার খান</li>
              <li>পর্যাপ্ত ঘুমান</li>
              <li>প্রয়োজনে পেশাজীবী সাহায্য নিন</li>
            </ul>
          </div>
        </div>
      </div>

      <div id="seasonal-food" class="tab-pane">
        <div class="content-area">
          <h3>ঋতু ভিত্তিক খাবার</h3>
          <p>প্রতিটি ঋতুতে আমাদের শরীরের পুষ্টির চাহিদা ভিন্ন হয়। ঋতু অনুযায়ী খাবার গ্রহণ করলে শারীরিক ও মানসিক স্বাস্থ্য ভালো থাকে।</p>
          
          <div style="background: #fff9e6; padding: 15px; border-radius: 10px; margin: 20px 0;">
            <h4>গ্রীষ্মকালীন খাবার:</h4>
            <ul style="text-align: left; padding-left: 20px;">
              <li>পানি জাতীয় ফল: তরমুজ, বেল, কাঁঠাল</li>
              <li>শীতল পানীয়: লেবু পানি, ডাবের পানি, ছাতু</li>
              <li>সবজি: শসা, টমেটো, পুঁইশাক</li>
              <li>হালকা খাবার: স্যুপ, সালাদ, দই</li>
            </ul>
          </div>
          
          <div class="sub-feature">
            <button onclick="showSeasonFood('spring')">বসন্তকালীন খাবার</button>
            <button onclick="showSeasonFood('monsoon')">বর্ষাকালীন খাবার</button>
            <button onclick="showSeasonFood('autumn')">শরৎকালীন খাবার</button>
            <button onclick="showSeasonFood('late-autumn')">হেমন্তকালীন খাবার</button>
            <button onclick="showSeasonFood('winter')">শীতকালীন খাবার</button>
          </div>
          
          <div id="season-food-content" style="margin-top: 20px;"></div>
        </div>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Mother and Baby Tracker Section -->
<section id="mababybuddy">
  <h2>👩‍👧 মা ও শিশুর ট্র্যাকার</h2>
  <p>মাতৃত্বকালীন ও শিশুর স্বাস্থ্য ফলোআপ রাখুন।</p>
  
  <div class="tab-container">
    <div class="tab-buttons">
      <button class="tab-button active" onclick="openTab('pregnancy-tracker', this)">গর্ভাবস্থা ট্র্যাকার</button>
      <button class="tab-button" onclick="openTab('baby-development', this)">শিশুর বিকাশ</button>
      <button class="tab-button" onclick="openTab('maternal-health', this)">মাতৃস্বাস্থ্য</button>
    </div>

    <div class="tab-content">
      <div id="pregnancy-tracker" class="tab-pane active">
        <div class="content-area">
          <h3>গর্ভাবস্থা ট্র্যাকার</h3>
          <div class="tracker-form">
            <div class="form-group">
              <label>আপনার শেষ মাসিকের তারিখ</label>
              <input type="date" id="lmp-date">
            </div>
            <button onclick="calculatePregnancy()">গর্ভাবস্থা হিসাব করুন</button>
          </div>
          
          <div id="pregnancy-result" style="display:none; margin-top: 20px;">
            <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>আপনার গর্ভাবস্থার তথ্য:</h4>
              <p>বর্তমান সপ্তাহ: <span id="current-week" style="font-weight: bold;">১২ সপ্তাহ</span></p>
              <p>প্রসবের সম্ভাব্য তারিখ: <span id="due-date" style="font-weight: bold;">১৫ ডিসেম্বর, ২০২৩</span></p>
              <p>গর্ভাবস্থার ত্রৈমাসিক: <span id="trimester" style="font-weight: bold;">প্রথম ত্রৈমাসিক</span></p>
            </div>
            
            <div style="margin-top: 20px;">
              <h4>এই সপ্তাহে আপনার শিশুর বিকাশ:</h4>
              <p>আপনার শিশু এখন প্রায় ৫ সেন্টিমিটার লম্বা এবং ওজন প্রায় ১৪ গ্রাম। শিশুর সমস্ত প্রধান অঙ্গ গঠিত হয়েছে এবং এখন সেগুলো আরও বিকশিত হচ্ছে।</p>
            </div>
            
            <div style="margin-top: 20px;">
              <h4>এই সপ্তাহে আপনার জন্য টিপস:</h4>
              <ul style="text-align: left; padding-left: 20px;">
                <li>পুষ্টিকর খাবার খান, বিশেষ করে ফলিক এসিড সমৃদ্ধ খাবার</li>
                <li>পর্যাপ্ত বিশ্রাম নিন</li>
                <li>হালকা ব্যায়াম করুন</li>
                <li>পানি পান করুন পর্যাপ্ত পরিমাণে</li>
                <li>ডাক্তারের নিয়মিত চেকআপ করুন</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div id="baby-development" class="tab-pane">
        <div class="content-area">
          <h3>শিশুর বিকাশ ট্র্যাকার</h3>
          <div class="tracker-form">
            <div class="form-group">
              <label>আপনার শিশুর জন্ম তারিখ</label>
              <input type="date" id="baby-birthdate">
            </div>
            <button onclick="trackBabyDevelopment()">শিশুর বিকাশ ট্র্যাক করুন</button>
          </div>
          
          <div id="baby-development-result" style="display:none; margin-top: 20px;">
            <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
              <h4>আপনার শিশুর বয়স: <span id="baby-age" style="font-weight: bold;">৬ মাস</span></h4>
            </div>
            
            <div style="margin-top: 20px;">
              <h4>এই বয়সে শিশুর বিকাশের মাইলফলক:</h4>
              <ul style="text-align: left; padding-left: 20px;">
                <li>বসতে পারে (সাহায্য সহকারে)</li>
                <li>বস্তু হাতে নিতে পারে</li>
                <li>এক হাত থেকে অন্য হাতে বস্তু স্থানান্তর করতে পারে</li>
                <li>শব্দের দিকে ফিরে তাকায়</li>
                <li>একক সিলেবল শব্দ করতে পারে</li>
              </ul>
            </div>
            
            <div style="margin-top: 20px;">
              <h4>আপনার শিশুর যত্নের টিপস:</h4>
              <ul style="text-align: left; padding-left: 20px;">
                <li>শিশুকে বিভিন্ন ধরনের খাবার দিন</li>
                <li>শিশুর সাথে কথা বলুন এবং গান গান</li>
                <li>শিশুকে খেলার জন্য নিরাপদ জায়গা দিন</li>
                <li>শিশুর টিকা নিশ্চিত করুন</li>
                <li>শিশুর ঘুমের রুটিন বজায় রাখুন</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div id="maternal-health" class="tab-pane">
        <div class="content-area">
          <h3>মাতৃস্বাস্থ্য</h3>
          <p>মাতৃত্বকালীন সময়ে মায়ের স্বাস্থ্যের যত্ন নেওয়া খুবই গুরুত্বপূর্ণ।</p>
          
          <div style="background: #fff9e6; padding: 15px; border-radius: 10px; margin: 20px 0;">
            <h4>মাতৃস্বাস্থ্য টিপস:</h4>
            <ul style="text-align: left; padding-left: 20px;">
              <li>পুষ্টিকর খাবার খান</li>
              <li>পর্যাপ্ত বিশ্রাম নিন</li>
              <li>নিয়মিত ব্যায়াম করুন</li>
              <li>পানি পান করুন পর্যাপ্ত পরিমাণে</li>
              <li>ডাক্তারের নিয়মিত চেকআপ করুন</li>
              <li>মানসিক স্বাস্থ্যের যত্ন নিন</li>
            </ul>
          </div>
          
          <div class="tracker-form">
            <h4>আপনার মাতৃস্বাস্থ্য ট্র্যাকার</h4>
            <div class="form-group">
              <label>আজকের তারিখ</label>
              <input type="date" id="maternal-health-date">
            </div>
            <div class="form-group">
              <label>আপনি কেমন অনুভব করছেন?</label>
              <select id="maternal-mood">
                <option value="very-good">খুব ভালো</option>
                <option value="good">ভালো</option>
                <option value="normal">স্বাভাবিক</option>
                <option value="bad">খারাপ</option>
                <option value="very-bad">খুব খারাপ</option>
              </select>
            </div>
            <div class="form-group">
              <label>আপনি কি কোনো শারীরিক সমস্যা অনুভব করছেন?</label>
              <textarea id="maternal-physical-issues" placeholder="আপনার শারীরিক সমস্যা লিখুন..."></textarea>
            </div>
            <div class="form-group">
              <label>আপনি কি কোনো মানসিক সমস্যা অনুভব করছেন?</label>
              <textarea id="maternal-mental-issues" placeholder="আপনার মানসিক সমস্যা লিখুন..."></textarea>
            </div>
            <button onclick="saveMaternalHealth()">সংরক্ষণ করুন</button>
          </div>
        </div>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- VoiceCare Section -->
<section id="voicecare">
  <h2>🎙 VoiceCare</h2>
  <p>ভয়েসে স্বাস্থ্য পরামর্শ শুনুন।</p>
  
  <div class="voice-player">
    <div class="voice-title">মানসিক স্বাস্থ্য রক্ষায় ধ্যান</div>
    <div class="voice-time">সময়কাল: ১০ মিনিট</div>
    
    <div class="voice-progress">
      <div class="voice-progress-bar" id="voice-progress-bar"></div>
    </div>
    
    <div class="voice-controls">
      <button class="voice-control-btn" onclick="previousAudio()">⏮</button>
      <button class="voice-control-btn" id="play-pause-btn" onclick="togglePlayPause()">▶</button>
      <button class="voice-control-btn" onclick="nextAudio()">⏭</button>
    </div>
    
    <div style="margin-top: 20px;">
      <h4>অন্যান্য অডিও সম্পদ:</h4>
      <div class="sub-feature">
        <button onclick="playAudio('stress-relief')">স্ট্রেস রিলিফ</button>
        <button onclick="playAudio('sleep-meditation')">ঘুমের জন্য ধ্যান</button>
        <button onclick="playAudio('breathing-exercise')">শ্বাসক্রিয়া ব্যায়াম</button>
        <button onclick="playAudio('positive-affirmations')">ইতিবাচক চিন্তা</button>
        <button onclick="playAudio('mindfulness')">মাইন্ডফুলনেস</button>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Community Forum Section -->
<section id="forum">
  <h2>💬 Community Forum</h2>
  <p>সম্প্রদায়ের সাথে আপনার অভিজ্ঞতা শেয়ার করুন এবং অন্যদের থেকে শিখুন।</p>
  
  <div class="content-area">
    <div class="tracker-form">
      <h3>নতুন পোস্ট তৈরি করুন</h3>
      <div class="form-group">
        <label>পোস্টের বিষয়</label>
        <input type="text" id="post-title" placeholder="আপনার পোস্টের শিরোনাম লিখুন...">
      </div>
      <div class="form-group">
        <label>পোস্টের বিষয়শ্রেণী</label>
        <select id="post-category">
          <option value="anxiety">উদ্বেগ</option>
          <option value="depression">বিষণ্ণতা</option>
          <option value="stress">স্ট্রেস</option>
          <option value="relationships">সম্পর্ক</option>
          <option value="self-care">আত্মযত্ন</option>
          <option value="therapy">থেরাপি</option>
          <option value="other">অন্যান্য</option>
        </select>
      </div>
      <div class="form-group">
        <label>আপনার পোস্ট</label>
        <textarea id="post-content" placeholder="আপনার চিন্তাভাবনা শেয়ার করুন..."></textarea>
      </div>
      <button onclick="createPost()">পোস্ট করুন</button>
    </div>
    
    <div style="margin-top: 30px;">
      <h3>সাম্প্রতিক পোস্টসমূহ</h3>
      
      <div class="forum-post">
        <div class="forum-post-header">
          <span>অনন্যা</span>
          <span>বিষয়: উদ্বেগ</span>
        </div>
        <div class="forum-post-content">
          আমি গত কয়েক মাস ধরে কাজের চাপে খুব উদ্বিগ্ন থাকছি। কেউ কি জানেন কিভাবে এই পরিস্থিতি মোকাবেলা করা যায়?
        </div>
        <div class="forum-post-actions">
          <span>👍 ১২</span>
          <span>💬 ৫ টি মন্তব্য</span>
          <span>🕒 ২ ঘন্টা আগে</span>
        </div>
      </div>
      
      <div class="forum-post">
        <div class="forum-post-header">
          <span>রহিম</span>
          <span>বিষয়: আত্মযত্ন</span>
        </div>
        <div class="forum-post-content">
          আমি সম্প্রতি ধ্যান শুরু করেছি এবং এটি আমার মানসিক স্বাস্থ্যের উন্নতি করছে। আমি প্রতিদিন ১০ মিনিট ধ্যান করি এবং এটি আমাকে খুব শান্ত রাখে।
        </div>
        <div class="forum-post-actions">
          <span>👍 ২৪</span>
          <span>💬 ৮ টি মন্তব্য</span>
          <span>🕒 ৫ ঘন্টা আগে</span>
        </div>
      </div>
      
      <div class="forum-post">
        <div class="forum-post-header">
          <span>সুমনা</span>
          <span>বিষয়: থেরাপি</span>
        </div>
        <div class="forum-post-content">
          আমি গত মাসে একজন থেরাপিস্টের সাথে কথা বলা শুরু করেছি এবং এটি আমার জন্য খুব উপকারী হচ্ছে। যারা থেরাপি নিয়ে চিন্তিত, তাদের বলবো একবার চেষ্টা করে দেখুন।
        </div>
        <div class="forum-post-actions">
          <span>👍 ১৮</span>
          <span>💬 ৭ টি মন্তব্য</span>
          <span>🕒 ১ দিন আগে</span>
        </div>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Daily Reminder Section -->
<section id="reminder">
  <h2>⏰ Daily Reminder</h2>
  <p>প্রতিদিনের স্বাস্থ্যকর অভ্যাস গড়ে তুলতে রিমাইন্ডার সেট করুন।</p>
  
  <div class="content-area">
    <div class="tracker-form">
      <h3>নতুন রিমাইন্ডার যোগ করুন</h3>
      <div class="form-group">
        <label>রিমাইন্ডারের শিরোনাম</label>
        <input type="text" id="reminder-title" placeholder="যেমন: পানি পান করুন">
      </div>
      <div class="form-group">
        <label>রিমাইন্ডারের সময়</label>
        <input type="time" id="reminder-time">
      </div>
      <div class="form-group">
        <label>পুনরাবৃত্তি</label>
        <select id="reminder-repeat">
          <option value="daily">প্রতিদিন</option>
          <option value="weekly">সাপ্তাহিক</option>
          <option value="monthly">মাসিক</option>
          <option value="custom">কাস্টম</option>
        </select>
      </div>
      <button onclick="addReminder()">রিমাইন্ডার যোগ করুন</button>
    </div>
    
    <div style="margin-top: 30px;">
      <h3>আপনার রিমাইন্ডারসমূহ</h3>
      
      <div class="reminder-item">
        <div class="reminder-icon">💧</div>
        <div class="reminder-content">
          <div>পানি পান করুন</div>
          <div class="reminder-time">প্রতি ২ ঘন্টা অন্তর</div>
        </div>
        <button class="reminder-toggle">🔔</button>
      </div>
      
      <div class="reminder-item">
        <div class="reminder-icon">😊</div>
        <div class="reminder-content">
          <div>হাসুন</div>
          <div class="reminder-time">সকাল ৯:০০ টা</div>
        </div>
        <button class="reminder-toggle">🔔</button>
      </div>
      
      <div class="reminder-item">
        <div class="reminder-icon">💤</div>
        <div class="reminder-content">
          <div>বিশ্রাম নিন</div>
          <div class="reminder-time">দুপুর ১:০০ টা</div>
        </div>
        <button class="reminder-toggle">🔔</button>
      </div>
      
      <div class="reminder-item">
        <div class="reminder-icon">🧘</div>
        <div class="reminder-content">
          <div>ধ্যান করুন</div>
          <div class="reminder-time">সন্ধ্যা ৬:০০ টা</div>
        </div>
        <button class="reminder-toggle">🔔</button>
      </div>
      
      <div class="reminder-item">
        <div class="reminder-icon">📖</div>
        <div class="reminder-content">
          <div>বই পড়ুন</div>
          <div class="reminder-time">রাত ৯:০০ টা</div>
        </div>
        <button class="reminder-toggle">🔔</button>
      </div>
    </div>
  </div>

  <button class="back-btn" onclick="back()">Back</button>
</section>

<!-- Chatbot -->
<div class="chatbot-toggle" onclick="toggleChatbot()">💬</div>
<div class="chatbot-container" id="chatbot-container">
  <div class="chatbot-header">
    <span>Shifa Assistant</span>
    <span onclick="toggleChatbot()" style="cursor: pointer;">✖</span>
  </div>
  <div class="chatbot-messages" id="chatbot-messages">
    <div class="message bot-message">হ্যালো! আমি শিফা অ্যাসিস্ট্যান্ট। আমি কিভাবে আপনাকে সাহায্য করতে পারি?</div>
  </div>
  <div class="chatbot-input">
    <input type="text" id="chatbot-input" placeholder="আপনার প্রশ্ন লিখুন..." onkeypress="handleChatbotInput(event)">
    <button onclick="sendChatbotMessage()">পাঠান</button>
  </div>
</div>

<script>
// Set current date for date inputs
document.addEventListener('DOMContentLoaded', function() {
  const today = new Date().toISOString().split('T')[0];
  document.getElementById('log-date').value = today;
  document.getElementById('maternal-health-date').value = today;
});

// Navigation functions
function hideAll() { 
  document.querySelectorAll('section').forEach(s => s.style.display='none'); 
}

function showLogin(){ 
  hideAll(); 
  document.getElementById('login').style.display='block'; 
}

function showSignUp(){ 
  hideAll(); 
  document.getElementById('signup').style.display='block'; 
}

function login(){ 
  hideAll(); 
  document.getElementById('menu').style.display='block'; 
}

function signup(){ 
  hideAll(); 
  document.getElementById('menu').style.display='block'; 
}

function openFeature(id){ 
  hideAll(); 
  document.getElementById(id).style.display='block'; 
}

function back(){ 
  hideAll(); 
  document.getElementById('menu').style.display='block'; 
}

// Tab functionality
function openTab(tabId, button) {
  // Hide all tab panes
  const tabPanes = document.querySelectorAll('.tab-pane');
  tabPanes.forEach(pane => pane.classList.remove('active'));
  
  // Remove active class from all tab buttons
  const tabButtons = document.querySelectorAll('.tab-button');
  tabButtons.forEach(btn => btn.classList.remove('active'));
  
  // Show the selected tab pane
  document.getElementById(tabId).classList.add('active');
  
  // Add active class to the clicked button
  button.classList.add('active');
}

// Dashboard functionality
function selectMood(element, mood) {
  // Remove selected class from all mood options
  const moodOptions = document.querySelectorAll('.mood-option');
  moodOptions.forEach(option => option.style.border = 'none');
  
  // Add selected class to the clicked mood option
  element.style.border = '2px solid #007acc';
  
  // Show mood note section
  document.getElementById('mood-note').style.display = 'block';
}

function saveMoodNote() {
  const moodNote = document.getElementById('mood-note-text').value;
  if (moodNote.trim() === '') {
    alert('অনুগ্রহ করে আপনার অনুভূতি লিখুন');
    return;
  }
  
  // Create a new log entry
  const logsContainer = document.getElementById('daily-logs');
  const newLog = document.createElement('div');
  newLog.className = 'forum-post';
  
  const today = new Date().toLocaleDateString('bn-BD', { year: 'numeric', month: 'long', day: 'numeric' });
  
  newLog.innerHTML = `
    <div class="forum-post-header">
      <span>${today}</span>
      <span>মেজাজ: 😊</span>
    </div>
    <div class="forum-post-content">
      ${moodNote}
    </div>
  `;
  
  // Add the new log at the beginning of the logs container
  logsContainer.insertBefore(newLog, logsContainer.firstChild.nextSibling);
  
  // Clear the mood note text
  document.getElementById('mood-note-text').value = '';
  
  // Show success message
  alert('আপনার মেজাজ সফলভাবে সংরক্ষিত হয়েছে!');
}

function saveDailyLog() {
  const logDate = document.getElementById('log-date').value;
  const logActivities = document.getElementById('log-activities').value;
  const logMood = document.getElementById('log-mood').value;
  
  if (logActivities.trim() === '') {
    alert('অনুগ্রহ করে আপনার কার্যক্রম লিখুন');
    return;
  }
  
  // Create a new log entry
  const logsContainer = document.getElementById('daily-logs');
  const newLog = document.createElement('div');
  newLog.className = 'forum-post';
  
  // Convert date to Bengali format
  const date = new Date(logDate);
  const formattedDate = date.toLocaleDateString('bn-BD', { year: 'numeric', month: 'long', day: 'numeric' });
  
  // Get mood emoji based on selected mood
  let moodEmoji = '😐';
  switch(logMood) {
    case 'very-happy': moodEmoji = '😄'; break;
    case 'happy': moodEmoji = '😊'; break;
    case 'neutral': moodEmoji = '😐'; break;
    case 'sad': moodEmoji = '😔'; break;
    case 'very-sad': moodEmoji = '😢'; break;
  }
  
  newLog.innerHTML = `
    <div class="forum-post-header">
      <span>${formattedDate}</span>
      <span>মেজাজ: ${moodEmoji}</span>
    </div>
    <div class="forum-post-content">
      ${logActivities}
    </div>
  `;
  
  // Add the new log at the beginning of the logs container
  logsContainer.insertBefore(newLog, logsContainer.firstChild.nextSibling);
  
  // Clear the form
  document.getElementById('log-activities').value = '';
  
  // Show success message
  alert('আপনার দৈনিক লগ সফলভাবে সংরক্ষিত হয়েছে!');
}

// Mind Test functionality
let currentQuestionIndex = 0;
const questions = [
  {
    question: "আপনি গত সপ্তাহে কতবার মনে হয়েছে যে আপনি নিজেকে নিয়ন্ত্রণ করতে পারছেন না?",
    options: ["কখনোই না", "খুব কমই", "কখনো কখনো", "বেশিরভাগ সময়", "প্রায় সব সময়"]
  },
  {
    question: "গত সপ্তাহে আপনি কতবার মনে হয়েছে যে আপনি ভবিষ্যৎ নিয়ে উদ্বিগ্ন?",
    options: ["কখনোই না", "খুব কমই", "কখনো কখনো", "বেশিরভাগ সময়", "প্রায় সব সময়"]
  },
  {
    question: "গত সপ্তাহে আপনি কতবার মনে হয়েছে যে আপনি বিষণ্ণ?",
    options: ["কখনোই না", "খুব কমই", "কখনো কখনো", "বেশিরভাগ সময়", "প্রায় সব সময়"]
  },
  {
    question: "গত সপ্তাহে আপনি কতবার মনে হয়েছে যে আপনি একা?",
    options: ["কখনোই না", "খুব কমই", "কখনো কখনো", "বেশিরভাগ সময়", "প্রায় সব সময়"]
  },
  {
    question: "গত সপ্তাহে আপনি কতবার মনে হয়েছে যে আপনি ঘুমাতে পারছেন না?",
    options: ["কখনোই না", "খুব কমই", "কখনো কখনো", "বেশিরভাগ সময়", "প্রায় সব সময়"]
  }
];

let userAnswers = [];

function selectOption(element, value) {
  // Remove selected class from all options
  const options = document.querySelectorAll('.assessment-option');
  options.forEach(option => option.classList.remove('selected'));
  
  // Add selected class to the clicked option
  element.classList.add('selected');
  
  // Store the answer
  userAnswers[currentQuestionIndex] = value;
  
  // Move to next question after a short delay
  setTimeout(() => {
    nextQuestion();
  }, 500);
}

function nextQuestion() {
  currentQuestionIndex++;
  
  if (currentQuestionIndex >= questions.length) {
    // Show results
    showAssessmentResults();
  } else {
    // Update progress bar
    const progress = ((currentQuestionIndex + 1) / questions.length) * 100;
    document.getElementById('assessment-progress').style.width = progress + '%';
    
    // Update question number
    document.getElementById('current-question').textContent = currentQuestionIndex + 1;
    
    // Load next question
    loadQuestion();
  }
}

function loadQuestion() {
  const question = questions[currentQuestionIndex];
  
  // Update question text
  document.querySelector('.assessment-question h3').textContent = question.question;
  
  // Update options
  const optionsContainer = document.querySelector('.assessment-options');
  optionsContainer.innerHTML = '';
  
  question.options.forEach((option, index) => {
    const optionElement = document.createElement('div');
    optionElement.className = 'assessment-option';
    optionElement.textContent = option;
    optionElement.onclick = function() { selectOption(this, index); };
    optionsContainer.appendChild(optionElement);
  });
}

function showAssessmentResults() {
  // Calculate score
  let totalScore = 0;
  userAnswers.forEach(answer => {
    totalScore += answer;
  });
  
  // Determine result based on score
  let resultText = '';
  let resultEmoji = '';
  let resultScore = '';
  
  if (totalScore <= 5) {
    resultText = 'আপনার মানসিক স্বাস্থ্য খুব ভালো অবস্থায় আছে। আপনি নিজের আবেগগুলোকে ভালোভাবে ব্যবস্থাপনা করতে পারছেন।';
    resultEmoji = '😄';
    resultScore = '৯/১০';
  } else if (totalScore <= 10) {
    resultText = 'আপনার মানসিক স্বাস্থ্য ভালো অবস্থায় আছে। আপনি সাধারণত নিজের আবেগগুলোকে ব্যবস্থাপনা করতে পারেন।';
    resultEmoji = '😊';
    resultScore = '৭/১০';
  } else if (totalScore <= 15) {
    resultText = 'আপনার মানসিক স্বাস্থ্য মাঝারি অবস্থায় আছে। আপনি কিছু সময় আবেগগত সমস্যার সম্মুখীন হতে পারেন।';
    resultEmoji = '😐';
    resultScore = '৫/১০';
  } else {
    resultText = 'আপনার মানসিক স্বাস্থ্য কিছুটা চাপের মধ্যে আছে। আপনি আবেগগত সমস্যার সম্মুখীন হচ্ছেন এবং সাহায্যের প্রয়োজন হতে পারে।';
    resultEmoji = '😔';
    resultScore = '৩/১০';
  }
  
  // Update result UI
  document.getElementById('score-value').textContent = resultScore;
  document.querySelector('#assessment-result p').textContent = resultText;
  document.querySelector('#assessment-result div').textContent = resultEmoji;
  
  // Hide assessment container and show result
  document.getElementById('assessment-container').style.display = 'none';
  document.getElementById('assessment-result').style.display = 'block';
}

function restartAssessment() {
  // Reset variables
  currentQuestionIndex = 0;
  userAnswers = [];
  
  // Reset UI
  document.getElementById('assessment-progress').style.width = '0%';
  document.getElementById('current-question').textContent = '1';
  document.getElementById('assessment-container').style.display = 'block';
  document.getElementById('assessment-result').style.display = 'none';
  
  // Load first question
  loadQuestion();
}

// Disease Radar functionality
function analyzeSymptoms() {
  // Get selected symptoms
  const symptoms = [];
  const checkboxes = document.querySelectorAll('.checkbox-item input:checked');
  
  checkboxes.forEach(checkbox => {
    symptoms.push(checkbox.value);
  });
  
  if (symptoms.length === 0) {
    alert('অনুগ্রহ করে কমপক্ষে একটি উপসর্গ নির্বাচন করুন');
    return;
  }
  
  // Show result
  document.getElementById('symptom-result').style.display = 'block';
}

// ChupLine functionality
function sendAnonymousMessage() {
  const helpType = document.getElementById('help-type').value;
  const messageText = document.getElementById('anonymous-message-text').value;
  const responsePreference = document.getElementById('response-preference').value;
  
  if (messageText.trim() === '') {
    alert('অনুগ্রহ করে আপনার বার্তা লিখুন');
    return;
  }
  
  // Show success message
  document.getElementById('anonymous-message-sent').style.display = 'block';
  
  // Clear form
  document.getElementById('anonymous-message-text').value = '';
}

// Rituboost functionality
function showSeasonTips(season) {
  const tipsContent = document.getElementById('season-tips-content');
  
  let tips = '';
  
  switch(season) {
    case 'spring':
      tips = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>বসন্তকালে মানসিক স্বাস্থ্য রক্ষার টিপস:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>প্রকৃতির সাথে সময় কাটান</li>
            <li>বাইরে হাঁটুন</li>
            <li>রঙিন ফল ও সবজি খান</li>
            <li>নতুন কিছু শিখুন</li>
            <li>সামাজিক যোগাযোগ বাড়ান</li>
          </ul>
        </div>
      `;
      break;
    case 'monsoon':
      tips = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>বর্ষাকালে মানসিক স্বাস্থ্য রক্ষার টিপস:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>ভিটামিন ডি গ্রহণ করুন</li>
            <li>ঘরের ভেতরে ব্যায়াম করুন</li>
            <li>গরম খাবার খান</li>
            <li>বই পড়ুন</li>
            <li>শখের কাজ করুন</li>
          </ul>
        </div>
      `;
      break;
    case 'autumn':
      tips = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>শরৎকালে মানসিক স্বাস্থ্য রক্ষার টিপস:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>সকালে হাঁটুন</li>
            <li>মৌসুমী ফল খান</li>
            <li>যোগব্যায়াম করুন</li>
            <li>পরিবারের সাথে সময় কাটান</li>
            <li>ধ্যান করুন</li>
          </ul>
        </div>
      `;
      break;
    case 'late-autumn':
      tips = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>হেমন্তকালে মানসিক স্বাস্থ্য রক্ষার টিপস:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>শরীর উষ্ণ রাখুন</li>
            <li>সূর্যের আলো গ্রহণ করুন</li>
            <li>গরম খাবার খান</li>
            <li>পর্যাপ্ত ঘুমান</li>
            <li>বন্ধুদের সাথে যোগাযোগ রাখুন</li>
          </ul>
        </div>
      `;
      break;
    case 'winter':
      tips = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>শীতকালে মানসিক স্বাস্থ্য রক্ষার টিপস:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>শরীর উষ্ণ রাখুন</li>
            <li>ভিটামিন ডি গ্রহণ করুন</li>
            <li>গরম খাবার খান</li>
            <li>ঘরের ভেতরে ব্যায়াম করুন</li>
            <li>আরামদায়ক পরিবেশে সময় কাটান</li>
          </ul>
        </div>
      `;
      break;
  }
  
  tipsContent.innerHTML = tips;
}

function showSeasonFood(season) {
  const foodContent = document.getElementById('season-food-content');
  
  let food = '';
  
  switch(season) {
    case 'spring':
      food = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>বসন্তকালীন খাবার:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>ফল: আম, কাঁঠাল, লিচু</li>
            <li>সবজি: পাট শাক, পালং শাক, লাল শাক</li>
            <li>পানীয়: ডাবের পানি, লেবু পানি</li>
            <li>অন্যান্য: মৌসুমী ফল, সালাদ</li>
          </ul>
        </div>
      `;
      break;
    case 'monsoon':
      food = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>বর্ষাকালীন খাবার:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>ফল: জাম, কাঁঠাল, আমড়া</li>
            <li>সবজি: কচু শাক, ঢেঁড়স, পটল</li>
            <li>পানীয়: গরম দুধ, চা, সুপ</li>
            <li>অন্যান্য: ভাজা খাবার, হালকা খাবার</li>
          </ul>
        </div>
      `;
      break;
    case 'autumn':
      food = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>শরৎকালীন খাবার:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>ফল: কলা, পেঁপে, আপেল</li>
            <li>সবজি: ফুলকপি, বাঁধাকপি, গাজর</li>
            <li>পানীয়: ফলের রস, দুধ</li>
            <li>অন্যান্য: মাছ, ডিম, দুধ</li>
          </ul>
        </div>
      `;
      break;
    case 'late-autumn':
      food = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>হেমন্তকালীন খাবার:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>ফল: আপেল, কমলা, মাল্টা</li>
            <li>সবজি: টমেটো, বেগুন, মূলা</li>
            <li>পানীয়: গরম দুধ, চা</li>
            <li>অন্যান্য: মাছ, মাংস, ডাল</li>
          </ul>
        </div>
      `;
      break;
    case 'winter':
      food = `
        <div style="background: #e7f5ff; padding: 15px; border-radius: 10px;">
          <h4>শীতকালীন খাবার:</h4>
          <ul style="text-align: left; padding-left: 20px;">
            <li>ফল: কমলা, মাল্টা, স্ট্রবেরি</li>
            <li>সবজি: শিম, বাঁধাকপি, গাজর</li>
            <li>পানীয়: গরম দুধ, চা, সুপ</li>
            <li>অন্যান্য: পিঠা, পায়েস, মাছ, মাংস</li>
          </ul>
        </div>
      `;
      break;
  }
  
  foodContent.innerHTML = food;
}

// Mother and Baby Tracker functionality
function calculatePregnancy() {
  const lmpDate = document.getElementById('lmp-date').value;
  
  if (lmpDate === '') {
    alert('অনুগ্রহ করে আপনার শেষ মাসিকের তারিখ নির্বাচন করুন');
    return;
  }
  
  // Calculate due date (40 weeks from LMP)
  const lmp = new Date(lmpDate);
  const dueDate = new Date(lmp);
  dueDate.setDate(dueDate.getDate() + 280); // 40 weeks = 280 days
  
  // Calculate current week
  const today = new Date();
  const diffTime = Math.abs(today - lmp);
  const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
  const currentWeek = Math.floor(diffDays / 7);
  
  // Determine trimester
  let trimester = '';
  if (currentWeek <= 13) {
    trimester = 'প্রথম ত্রৈমাসিক';
  } else if (currentWeek <= 27) {
    trimester = 'দ্বিতীয় ত্রৈমাসিক';
  } else {
    trimester = 'তৃতীয় ত্রৈমাসিক';
  }
  
  // Format due date in Bengali
  const formattedDueDate = dueDate.toLocaleDateString('bn-BD', { 
    year: 'numeric', 
    month: 'long', 
    day: 'numeric' 
  });
  
  // Update UI
  document.getElementById('current-week').textContent = currentWeek + ' সপ্তাহ';
  document.getElementById('due-date').textContent = formattedDueDate;
  document.getElementById('trimester').textContent = trimester;
  
  // Show result
  document.getElementById('pregnancy-result').style.display = 'block';
}

function trackBabyDevelopment() {
  const birthdate = document.getElementById('baby-birthdate').value;
  
  if (birthdate === '') {
    alert('অনুগ্রহ করে আপনার শিশুর জন্ম তারিখ নির্বাচন করুন');
    return;
  }
  
  // Calculate baby's age
  const birth = new Date(birthdate);
  const today = new Date();
  const diffTime = Math.abs(today - birth);
  const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
  const diffMonths = Math.floor(diffDays / 30);
  
  // Update UI
  document.getElementById('baby-age').textContent = diffMonths + ' মাস';
  
  // Show result
  document.getElementById('baby-development-result').style.display = 'block';
}

function saveMaternalHealth() {
  const date = document.getElementById('maternal-health-date').value;
  const mood = document.getElementById('maternal-mood').value;
  const physicalIssues = document.getElementById('maternal-physical-issues').value;
  const mentalIssues = document.getElementById('maternal-mental-issues').value;
  
  if (date === '') {
    alert('অনুগ্রহ করে তারিখ নির্বাচন করুন');
    return;
  }
  
  // Show success message
  alert('আপনার মাতৃস্বাস্থ্য তথ্য সফলভাবে সংরক্ষিত হয়েছে!');
  
  // Clear form
  document.getElementById('maternal-physical-issues').value = '';
  document.getElementById('maternal-mental-issues').value = '';
}

// VoiceCare functionality
let isPlaying = false;
let currentAudio = 'meditation';
let audioProgress = 0;
let audioInterval;

function togglePlayPause() {
  const playPauseBtn = document.getElementById('play-pause-btn');
  
  if (isPlaying) {
    // Pause
    playPauseBtn.textContent = '▶';
    isPlaying = false;
    clearInterval(audioInterval);
  } else {
    // Play
    playPauseBtn.textContent = '⏸';
    isPlaying = true;
    
    // Simulate audio progress
    audioInterval = setInterval(() => {
      audioProgress += 1;
      document.getElementById('voice-progress-bar').style.width = audioProgress + '%';
      
      if (audioProgress >= 100) {
        // Audio ended
        clearInterval(audioInterval);
        playPauseBtn.textContent = '▶';
        isPlaying = false;
        audioProgress = 0;
      }
    }, 100); // Update every 100ms for smooth progress
  }
}

function playAudio(audioType) {
  // Reset progress
  audioProgress = 0;
  document.getElementById('voice-progress-bar').style.width = '0%';
  
  // Update title based on audio type
  const titleElement = document.querySelector('.voice-title');
  const timeElement = document.querySelector('.voice-time');
  
  switch(audioType) {
    case 'stress-relief':
      titleElement.textContent = 'স্ট্রেস রিলিফ';
      timeElement.textContent = 'সময়কাল: ৮ মিনিট';
      break;
    case 'sleep-meditation':
      titleElement.textContent = 'ঘুমের জন্য ধ্যান';
      timeElement.textContent = 'সময়কাল: ১৫ মিনিট';
      break;
    case 'breathing-exercise':
      titleElement.textContent = 'শ্বাসক্রিয়া ব্যায়াম';
      timeElement.textContent = 'সময়কাল: ৫ মিনিট';
      break;
    case 'positive-affirmations':
      titleElement.textContent = 'ইতিবাচক চিন্তা';
      timeElement.textContent = 'সময়কাল: ৭ মিনিট';
      break;
    case 'mindfulness':
      titleElement.textContent = 'মাইন্ডফুলনেস';
      timeElement.textContent = 'সময়কাল: ১২ মিনিট';
      break;
    default:
      titleElement.textContent = 'মানসিক স্বাস্থ্য রক্ষায় ধ্যান';
      timeElement.textContent = 'সময়কাল: ১০ মিনিট';
  }
  
  currentAudio = audioType;
  
  // Auto play
  if (isPlaying) {
    // If already playing, continue with new audio
    clearInterval(audioInterval);
    togglePlayPause();
    togglePlayPause();
  }
}

function previousAudio() {
  // This would typically go to the previous track in a playlist
  // For demo purposes, we'll just reset the current audio
  audioProgress = 0;
  document.getElementById('voice-progress-bar').style.width = '0%';
}

function nextAudio() {
  // This would typically go to the next track in a playlist
  // For demo purposes, we'll just reset the current audio
  audioProgress = 0;
  document.getElementById('voice-progress-bar').style.width = '0%';
}

// Community Forum functionality
function createPost() {
  const title = document.getElementById('post-title').value;
  const category = document.getElementById('post-category').value;
  const content = document.getElementById('post-content').value;
  
  if (title.trim() === '' || content.trim() === '') {
    alert('অনুগ্রহ করে পোস্টের শিরোনাম এবং বিষয়বস্তু লিখুন');
    return;
  }
  
  // Create a new post element
  const postsContainer = document.querySelector('#forum .content-area > div:last-of-type');
  const newPost = document.createElement('div');
  newPost.className = 'forum-post';
  
  // Get category name in Bengali
  let categoryName = '';
  switch(category) {
    case 'anxiety': categoryName = 'উদ্বেগ'; break;
    case 'depression': categoryName = 'বিষণ্ণতা'; break;
    case 'stress': categoryName = 'স্ট্রেস'; break;
    case 'relationships': categoryName = 'সম্পর্ক'; break;
    case 'self-care': categoryName = 'আত্মযত্ন'; break;
    case 'therapy': categoryName = 'থেরাপি'; break;
    default: categoryName = 'অন্যান্য';
  }
  
  newPost.innerHTML = `
    <div class="forum-post-header">
      <span>আপনি</span>
      <span>বিষয়: ${categoryName}</span>
    </div>
    <div class="forum-post-content">
      ${content}
    </div>
    <div class="forum-post-actions">
      <span>👍 ০</span>
      <span>💬 ০ টি মন্তব্য</span>
      <span>🕒 এইমাত্র</span>
    </div>
  `;
  
  // Add the new post at the beginning of the posts container
  postsContainer.insertBefore(newPost, postsContainer.firstChild);
  
  // Clear form
  document.getElementById('post-title').value = '';
  document.getElementById('post-content').value = '';
  
  // Show success message
  alert('আপনার পোস্ট সফলভাবে পোস্ট করা হয়েছে!');
}

// Daily Reminder functionality
function addReminder() {
  const title = document.getElementById('reminder-title').value;
  const time = document.getElementById('reminder-time').value;
  const repeat = document.getElementById('reminder-repeat').value;
  
  if (title.trim() === '' || time === '') {
    alert('অনুগ্রহ করে রিমাইন্ডারের শিরোনাম এবং সময় দিন');
    return;
  }
  
  // Get repeat text in Bengali
  let repeatText = '';
  switch(repeat) {
    case 'daily': repeatText = 'প্রতিদিন'; break;
    case 'weekly': repeatText = 'সাপ্তাহিক'; break;
    case 'monthly': repeatText = 'মাসিক'; break;
    default: repeatText = 'কাস্টম';
  }
  
  // Create a new reminder element
  const remindersContainer = document.querySelector('#reminder .content-area > div:last-of-type');
  const newReminder = document.createElement('div');
  newReminder.className = 'reminder-item';
  
  // Choose an icon based on the title
  let icon = '📝';
  if (title.toLowerCase().includes('পানি')) icon = '💧';
  else if (title.toLowerCase().includes('হাস')) icon = '😊';
  else if (title.toLowerCase().includes('বিশ্রাম') || title.toLowerCase().includes('ঘুম')) icon = '💤';
  else if (title.toLowerCase().includes('ধ্যান') || title.toLowerCase().includes('যোগ')) icon = '🧘';
  else if (title.toLowerCase().includes('বই') || title.toLowerCase().includes('পড়')) icon = '📖';
  
  newReminder.innerHTML = `
    <div class="reminder-icon">${icon}</div>
    <div class="reminder-content">
      <div>${title}</div>
      <div class="reminder-time">${repeatText}, ${time}</div>
    </div>
    <button class="reminder-toggle">🔔</button>
  `;
  
  // Add the new reminder to the reminders container
  remindersContainer.appendChild(newReminder);
  
  // Clear form
  document.getElementById('reminder-title').value = '';
  document.getElementById('reminder-time').value = '';
  
  // Show success message
  alert('আপনার রিমাইন্ডার সফলভাবে যোগ করা হয়েছে!');
}

// Chatbot functionality
function toggleChatbot() {
  const chatbotContainer = document.getElementById('chatbot-container');
  if (chatbotContainer.style.display === 'flex') {
    chatbotContainer.style.display = 'none';
  } else {
    chatbotContainer.style.display = 'flex';
  }
}

function openChatbot() {
  document.getElementById('chatbot-container').style.display = 'flex';
}

function sendChatbotMessage() {
  const input = document.getElementById('chatbot-input');
  const message = input.value.trim();
  
  if (message === '') return;
  
  // Add user message to chat
  addMessageToChat(message, 'user');
  
  // Clear input
  input.value = '';
  
  // Generate bot response
  setTimeout(() => {
    const response = generateBotResponse(message);
    addMessageToChat(response, 'bot');
  }, 1000);
}

function handleChatbotInput(event) {
  if (event.key === 'Enter') {
    sendChatbotMessage();
  }
}

function addMessageToChat(message, sender) {
  const messagesContainer = document.getElementById('chatbot-messages');
  const messageElement = document.createElement('div');
  messageElement.className = `message ${sender}-message`;
  messageElement.textContent = message;
  messagesContainer.appendChild(messageElement);
  
  // Scroll to bottom
  messagesContainer.scrollTop = messagesContainer.scrollHeight;
}

function generateBotResponse(message) {
  // Simple keyword-based responses
  const lowerMessage = message.toLowerCase();
  
  if (lowerMessage.includes('হ্যালো') || lowerMessage.includes('হাই')) {
    return 'হ্যালো! আমি শিফা অ্যাসিস্ট্যান্ট। আমি কিভাবে আপনাকে সাহায্য করতে পারি?';
  } else if (lowerMessage.includes('উদ্বেগ') || lowerMessage.includes('উদ্বিগ্ন')) {
    return 'উদ্বেগ একটি সাধারণ মানসিক অবস্থা। আপনি গভীর শ্বাস নিতে পারেন, ধ্যান করতে পারেন, বা আমাদের মনের পরীক্ষা বিভাগে যেতে পারেন।';
  } else if (lowerMessage.includes('বিষণ্ণতা') || lowerMessage.includes('ডিপ্রেশন')) {
    return 'বিষণ্ণতা একটি গুরুতর মানসিক স্বাস্থ্য সমস্যা। আপনি একজন মানসিক স্বাস্থ্য পেশাজীবীর সাথে কথা বলতে পারেন বা আমাদের চুপলাইন ব্যবহার করতে পারেন।';
  } else if (lowerMessage.includes('স্ট্রেস') || lowerMessage.includes('চাপ')) {
    return 'স্ট্রেস মোকাবেলার জন্য আপনি ব্যায়াম করতে পারেন, পর্যাপ্ত ঘুমাতে পারেন, বা আমাদের ভয়েসকেয়ার ব্যবহার করতে পারেন।';
  } else if (lowerMessage.includes('ঘুম') || lowerMessage.includes('অনিদ্রা')) {
    return 'ভালো ঘুমের জন্য আপনি নিয়মিত সময়ে ঘুমাতে পারেন, ঘুমানোর আগে ফোন বা টিভি এড়িয়ে চলতে পারেন, বা আমাদের ঘুমের জন্য ধ্যান অডিও শুনতে পারেন।';
  } else if (lowerMessage.includes('ধ্যান') || lowerMessage.includes('মেডিটেশন')) {
    return 'ধ্যান মানসিক স্বাস্থ্যের জন্য খুবই উপকারী। আপনি আমাদের ভয়েসকেয়ার বিভাগে বিভিন্ন ধরনের ধ্যান অডিও পাবেন।';
  } else if (lowerMessage.includes('সাহায্য') || lowerMessage.includes('হেল্প')) {
    return 'আমি আপনাকে সাহায্য করতে পারি। আপনি কি ধরনের সাহায্য চান? আপনি আমাদের বিভিন্ন বিভাগ যেমন মনের পরীক্ষা, রোগরাডার, চুপলাইন ইত্যাদি ব্যবহার করতে পারেন।';
  } else if (lowerMessage.includes('ধন্যবাদ')) {
    return 'আপনাকে ধন্যবাদ! আর কিছু জানার থাকলে আমাকে জিজ্ঞাসা করুন।';
  } else {
    return 'আমি বুঝতে পারছি যে আপনি সাহায্য চাচ্ছেন। আপনি আমাদের বিভিন্ন বিভাগ যেমন মনের পরীক্ষা, রোগরাডার, চুপলাইন ইত্যাদি ব্যবহার করতে পারেন বা আমাকে আরও নির্দিষ্ট প্রশ্ন জিজ্ঞাসা করতে পারেন।';
  }
}
</script>

</body>
</html>
