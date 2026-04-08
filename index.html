<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>WorkTime Pro - Cloud Secure</title>
    <link href="https://fonts.googleapis.com/css2?family=Assistant:wght@400;600;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #6C5CE7;
            --bg-start: #F0F3F7;
            --bg-end: #E0E6ED;
            --card: #FFFFFF;
            --danger: #FF7675;
            --secondary: #00B894;
            --edit: #FAB1A0;
            --text-main: #2D3436;
            --shadow: 0 10px 30px rgba(108, 92, 231, 0.15);
        }

        body { 
            font-family: 'Assistant', sans-serif; 
            background: linear-gradient(135deg, var(--bg-start) 0%, var(--bg-end) 100%); 
            color: var(--text-main); 
            margin: 0; 
            padding: env(safe-area-inset-top) 15px 40px 15px; 
            min-height: 100vh;
        }
        .container { max-width: 500px; margin: auto; }
        .card { background: var(--card); border-radius: 30px; padding: 25px; box-shadow: var(--shadow); margin-bottom: 25px; }
        h1 { text-align: center; color: var(--primary); font-weight: 800; }
        
        label { display: block; margin-bottom: 8px; font-weight: 700; color: var(--primary); font-size: 15px; text-align: center; width: 100%; }
        input, select { 
            width: 100%; padding: 12px; border-radius: 16px; border: 2px solid #E0E6ED; 
            margin-bottom: 20px; box-sizing: border-box; font-size: 17px; height: 55px;
            text-align: center; background-color: #FAFBFC;
        }

        .time-row { display: flex; gap: 15px; width: 100%; justify-content: space-between; }
        .time-group { flex: 1; display: flex; flex-direction: column; align-items: center; }
        
        .btn { width: 100%; padding: 18px; border-radius: 18px; border: none; font-weight: 800; font-size: 17px; cursor: pointer; color: white; margin-bottom: 12px; }
        .btn-save { background: var(--primary); box-shadow: 0 4px 12px rgba(108, 92, 231, 0.3); }
        
        .btn-logout { background-color: transparent; color: var(--danger); border: 2px solid var(--danger); padding: 8px 16px; border-radius: 12px; font-weight: 800; font-size: 14px; cursor: pointer; }
        .btn-back-admin { background-color: #2D3436; color: white; border: none; padding: 8px 16px; border-radius: 12px; font-weight: 800; font-size: 14px; cursor: pointer; }

        .history-item { background: var(--card); padding: 15px; border-radius: 20px; margin-bottom: 10px; box-shadow: var(--shadow); border-right: 6px solid var(--primary); }
        .badge { background: var(--primary); color: white; padding: 5px 12px; border-radius: 12px; font-size: 13px; font-weight: 800; }
        #login, #app, #adminPanel { display: none; }
        .mini-btn { padding: 8px 15px; border-radius: 10px; border: none; font-weight: 700; color: white; cursor: pointer; margin-left: 5px; }
        
        #syncStatus { font-size: 12px; text-align: center; margin-top: -15px; margin-bottom: 15px; color: #888; font-weight: 600; min-height: 15px; }
    </style>
</head>
<body>

<div class="container">
    <div id="login">
        <h1>WorkTime Pro</h1>
        <div class="card">
            <label>בחר משתמש</label>
            <select id="userSelect"></select>
            <input type="password" id="pass" placeholder="סיסמה">
            <button class="btn btn-save" onclick="login()">כניסה</button>
            <hr style="opacity:0.2; margin:20px 0;">
            <input type="text" id="newName" placeholder="שם מלא">
            <input type="password" id="newPass" placeholder="סיסמה">
            <button class="btn" style="background:var(--secondary)" onclick="addUser()">צור חשבון חדש</button>
        </div>
    </div>

    <div id="app">
        <div id="syncStatus">מתחבר לענן...</div>
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:15px;">
            <span class="badge" id="userNameBadge"></span>
            <div id="navButtons"></div>
        </div>
        
        <div class="card">
            <input type="hidden" id="editIndex" value="-1">
            <label>תאריך עבודה</label>
            <input type="date" id="workDate">
            <div class="time-row">
                <div class="time-group"><label>שעת כניסה</label><input type="time" id="startTime"></div>
                <div class="time-group"><label>שעת יציאה</label><input type="time" id="endTime"></div>
            </div>
            <label>שכר שעתי (₪)</label>
            <input type="number" id="hourlyRate" value="50">
            <button class="btn btn-save" id="mainBtn" onclick="saveShift()">שמור משמרת</button>
            <div id="adminEntryArea"></div>
        </div>

        <div style="display:flex; justify-content:space-between; margin-bottom:10px; align-items: center;">
            <h3 style="margin:0;">היסטוריה</h3>
            <button onclick="exportCSV()" style="background:none; border:none; color:var(--secondary); font-weight:800; cursor:pointer;">ייצוא אקסל ⬇️</button>
        </div>
        <div id="historyList"></div>
    </div>

    <div id="adminPanel">
        <h2 style="color:var(--danger); text-align:center;">ניהול מערכת</h2>
        <div class="card">
            <button class="btn" style="background:#444" onclick="downloadBackup()">📦 גיבוי ידני לקובץ</button>
            <div id="adminUserList"></div>
        </div>
        <button class="btn" style="background:#888" onclick="closeAdmin()">חזרה למסך הראשי</button>
    </div>
</div>

<script>
    const CLOUD_CONFIG = {
        apiKey: "$2a$10$BIXzeiUj1VK8RV.YMZ4hNe7.GMH3.XNP2lSRhX/JrzfX2NidTZpNG",
        binId: "69d6000410716a4d5de597ef"
    };

    let db = JSON.parse(localStorage.getItem('wt_final_fixed_db') || "{}");
    let currentUser = null;
    let actualLoggedInUser = null; 
    const ADMIN = "אבי לביא";

    function updateSyncStatus(msg) {
        const el = document.getElementById('syncStatus');
        if (el) el.innerText = msg;
    }

    async function saveDb() { 
        localStorage.setItem('wt_final_fixed_db', JSON.stringify(db));
        updateSyncStatus("מגבה נתונים בענן...");
        
        try {
            await fetch(`https://api.jsonbin.io/v3/b/${CLOUD_CONFIG.binId}`, {
                method: 'PUT',
                headers: { 'Content-Type': 'application/json', 'X-Master-Key': CLOUD_CONFIG.apiKey },
                body: JSON.stringify(db)
            });
            updateSyncStatus("✅ המידע שמור בענן");
        } catch (e) {
            updateSyncStatus("⚠️ שגיאת גיבוי (עובד מקומית)");
        }
    }

    async function loadFromCloud() {
        try {
            const res = await fetch(`https://api.jsonbin.io/v3/b/${CLOUD_CONFIG.binId}/latest`, {
                headers: { 'X-Master-Key': CLOUD_CONFIG.apiKey }
            });
            const data = await res.json();
            if (data.record && Object.keys(data.record).length > 0) {
                db = data.record;
                localStorage.setItem('wt_final_fixed_db', JSON.stringify(db));
                updateSyncStatus("✅ נתונים סונכרנו מהענן");
            } else {
                updateSyncStatus("ענן ריק - מתחיל מאפס");
            }
            init();
        } catch (e) {
            updateSyncStatus("מצב לא מקוון - טוען מהמכשיר");
            init();
        }
    }

    function init() {
        const select = document.getElementById('userSelect');
        const names = Object.keys(db);
        select.innerHTML = names.map(n => `<option value="${n}">${n}</option>`).join('');
        document.getElementById('login').style.display = 'block';
    }

    function login() {
        const n = document.getElementById('userSelect').value;
        const p = document.getElementById('pass').value;
        if(db[n] && db[n].password === p) { 
            actualLoggedInUser = n; 
            currentUser = n; 
            showApp(); 
        } 
        else alert("טעות בסיסמה");
    }

    function showApp() {
        document.getElementById('login').style.display = 'none';
        document.getElementById('adminPanel').style.display = 'none';
        document.getElementById('app').style.display = 'block';
        document.getElementById('userNameBadge').innerText = (currentUser === ADMIN) ? "מנהל: " + currentUser : "עובד: " + currentUser;
        document.getElementById('workDate').valueAsDate = new Date();
        
        const navDiv = document.getElementById('navButtons');
        const adminEntry = document.getElementById('adminEntryArea');
        
        if (actualLoggedInUser === ADMIN) {
            if (currentUser === ADMIN) {
                navDiv.innerHTML = `<button class="btn-logout" onclick="logout()">יציאה ✖</button>`;
                adminEntry.innerHTML = `<button class="btn" style="background:#2D3436; margin-top:10px;" onclick="openAdmin()">פאנל ניהול 🛠️</button>`;
            } else {
                navDiv.innerHTML = `<button class="btn-back-admin" onclick="openAdmin()">חזרה לניהול ⚙️</button>`;
                adminEntry.innerHTML = "";
            }
        } else {
            navDiv.innerHTML = `<button class="btn-logout" onclick="logout()">יציאה ✖</button>`;
            adminEntry.innerHTML = "";
        }
        resetForm();
        renderHistory();
    }

    async function saveShift() {
        const dateInput = document.getElementById('workDate').value;
        const start = document.getElementById('startTime').value;
        const end = document.getElementById('endTime').value;
        const rate = parseFloat(document.getElementById('hourlyRate').value);
        const editIdx = parseInt(document.getElementById('editIndex').value);

        if(!dateInput || !start || !end) return alert("נא למלא תאריך ושעות");

        const today = new Date(); today.setHours(0,0,0,0);
        if (new Date(dateInput) > today) return alert("לא ניתן לרשום משמרת לעתיד!");

        const newStart = new Date(`${dateInput}T${start}`);
        const newEnd = new Date(`${dateInput}T${end}`);
        if (newEnd <= newStart) newEnd.setDate(newEnd.getDate() + 1);

        const shifts = db[currentUser].shifts;
        for (let i = 0; i < shifts.length; i++) {
            if (i === editIdx) continue;
            const s = shifts[i];
            const existStart = new Date(`${s.date}T${s.start}`);
            const existEnd = new Date(`${s.date}T${s.end}`);
            if (existEnd <= existStart) existEnd.setDate(existEnd.getDate() + 1);
            if (newStart < existEnd && newEnd > existStart) return alert(`שגיאה: חפיפה עם משמרת קיימת!`);
        }

        let diff = (newEnd - newStart) / (1000 * 60 * 60);
        const total = (diff * rate + diff * 2.29).toFixed(2);
        const shift = { date: dateInput, start, end, hours: diff.toFixed(2), total, rate };

        if(editIdx === -1) db[currentUser].shifts.push(shift);
        else db[currentUser].shifts[editIdx] = shift;

        await saveDb();
        resetForm(); renderHistory();
    }

    function renderHistory() {
        const list = document.getElementById('historyList');
        if (!db[currentUser].shifts) db[currentUser].shifts = [];
        list.innerHTML = db[currentUser].shifts.map((s, i) => `
            <div class="history-item">
                <div style="display:flex; justify-content:space-between;">
                    <strong>${s.date.split('-').reverse().join('/')}</strong>
                    <strong style="color:var(--secondary)">₪${s.total}</strong>
                </div>
                <div style="font-size:14px; color:#666; margin-top:5px;">${s.start} - ${s.end} (${s.hours} שעות)</div>
                <div style="margin-top:10px;">
                    <button class="mini-btn" style="background:var(--edit)" onclick="editShift(${i})">ערוך</button>
                    <button class="mini-btn" style="background:var(--danger)" onclick="deleteShift(${i})">מחק</button>
                </div>
            </div>
        `).reverse().join('');
    }

    function editShift(i) {
        const s = db[currentUser].shifts[i];
        document.getElementById('workDate').value = s.date;
        document.getElementById('startTime').value = s.start;
        document.getElementById('endTime').value = s.end;
        document.getElementById('editIndex').value = i;
        document.getElementById('mainBtn').innerText = "עדכן משמרת";
        window.scrollTo(0,0);
    }

    async function deleteShift(i) { if(confirm("למחוק?")) { db[currentUser].shifts.splice(i, 1); await saveDb(); renderHistory(); } }
    function resetForm() { document.getElementById('editIndex').value = "-1"; document.getElementById('mainBtn').innerText = "שמור משמרת"; }
    function logout() { currentUser = null; actualLoggedInUser = null; init(); }
    
    function addUser() {
        const n = document.getElementById('newName').value.trim();
        const p = document.getElementById('newPass').value;
        if(!n || !p) return alert("מלא פרטים");
        if(db[n]) return alert("משתמש כבר קיים");
        db[n] = { password: p, shifts: [], rate: 50 };
        saveDb(); init();
    }

    function openAdmin() {
        if(actualLoggedInUser !== ADMIN) return;
        document.getElementById('app').style.display = 'none';
        document.getElementById('adminPanel').style.display = 'block';
        const list = document.getElementById('adminUserList');
        list.innerHTML = Object.keys(db).map(name => {
            const sum = db[name].shifts.reduce((a, b) => a + parseFloat(b.total), 0);
            return `<div style="padding:10px; border-bottom:1px solid #eee; display:flex; justify-content:space-between; align-items:center;">
                <strong>${name} (₪${sum.toFixed(2)})</strong>
                <button class="mini-btn" style="background:var(--primary)" onclick="adminEnterUser('${name}')">צפה</button>
            </div>`;
        }).join('');
    }

    function adminEnterUser(name) { currentUser = name; showApp(); }
    function closeAdmin() { currentUser = actualLoggedInUser; showApp(); }
    function downloadBackup() {
        const blob = new Blob([JSON.stringify(db, null, 2)], { type: 'application/json' });
        const url = window.URL.createObjectURL(blob);
        const link = document.createElement("a");
        link.href = url; link.download = "WorkTime_Backup.json"; link.click();
    }

    function exportCSV() {
        let csv = "\uFEFFתאריך,כניסה,יציאה,שעות,סהכ\n";
        db[currentUser].shifts.forEach(s => csv += `${s.date},${s.start},${s.end},${s.hours},${s.total}\n`);
        const blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
        const link = document.createElement("a");
        link.href = window.URL.createObjectURL(blob); link.download = `Report_${currentUser}.csv`; link.click();
    }

    loadFromCloud();
</script>
</body>
</html>
