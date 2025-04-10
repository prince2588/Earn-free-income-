<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title id="pageTitle">Yosemite 4x4 Car Company Giveaway</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    /* Global Style */
    * { box-sizing: border-box; }
    body {
      font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
      background: #f2f2f2;
      margin: 0;
      padding: 0;
    }
    header {
      text-align: center;
      color: #fff;
      padding: 20px;
      background: linear-gradient(45deg, #3b5998, #8b9dc3);
      background-size: cover;
      background-position: center;
      box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    }
    /* Loader Screens */
    #loadingScreen, #withdrawLoadingScreen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: #fff;
      z-index: 9999;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24px;
      color: #333;
      text-align: center;
      padding: 20px;
    }
    #withdrawLoadingScreen { display: none; }
    
    /* Authentication Container */
    .auth-container {
      max-width: 400px;
      margin: 80px auto;
      background: #fff;
      border-radius: 10px;
      padding: 30px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      display: none;
    }
    .auth-container h2 {
      margin: 0 0 10px;
      text-align: center;
    }
    .auth-container p {
      text-align: center;
    }
    .auth-container label {
      margin-top: 15px;
      display: block;
      font-weight: bold;
    }
    .auth-container input[type="email"],
    .auth-container input[type="password"],
    .auth-container input[type="text"] {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .auth-container .primary-button, .auth-container .google-button {
      width: 100%;
      padding: 12px;
      margin-top: 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
      transition: background 0.3s;
    }
    .auth-container .primary-button {
      background: #28a745;
      color: #fff;
    }
    .auth-container .primary-button:hover {
      background: #218838;
    }
    .auth-container .google-button {
      background: #fff;
      border: 1px solid #ccc;
      color: #333;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .auth-container .google-button img {
      width: 20px;
      height: 20px;
      margin-right: 10px;
    }
    .auth-container .alt-link {
      text-align: center;
      margin-top: 15px;
      font-size: 14px;
      cursor: pointer;
      color: #007bff;
    }
    .auth-container .checkbox-group {
      margin-top: 10px;
      font-size: 14px;
      display: flex;
      align-items: center;
    }
    .auth-container .checkbox-group input {
      margin-right: 5px;
    }
    hr {
      margin: 20px 0;
      border: 0;
      border-top: 1px solid #ccc;
    }
    /* Containers: Dashboard, Broker, Withdrawal, Customize */
    .container {
      max-width: 700px;
      margin: 40px auto;
      background: #fff;
      padding: 20px;
      border-radius: 5px;
      border: 1px solid #ccc;
      display: none;
    }
    .container h2, .container h3 {
      margin-top: 0;
      font-weight: bold;
    }
    .container p {
      font-size: 16px;
      line-height: 1.6;
    }
    .link-button {
      color: #007bff;
      text-decoration: underline;
      cursor: pointer;
      margin-top: 10px;
      font-size: 14px;
    }
    .hidden { display: none; }
    #notifications {
      max-height: 150px;
      overflow-y: auto;
      border: 1px solid #ccc;
      background: #f9f9f9;
      padding: 10px;
      margin-top: 10px;
    }
    .notification {
      border-bottom: 1px solid #ddd;
      padding: 5px 0;
      font-size: 14px;
    }
    #dashboardImage, #withdrawDashboardImage {
      max-width: 100%;
      height: auto;
      margin-bottom: 15px;
    }
    /* User Email Display */
    #userEmailDisplay {
      font-size: 32px;
      font-weight: bold;
      margin: 10px 0;
      text-align: center;
      color: #333;
    }
    /* Company News Section */
    #companyNews {
      background: #eef3f8;
      border: 1px solid #ccc;
      padding: 10px;
      border-radius: 5px;
      margin-top: 15px;
    }
    #companyNews h3 {
      margin: 0 0 10px;
    }
    /* Responsive adjustments */
    @media (max-width: 480px) {
      .auth-container, .container {
        margin: 20px;
        padding: 20px;
      }
    }
    /* Admin Editor Panel */
    .admin-editor {
      margin-top: 20px;
      border-top: 1px solid #ccc;
      padding-top: 15px;
    }
    .admin-editor label {
      display: block;
      margin-top: 10px;
      font-weight: bold;
    }
    .admin-editor input[type="text"],
    .admin-editor input[type="url"],
    .admin-editor input[type="number"],
    .admin-editor input[type="file"] {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 3px;
    }
    .admin-editor .save-editor-btn,
    .admin-editor .upload-editor-btn {
      margin-top: 15px;
      padding: 10px;
      background: #007bff;
      color: #fff;
      border: none;
      width: 100%;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
    }
    .admin-editor .save-editor-btn:hover,
    .admin-editor .upload-editor-btn:hover {
      background: #0069d9;
    }
  </style>
</head>
<body>
  <!-- General Loading Screen -->
  <div id="loadingScreen">
    <p>Loading...</p>
  </div>
  <!-- Withdrawal Process Loading Screen -->
  <div id="withdrawLoadingScreen">
    <p>Please wait patiently while we proceed with the process…</p>
  </div>
  
  <!-- Header -->
  <header>
    <h1 id="companyNameHeader">Yosemite 4x4 Car Company Giveaway</h1>
  </header>
  
  <!-- Authentication Container (Login/Registration) -->
  <div id="authContainer" class="auth-container">
    <!-- Registration Form -->
    <div id="registerForm" class="form-container">
      <h2>Create Your Account</h2>
      <p>Join us for a trusted brokerage experience!</p>
      <button class="google-button" onclick="handleGoogleSignup()">
        <img src="https://via.placeholder.com/20" alt="Google Logo" /> 
        Sign up with Google
      </button>
      <hr />
      <label for="regEmail">Email Address</label>
      <input type="email" id="regEmail" placeholder="you@example.com" required />
      <label for="regPassword">Password</label>
      <input type="password" id="regPassword" placeholder="Enter a secure password" required />
      <div class="checkbox-group">
        <input type="checkbox" id="marketingConsent" />
        <label for="marketingConsent">Yes, keep me updated with our latest news (optional).</label>
      </div>
      <div class="checkbox-group">
        <input type="checkbox" id="termsConsent" required />
        <label for="termsConsent">I agree to the Terms and Conditions.</label>
      </div>
      <button class="primary-button" onclick="createAccount()">Create Account</button>
      <p class="alt-link" onclick="showLogin()">Already have an account? Log in!</p>
    </div>
    <!-- Login Form -->
    <div id="loginFormAuth" class="form-container hidden">
      <h2>Welcome Back!</h2>
      <p>Access your personalized dashboard below.</p>
      <button class="google-button" onclick="handleGoogleLogin()">
        <img src="https://via.placeholder.com/20" alt="Google Logo" /> 
        Sign in with Google
      </button>
      <hr />
      <label for="loginEmail">Email Address</label>
      <input type="email" id="loginEmail" placeholder="you@example.com" required />
      <label for="loginPassword">Password</label>
      <input type="password" id="loginPassword" placeholder="Enter your password" required />
      <button class="primary-button" onclick="processLogin()">Log In</button>
      <p class="alt-link" onclick="showForgotPassword()">Forgot Password?</p>
      <p class="alt-link" onclick="showRegister()">Don't have an account? Create one!</p>
    </div>
  </div>
  
  <!-- Forgot Password Container -->
  <div id="forgotPassword" class="container">
    <h2>Reset Your Password</h2>
    <form id="forgotPasswordForm">
      <label for="forgotEmail">Email Address</label>
      <input type="email" id="forgotEmail" placeholder="you@example.com" required>
      <button type="submit">Send Verification Code</button>
    </form>
    <form id="resetPasswordForm" class="hidden">
      <label for="verificationCode">Verification Code</label>
      <input type="text" id="verificationCode" placeholder="Enter code">
      <label for="newPassword">New Password</label>
      <input type="password" id="newPassword" placeholder="Enter new password">
      <button type="submit">Reset Password</button>
    </form>
    <p class="link-button" onclick="showLogin()">Back to Login</p>
  </div>
  
  <!-- Dashboard Container (User Dashboard) -->
  <div id="dashboard" class="container">
    <!-- New element to display user's email in large uppercase text -->
    <h1 id="userEmailDisplay" class="hidden"></h1>
    <h2>User Dashboard</h2>
    <img id="dashboardImage" class="hidden" src="" alt="Main Dashboard Image">
    <!-- Optional Withdrawal Dashboard Image -->
    <img id="withdrawDashboardImage" class="hidden" src="" alt="Withdrawal Dashboard Image" style="margin-top:15px;">
    <p id="welcomeMessage"></p>
    <p>Your current balance: $<span id="userBalance">0</span></p>
    <p id="verificationStatus" style="font-weight: bold; color: red;">Not Verified</p>
    <p id="withdrawLinkContainer" class="link-button" onclick="showSection('withdraw')">Proceed to Withdraw</p>
    <!-- Broker Administration link is visible only for admin -->
    <p id="brokerLinkContainer" class="link-button" onclick="showSection('broker')">Broker Administration</p>
    
    <!-- Company News Section -->
    <div id="companyNews">
      <h3>Latest Company News</h3>
      <p>Our company recently secured a new partnership with global financial institutions to streamline your transactions. Stay tuned for more exciting updates!</p>
    </div>
    
    <h3>Recent Activity</h3>
    <div id="notifications"></div>
    <!-- Customize Website link (admin only) -->
    <p id="customizeLinkContainer" class="link-button hidden" onclick="showSection('customize')">Customize Website</p>
    <p class="link-button" onclick="logout()">Logout</p>
    
    <!-- Admin Editor Panel (only visible to admin) -->
    <div id="adminEditor" class="admin-editor hidden">
      <h3>Editor Settings</h3>
      <!-- Main Dashboard Editor -->
      <label for="editCompanyName">Main Dashboard Editor - Company Name</label>
      <input type="text" id="editCompanyName" placeholder="Enter new company name">
      <label for="editDashboardImage">Main Dashboard Image URL</label>
      <input type="url" id="editDashboardImage" placeholder="https://">
      <label for="uploadDashboardImage">Or Upload Main Dashboard Image</label>
      <input type="file" id="uploadDashboardImage" accept="image/*">
      <button class="upload-editor-btn" onclick="uploadDashboardImage()">Upload Main Image</button>
      
      <!-- Withdrawal Dashboard Editor -->
      <hr>
      <h4>Withdrawal Dashboard Editor</h4>
      <label for="editWithdrawDashboardImage">Withdrawal Dashboard Image URL</label>
      <input type="url" id="editWithdrawDashboardImage" placeholder="https://">
      <label for="uploadWithdrawDashboardImage">Or Upload Withdrawal Dashboard Image</label>
      <input type="file" id="uploadWithdrawDashboardImage" accept="image/*">
      <button class="upload-editor-btn" onclick="uploadWithdrawDashboardImage()">Upload Withdrawal Image</button>
      
      <!-- Website Background Editor -->
      <hr>
      <h4>Website Background Editor</h4>
      <label for="editWebsiteBackgroundImage">Website Background Image URL</label>
      <input type="url" id="editWebsiteBackgroundImage" placeholder="Enter website background image URL">
      <label for="uploadWebsiteBackgroundImage">Or Upload Website Background Image</label>
      <input type="file" id="uploadWebsiteBackgroundImage" accept="image/*">
      <button class="upload-editor-btn" onclick="uploadWebsiteBackgroundImage()">Upload Website Background Image</button>
      
      <!-- Company Name Header Editor -->
      <hr>
      <h4>Company Name Header Editor</h4>
      <label for="editCompanyNameBackground">Company Name Header Background Image URL</label>
      <input type="url" id="editCompanyNameBackground" placeholder="Enter header background URL">
      <label for="uploadCompanyNameBackground">Or Upload Company Name Header Background Image</label>
      <input type="file" id="uploadCompanyNameBackground" accept="image/*">
      <button class="upload-editor-btn" onclick="uploadCompanyNameBackground()">Upload Header Background</button>
      
      <!-- Company News Editor -->
      <hr>
      <h4>Company News Editor</h4>
      <label for="editCompanyNews">Update Company News</label>
      <input type="text" id="editCompanyNews" placeholder="Enter latest company news">
      
      <!-- Login/Registration Style Editor -->
      <hr>
      <h4>Login/Registration Style Editor</h4>
      <label for="loginWidth">Login Form Width (px)</label>
      <input type="number" id="loginWidth" placeholder="e.g., 400">
      <label for="loginBorderRadius">Login Form Border Radius (px)</label>
      <input type="number" id="loginBorderRadius" placeholder="e.g., 10">
      
      <button class="save-editor-btn" onclick="saveEditorSettings()">Save Editor Settings</button>
    </div>
  </div>
  
  <!-- Broker Administration Container (Admin Only) -->
  <div id="broker" class="container">
    <h2>Broker Administration</h2>
    <div id="adminSection">
      <h3>Fund User Account</h3>
      <form id="fundForm">
        <input type="email" id="targetEmail" placeholder="User Email" required>
        <input type="number" id="fundAmount" placeholder="Amount" required>
        <button type="submit">Add Funds</button>
      </form>
      <h3>Verify User Account</h3>
      <form id="verifyForm">
        <input type="email" id="verifyEmail" placeholder="User Email" required>
        <button type="submit">Verify User</button>
      </form>
    </div>
    <p class="link-button" onclick="showSection('dashboard')">Back to Dashboard</p>
    <p class="link-button" onclick="logout()">Logout</p>
  </div>
  
  <!-- Withdraw Funds Container -->
  <div id="withdraw" class="container">
    <h2>Withdrawal Process</h2>
    <p>For security, your withdrawal request is being processed by our trusted banking partners. Please review your details below.</p>
    <form id="withdrawForm">
      <input type="text" id="bankName" placeholder="Bank Name" required>
      <input type="text" id="accountNumber" placeholder="Account Number" required>
      <input type="number" step="0.01" id="withdrawAmount" placeholder="Withdrawal Amount" required>
      <button type="submit">Request Withdrawal</button>
    </form>
    <p class="link-button" onclick="showSection('dashboard')">Back to Dashboard</p>
  </div>
  
  <!-- Customize Website Container (Admin Only) -->
  <div id="customize" class="container">
    <h2>Customize Website</h2>
    <form id="customizeForm">
      <input type="text" id="newCompanyName" placeholder="New Company Name">
      <input type="url" id="newDashboardImage" placeholder="Dashboard Image URL">
      <button type="submit">Save Changes</button>
    </form>
    <p class="link-button" onclick="showSection('dashboard')">Back to Dashboard</p>
  </div>
  
  <script>
    /* -------------------------
       Helper & Storage Functions
    ------------------------- */
    const ADMIN_EMAIL = "admin@yosemite4x4.com";
    const ADMIN_PASSWORD = "admin";
    const DEFAULT_COMPANY_NAME = "Yosemite 4x4 Car Company Giveaway";
    
    let notificationsInterval = null;
    
    // Simulated user database in localStorage
    function getUsers() {
      return JSON.parse(localStorage.getItem('users')) || {};
    }
    function setUsers(users) {
      localStorage.setItem('users', JSON.stringify(users));
    }
    function setCurrentUser(email) {
      localStorage.setItem('currentUser', email);
    }
    function getCurrentUser() {
      return localStorage.getItem('currentUser');
    }
    
    // Company name and images
    function getCompanyName() {
      return localStorage.getItem('companyName') || DEFAULT_COMPANY_NAME;
    }
    function setCompanyName(name) {
      localStorage.setItem('companyName', name);
    }
    function getDashboardImageURL() {
      return localStorage.getItem('dashboardImage') || "";
    }
    function setDashboardImageURL(url) {
      localStorage.setItem('dashboardImage', url);
    }
    function getWithdrawDashboardImageURL() {
      return localStorage.getItem('withdrawDashboardImage') || "";
    }
    function setWithdrawDashboardImageURL(url) {
      localStorage.setItem('withdrawDashboardImage', url);
    }
    function getWebsiteBackgroundImage() {
      return localStorage.getItem('websiteBackgroundImage') || "";
    }
    function setWebsiteBackgroundImage(url) {
      localStorage.setItem('websiteBackgroundImage', url);
    }
    function getCompanyNameBackgroundImage() {
      return localStorage.getItem('companyNameBackground') || "";
    }
    function setCompanyNameBackgroundImage(url) {
      localStorage.setItem('companyNameBackground', url);
    }
    function getCompanyNews() {
      return localStorage.getItem('companyNews') || "Welcome to our broker platform. Stay tuned for more updates!";
    }
    function setCompanyNews(news) {
      localStorage.setItem('companyNews', news);
    }
    
    // Update header, page title, and website background
    function updateHeader() {
      const name = getCompanyName();
      document.getElementById('companyNameHeader').textContent = name;
      document.getElementById('pageTitle').textContent = name;
      
      // Update header background if provided
      const headerBg = getCompanyNameBackgroundImage();
      if(headerBg.trim() !== "") {
        document.querySelector('header').style.backgroundImage = "url('" + headerBg + "')";
        document.querySelector('header').style.backgroundSize = "cover";
        document.querySelector('header').style.backgroundPosition = "center";
      } else {
        document.querySelector('header').style.backgroundImage = "linear-gradient(45deg, #3b5998, #8b9dc3)";
      }
      updateWebsiteBackground();
    }
    
    // Update website background image
    function updateWebsiteBackground() {
      const bg = getWebsiteBackgroundImage();
      if(bg.trim() !== "") {
        document.body.style.backgroundImage = "url('" + bg + "')";
        document.body.style.backgroundSize = "cover";
        document.body.style.backgroundRepeat = "no-repeat";
      } else {
        document.body.style.backgroundImage = "none";
        document.body.style.backgroundColor = "#f2f2f2";
      }
    }
    
    // Show and hide sections by id
    function showSection(sectionId) {
      document.getElementById('authContainer').style.display = 'none';
      document.getElementById('forgotPassword').style.display = 'none';
      const sections = ['dashboard', 'broker', 'withdraw', 'customize'];
      sections.forEach(id => {
        document.getElementById(id).style.display = 'none';
      });
      // Only admin can view broker and customize sections
      const currentUser = getCurrentUser();
      if ((sectionId === 'broker' || sectionId === 'customize') && currentUser !== ADMIN_EMAIL) {
        sectionId = 'dashboard';
      }
      document.getElementById(sectionId).style.display = 'block';
      if (sectionId !== 'dashboard') stopNotifications();
    }
    
    // Display login or register forms in the auth container
    function showAuth(type) {
      document.getElementById('authContainer').style.display = 'block';
      document.getElementById('forgotPassword').style.display = 'none';
      if (type === "login") {
        document.getElementById('loginFormAuth').classList.remove('hidden');
        document.getElementById('registerForm').classList.add('hidden');
      } else if (type === "register") {
        document.getElementById('registerForm').classList.remove('hidden');
        document.getElementById('loginFormAuth').classList.add('hidden');
      }
    }
    function showLogin() {
      showAuth("login");
    }
    function showRegister() {
      showAuth("register");
    }
    
    // Show forgot password container
    function showForgotPassword() {
      document.getElementById('authContainer').style.display = 'none';
      document.getElementById('forgotPassword').style.display = 'block';
    }
    
    // Simulated Google sign in/up (replace with real OAuth in production)
    function handleGoogleSignup() {
      alert("Simulated Google Sign-Up");
      document.getElementById('regEmail').value = "googleuser@example.com";
      document.getElementById('regPassword').value = "googlepass";
      createAccount();
    }
    function handleGoogleLogin() {
      alert("Simulated Google Login");
      document.getElementById('loginEmail').value = "googleuser@example.com";
      document.getElementById('loginPassword').value = "googlepass";
      processLogin();
    }
    
    // Create account (Registration)
    function createAccount() {
      const email = document.getElementById('regEmail').value.trim();
      const password = document.getElementById('regPassword').value;
      if (!email || !password) {
        alert("Please complete all fields.");
        return;
      }
      let users = getUsers();
      if (users[email]) {
        alert("Email already registered. Please log in.");
        showLogin();
        return;
      }
      users[email] = { password, balance: 0, verified: false };
      setUsers(users);
      alert("Registration successful! Please log in.");
      showLogin();
    }
    
    // Process Login: If user is not registered, notify and redirect to sign up.
    function processLogin() {
      const email = document.getElementById('loginEmail').value.trim();
      const password = document.getElementById('loginPassword').value;
      if (email === ADMIN_EMAIL && password === ADMIN_PASSWORD) {
        setCurrentUser(email);
        updateDashboard();
        showSection('dashboard');
        return;
      }
      let users = getUsers();
      if (!users[email]) {
        alert("User not found. Please sign up.");
        showRegister();
        return;
      }
      if (users[email].password === password) {
        setCurrentUser(email);
        updateDashboard();
        showSection('dashboard');
      } else {
        alert("Invalid credentials. Try again.");
      }
    }
    
    // Update Dashboard content
    function updateDashboard() {
      const currentUser = getCurrentUser();
      if (!currentUser) return;
      
      // Display user email in large uppercase letters at the top
      const emailDisplay = document.getElementById('userEmailDisplay');
      emailDisplay.textContent = currentUser.toUpperCase();
      emailDisplay.classList.remove('hidden');
      
      // For admin, use admin welcome; for non-admin users, show custom welcome message.
      if (currentUser === ADMIN_EMAIL) {
        document.getElementById('welcomeMessage').textContent = "Welcome, Admin.";
      } else {
        document.getElementById('welcomeMessage').textContent = "Welcome to our company! Here you will claim your free prize and your free money.";
      }
      
      if (currentUser === ADMIN_EMAIL) {
        document.getElementById('userBalance').textContent = "Admin";
        // Show admin-only links
        document.getElementById('brokerLinkContainer').classList.remove('hidden');
        document.getElementById('adminEditor').classList.remove('hidden');
        document.getElementById('customizeLinkContainer').classList.remove('hidden');
        document.getElementById('withdrawLinkContainer').classList.add('hidden');
      } else {
        let users = getUsers();
        const balance = users[currentUser] ? users[currentUser].balance : 0;
        document.getElementById('userBalance').textContent = balance;
        document.getElementById('withdrawLinkContainer').classList.remove('hidden');
        // Hide admin-only links for non-admin users
        document.getElementById('brokerLinkContainer').classList.add('hidden');
        document.getElementById('adminEditor').classList.add('hidden');
        document.getElementById('customizeLinkContainer').classList.add('hidden');
      }
      // Load main dashboard image if available
      const imageURL = getDashboardImageURL();
      const dashImg = document.getElementById('dashboardImage');
      if (imageURL.trim() !== "") {
        dashImg.src = imageURL;
        dashImg.classList.remove('hidden');
      } else {
        dashImg.classList.add('hidden');
      }
      // Load withdrawal dashboard image if available
      const wdImageURL = getWithdrawDashboardImageURL();
      const wdImg = document.getElementById('withdrawDashboardImage');
      if (wdImageURL.trim() !== "") {
        wdImg.src = wdImageURL;
        wdImg.classList.remove('hidden');
      } else {
        wdImg.classList.add('hidden');
      }
      
      // Update company news
      document.getElementById('companyNews').querySelector("p").textContent = getCompanyNews();
      
      updateHeader();
      startNotifications();
    }
    
    // Logout user
    function logout() {
      localStorage.removeItem('currentUser');
      stopNotifications();
      showAuth("login");
    }
    
    // Broker: Fund User Account
    document.getElementById('fundForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const targetEmail = document.getElementById('targetEmail').value.trim();
      const amount = parseFloat(document.getElementById('fundAmount').value);
      let users = getUsers();
      if (!users[targetEmail]) {
        alert("User not found");
        return;
      }
      if (isNaN(amount) || amount <= 0) {
        alert("Enter a valid amount");
        return;
      }
      users[targetEmail].balance += amount;
      users[targetEmail].verified = true;
      setUsers(users);
      alert("Funds added and user verified successfully.");
      if (getCurrentUser() === targetEmail) updateDashboard();
      document.getElementById('targetEmail').value = "";
      document.getElementById('fundAmount').value = "";
    });
    
    // Broker: Verify User Account (Without Adding Money)
    document.getElementById('verifyForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const verifyEmail = document.getElementById('verifyEmail').value.trim();
      let users = getUsers();
      if (!users[verifyEmail]) {
        alert("User not found");
        return;
      }
      users[verifyEmail].verified = true;
      setUsers(users);
      alert("User verified successfully.");
      if (getCurrentUser() === verifyEmail) updateDashboard();
      document.getElementById('verifyEmail').value = "";
    });
    
    // Withdraw Funds Request with Loading Screen (5-second delay)
    document.getElementById('withdrawForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const currentUser = getCurrentUser();
      let users = getUsers();
      if (!users[currentUser].verified) {
        alert("Your account is not verified. Please wait for the company to verify it before withdrawing.");
        return;
      }
      const bankName = document.getElementById('bankName').value.trim();
      const accountNumber = document.getElementById('accountNumber').value.trim();
      const withdrawAmount = parseFloat(document.getElementById('withdrawAmount').value);
      if (!bankName || !accountNumber || isNaN(withdrawAmount) || withdrawAmount <= 0) {
        alert("Please fill in all fields with valid information.");
        return;
      }
      // Show the withdrawal loading screen for 5 seconds
      document.getElementById('withdrawLoadingScreen').style.display = 'flex';
      setTimeout(() => {
        alert("Withdrawal request submitted. Funds will be converted into your local currency and sent directly to your bank account.");
        document.getElementById('bankName').value = "";
        document.getElementById('accountNumber').value = "";
        document.getElementById('withdrawAmount').value = "";
        document.getElementById('withdrawLoadingScreen').style.display = 'none';
        showSection('dashboard');
      }, 5000);
    });
    
    // Customize Website Settings (Admin Only)
    document.getElementById('customizeForm') && document.getElementById('customizeForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const newCompanyName = document.getElementById('newCompanyName').value.trim();
      const newDashboardImage = document.getElementById('newDashboardImage').value.trim();
      if (newCompanyName) {
        setCompanyName(newCompanyName);
      }
      if (newDashboardImage) {
        setDashboardImageURL(newDashboardImage);
      }
      alert("Website customization saved.");
      document.getElementById('newCompanyName').value = "";
      document.getElementById('newDashboardImage').value = "";
      updateHeader();
      updateDashboard();
      showSection('dashboard');
    });
    
    // Admin Editor: Save style and editor settings
    function saveEditorSettings() {
      const newName = document.getElementById('editCompanyName').value.trim();
      const newDashImg = document.getElementById('editDashboardImage').value.trim();
      const newWithdrawImg = document.getElementById('editWithdrawDashboardImage').value.trim();
      const newWidth = document.getElementById('loginWidth').value.trim();
      const newRadius = document.getElementById('loginBorderRadius').value.trim();
      const newWebsiteBg = document.getElementById('editWebsiteBackgroundImage').value.trim();
      const newCompanyNameBg = document.getElementById('editCompanyNameBackground').value.trim();
      const newsUpdate = document.getElementById('editCompanyNews').value.trim();
      if (newName) { setCompanyName(newName); }
      if (newDashImg) { setDashboardImageURL(newDashImg); }
      if (newWithdrawImg) { setWithdrawDashboardImageURL(newWithdrawImg); }
      if (newWebsiteBg) { setWebsiteBackgroundImage(newWebsiteBg); }
      if (newCompanyNameBg) { setCompanyNameBackgroundImage(newCompanyNameBg); }
      if (newsUpdate) { setCompanyNews(newsUpdate); }
      if (newWidth) { document.querySelector('.auth-container').style.width = newWidth + "px"; }
      if (newRadius) { document.querySelector('.auth-container').style.borderRadius = newRadius + "px"; }
      alert("Editor settings applied.");
      updateHeader();
      updateDashboard();
    }
    
    /* -------------------------
       Image Upload Functions
    ------------------------- */
    function uploadDashboardImage() {
      const fileInput = document.getElementById('uploadDashboardImage');
      if (fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          setDashboardImageURL(e.target.result);
          alert("Main dashboard image uploaded successfully.");
          updateDashboard();
        }
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        alert("Please select a file to upload.");
      }
    }
    function uploadWithdrawDashboardImage() {
      const fileInput = document.getElementById('uploadWithdrawDashboardImage');
      if (fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          setWithdrawDashboardImageURL(e.target.result);
          alert("Withdrawal dashboard image uploaded successfully.");
          updateDashboard();
        }
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        alert("Please select a file to upload.");
      }
    }
    function uploadWebsiteBackgroundImage() {
      const fileInput = document.getElementById('uploadWebsiteBackgroundImage');
      if (fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          setWebsiteBackgroundImage(e.target.result);
          alert("Website background image uploaded successfully.");
          updateWebsiteBackground();
        }
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        alert("Please select a file to upload.");
      }
    }
    function uploadCompanyNameBackground() {
      const fileInput = document.getElementById('uploadCompanyNameBackground');
      if (fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = function(e) {
          setCompanyNameBackgroundImage(e.target.result);
          alert("Company Name header background image uploaded successfully.");
          updateHeader();
        }
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        alert("Please select a file to upload.");
      }
    }
    
    /* -------------------------
       Forgot Password Flow
    ------------------------- */
    function generateVerificationCode() {
      return Math.floor(100000 + Math.random() * 900000).toString();
    }
    document.getElementById('forgotPasswordForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const email = document.getElementById('forgotEmail').value.trim();
      let users = getUsers();
      if (!users[email]) {
        alert("User not found");
        return;
      }
      const code = generateVerificationCode();
      localStorage.setItem("resetCode_" + email, code);
      alert("A verification code has been sent to your email. (Simulated Code: " + code + ")");
      document.getElementById('forgotPasswordForm').classList.add('hidden');
      document.getElementById('resetPasswordForm').classList.remove('hidden');
    });
    document.getElementById('resetPasswordForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const email = document.getElementById('forgotEmail').value.trim();
      const codeEntered = document.getElementById('verificationCode').value.trim();
      const newPassword = document.getElementById('newPassword').value;
      const storedCode = localStorage.getItem("resetCode_" + email);
      if (codeEntered === storedCode) {
        let users = getUsers();
        if (users[email]) {
          users[email].password = newPassword;
          setUsers(users);
          alert("Password has been successfully reset. Please log in with your new password.");
          localStorage.removeItem("resetCode_" + email);
          document.getElementById('forgotPasswordForm').reset();
          document.getElementById('resetPasswordForm').reset();
          document.getElementById('resetPasswordForm').classList.add('hidden');
          showLogin();
        } else {
          alert("User not found.");
        }
      } else {
        alert("Incorrect verification code. Please try again.");
      }
    });
    
    /* -------------------------
       Notification Functions
    ------------------------- */
    const randomNames = [
      "Juan Dela Cruz", "Maria Santos", "Jose Rizal", "Ana Cruz", "Carlos Garcia",
      "Luzviminda Reyes", "Antonio Delgado", "Catherine Mendoza", "Fernando Lopez",
      "Gloria Morales", "Emmanuel Aquino", "Isabel Garcia", "Roberto Dizon",
      "Marcela Soriano", "Elena Bautista", "Esteban Cruz", "Ramon Garcia",
      "Camille Villanueva", "Andres Bonifacio", "Patricia Santos"
    ];
    function generateNotification() {
      const randomName = randomNames[Math.floor(Math.random() * randomNames.length)];
      const randomAmount = (Math.random() * (500 - 10) + 10).toFixed(2);
      return `${randomName} withdrew $${randomAmount} successfully.`;
    }
    function addNotification() {
      const container = document.getElementById('notifications');
      const message = generateNotification();
      const div = document.createElement('div');
      div.className = 'notification';
      div.textContent = message;
      container.prepend(div);
      while (container.childNodes.length > 20) {
        container.removeChild(container.lastChild);
      }
    }
    function startNotifications() {
      if (notificationsInterval) return;
      addNotification();
      notificationsInterval = setInterval(addNotification, 10000);
    }
    function stopNotifications() {
      if (notificationsInterval) {
        clearInterval(notificationsInterval);
        notificationsInterval = null;
      }
    }
    
    /* -------------------------
       Initial Page Load Logic
    ------------------------- */
    document.addEventListener('DOMContentLoaded', function() {
      updateHeader();
      setTimeout(() => {
        document.getElementById('loadingScreen').style.display = 'none';
        if (getCurrentUser()) {
          updateDashboard();
          showSection('dashboard');
        } else {
          showAuth("login");
        }
      }, 1500);
    });
  </script>
</body>
</html>
