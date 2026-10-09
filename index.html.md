<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Money Setu - Instant Digital Credit & Loan Line</title>
  
  <style>
    :root {
      --primary: #4f46e5;
      --primary-gradient: linear-gradient(135deg, #6366f1 0%, #4f46e5 100%);
      --accent-gradient: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
      --success-gradient: linear-gradient(135deg, #22c55e 0%, #15803d 100%);
      --success: #16a34a;
      --danger: #dc2626;
      --warning: #d97706;
      --bg-gradient: radial-gradient(circle at top right, #e0e7ff 0%, #f8fafc 40%, #f1f5f9 100%);
      --card-bg: rgba(255, 255, 255, 0.95);
      --text-main: #0f172a;
      --text-muted: #64748b;
      --border-color: #e2e8f0;
      --shadow-lg: 0 25px 50px -12px rgba(79, 70, 229, 0.15);
    }

    * {
      box-sizing: border-box;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      margin: 0;
      padding: 0;
    }

    body {
      background: var(--bg-gradient);
      background-attachment: fixed;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 20px;
    }

    .app-card {
      background: var(--card-bg);
      backdrop-filter: blur(12px);
      padding: 36px 32px;
      border-radius: 24px;
      box-shadow: var(--shadow-lg);
      width: 100%;
      max-width: 500px;
      border: 1px solid rgba(255, 255, 255, 0.9);
      position: relative;
      overflow: hidden;
    }

    .app-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 6px;
      background: var(--primary-gradient);
    }

    .app-header {
      text-align: center;
      margin-bottom: 28px;
    }

    .app-logo {
      font-size: 30px;
      font-weight: 900;
      background: var(--primary-gradient);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      letter-spacing: -0.8px;
    }

    .app-subtitle {
      font-size: 13px;
      color: var(--text-muted);
      margin-top: 6px;
      font-weight: 500;
    }

    .trust-badges {
      display: flex;
      justify-content: center;
      gap: 16px;
      margin-top: 14px;
      font-size: 11px;
      color: var(--text-muted);
      font-weight: 600;
      background: #f8fafc;
      padding: 6px 12px;
      border-radius: 20px;
      border: 1px solid var(--border-color);
    }

    .space-y > * + * {
      margin-top: 16px;
    }

    .hidden {
      display: none !important;
    }

    .field-label {
      display: block;
      font-size: 13px;
      font-weight: 700;
      color: var(--text-main);
      margin-bottom: 6px;
    }

    .form-input, .form-select {
      width: 100%;
      padding: 14px 16px;
      border: 1.5px solid var(--border-color);
      border-radius: 12px;
      font-size: 14px;
      outline: none;
      background: #ffffff;
      color: var(--text-main);
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .form-input:focus, .form-select:focus {
      border-color: var(--primary);
      box-shadow: 0 0 0 4px rgba(79, 70, 229, 0.12);
      background: #fff;
    }

    .btn {
      width: 100%;
      padding: 14px;
      border: none;
      border-radius: 12px;
      font-weight: 700;
      font-size: 15px;
      cursor: pointer;
      color: #ffffff;
      transition: all 0.2s ease;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
    }

    .btn:active {
      transform: scale(0.98);
    }

    .btn-primary { background: var(--primary-gradient); }
    .btn-primary:hover { opacity: 0.92; box-shadow: 0 6px 16px rgba(79, 70, 229, 0.25); }
    
    .btn-success { background: var(--success-gradient); }
    .btn-success:hover { opacity: 0.92; }

    .btn-warning { background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%); }
    .btn-secondary { background: #64748b; }
    .btn-disabled { opacity: 0.5 !important; cursor: not-allowed !important; transform: none !important; box-shadow: none !important; }

    .student-toggle-box {
      background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
      padding: 14px 18px;
      border-radius: 12px;
      border: 1px solid #bfdbfe;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 13px;
      color: #1e3a8a;
      font-weight: 700;
    }

    .section-header {
      font-weight: 800;
      color: var(--text-main);
      border-bottom: 2px solid #f1f5f9;
      padding-bottom: 8px;
      margin-top: 24px;
      font-size: 14px;
      letter-spacing: -0.2px;
    }

    .camera-container {
      width: 100%;
      height: 220px;
      background: #000000;
      border-radius: 14px;
      overflow: hidden;
      position: relative;
      margin-top: 8px;
      border: 2px solid var(--border-color);
    }

    .camera-container video, .camera-container img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .button-group {
      display: flex;
      gap: 10px;
      margin-top: 10px;
    }

    .result-card {
      background: #ffffff;
      border: 1px solid #bbf7d0;
      padding: 24px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 10px 25px rgba(22, 163, 74, 0.08);
    }

    .rejected-card {
      background: #ffffff;
      border: 1px solid #fecaca;
      padding: 24px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 10px 25px rgba(220, 38, 38, 0.08);
    }

    .badge-card {
      background: #f8fafc;
      padding: 14px 16px;
      border-radius: 12px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 13px;
      font-weight: 700;
      margin: 16px 0;
      color: #1e3a8a;
      border: 1px solid #e2e8f0;
    }

    .breakdown-card {
      background: #f8fafc;
      padding: 18px;
      border-radius: 14px;
      border: 1px solid #e2e8f0;
      margin: 16px 0;
      text-align: left;
    }

    .breakdown-row {
      display: flex;
      justify-content: space-between;
      font-size: 13px;
      margin-bottom: 10px;
      color: var(--text-muted);
      font-weight: 500;
    }

    .row-main {
      font-size: 15px;
      font-weight: 800;
      border-top: 1px solid #cbd5e1;
      padding-top: 12px;
      margin-top: 8px;
      color: var(--success);
    }

    .row-repay {
      font-size: 14px;
      font-weight: 800;
      border-top: 1px dashed #cbd5e1;
      padding-top: 12px;
      margin-top: 8px;
      color: var(--primary);
    }

    .text-bold { font-weight: 700; }
    .text-green { color: var(--success); }
    .text-red { color: var(--danger); }

    .autopay-box {
      background: #eef2ff;
      padding: 16px;
      border-radius: 14px;
      border: 1px solid #c7d2fe;
      text-align: left;
      margin: 16px 0;
    }

    .badge-red {
      background: #fee2e2;
      color: #991b1b;
      padding: 4px 10px;
      border-radius: 6px;
      font-size: 11px;
      font-weight: 800;
    }

    .badge-green {
      background: #dcfce7;
      color: #166534;
      padding: 4px 10px;
      border-radius: 6px;
      font-size: 11px;
      font-weight: 800;
    }

    .status-text {
      text-align: center;
      font-size: 13px;
      font-weight: 700;
      margin-top: 16px;
      letter-spacing: -0.1px;
    }

    .timer-box {
      background: #fef3c7;
      color: #92400e;
      padding: 12px;
      border-radius: 10px;
      font-size: 12px;
      border: 1px solid #fde68a;
      font-weight: 700;
      margin-top: 10px;
    }
  </style>
</head>
<body>

  <div class="app-card">
    <div class="app-header">
      <h1 class="app-logo">Money Setu</h1>
      <p class="app-subtitle">Instant DigiLocker KYC & Credit Line Platform</p>
      <div class="trust-badges">
        <span>🔒 256-Bit Secure</span>
        <span>⚡ RBI Compliant Partner</span>
        <span>🛡️ Zero Hidden Fees</span>
      </div>
    </div>

    <!-- Step 1: Mobile Number Input -->
    <div id="step-phone" class="space-y">
      <label class="field-label">Mobile Number (Linked with Aadhaar)</label>
      <input type="tel" id="phone-number" placeholder="+91 98765 43210" value="+91" class="form-input">
      
      <button type="button" onclick="sendOTP()" class="btn btn-primary">
        Proceed with Secure OTP →
      </button>
    </div>

    <!-- Step 2: OTP Verification -->
    <div id="step-otp" class="space-y hidden">
      <label class="field-label">Enter 6-Digit Verification Code (Default: 123456)</label>
      <input type="text" id="otp-code" placeholder="123456" maxlength="6" class="form-input" style="letter-spacing: 4px; font-weight: bold; text-align: center;">
      
      <button type="button" onclick="verifyOTP()" class="btn btn-success">
        Verify & Continue ✓
      </button>
    </div>

    <!-- Step 3: Full KYC Form -->
    <form id="step-kyc" class="space-y hidden" onsubmit="submitKYC(event)">
      
      <div class="student-toggle-box">
        <span>🎓 Applying as a Student?</span>
        <input type="checkbox" id="is-student" onchange="toggleStudentMode()" style="width: 20px; height: 20px; accent-color: var(--primary); cursor: pointer;">
      </div>

      <div class="section-header">👤 1. Personal & Identity Info</div>

      <div>
        <label class="field-label">Full Name (As per PAN/Aadhaar)</label>
        <input type="text" id="full-name" required placeholder="Rahul Sharma" class="form-input">
      </div>

      <div id="income-field-group">
        <label class="field-label">Monthly Income (₹)</label>
        <input type="number" id="monthly-income" placeholder="45000" class="form-input">
      </div>

      <div>
        <label class="field-label">Aadhaar Card Number (12 Digits)</label>
        <input type="text" id="aadhaar-no" required maxlength="12" placeholder="4521 8963 1204" oninput="this.value = this.value.replace(/[^0-9]/g, '')" class="form-input">
      </div>

      <div>
        <label class="field-label">PAN Card Number</label>
        <input type="text" id="pan-no" required maxlength="10" placeholder="ABCDE1234F" oninput="formatPAN(this)" class="form-input" style="text-transform: uppercase;">
      </div>

      <div>
        <label id="dob-label" class="field-label">Date of Birth (Must be 18+ Years)</label>
        <input type="date" id="dob" required class="form-input">
      </div>

      <div class="section-header">🏦 2. Bank Account Details</div>

      <div class="space-y">
        <div>
          <label class="field-label">Bank Account Number</label>
          <input type="text" id="bank-acc-no" required placeholder="32145698701" oninput="this.value = this.value.replace(/[^0-9]/g, '')" class="form-input">
        </div>
        <div>
          <label class="field-label">IFSC Code (11 Characters)</label>
          <input type="text" id="bank-ifsc" required maxlength="11" placeholder="HDFC0001234" oninput="this.value = this.value.toUpperCase()" class="form-input" style="text-transform: uppercase;">
        </div>
      </div>

      <div class="section-header">📂 3. Document Verification</div>

      <div id="regular-docs-group" class="space-y">
        <div>
          <label class="field-label">Aadhaar Card Front Photo</label>
          <input type="file" id="aadhaar-front" accept="image/*" class="form-input" style="padding: 10px;">
        </div>
        <div>
          <label class="field-label">Aadhaar Card Back Photo</label>
          <input type="file" id="aadhaar-back" accept="image/*" class="form-input" style="padding: 10px;">
        </div>
        <div>
          <label class="field-label">PAN Card Front Photo</label>
          <input type="file" id="pan-front" accept="image/*" class="form-input" style="padding: 10px;">
        </div>
      </div>

      <div id="student-docs-group" class="space-y hidden">
        <div>
          <label class="field-label">Select Student Document Type</label>
          <select id="student-doc-type" class="form-select">
            <option value="College ID">College ID Card</option>
            <option value="Fees Receipt">Fees Receipt</option>
            <option value="Admit Card">Examination Admit Card</option>
          </select>
        </div>
        <div>
          <label class="field-label">Upload Document File</label>
          <input type="file" id="student-doc-file" accept="image/*,.pdf" class="form-input" style="padding: 10px;">
        </div>
      </div>

      <div class="section-header">📸 4. Live Face Selfie</div>

      <div class="space-y" style="text-align: center;">
        <div class="camera-container">
          <video id="webcam" autoplay playsinline></video>
          <canvas id="selfie-canvas" class="hidden"></canvas>
          <img id="selfie-preview" class="hidden" alt="Selfie Preview">
        </div>

        <div class="button-group">
          <button type="button" onclick="startCamera()" class="btn btn-secondary" style="flex:1;">Start Camera</button>
          <button type="button" onclick="captureSelfie()" id="btn-capture" class="btn btn-primary" style="flex:1;">Capture Selfie</button>
          <button type="button" onclick="retrySelfie()" id="btn-retry" class="btn btn-warning hidden" style="flex:1;">Retake</button>
        </div>
      </div>

      <button type="submit" id="submit-btn" class="btn btn-primary" style="margin-top: 24px;">
        Submit & Verify Details →
      </button>
    </form>

    <!-- Success Result Screen -->
    <div id="result-box" class="result-card hidden">
      <div style="font-size: 42px; margin-bottom: 6px;">🎉</div>
      <h3 style="font-size: 20px; font-weight: 900; color: #0f172a;">Verification Successful!</h3>
      <p id="approval-status" style="font-size: 13px; font-weight: 700; color: var(--primary); margin-top: 4px;"></p>

      <div id="cibil-badge-card" class="badge-card">
        <span>Verified CIBIL Score: <strong id="cibil-display" style="font-size: 16px; color: var(--success);">750</strong></span>
        <span id="overdue-status" class="text-green">Status: Excellent</span>
      </div>

      <div class="breakdown-card">
        <div class="breakdown-row">
          <span>Approved Credit Limit:</span>
          <span id="card-approved-limit" class="text-bold" style="color: #0f172a;">₹0</span>
        </div>
        <div class="breakdown-row text-red">
          <span>Processing Fee & GST (~30%):</span>
          <span id="card-deductions" class="text-bold">-₹0</span>
        </div>
        <div class="breakdown-row row-main text-green">
          <span>Net Disbursed Amount (In Bank):</span>
          <span id="card-disbursed-amt">₹0</span>
        </div>
        
        <div class="breakdown-row text-red hidden" id="late-fee-row">
          <span>Late Fine Charge (Overdue):</span>
          <span id="card-late-fee" class="text-bold">+₹0</span>
        </div>

        <div class="breakdown-row row-repay">
          <span>Total Repayment Due Amount:</span>
          <span id="card-repay-amt">₹0</span>
        </div>
      </div>

      <div id="autopay-section" class="autopay-box">
        <div class="breakdown-row" style="margin-bottom: 6px;">
          <h4 class="text-bold" style="font-size: 13px; color: #1e3a8a;">UPI AutoPay e-Mandate <span class="text-red">*Required</span></h4>
          <span id="autopay-badge" class="badge-red">Mandate Pending</span>
        </div>
        <p style="font-size: 11px; color: #475569; margin-bottom: 12px;">Setup mandatory secure e-Mandate to authorize direct bank disbursement.</p>

        <div id="autopay-form" class="space-y">
          <input type="text" id="upi-id" placeholder="yourname@upi / ybl" class="form-input">
          <button type="button" onclick="setupAutoPay()" id="btn-autopay" class="btn btn-primary">
            Enable Secure e-Mandate
          </button>
        </div>
      </div>

      <div id="repayment-section" class="space-y">
        <button type="button" onclick="simulateRepayment()" id="pay-btn" disabled class="btn btn-success btn-disabled">
          Pay Active Due & Upgrade Limit (+30%)
        </button>

        <button type="button" onclick="applyOverduePenalty()" class="btn btn-warning">
          Simulate 24-Hour Overdue (+₹975 Fine & Impact CIBIL)
        </button>

        <p id="repay-timer" class="timer-box hidden"></p>
      </div>
    </div>

    <!-- Rejection Result Screen (CIBIL < 650) -->
    <div id="rejection-box" class="rejected-card hidden">
      <div style="font-size: 42px; margin-bottom: 6px;">❌</div>
      <h3 style="font-size: 20px; font-weight: 900; color: var(--danger);">Loan Application Rejected</h3>
      <p style="font-size: 13px; color: var(--text-muted); margin-top: 6px;">
        As per RBI guidelines and internal risk policy, your calculated CIBIL score is below 650. Hence, your credit line request cannot be approved right now.
      </p>

      <div class="badge-card" style="background: #fef2f2; border-color: #fca5a5; color: #991b1b; margin: 20px 0;">
        <span>Assessed CIBIL Score: <strong id="rejected-cibil-val">620</strong></span>
        <span>Status: High Risk</span>
      </div>

      <div class="timer-box" style="background: #fff1f2; color: #be123c; border-color: #fecdd3; margin-bottom: 20px;">
        ⏳ Cool-down Period Active: You can re-apply after <strong id="cooldown-days-left">30</strong> days.
      </div>

      <button type="button" onclick="resetToHome()" class="btn btn-secondary">
        ← Back to Home / Try Later
      </button>
    </div>

    <p id="status-msg" class="status-text"></p>
  </div>

  <script>
    let selfieBase64Data = "";
    let currentLimit = 0;
    let currentCibilScore = 750;
    let accumulatedLatePenalty = 0;
    let isAutoPayEnabled = false;

    window.onload = function() {
      updateAgeLimit(18);
    };

    function formatPAN(input) {
      let val = input.value.toUpperCase().replace(/[^A-Z0-9]/g, '');
      let formatted = '';
      
      for (let i = 0; i < val.length && i < 10; i++) {
        if (i < 5) {
          if (/[A-Z]/.test(val[i])) formatted += val[i];
        } else if (i >= 5 && i < 9) {
          if (/[0-9]/.test(val[i])) formatted += val[i];
        } else if (i === 9) {
          if (/[A-Z]/.test(val[i])) formatted += val[i];
        }
      }
      input.value = formatted;
    }

    function updateAgeLimit(minAge) {
      const today = new Date();
      const maxDate = new Date(today.getFullYear() - minAge, today.getMonth(), today.getDate()).toISOString().split('T')[0];
      document.getElementById('dob').setAttribute('max', maxDate);
      document.getElementById('dob-label').innerText = `Date of Birth (Must be ${minAge}+ Years)`;
    }

    function toggleStudentMode() {
      const isStudent = document.getElementById('is-student').checked;
      const incomeGroup = document.getElementById('income-field-group');
      const regularDocs = document.getElementById('regular-docs-group');
      const studentDocs = document.getElementById('student-docs-group');

      if (isStudent) {
        updateAgeLimit(16);
        incomeGroup.classList.add('hidden');
        regularDocs.classList.add('hidden');
        studentDocs.classList.remove('hidden');
      } else {
        updateAgeLimit(18);
        incomeGroup.classList.remove('hidden');
        regularDocs.classList.remove('hidden');
        studentDocs.classList.add('hidden');
      }
    }

    function showStatus(text, isError = false) {
      const el = document.getElementById('status-msg');
      el.textContent = text;
      el.style.color = isError ? 'var(--danger)' : 'var(--success)';
    }

    function sendOTP() {
      const phone = document.getElementById('phone-number').value.trim();
      if (!phone || phone.length < 10) return showStatus("Please enter a valid phone number with +91", true);

      showStatus("Sending OTP...");
      setTimeout(() => {
        document.getElementById('step-phone').classList.add('hidden');
        document.getElementById('step-otp').classList.remove('hidden');
        showStatus("OTP Sent Successfully! (Default: 123456)");
      }, 400);
    }

    function verifyOTP() {
      const code = document.getElementById('otp-code').value.trim();
      if (!code) return showStatus("Please enter the verification code", true);

      showStatus("Verifying OTP...");
      setTimeout(() => {
        document.getElementById('step-otp').classList.add('hidden');
        document.getElementById('step-kyc').classList.remove('hidden');
        showStatus("Login Successful! Please fill your KYC details.");
      }, 400);
    }

    async function startCamera() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" } });
        document.getElementById('webcam').srcObject = stream;
        showStatus("Camera Ready! Click Capture Selfie.");
      } catch (err) {
        showStatus("Camera loading... Tap Capture to proceed.", false);
      }
    }

    function captureSelfie() {
      const video = document.getElementById('webcam');
      const canvas = document.getElementById('selfie-canvas');
      const preview = document.getElementById('selfie-preview');
      
      canvas.width = video.videoWidth || 320;
      canvas.height = video.videoHeight || 240;
      const ctx = canvas.getContext('2d');
      ctx.drawImage(video, 0, 0, canvas.width, canvas.height);

      selfieBase64Data = canvas.toDataURL('image/jpeg');

      if (!selfieBase64Data || selfieBase64Data.length < 100) {
        selfieBase64Data = "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mNk+M9QDwADhgGAWjR9awAAAABJRU5ErkJggg==";
      }

      preview.src = selfieBase64Data;
      preview.classList.remove('hidden');
      video.classList.add('hidden');

      document.getElementById('btn-capture').classList.add('hidden');
      document.getElementById('btn-retry').classList.remove('hidden');
      showStatus("Selfie captured successfully!");
    }

    function retrySelfie() {
      const video = document.getElementById('webcam');
      const preview = document.getElementById('selfie-preview');

      selfieBase64Data = "";
      preview.classList.add('hidden');
      video.classList.remove('hidden');

      document.getElementById('btn-capture').classList.remove('hidden');
      document.getElementById('btn-retry').classList.add('hidden');
      showStatus("Retake: Click Capture to take a new selfie.");
    }

    function calculateFinancialBreakdown(limit) {
      const deductions = Math.round(limit * 0.30);
      const disbursedAmount = limit - deductions; 
      const baseRepayAmount = Math.round(limit * 1.23); 
      const totalRepayAmount = baseRepayAmount + accumulatedLatePenalty;

      return { deductions, disbursedAmount, totalRepayAmount };
    }

    function updateBreakdownUI() {
      const calc = calculateFinancialBreakdown(currentLimit);
      document.getElementById('card-approved-limit').innerText = "₹" + currentLimit.toLocaleString('en-IN');
      document.getElementById('card-deductions').innerText = "-₹" + calc.deductions.toLocaleString('en-IN');
      document.getElementById('card-disbursed-amt').innerText = "₹" + calc.disbursedAmount.toLocaleString('en-IN');
      document.getElementById('card-repay-amt').innerText = "₹" + calc.totalRepayAmount.toLocaleString('en-IN');
      document.getElementById('cibil-display').innerText = currentCibilScore;

      if (accumulatedLatePenalty > 0) {
        document.getElementById('late-fee-row').classList.remove('hidden');
        document.getElementById('card-late-fee').innerText = "+₹" + accumulatedLatePenalty.toLocaleString('en-IN');
      } else {
        document.getElementById('late-fee-row').classList.add('hidden');
      }
    }

    function applyOverduePenalty() {
      accumulatedLatePenalty += 975;
      currentCibilScore = Math.max(300, currentCibilScore - 50);

      const overdueBadge = document.getElementById('overdue-status');
      overdueBadge.className = "text-red text-bold";
      overdueBadge.innerText = "OVERDUE (-50 CIBIL Impact)";

      updateBreakdownUI();
      showStatus("⚠️ Overdue Warning: ₹975 late fee added & CIBIL score decreased!", true);
    }

    function setupAutoPay() {
      const upiId = document.getElementById('upi-id').value.trim();

      if (!upiId || !upiId.includes('@')) {
        return showStatus("Please enter a valid UPI ID (e.g., user@upi)!", true);
      }

      const btn = document.getElementById('btn-autopay');
      btn.disabled = true;
      btn.innerText = "Connecting to UPI App...";

      showStatus("Connecting to UPI for Mandatory e-Mandate approval...");

      setTimeout(() => {
        isAutoPayEnabled = true;
        const badge = document.getElementById('autopay-badge');
        badge.className = "badge-green";
        badge.innerText = "e-Mandate Active ✓";

        document.getElementById('autopay-form').innerHTML = `
          <p style="color:var(--success); font-size:12px; font-weight:bold;">
            ✓ e-Mandate Linked & Approved with UPI: ${upiId}
          </p>
        `;

        const payBtn = document.getElementById('pay-btn');
        payBtn.disabled = false;
        payBtn.classList.remove('btn-disabled');

        showStatus("e-Mandate Approved! You can now proceed to disbursement.");
      }, 900);
    }

    function generateVerifiedOffer(income, isStudent) {
      if (isStudent) {
        // Students get randomized/tested CIBIL to demonstrate both cases, let's give 720 for student
        return { cibilScore: 720, approvedAmount: 3000 };
      }
      // For demonstration: if income < 15000, let's simulate a low CIBIL (< 650) to test rejection easily, otherwise 750+
      let simulatedCibil = income < 18000 ? 620 : 760;
      const calculatedAmount = Math.min(income * 3, 500000);
      const approvedAmount = Math.max(calculatedAmount, 5000);
      return { cibilScore: simulatedCibil, approvedAmount };
    }

    function submitKYC(e) {
      e.preventDefault();

      const isStudent = document.getElementById('is-student').checked;
      const aadhaarVal = document.getElementById('aadhaar-no').value.trim();
      const panVal = document.getElementById('pan-no').value.trim().toUpperCase();
      const dobVal = document.getElementById('dob').value;
      const bankAcc = document.getElementById('bank-acc-no').value.trim();
      const bankIfsc = document.getElementById('bank-ifsc').value.trim().toUpperCase();

      if (aadhaarVal.length !== 12 || !/^\d{12}$/.test(aadhaarVal)) {
        return showStatus("Please enter a valid 12-digit Aadhaar Number!", true);
      }

      const panRegex = /^[A-Z]{5}[0-9]{4}[A-Z]{1}$/;
      if (!panRegex.test(panVal)) {
        return showStatus("Invalid PAN Format! (e.g., ABCDE1234F)", true);
      }

      if (!bankAcc || bankAcc.length < 9) {
        return showStatus("Please enter a valid Bank Account Number!", true);
      }

      if (!bankIfsc || bankIfsc.length !== 11) {
        return showStatus("Please enter a valid 11-Digit IFSC Code!", true);
      }

      if (!dobVal) return showStatus("Please select your Date of Birth!", true);
      const dobDate = new Date(dobVal);
      const today = new Date();
      let age = today.getFullYear() - dobDate.getFullYear();
      const m = today.getMonth() - dobDate.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < dobDate.getDate())) age--;

      const requiredAge = isStudent ? 16 : 18;
      if (age < requiredAge) {
        return showStatus(`You must be at least ${requiredAge} years old to apply.`, true);
      }

      if (!selfieBase64Data) selfieBase64Data = "dummy_selfie";

      showStatus("Connecting to Credit Bureau (CIBIL/Equifax)...");
      document.getElementById('submit-btn').disabled = true;

      setTimeout(() => {
        const income = parseFloat(document.getElementById('monthly-income').value) || (isStudent ? 20000 : 0);
        const offer = generateVerifiedOffer(income, isStudent);

        currentCibilScore = offer.cibilScore;

        document.getElementById('step-kyc').classList.add('hidden');
        document.getElementById('submit-btn').disabled = false;

        // Check CIBIL Rejection Condition (< 650)
        if (currentCibilScore < 650) {
          document.getElementById('rejected-cibil-val').innerText = currentCibilScore;
          document.getElementById('rejection-box').classList.remove('hidden');
          showStatus("Application Rejected due to low CIBIL score.", true);
          return;
        }

        // If Approved
        currentLimit = offer.approvedAmount;
        document.getElementById('result-box').classList.remove('hidden');
        
        if (isStudent) {
          document.getElementById('approval-status').innerText = "Student Credit Line Approved!";
        } else {
          document.getElementById('approval-status').innerText = "DigiLocker & Bureau Verified Offer";
        }

        updateBreakdownUI();
        showStatus("KYC & CIBIL Verified Successfully! Setup e-Mandate.");
      }, 800);
    }

    function resetToHome() {
      document.getElementById('rejection-box').classList.add('hidden');
      document.getElementById('step-phone').classList.remove('hidden');
      document.getElementById('phone-number').value = "+91";
      showStatus("You can re-apply after the 30-day cool-down period.");
    }

    function simulateRepayment() {
      if (!isAutoPayEnabled) {
        return showStatus("Setting up e-Mandate / AutoPay is compulsory!", true);
      }

      const payBtn = document.getElementById('pay-btn');
      const timerEl = document.getElementById('repay-timer');

      payBtn.disabled = true;
      payBtn.classList.add('btn-disabled');
      timerEl.classList.remove('hidden');

      let timeLeft = 120; // 2 minutes countdown

      showStatus("Payment Successful! Upgrading Credit Limit in 2 minutes...");

      const countdown = setInterval(() => {
        timeLeft--;
        const mins = Math.floor(timeLeft / 60);
        const secs = timeLeft % 60;
        timerEl.innerText = `⏳ Limit Upgrade (+30%) in ${mins}:${secs < 10 ? '0' : ''}${secs} minutes...`;

        if (timeLeft <= 0) {
          clearInterval(countdown);
          
          accumulatedLatePenalty = 0;
          currentLimit = Math.round(currentLimit * 1.30);

          updateBreakdownUI();
          
          const calc = calculateFinancialBreakdown(currentLimit);
          timerEl.innerText = `🎉 Limit upgraded by 30% to ₹${currentLimit.toLocaleString('en-IN')}. New Disbursed: ₹${calc.disbursedAmount.toLocaleString('en-IN')}`;
          
          showStatus("Limit Upgrade Successful!");

          payBtn.disabled = false;
          payBtn.classList.remove('btn-disabled');
        }
      }, 1000);
    }
  </script>
</body>
</html>
```