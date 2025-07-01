# juju-shop-website
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>JuJu Shop - ระบบเติม Robux</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { font-family: sans-serif; background: #f5f5f5; margin: 0; display: flex; justify-content: center; align-items: center; min-height: 100vh; }
    .container { max-width: 500px; margin: 30px auto; padding: 20px; background: #fff; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); width: 100%; box-sizing: border-box; }
    input, select { width: calc(100% - 22px); padding: 10px; margin: 10px 0; border: 1px solid #ccc; border-radius: 5px; box-sizing: border-box; }
    button { width: 100%; padding: 12px; background: #5a189a; color: white; border: none; border-radius: 5px; cursor: pointer; margin-top: 5px; }
    button:hover { background-color: #45137a; }
    h2 { text-align: center; }
    img { max-width: 100px; margin-top: 10px; display: block; }
    ul { padding-left: 20px; }
    table { width: 100%; border-collapse: collapse; margin-top: 15px; }
    th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
    th { background-color: #f2f2f2; }
    .admin-button { background-color: #17a2b8; /* สีฟ้าสำหรับแอดมิน */ }
    .admin-button:hover { background-color: #138496; }
  </style>
</head>
<body>

  <div class="container" id="registerPage">
    <h2>สมัครสมาชิก</h2>
    <input type="text" id="newUsername" placeholder="ชื่อผู้ใช้" />
    <input type="password" id="newPassword" placeholder="รหัสผ่าน" />
    <button onclick="registerUser()">สมัครสมาชิก</button>
    <button type="button" onclick="showVerifyPage()" style="background-color: #007bff; margin-top: 10px;">ลงชื่อเข้าใช้</button>
  </div>

  <div class="container" id="verifyPage" style="display:none;">
    <h2>ลงชื่อเข้าใช้</h2>
    <input type="text" id="loginUsername" placeholder="ชื่อผู้ใช้" />
    <input type="password" id="loginPassword" placeholder="รหัสผ่านที่คุณตั้งไว้" />
    <button onclick="verifyLogin()">เข้าสู่ระบบ</button>
    <button type="button" onclick="adminLogin()" class="admin-button" style="margin-top: 10px;">เข้าสู่ระบบแอดมิน</button>
  </div>

  <div class="container" id="mainPage" style="display:none;">
    <h2>เติม <strong>Robux</strong></h2>
    <input type="text" id="gameName" placeholder="ชื่อเกม" />
    <input type="password" id="gameCode" placeholder="รหัสเข้าเกม" />
    <select id="amount">
      <option value="80">80 Robux – 35 บาท</option>
      <option value="160">160 Robux – 64 บาท</option>
      <option value="240">240 Robux – 95 บาท</option>
      <option value="320">320 Robux – 126 บาท</option>
    </select>
    <p><strong>ใส่รูปสลิปเพื่อดำเนินการเติมเกม</strong></p>
    <input type="file" id="slip" accept="image/*" />
    <button onclick="submitOrder()">ส่งสลิปและเติมเกม</button>
    <button onclick="showPage('historyPage')" style="background-color: #6c757d;">ดูประวัติการเติม</button>
  </div>

  <div class="container" id="historyPage" style="display:none;">
    <h2>ประวัติการเติมของคุณ</h2>
    <ul id="orderHistory"></ul>
    <button onclick="showPage('mainPage')">กลับไปหน้าเติม Robux</button>
  </div>

  <div class="container" id="adminPage" style="display:none;">
    <h2>ระบบหลังบ้าน</h2>
    <table width="100%" border="1" cellpadding="5" cellspacing="0">
      <thead>
        <tr><th>ชื่อผู้ใช้</th><th>ชื่อเกม</th><th>จำนวน Robux</th><th>ราคา</th><th>สลิป</th></tr>
      </thead>
      <tbody id="adminOrders"></tbody>
    </table>
    <button onclick="showPage('mainPage')" style="background-color: #6c757d;">กลับไปหน้าเติม Robux</button>
  </div>

<script>
  let currentUser = ""; // เก็บชื่อผู้ใช้ที่เข้าสู่ระบบปัจจุบัน
  const adminUser = "Admin_jayjay";
  const adminPass = "JuJu_shop";

  // เมื่อโหลดหน้าเว็บครั้งแรก
  document.addEventListener('DOMContentLoaded', function() {
    const users = JSON.parse(localStorage.getItem("users") || "{}");
    // หากมีผู้ใช้อยู่แล้ว ให้ไปหน้า verifyPage ทันที
    if (Object.keys(users).length > 0) {
      showPage('verifyPage');
      // กำหนดค่า username ในหน้า verifyPage หากมีผู้ใช้ที่เคยลงทะเบียน
      document.getElementById("loginUsername").value = Object.keys(users)[0]; // ดึงชื่อผู้ใช้คนแรกมาแสดง
      currentUser = Object.keys(users)[0]; // กำหนด currentUser เป็นผู้ใช้คนแรก
    } else {
      showPage('registerPage');
    }
  });

  // ฟังก์ชันสำหรับปุ่ม "ลงชื่อเข้าใช้" ในหน้าสมัครสมาชิก
  function showVerifyPage() {
    document.getElementById("registerPage").style.display = "none";
    document.getElementById("verifyPage").style.display = "block";
    const users = JSON.parse(localStorage.getItem("users") || "{}");
    if (Object.keys(users).length > 0) {
      document.getElementById("loginUsername").value = Object.keys(users)[0]; // ดึงชื่อผู้ใช้คนแรกมาแสดง
      currentUser = Object.keys(users)[0];
    }
  }

  function registerUser() {
    const u = document.getElementById("newUsername").value;
    const p = document.getElementById("newPassword").value;
    if (!u || !p) return alert("กรุณากรอกข้อมูลให้ครบ");
    let users = JSON.parse(localStorage.getItem("users") || "{}");
    if (users[u]) return alert("มีผู้ใช้นี้อยู่แล้ว");
    users[u] = p;
    localStorage.setItem("users", JSON.stringify(users));
    currentUser = u; // ตั้งค่าผู้ใช้ปัจจุบันทันทีที่ลงทะเบียน
    document.getElementById("loginUsername").value = u; // ใส่ชื่อผู้ใช้ในช่อง login
    alert("สมัครสมาชิกสำเร็จ! กรุณาเข้าสู่ระบบ");
    showVerifyPage(); // ไปหน้าลงชื่อเข้าใช้
  }

  function verifyLogin() {
    const u = document.getElementById("loginUsername").value; // ดึงชื่อผู้ใช้จากช่อง login
    const p = document.getElementById("loginPassword").value;
    let users = JSON.parse(localStorage.getItem("users") || "{}");

    if (!u || !p) {
        alert("กรุณากรอกชื่อผู้ใช้และรหัสผ่าน");
        return;
    }

    if (users[u] && users[u] === p) {
      currentUser = u; // ตั้งค่าผู้ใช้ปัจจุบันเมื่อเข้าสู่ระบบสำเร็จ
      alert("เข้าสู่ระบบสำเร็จ");
      showPage("mainPage");
    } else {
      alert("ชื่อผู้ใช้หรือรหัสผ่านไม่ถูกต้อง");
    }
  }

  function submitOrder() {
    const name = document.getElementById("gameName").value;
    const code = document.getElementById("gameCode").value;
    const robux = document.getElementById("amount").value;
    const slipFile = document.getElementById("slip").files[0];
    if (!name || !code || !slipFile) return alert("กรอกให้ครบทุกช่อง");

    const reader = new FileReader();
    reader.onload = function(e) {
      const orders = JSON.parse(localStorage.getItem("orders") || "[]");
      // เพิ่ม currentUser เข้าไปในข้อมูลการสั่งซื้อ
      orders.push({ username: currentUser, name, robux, price: getPrice(robux), slip: e.target.result });
      localStorage.setItem("orders", JSON.stringify(orders));
      alert("ส่งคำสั่งซื้อสำเร็จ");
      loadOrderHistory(); // โหลดประวัติการสั่งซื้อสำหรับผู้ใช้ปัจจุบัน
      showPage("historyPage");
    };
    reader.readAsDataURL(slipFile);
  }

  function getPrice(robux) {
    return { "80": 35, "160": 64, "240": 95, "320": 126 }[robux] || 0;
  }

  function loadOrderHistory() {
    const orders = JSON.parse(localStorage.getItem("orders") || "[]");
    // กรองประวัติการสั่งซื้อตาม currentUser
    const history = orders.filter(o => o.username === currentUser);
    const list = document.getElementById("orderHistory");
    list.innerHTML = "";
    if (history.length === 0) {
        list.innerHTML = "<li>ไม่มีประวัติการเติม</li>";
        return;
    }
    history.forEach(o => {
      const li = document.createElement("li");
      li.innerHTML = `<strong>ชื่อเกม:</strong> ${o.name}, <strong>Robux:</strong> ${o.robux} – ${o.price} บาท<br><img src="${o.slip}" style="max-width: 150px; margin-top: 5px;" />`;
      list.appendChild(li);
    });
  }

  function adminLogin() {
    const u = document.getElementById("loginUsername").value; // ดึงชื่อผู้ใช้จากช่อง input
    const p = document.getElementById("loginPassword").value; // ดึงรหัสผ่านจากช่อง input

    // ตรวจสอบว่าเป็น Admin_jayjay และ JuJu_shop หรือไม่
    if (u === adminUser && p === adminPass) {
      currentUser = adminUser; // ตั้งค่าผู้ใช้ปัจจุบันเป็นแอดมิน
      alert("เข้าสู่ระบบแอดมินสำเร็จ");
      showPage("adminPage");
      loadAdminOrders();
    } else {
      alert("ชื่อผู้ใช้หรือรหัสผ่านแอดมินไม่ถูกต้อง");
    }
  }

  function loadAdminOrders() {
    const orders = JSON.parse(localStorage.getItem("orders") || "[]");
    const table = document.getElementById("adminOrders");
    table.innerHTML = ""; // Clear existing rows
    orders.forEach(o => {
      const row = document.createElement("tr");
      // เพิ่มชื่อผู้ใช้ในตารางแอดมิน
      row.innerHTML = `<td>${o.username || 'N/A'}</td><td>${o.name}</td><td>${o.robux}</td><td>${o.price}</td><td><img src="${o.slip}" style="max-width: 100px;" /></td>`;
      table.appendChild(row);
    });
  }

  function showPage(id) {
    ["registerPage","verifyPage","mainPage","historyPage","adminPage"].forEach(p => {
      document.getElementById(p).style.display = "none";
    });
    document.getElementById(id).style.display = "block";
  }
</script>

</body>
</html>
