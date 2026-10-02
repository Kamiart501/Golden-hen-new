OCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Golden Hen</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
  font-family:Arial,sans-serif;
}

body{
  background:radial-gradient(circle at top,#3b2b00,#171717 45%,#050505);
  color:#fff;
  min-height:100vh;
}

.hidden{display:none!important}
.gold{color:#ffd54a}
.center{text-align:center}

.card{
  background:rgba(30,30,30,.95);
  border:1px solid #5e4910;
  border-radius:18px;
  padding:18px;
  margin:14px 0;
  box-shadow:0 8px 25px rgba(0,0,0,.35);
}

h1,h2,h3{color:#ffd54a}

input{
  width:100%;
  padding:14px;
  margin:7px 0;
  border:1px solid transparent;
  border-radius:12px;
  background:#252525;
  color:#fff;
  outline:none;
}

input:focus{
  border-color:#ffd54a;
}

.btn{
  width:100%;
  border:none;
  border-radius:13px;
  padding:14px;
  margin-top:10px;
  background:linear-gradient(135deg,#ffd54a,#b88600);
  color:#111;
  font-weight:bold;
  font-size:15px;
  cursor:pointer;
}

.btn.secondary{
  background:#292929;
  color:#ffd54a;
  border:1px solid #6d5410;
}

.btn.whatsapp{
  background:#25D366;
  color:#fff;
}

.btn.logout{
  background:#8b2020;
  color:#fff;
}

.login-screen{
  min-height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  padding:20px;
}

.login-box{
  width:100%;
  max-width:430px;
  background:rgba(20,20,20,.97);
  border:1px solid #6b5110;
  border-radius:25px;
  padding:25px;
  box-shadow:0 15px 45px rgba(0,0,0,.55);
}

.logo{
  width:95px;
  height:95px;
  border-radius:50%;
  margin:0 auto 12px;
  display:flex;
  justify-content:center;
  align-items:center;
  font-size:52px;
  background:linear-gradient(145deg,#ffe16b,#b57d00);
  box-shadow:0 0 30px rgba(255,210,60,.35);
}

.login-title{
  text-align:center;
  font-size:30px;
  color:#ffd54a;
  font-weight:bold;
}

.subtitle{
  text-align:center;
  color:#aaa;
  margin:6px 0 20px;
}

.app{
  max-width:700px;
  margin:auto;
  padding-bottom:90px;
}

.topbar{
  position:sticky;
  top:0;
  z-index:10;
  padding:15px;
  background:rgba(10,10,10,.96);
  border-bottom:1px solid #4f3c0b;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.topbar-title{
  color:#ffd54a;
  font-weight:bold;
  font-size:19px;
}

.top-email{
  max-width:145px;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  color:#aaa;
  font-size:12px;
}

.page{padding:14px}

.balance-card{
  text-align:center;
  padding:25px;
  background:linear-gradient(145deg,rgba(94,70,8,.95),rgba(25,25,25,.95));
}

.balance{
  font-size:38px;
  font-weight:bold;
  color:#ffd54a;
  margin:10px 0;
}

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:10px;
}

.stat{
  background:#222;
  border:1px solid #4e3c0e;
  border-radius:14px;
  padding:15px 5px;
  text-align:center;
}

.stat-number{
  font-size:23px;
  color:#ffd54a;
  font-weight:bold;
  margin-top:5px;
}

.hen-card{
  text-align:center;
  background:linear-gradient(145deg,#3e3007,#171717);
}

.hen-icon{
  font-size:80px;
  margin:10px;
}

.price{
  font-size:28px;
  color:#ffd54a;
  font-weight:bold;
  margin:10px;
}

.info{
  color:#aaa;
  line-height:1.6;
  margin:7px 0;
}

.progress{
  height:12px;
  background:#333;
  border-radius:20px;
  overflow:hidden;
  margin:12px 0;
}

.progress-bar{
  height:100%;
  width:0%;
  background:linear-gradient(90deg,#ffd54a,#fff0a1);
}

.rate-row{
  display:flex;
  justify-content:space-between;
  padding:11px;
  border-bottom:1px solid #333;
}

.badge{
  display:inline-block;
  padding:5px 9px;
  border-radius:10px;
  font-size:11px;
  background:#4b3a08;
  color:#ffd54a;
}

.history-item{
  padding:12px;
  border-bottom:1px solid #333;
}

.empty{
  color:#888;
  text-align:center;
  padding:20px;
}

.small{
  font-size:12px;
  color:#888;
}

.nav{
  position:fixed;
  bottom:0;
  left:0;
  right:0;
  z-index:20;
  background:#111;
  border-top:1px solid #4e3c0e;
  display:flex;
  justify-content:space-around;
  padding:7px 2px;
}

.nav button{
  flex:1;
  border:none;
  background:transparent;
  color:#888;
  font-size:11px;
  padding:7px 2px;
}

.nav button.active{
  color:#ffd54a;
}

.nav-icon{
  display:block;
  font-size:20px;
  margin-bottom:2px;
}

.toast{
  position:fixed;
  left:50%;
  bottom:80px;
  transform:translateX(-50%);
  background:#222;
  border:1px solid #ffd54a;
  color:#fff;
  padding:12px 18px;
  border-radius:12px;
  z-index:100;
  display:none;
  max-width:90%;
  text-align:center;
}

@media(max-width:420px){
  .stats{gap:5px}
  .stat{padding:12px 3px}
  .stat-number{font-size:20px}
}
</style>
</head>

<body>

<!-- LOGIN -->

<div id="loginScreen" class="login-screen">

  <div class="login-box">

    <div class="logo">🐔</div>

    <div class="login-title">
      GOLDEN HEN
    </div>

    <div class="subtitle">
      Build your virtual farm
    </div>

    <input id="loginEmail" type="email" placeholder="Email">

    <input id="loginPassword" type="password" placeholder="Password">

    <button class="btn" onclick="login()">
      LOGIN
    </button>

    <button class="btn secondary" onclick="signup()">
      CREATE ACCOUNT
    </button>

    <p class="small center" style="margin-top:18px">
      Virtual rewards system
    </p>

  </div>

</div>


<!-- APP -->

<div id="app" class="app hidden">

  <div class="topbar">

    <div class="topbar-title">
      🐔 GOLDEN HEN
    </div>

    <div id="topEmail" class="top-email">
      Guest
    </div>

  </div>


  <!-- HOME -->

  <section id="homePage" class="page">

    <div class="card balance-card">

      <div>AVAILABLE BALANCE</div>

      <div id="balance" class="balance">
        Rs. 0
      </div>

      <div class="small">
        Golden Hen Wallet
      </div>

    </div>

    <div class="stats">

      <div class="stat">
        🐔
        <div>MY HENS</div>
        <div id="hens" class="stat-number">0</div>
      </div>

      <div class="stat">
        🥚
        <div>EGGS</div>
        <div id="eggs" class="stat-number">0</div>
      </div>

      <div class="stat">
        👥
        <div>REFERRALS</div>
        <div id="referrals" class="stat-number">0</div>
      </div>

    </div>

    <div class="card hen-card">

      <div class="badge">VIP HEN</div>

      <div class="hen-icon">🐔</div>

      <h2>Golden Hen Shop</h2>

      <div class="price">Rs. 600</div>

      <p class="info">
        One Golden Hen produces
        <b class="gold">1 virtual egg</b>
        every 24 hours.
      </p>

      <button class="btn" onclick="buyHen()">
        BUY GOLDEN HEN
      </button>

    </div>

    <div class="card">

      <h3>🥚 Egg Rates</h3>

      <div class="rate-row">
        <span>1 - 9 Eggs</span>
        <b class="gold">Rs. 35 / egg</b>
      </div>

      <div class="rate-row">
        <span>10 - 19 Eggs</span>
        <b class="gold">Rs. 40 / egg</b>
      </div>

      <div class="rate-row">
        <span>20 - 29 Eggs</span>
        <b class="gold">Rs. 45 / egg</b>
      </div>

      <div class="rate-row">
        <span>30+ Eggs</span>
        <b class="gold">Rs. 50 / egg</b>
      </div>

    </div>

  </section>


  <!-- HENS -->

  <section id="hensPage" class="page hidden">

    <div class="card center">

      <h2>🐔 My Golden Hens</h2>

      <div class="hen-icon">🐔</div>

      <h3>
        Hens: <span id="henCount2">0</span>
      </h3>

      <div class="progress">
        <div id="progressBar" class="progress-bar"></div>
      </div>

      <p id="eggTimer" class="info">
        No active hens
      </p>

      <button class="btn" onclick="collectEggs()">
        COLLECT EGGS
      </button>

    </div>

  </section>


  <!-- EGGS -->

  <section id="eggsPage" class="page hidden">

    <div class="card center">

      <h2>🥚 My Eggs</h2>

      <div style="font-size:60px;margin:15px">
        🥚
      </div>

      <h1 id="eggInventory">0</h1>

      <p class="info">Current Egg Value</p>

      <h2 id="eggValue">Rs. 0</h2>

      <button class="btn" onclick="sellAllEggs()">
        SELL ALL EGGS
      </button>

    </div>

  </section>


  <!-- SELL -->

  <section id="sellPage" class="page hidden">

    <div class="card">

      <h2>💰 Sell Eggs</h2>

      <p class="info">
        Select how many eggs you want to sell.
      </p>

      <input
        id="sellEggAmount"
        type="number"
        min="1"
        placeholder="Number of eggs"
      >

      <button class="btn" onclick="sellEggs()">
        SELL EGGS
      </button>

    </div>

    <div class="card">

      <h3>Current Rates</h3>

      <div class="rate-row">
        <span>1 - 9</span>
        <b class="gold">Rs.35</b>
      </div>

      <div class="rate-row">
        <span>10 - 19</span>
        <b class="gold">Rs.40</b>
      </div>

      <div class="rate-row">
        <span>20 - 29</span>
        <b class="gold">Rs.45</b>
      </div>

      <div class="rate-row">
        <span>30+</span>
        <b class="gold">Rs.50</b>
      </div>

    </div>

  </section>


  <!-- WALLET -->

  <section id="walletPage" class="page hidden">

    <div class="card balance-card">

      <div>WALLET BALANCE</div>

      <div id="walletBalance" class="balance">
        Rs. 0
      </div>

    </div>


    <div class="card">

      <h2>💳 Deposit Money</h2>

      <p class="info">
        Payment karne ke baad amount aur
        transaction details submit karein.
        Admin verification ke baad balance add hoga.
      </p>

      <div class="card">

        <h3>Payment Method</h3>

        <p class="info">

          <b class="gold">
            JazzCash / EasyPaisa
          </b>

          <br><br>

          Account Name:
          <br>

          <b class="gold">
            MUHAMMAD KAMRAN ALTAF
          </b>

          <br><br>

          Payment Number:
          <br>

          <b id="paymentNumber" class="gold">
            03482179022
          </b>

          <br><br>

          Payment karne ke baad
          Transaction ID neeche enter karein.

        </p>

      </div>

      <input
        id="depositAmount"
        type="number"
        min="100"
        placeholder="Deposit Amount (Minimum Rs.100)"
      >

      <input
        id="depositTransaction"
        type="text"
        placeholder="Transaction ID"
      >

      <input
        id="depositNumber"
        type="text"
        placeholder="Your JazzCash / EasyPaisa Number"
      >

      <button class="btn" onclick="submitDeposit()">
        SUBMIT DEPOSIT REQUEST
      </button>

    </div>


    <div class="card">

      <h2>💸 Withdraw</h2>

      <p class="info">
        Withdrawal request submit karein.
        Admin verification/payment ke baad request complete hogi.
      </p>

      <input
        id="withdrawAmount"
        type="number"
        min="100"
        placeholder="Withdrawal Amount"
      >

      <input
        id="withdrawNumber"
        type="text"
        placeholder="Your JazzCash / EasyPaisa Number"
      >

      <button class="btn" onclick="requestWithdraw()">
        REQUEST WITHDRAWAL
      </button>

    </div>


    <div class="card">

      <h2>📋 Deposit History</h2>

      <div id="depositHistory">
        <div class="empty">
          No deposit requests yet.
        </div>
      </div>

    </div>

  </section>


  <!-- REFERRAL -->

  <section id="referralPage" class="page hidden">

    <div class="card center">

      <h2>👥 Referral System</h2>

      <div style="font-size:60px;margin:15px">
        👥
      </div>

      <h1 id="referralCount">0</h1>

      <p class="info">
        Referral system is ready for future backend integration.
      </p>

    </div>

  </section>


  <!-- PROFILE -->

  <section id="profilePage" class="page hidden">

    <div class="card center">

      <div style="font-size:70px">
        👤
      </div>

      <h2>Golden Hen Member</h2>

      <p id="profileEmail" class="info">
        Guest
      </p>

    </div>


    <div class="card">

      <h3>Account</h3>

      <p class="info">
        Email:
        <b id="profileEmail2">Guest</b>
      </p>

      <p class="info">
        Total Earned:
        <b id="profileTotal" class="gold">
          Rs. 0
        </b>
      </p>

    </div>


    <!-- WHATSAPP CHANNEL -->

    <div class="card center">

      <h3>📢 Golden Hen Updates</h3>

      <p class="info">
        Latest updates aur announcements ke liye
        hamara WhatsApp Channel join karein.
      </p>

      <button
        class="btn whatsapp"
        onclick="joinWhatsApp()"
      >
        📢 JOIN WHATSAPP CHANNEL
      </button>

    </div>


    <button class="btn" onclick="openDepositFromProfile()">
      💳 ADD MONEY
    </button>

    <button class="btn secondary" onclick="showSettings()">
      ⚙️ SETTINGS
    </button>

    <button class="btn logout" onclick="logout()">
      LOGOUT
    </button>

  </section>


  <!-- SETTINGS -->

  <section id="settingsPage" class="page hidden">

    <div class="card">

      <h2>⚙️ Settings</h2>

      <p class="info">
        Account Information
      </p>

      <p class="info">
        Email:
        <b id="settingsEmail">Guest</b>
      </p>

    </div>


    <div class="card">

      <h3>🔐 Change Password</h3>

      <input
        id="newPassword"
        type="password"
        placeholder="New Password"
      >

      <button class="btn" onclick="changePassword()">
        CHANGE PASSWORD
      </button>

    </div>


    <button
      class="btn secondary"
      onclick="showPage('profilePage')"
    >
      ← BACK TO PROFILE
    </button>

  </section>


  <!-- BOTTOM NAV -->

  <div class="nav">

    <button id="navHome" onclick="showPage('homePage')">
      <span class="nav-icon">🏠</span>
      Home
    </button>

    <button id="navHens" onclick="showPage('hensPage')">
      <span class="nav-icon">🐔</span>
      Hens
    </button>

    <button id="navEggs" onclick="showPage('eggsPage')">
      <span class="nav-icon">🥚</span>
      Eggs
    </button>

    <button id="navSell" onclick="showPage('sellPage')">
      <span class="nav-icon">💰</span>
      Sell
    </button>

    <button id="navWallet" onclick="showPage('walletPage')">
      <span class="nav-icon">💳</span>
      Wallet
    </button>

    <button id="navProfile" onclick="showPage('profilePage')">
      <span class="nav-icon">👤</span>
      Profile
    </button>

  </div>

</div>


<div id="toast" class="toast"></div>


<!-- FIREBASE -->

<script type="module">

import {
  initializeApp
} from "https://www.gstatic.com/firebasejs/12.1.0/firebase-app.js";

import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword,
  onAuthStateChanged,
  signOut,
  updatePassword
} from "https://www.gstatic.com/firebasejs/12.1.0/firebase-auth.js";

import {
  getFirestore,
  doc,
  getDoc,
  setDoc,
  collection,
  addDoc,
  query,
  where,
  getDocs,
  serverTimestamp
} from "https://www.gstatic.com/firebasejs/12.1.0/firebase-firestore.js";


/* FIREBASE CONFIG */

const firebaseConfig = {
  apiKey:"AIzaSyD-uhTjZklnHdeOXMyR_gRiAWXyqIwAuFk",
  authDomain:"earn-app-8f00d.firebaseapp.com",
  projectId:"earn-app-8f00d",
  storageBucket:"earn-app-8f00d.firebasestorage.app",
  messagingSenderId:"864949482951",
  appId:"1:864949482951:web:1ce6dd7fe2b911ecea55e2",
  measurementId:"G-MBV2HQ0H49"
};

const app = initializeApp(firebaseConfig);

const auth = getAuth(app);

const db = getFirestore(app);


/* PAYMENT DETAILS */

const ADMIN_PAYMENT_NUMBER =
  "03482179022";

const ADMIN_PAYMENT_NAME =
  "MUHAMMAD KAMRAN ALTAF";


/* WHATSAPP CHANNEL */

const WHATSAPP_CHANNEL =
  "https://whatsapp.com/channel/0029VbDVUFYAzNboHlLiHK31";


let currentUser = null;

let data = {
  email:"",
  balance:0,
  hens:0,
  eggs:0,
  referrals:0,
  totalEarned:0,
  lastEggTime:0
};


/* TOAST */

function toast(message){

  const box =
    document.getElementById("toast");

  box.innerText = message;

  box.style.display = "block";

  setTimeout(()=>{
    box.style.display = "none";
  },3000);
}


/* MONEY */

function money(value){

  return "Rs. " +
    Number(value || 0).toLocaleString();

}


/* LOAD USER */

async function loadUserData(){

  if(!currentUser)return;

  const ref =
    doc(db,"user",currentUser.uid);

  const snap =
    await getDoc(ref);

  if(snap.exists()){

    const d = snap.data();

    data = {

      email:d.Email || currentUser.email || "",

      balance:Number(d.Coin || 0),

      hens:Number(d.Hens || 0),

      eggs:Number(d.Eggs || 0),

      referrals:Number(d.Referrals || 0),

      totalEarned:
        Number(d["Total earning"] || 0),

      lastEggTime:
        Number(d.LastEggTime || 0)

    };

  }else{

    data = {

      email:currentUser.email || "",
      balance:0,
      hens:0,
      eggs:0,
      referrals:0,
      totalEarned:0,
      lastEggTime:0

    };

    await setDoc(
      ref,
      {
        Email:currentUser.email || "",
        Name:"",
        Coin:0,
        Hens:0,
        Eggs:0,
        Referrals:0,
        "Total earning":0,
        LastEggTime:0,
        CreatedAt:serverTimestamp()
      }
    );

  }

  updateUI();

}


/* SAVE USER */

async function saveUserData(){

  if(!currentUser)return;

  await setDoc(
    doc(db,"user",currentUser.uid),
    {
      Email:data.email,
      Coin:Number(data.balance),
      Hens:Number(data.hens),
      Eggs:Number(data.eggs),
      Referrals:Number(data.referrals),
      "Total earning":
        Number(data.totalEarned),
      LastEggTime:
        Number(data.lastEggTime)
    },
    {merge:true}
  );

  updateUI();

}


/* UPDATE UI */

function updateUI(){

  document.getElementById("balance").innerText =
    money(data.balance);

  document.getElementById("walletBalance").innerText =
    money(data.balance);

  document.getElementById("hens").innerText =
    data.hens;

  document.getElementById("henCount2").innerText =
    data.hens;

  document.getElementById("eggs").innerText =
    data.eggs;

  document.getElementById("eggInventory").innerText =
    data.eggs;

  document.getElementById("referrals").innerText =
    data.referrals;

  document.getElementById("referralCount").innerText =
    data.referrals;

  document.getElementById("profileEmail").innerText =
    data.email || "Guest";

  document.getElementById("profileEmail2").innerText =
    data.email || "Guest";

  document.getElementById("settingsEmail").innerText =
    data.email || "Guest";

  document.getElementById("topEmail").innerText =
    data.email || "Guest";


  document.getElementById("profileTotal").innerText =
    money(data.totalEarned);


  let value = 0;

  if(data.eggs >= 30)
    value = data.eggs * 50;

  else if(data.eggs >= 20)
    value = data.eggs * 45;

  else if(data.eggs >= 10)
    value = data.eggs * 40;

  else
    value = data.eggs * 35;


  document.getElementById("eggValue").innerText =
    money(value);

}


/* LOGIN */

async function login(){

  const email =
    document.getElementById("loginEmail").value.trim();

  const password =
    document.getElementById("loginPassword").value;

  if(!email || !password){

    toast("Email aur password enter karein.");

    return;
  }

  try{

    await signInWithEmailAndPassword(
      auth,
      email,
      password
    );

    toast("Login successful.");

  }catch(error){

    toast(
      error.message.replace("Firebase:","")
    );

  }

}


/* SIGNUP */

async function signup(){

  const email =
    document.getElementById("loginEmail").value.trim();

  const password =
    document.getElementById("loginPassword").value;

  if(!email || !password){

    toast("Email aur password enter karein.");

    return;
  }

  if(password.length < 6){

    toast("Password minimum 6 characters ka hona chahiye.");

    return;
  }

  try{

    const result =
      await createUserWithEmailAndPassword(
        auth,
        email,
        password
      );

    await setDoc(
      doc(db,"user",result.user.uid),
      {
        Email:email,
        Name:"",
        Coin:0,
        Hens:0,
        Eggs:0,
        Referrals:0,
        "Total earning":0,
        LastEggTime:0,
        CreatedAt:serverTimestamp()
      }
    );

    toast("Account created successfully.");

  }catch(error){

    toast(
      error.message.replace("Firebase:","")
    );

  }

}


/* AUTH */

onAuthStateChanged(
  auth,
  async user => {

    if(user){

      currentUser = user;

      document.getElementById(
        "loginScreen"
      ).classList.add("hidden");

      document.getElementById(
        "app"
      ).classList.remove("hidden");

      await loadUserData();

      showPage("homePage");

      startTimer();

    }else{

      currentUser = null;

      document.getElementById(
        "loginScreen"
      ).classList.remove("hidden");

      document.getElementById(
        "app"
      ).classList.add("hidden");

    }

  }
);


/* BUY HEN */

async function buyHen(){

  const price = 600;

  if(!currentUser){

    toast("Please login first.");

    return;
  }

  if(data.balance < price){

    toast(
      "Golden Hen buy karne ke liye Rs.600 balance required hai."
    );

    return;
  }

  data.balance -= price;

  data.hens += 1;

  if(data.lastEggTime === 0){

    data.lastEggTime = Date.now();

  }

  await saveUserData();

  toast("Golden Hen purchased successfully.");

}


/* COLLECT EGGS */

async function collectEggs(){

  if(data.hens <= 0){

    toast("Pehle Golden Hen buy karein.");

    return;
  }

  if(!data.lastEggTime){

    data.lastEggTime = Date.now();

    await saveUserData();

    toast("Egg production started.");

    return;
  }

  const day =
    24 * 60 * 60 * 1000;

  const cycles =
    Math.floor(
      (Date.now()-data.lastEggTime)/day
    );

  if(cycles < 1){

    toast("Abhi eggs ready nahi hain.");

    return;
  }

  const produced =
    cycles * data.hens;

  data.eggs += produced;

  data.lastEggTime +=
    cycles * day;

  await saveUserData();

  toast(
    produced + " egg(s) collected."
  );

}


/* TIMER */

function startTimer(){

  setInterval(updateTimer,1000);

  updateTimer();

}


function updateTimer(){

  if(!data.hens){

    document.getElementById("eggTimer").innerText =
      "No active hens";

    document.getElementById("progressBar").style.width =
      "0%";

    return;
  }

  if(!data.lastEggTime){

    document.getElementById("eggTimer").innerText =
      "Production starting...";

    return;
  }

  const day =
    24*60*60*1000;

  const passed =
    Date.now()-data.lastEggTime;

  const remaining =
    Math.max(
      0,
      day-(passed%day)
    );

  const hours =
    Math.floor(
      remaining/(60*60*1000)
    );

  const minutes =
    Math.floor(
      (remaining%(60*60*1000))/(60*1000)
    );

  const seconds =
    Math.floor(
      (remaining%(60*1000))/1000
    );

  document.getElementById("eggTimer").innerText =
    "Next eggs in "+
    hours+"h "+
    minutes+"m "+
    seconds+"s";

  document.getElementById("progressBar").style.width =
    ((passed%day)/day*100)+"%";

}


/* EGG VALUE */

function calculateEggValue(eggs){

  if(eggs>=30)return eggs*50;

  if(eggs>=20)return eggs*45;

  if(eggs>=10)return eggs*40;

  return eggs*35;

}


/* SELL ALL */

async function sellAllEggs(){

  if(data.eggs<=0){

    toast("Aapke paas eggs nahi hain.");

    return;
  }

  const amount =
    calculateEggValue(data.eggs);

  data.balance += amount;

  data.totalEarned += amount;

  data.eggs = 0;

  await saveUserData();

  toast(
    "Eggs sold for "+money(amount)
  );

}


/* SELL */

async function sellEggs(){

  const amount =
    Number(
      document.getElementById(
        "sellEggAmount"
      ).value
    );

  if(!amount || amount<=0){

    toast("Egg quantity enter karein.");

    return;
  }

  if(amount>data.eggs){

    toast("Aapke paas itne eggs nahi hain.");

    return;
  }

  const value =
    calculateEggValue(amount);

  data.eggs -= amount;

  data.balance += value;

  data.totalEarned += value;

  await saveUserData();

  document.getElementById(
    "sellEggAmount"
  ).value="";

  toast(
    amount+
    " eggs sold for "+
    money(value)
  );

}


/* DEPOSIT */

async function submitDeposit(){

  if(!currentUser){

    toast("Please login first.");

    return;
  }

  const amount =
    Number(
      document.getElementById(
        "depositAmount"
      ).value
    );

  const transaction =
    document.getElementById(
      "depositTransaction"
    ).value.trim();

  const number =
    document.getElementById(
      "depositNumber"
    ).value.trim();


  if(amount<100){

    toast("Minimum deposit Rs.100 hai.");

    return;
  }

  if(!transaction){

    toast("Transaction ID enter karein.");

    return;
  }

  if(!number){

    toast("Apna payment number enter karein.");

    return;
  }


  try{

    await addDoc(
      collection(db,"depositRequests"),
      {
        uid:currentUser.uid,
        Email:currentUser.email,
        Amount:amount,
        TransactionID:transaction,
        Num:number,
        Method:"JazzCash / EasyPaisa",
        PaymentAccountName:
          ADMIN_PAYMENT_NAME,
        PaymentAccountNumber:
          ADMIN_PAYMENT_NUMBER,
        Status:"Pending",
        CreatedAt:serverTimestamp()
      }
    );


    document.getElementById(
      "depositAmount"
    ).value="";

    document.getElementById(
      "depositTransaction"
    ).value="";

    document.getElementById(
      "depositNumber"
    ).value="";


    toast(
      "Deposit request submitted. Admin verification ke baad balance add hoga."
    );

    loadDepositHistory();

  }catch(error){

    toast(
      "Deposit error: "+error.message
    );

  }

}


/* DEPOSIT HISTORY */

async function loadDepositHistory(){

  if(!currentUser)return;

  const box =
    document.getElementById(
      "depositHistory"
    );

  try{

    const q =
      query(
        collection(db,"depositRequests"),
        where("uid","==",currentUser.uid)
      );

    const snap =
      await getDocs(q);

    if(snap.empty){

      box.innerHTML =
        '<div class="empty">No deposit requests yet.</div>';

      return;
    }

    let html="";

    snap.forEach(item=>{

      const d=item.data();

      html+=`

        <div class="history-item">

          <b class="gold">
            ${money(d.Amount)}
          </b>

          <br>

          Transaction:
          ${d.TransactionID || "-"}

          <br>

          Status:
          <span class="badge">
            ${d.Status || "Pending"}
          </span>

        </div>

      `;

    });

    box.innerHTML=html;

  }catch(error){

    box.innerHTML =
      '<div class="empty">History load nahi ho saki.</div>';

  }

}


/* WITHDRAW */

async function requestWithdraw(){

  if(!currentUser){

    toast("Please login first.");

    return;
  }

  const amount =
    Number(
      document.getElementById(
        "withdrawAmount"
      ).value
    );

  const number =
    document.getElementById(
      "withdrawNumber"
    ).value.trim();


  if(amount<100){

    toast("Minimum withdrawal Rs.100 hai.");

    return;
  }

  if(amount>data.balance){

    toast("Insufficient balance.");

    return;
  }

  if(!number){

    toast("Payment number enter karein.");

    return;
  }


  try{

    await addDoc(
      collection(db,"withdrawalRequests"),
      {
        uid:currentUser.uid,
        Email:currentUser.email,
        Amount:amount,
        Num:number,
        Method:"JazzCash / EasyPaisa",
        Status:"Pending",
        CreatedAt:serverTimestamp()
      }
    );


    document.getElementById(
      "withdrawAmount"
    ).value="";

    document.getElementById(
      "withdrawNumber"
    ).value="";


    toast(
      "Withdrawal request submitted."
    );

  }catch(error){

    toast(
      "Withdrawal error: "+error.message
    );

  }

}


/* WHATSAPP */

window.joinWhatsApp=function(){

  window.open(
    WHATSAPP_CHANNEL,
    "_blank"
  );

};


/* PAGE */

window.showPage=function(pageId){

  const pages=[
    "homePage",
    "hensPage",
    "eggsPage",
    "sellPage",
    "walletPage",
    "referralPage",
    "profilePage",
    "settingsPage"
  ];

  pages.forEach(id=>{
    document.getElementById(id)
      .classList.add("hidden");
  });

  document.getElementById(pageId)
    .classList.remove("hidden");


  const navs=[
    "navHome",
    "navHens",
    "navEggs",
    "navSell",
    "navWallet",
    "navProfile"
  ];

  navs.forEach(id=>{
    document.getElementById(id)
      .classList.remove("active");
  });


  const map={
    homePage:"navHome",
    hensPage:"navHens",
    eggsPage:"navEggs",
    sellPage:"navSell",
    walletPage:"navWallet",
    profilePage:"navProfile"
  };


  if(map[pageId]){

    document.getElementById(
      map[pageId]
    ).classList.add("active");

  }


  if(pageId==="walletPage"){

    loadDepositHistory();

  }

};


/* PROFILE → DEPOSIT */

window.openDepositFromProfile=function(){

  showPage("walletPage");

  setTimeout(()=>{
    window.scrollTo({
      top:0,
      behavior:"smooth"
    });
  },100);

};


/* SETTINGS */

window.showSettings=function(){

  showPage("settingsPage");

};


/* CHANGE PASSWORD */

window.changePassword=async function(){

  if(!currentUser){

    toast("Please login first.");

    return;
  }

  const password =
    document.getElementById(
      "newPassword"
    ).value;

  if(password.length<6){

    toast(
      "Password minimum 6 characters ka hona chahiye."
    );

    return;
  }

  try{

    await updatePassword(
      currentUser,
      password
    );

    document.getElementById(
      "newPassword"
    ).value="";

    toast(
      "Password changed successfully."
    );

  }catch(error){

    toast(
      "Password change failed. Dobara login karke try karein."
    );

  }

};


/* LOGOUT */

window.logout=async function(){

  try{

    await signOut(auth);

  }catch(error){

    toast(error.message);

  }

};


/* GLOBAL FUNCTIONS */

window.login=login;
window.signup=signup;
window.buyHen=buyHen;
window.collectEggs=collectEggs;
window.sellAllEggs=sellAllEggs;
window.sellEggs=sellEggs;
window.submitDeposit=submitDeposit;
window.requestWithdraw=requestWithdraw;
window.loadDepositHistory=loadDepositHistory;

</script>

</body>
</html>
