<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ውሉደ ብርሐን ሰ/ት/ቤት - መመዝገቢያና አቴንዳንስ</title>    
  <style>    
    body {
      margin: 0;
      font-family: 'Poppins', 'Segoe UI', sans-serif;
      background: #f1f5f9;
      color: #111827;
    }
    header {
      background: linear-gradient(135deg, #1e293b, #0f172a);
      padding: 25px 20px;
      text-align: center;
      color: white;
      box-shadow: 0 4px 10px rgba(0,0,0,0.4);
      border-bottom: 4px solid #f59e0b;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 20px;
    }
    .header-logo {
      width: 90px;
      height: 90px;
      object-fit: cover;
      border-radius: 50%;
      border: 3px solid #facc15;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
    }
    header h1 {
      margin: 0;
      font-size: 24px;
      font-weight: bold;
      letter-spacing: 1px;
      color: #facc15;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
      line-height: 1.4;
    }
    header span {
      font-size: 19px;
      color: white;
      font-weight: 600;
    }
    header p {
      margin: 8px 0 0 0;
      font-size: 14px;
      color: #cbd5e1;
      background: #111827;
      display: inline-block;
      padding: 6px 14px;
      border-radius: 30px;
      border: 1px solid #334155;
    }
    .container {
      max-width: 1200px;
      margin: auto;
      padding: 20px;
    }
    .dashboard-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(170px, 1fr));
      gap: 15px;
      margin-bottom: 20px;
    }
    .small {
      background: white;
      padding: 18px;
      border-radius: 18px;
      text-align: center;
      color: #111827;
      font-weight: 600;
      box-shadow: 0 5px 18px rgba(0,0,0,0.08);
      transition: 0.3s;
      border: 1px solid #e5e7eb;
    }
    .small:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.12);
    }
    .app-page {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      overflow-y: scroll;
      overflow-x: hidden;
      background: #f1f5f9;
      z-index: 100;
      box-sizing: border-box;
      padding-bottom: 60px;
    }
    .page-content {
      max-width: 1150px;
      margin: 30px auto;
      background: white;
      padding: 30px;
      border-radius: 24px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.1);
    }
    input, select {
      width: 100%;
      padding: 14px;
      margin-top: 10px;
      border-radius: 14px;
      border: 2px solid #e5e7eb;
      background: white;
      color: black;
      font-size: 15px;
      box-sizing: border-box;
      transition: 0.3s;
    }
    input:focus, select:focus {
      outline: none;
      border-color: #3b82f6;
      box-shadow: 0 0 12px rgba(59,130,246,0.25);
    }
    button {
      width: 100%;
      padding: 14px;
      border: none;
      border-radius: 14px;
      margin-top: 10px;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover { transform: scale(1.02); }
    .add { background: #22c55e; color: white; }
    .add:hover { background: #16a34a; }
    .save { background: #2563eb; color: white; }
    .save:hover { background: #1d4ed8; }
    .edit { background: #f59e0b; color: white; }
    .edit:hover { background: #d97706; }
    .del { background: #ef4444; color: white; }
    .del:hover { background: #dc2626; }
    .view { background: #0ea5e9; color: white; }
    .view:hover { background: #0284c7; }
    .sectionBtn { background: #1e293b; color: white; }
    .cancel { background: #64748b; color: white; }
    .card {
      background: white;
      padding: 22px;
      border-radius: 22px;
      margin-top: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.08);
      border: 1px solid #e5e7eb;
    }
    .studentCard {
      background: white;
      color: #111827;
      padding: 18px;
      border-radius: 18px;
      margin-top: 15px;
      box-shadow: 0 5px 18px rgba(0,0,0,0.08);
      border-left: 5px solid #3b82f6;
    }
    .preview {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 8px;
      margin-top: 10px;
      display: none;
      border: 3px solid #3b82f6;
    }
    .settings-item {
      background: #f8fafc;
      padding: 18px;
      border-radius: 16px;
      margin-top: 12px;
      cursor: pointer;
      border: 1px solid #e5e7eb;
      font-weight: bold;
      display: flex;
      justify-content: space-between;
      align-items: center;
      transition: 0.2s;
    }
    .settings-item:hover {
      background: #f1f5f9;
      transform: translateX(4px);
    }
    
    /* የተሻሻለ የሰንጠረዥ ስታይል - ይበልጥ ግልፅ እና ማራኪ እንዲሆን */
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 15px;
      font-size: 14px;
      background-color: #ffffff;
      box-shadow: 0 4px 12px rgba(0,0,0,0.05);
      border-radius: 8px;
      overflow: hidden;
    }
    th, td {
      border: 1px solid #cbd5e1;
      padding: 14px 16px;
      text-align: left;
    }
    th {
      background-color: #0f172a;
      color: #ffffff;
      font-weight: 600;
      letter-spacing: 0.5px;
    }
    tr:nth-child(even) {
      background-color: #f8fafc;
    }
    tr:hover {
      background-color: #f1f5f9;
    }
    
    .hidden { display: none !important; }
    
    /* 🪦 የተስተካከለ የማህደር ግሪድ እና 4x4 ካርድ ዲዛይን */
.rip-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr)); /* 💡 ካርዶቹ ለፎቶ እንዲመቹ አነስ ማለታቸው */
  gap: 12px;
  margin-top: 20px;
}
.rip-card {
  background: #1e293b;
  color: white;
  padding: 10px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0,0,0,0.15);
  border: 1px solid #334155;
  cursor: pointer;
  transition: transform 0.2s;
}
.rip-card:active {
  transform: scale(0.96);
}
.rip-card img {
  width: 100%;
  aspect-ratio: 1 / 1; /* 💡 ፎቶው ፍጹም 4x4 አራት ማዕዘን (Square) እንዲሆን ያደርገዋል */
  object-fit: cover;
  border-radius: 8px; /* ክብ የነበረው ጠፍቶ ለጥጉ ብቻ ማለስለሻ ይሆናል */
  border: 2px solid #facc15;
  margin-bottom: 8px;
  background: #0f172a;
}
    
    /* ማስታወሻ ፎቶ ጋለሪ ስታይል */
    .gallery-container {
      max-width: 500px;
      margin: 20px auto;
      text-align: center;
      background: #1e293b;
      padding: 25px;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
      border: 2px solid #334155;
    }
    .gallery-img {
      width: 100%;
      max-height: 350px;
      object-fit: contain;
      border-radius: 12px;
      border: 3px solid #facc15;
      background: #0f172a;
      margin-bottom: 15px;
    }
    .gallery-info {
      color: #facc15;
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 15px;
    }
    .gallery-controls {
      display: flex;
      gap: 10px;
      justify-content: space-between;
    }
    /* ለአዲሱ ፎቶ ማከማቻ እና ለስታቲስቲክስ ሪፖርት ማስተካከያ */
#partStatsTableContainer, #learningSummaryTableContainer, #completedSummaryTableContainer {
  width: 100%;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  margin-top: 15px;
}

#partStatsTableContainer table, #learningSummaryTableContainer table, #completedSummaryTableContainer table {
  min-width: 600px;
}

.gallery-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 15px;
  margin-top: 20px;
}

.photo-card {
  background: white;
  border-radius: 8px;
  padding: 10px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
  border: 1px solid #e2e8f0;
  text-align: center;
}

.photo-card img {
  width: 100%;
  height: 120px;
  object-fit: cover;
  border-radius: 6px;
  cursor: pointer;
  transition: transform 0.2s;
}

.photo-card img:hover { 
  transform: scale(1.02); 
}

/* ሙሉ ገፅ ፎቶ ማያ (Lightbox Modal) */
.lightbox {
  position: fixed;
  top: 0; left: 0; width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.9);
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  opacity: 0; pointer-events: none;
  transition: opacity 0.3s ease;
}

.lightbox.active { 
  opacity: 1; pointer-events: auto; 
}

.lightbox img { 
  max-width: 90%; max-height: 75%; object-fit: contain; transition: transform 0.2s ease; 
}

.lightbox-controls { 
  margin-top: 15px; display: flex; gap: 10px; 
}

.lightbox-btn { 
  background: #cbd5e1; color: black; padding: 8px 16px; border: none; border-radius: 6px; font-weight: bold; cursor: pointer; 
}
    .design-by {
      text-align: center;
      margin-top: 40px;
      font-size: 14px;
      color: #64748b;
      font-weight: bold;
      border-top: 1px dashed #cbd5e1;
      padding-top: 15px;
    }
@media print {
  /* 1. ሁሉንም የጀርባ ሲስተም ገጾች በፕሪንት ጊዜ ብቻ መደበቅ */
  body > :not(#printArea) {
    display: none !important;
  }
  
  body {
    background: white !important;
    color: #000000 !important;
  }

  /* 2. የማተሚያ ቦታውን በግድ እንዲታይ ማድረጊያ */
  #printArea {
    display: block !important;
    position: absolute !important;
    left: 0 !important;
    top: 0 !important;
    width: 100% !important;
    background: white !important;
    color: #000000 !important;
    visibility: visible !important;
  }
  
  #printArea * {
    visibility: visible !important;
    color: #000000 !important;
  }

  /* 3. ሰንጠረዦች በጥቁር መስመር እንዲታጠሩ ማስገደጃ */
  table {
    width: 100% !important;
    border-collapse: collapse !important;
    border: 1px solid #000000 !important;
  }
  
  td, th {
    border: 1px solid #000000 !important;
    padding: 8px !important;
    color: #000000 !important;
  }

  /* 4. የቤት ቁጥር በቀይ ቀለም ብቻ እንዲወጣ መፍቀጃ */
  .print-red-row td, td[style*="color:#dc2626"] {
    color: #dc2626 !important;
    -webkit-print-color-adjust: exact !important;
    print-color-adjust: exact !important;
  }
}
    @media print {
      body * { visibility: hidden; }
      #printArea, #printArea * { visibility: visible; }
      #printArea { position: absolute; left: 0; top: 0; width: 100%; color: black; background: white; }
      table { width: 100%; border-collapse: collapse; }
      th, td { border: 1px solid #000 !important; padding: 10px; text-align: left; color: black !important; }
    }
    @media(max-width:768px){
      .dashboard-grid { grid-template-columns: 1fr; }
      header { flex-direction: column; gap: 10px; }
      header h1 { font-size: 18px; }
    }
    .upload-section { background: white; margin: 15px 0; padding: 15px; border-radius: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }
.upload-section input[type="text"], .upload-section input[type="date"] {
  width: 100%; padding: 10px; margin-top: 10px; border: 1px solid #cbd5e1; border-radius: 6px; box-sizing: border-box;
}
.btn-upload { width: 100%; background: #0d9488; color: white; border: none; padding: 12px; margin-top: 12px; border-radius: 6px; font-size: 16px; font-weight: bold; cursor: pointer; }
.preview-container { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 10px; }
.preview-img { width: 70px; height: 70px; object-fit: cover; border-radius: 6px; border: 1px solid #cbd5e1; }

.gallery-section { padding: 10px 0; }
.photo-gallery { display: grid; grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); gap: 12px; }
.gallery-item { background: white; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 4px rgba(0,0,0,0.05); position: relative; border: 1px solid #e2e8f0; }
.gallery-item img { width: 100%; height: 120px; object-fit: cover; cursor: pointer; }
.item-info { padding: 8px; font-size: 12px; color: #334155; }
.btn-delete { position: absolute; top: 5px; right: 5px; background: rgba(239, 68, 68, 0.9); color: white; border: none; border-radius: 50%; width: 26px; height: 26px; font-size: 12px; cursor: pointer; }

/* የሙሉ ገጽ መመልከቻ (በተኖቹ ዙም ሲደረግ እንዳይንቀሳቀሱ የተቆለፉበት) */
.viewer-modal {
  position: fixed; top: 0; left: 0; width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.95); z-index: 2000; display: none;
  flex-direction: column; justify-content: center; align-items: center;
}
.viewer-controls {
  position: absolute; top: 20px; left: 0; width: 100%; display: flex;
  justify-content: space-between; padding: 0 20px; box-sizing: border-box; z-index: 2100;
}
.control-btn {
  background: rgba(255, 255, 255, 0.2); color: white; border: none;
  padding: 10px 16px; border-radius: 20px; font-size: 14px; font-weight: bold;
  backdrop-filter: blur(5px); cursor: pointer;
}
.close-btn { background: rgba(239, 68, 68, 0.8); }
.download-btn { background: rgba(16, 185, 129, 0.8); }
.viewer-content { width: 100%; height: 100%; display: flex; justify-content: center; align-items: center; overflow: auto; }
.viewer-content img { max-width: 95%; max-height: 80%; object-fit: contain; transition: transform 0.3s ease; cursor: zoom-in; }
.viewer-content img.zoomed { transform: scale(2.5); max-width: none; max-height: none; cursor: zoom-out; }
.viewer-caption { position: absolute; bottom: 20px; left: 5%; width: 90%; background: rgba(0,0,0,0.7); color: white; padding: 12px; border-radius: 8px; text-align: center; font-size: 14px; z-index: 2100; }

/* 🎥 እንደ አዲስ የተሰራ የቪዲዮ ማስታወሻ ገጽ CSS */
.v-container {
  background: white;
  padding: 18px;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.05);
  margin-bottom: 20px;
  border: 1px solid #e2e8f0;
}
.v-group {
  margin-bottom: 12px;
}
.v-group label {
  font-weight: bold;
  display: block;
  margin-bottom: 5px;
  color: #334155;
  font-size: 13px;
}
.v-group input {
  width: 100%;
  padding: 10px;
  border: 1px solid #cbd5e1;
  border-radius: 8px;
  font-size: 14px;
  box-sizing: border-box;
}
.v-group input:focus {
  border-color: #0d9488;
  outline: none;
}
.v-or {
  text-align: center;
  margin: 10px 0;
  color: #94a3b8;
  font-weight: bold;
  font-size: 12px;
}
.v-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 15px;
}
.v-card {
  background: white;
  border-radius: 10px;
  box-shadow: 0 3px 6px rgba(0,0,0,0.08);
  overflow: hidden;
  border: 1px solid #e2e8f0;
  display: flex;
  flex-direction: column;
}
.v-thumb {
  position: relative;
  background: #0f172a;
  height: 110px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
.v-badge {
  position: absolute;
  top: 6px;
  left: 6px;
  color: white;
  padding: 2px 6px;
  font-size: 9px;
  border-radius: 4px;
  font-weight: bold;
}
.v-play-btn {
  font-size: 36px;
  background: rgba(255,255,255,0.2);
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  backdrop-filter: blur(3px);
}
/* በኮምፒውተር ላይ የካርድ ማሳለፊያው መስመር ውብ እንዲሆን */
#ripContainer::-webkit-scrollbar {
  height: 8px; /* የመስመሩ ውፍረት */
}
#ripContainer::-webkit-scrollbar-track {
  background: #1e293b; /* የመስመሩ መነሻ ቀለም */
  border-radius: 10px;
}
#ripContainer::-webkit-scrollbar-thumb {
  background: #64748b; /* ተንቀሳቃሹ ክፍል ቀለም */
  border-radius: 10px;
}
#ripContainer::-webkit-scrollbar-thumb:hover {
  background: #3b82f6; /* ማውዙ ሲያርፍበት ሰማያዊ ይሆናል */
}
  </style>
</head>
<body>

  <div id="loginPage" style="position:fixed; top:0; left:0; width:100%; height:100%; background:linear-gradient(135deg, #0f172a, #1e293b); z-index:9999; display:flex; align-items:center; justify-content:center;">
    <div style="background:white; padding:35px 30px; border-radius:24px; box-shadow:0 20px 40px rgba(0,0,0,0.4); max-width:440px; width:92%; text-align:center; max-height: 95vh; overflow-y: auto;">
      <img src="https://i.postimg.cc/cLGxGjtR/maxresdefault-(1).jpg" alt="Holy Trinity" style="width:100%; height:auto; max-height:220px; object-fit:contain; border-radius:14px; margin-bottom:15px; border:2px solid #cbd5e1; display:block;">
      <h2 style="color:#1e293b; margin:5px 0;">እንጦጦ መንበረ ስብሐት ቅድስት ስላሥ ቤተክርስትያን ውሉደ ብርሐን ሰ/ት/ቤት</h2>
      <p style="color:#64748b; margin-top:0; font-size:14px;">የመረጃ መያዣ እና አቴንዳንስ ሲስተም </p>
      <hr style="border:1px dashed #e5e7eb; margin:15px 0;">
      <label style="display:block; text-align:left; font-weight:bold; color:#475569;"></label>
      <input type="password" id="loginPassInput" placeholder="Password" style="margin-bottom:20px; text-align:center; font-size:18px; letter-spacing:3px;">
      <button class="save" onclick="checkLoginPass()" style="font-size:16px; padding:14px;">🔓 ግባ (Login)</button>
      <p class="design-by" style="margin-top:25px; border:none; padding:0;">Design By: 7@MH@ll,wende<br>📞 0919484894</p>
    </div>
  </div>

  <div id="app" style="display:none;">
    <header>
      <img src="IMG_20260520_133932_534.jpg" alt="Logo Left" class="header-logo">
      <div>
        <h1>የእንጦጦ መንበረ ስብሐት ቅድስት ሥላሴ ቤ/ክ<br><span>ውሉደ ብርሐን ሰ/ት/ቤት</span></h1>
        <p>📘 የአላባት መመዝገቢያ እና መረጃ መያዣ ድረገፅ</p>
      </div>
      <img src="IMG_20260520_133932_534.jpg" alt="Logo Right" class="header-logo">
    </header>

    <div class="container">
      <div class="dashboard-grid">
        <div class="small">👥 ጠቅላላ ተማሪ: <span id="total">0</span></div>
        <div class="small">👨 ወንድ: <span id="male">0</span></div>
        <div class="small">👩 ሴት: <span id="female">0</span></div>
        <div class="small">🟢 Active (አገልግሎት ላይ): <span id="active">0</span></div>
        <div class="small">🔴 Inactive (የራቁ): <span id="inactive">0</span></div>
        <div class="small" onclick="togglePartStats()" style="cursor:pointer; background: #e2e8f0;">📈 ፓርትስፔሽን ⬇</div>
      </div>

      <div id="partStats" class="dashboard-grid hidden">
        <div class="small" style="border-top: 4px solid green;">ጥሩ (ከ75% በላይ): <span id="high">0</span></div>
        <div class="small" style="border-top: 4px solid orange;">መካከለኛ (50%-75%): <span id="medium">0</span></div>
        <div class="small" style="border-top: 4px solid red;">ዝቅተኛ (ከ50% በታች): <span id="low">0</span></div>
      </div>

      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; margin-top: 20px;">
        <button class="save" onclick="navigateTo('addStudentPage')">+ Add Student (ተማሪ መዝግብ)</button>
        <button class="add" onclick="openAllStudentsPage()">👥 All Students (ሁሉንም አሳይ)</button>

        <button class="sectionBtn" onclick="navigateTo('settingsPage')">⚙ Settings (ማስተካከያ)</button>
      </div>
      <button class="view" onclick="navigateTo('attendancePage')">
  📅 Attendance (አቴንዳንስ ሲስተም)
</button>

<div id="attendancePage" class="app-page">
  <div class="page-content">
    <h2>📅 Attendance & Record System</h2>

    <div style="background:#f8fafc; padding:15px; border-radius:12px; margin-bottom:15px; border:1px solid #cbd5e1;">

     <label><b>1. የመርሀ ግብር ቀን ይምረጡ፦</b></label>

<input type="text" id="attDate" readonly
       placeholder="ቀን ለመሙላት እዚህ ይጫኑ..."
       onclick="openGlobalCalendar('attDate')"
       onkeydown="return false"
       style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px; cursor:pointer; background:white;">

      <label style="display:block; margin-top:10px;"><b>2. የመርሀ ግብሩ አይነት፦</b></label>
      <select id="attProgramType">
        <option value="ፀሎት">ፀሎት</option>
        <option value="ልዩ ጉባኤ">ልዩ ጉባኤ</option>
        <option value="ፅዋ">ፅዋ</option>
        <option value="መዝሙር">መዝሙር</option>
        <option value="ትምህርት">ትምህርት</option>
      </select>

      <label style="display:block; margin-top:10px;"><b>3. የክፍል ደረጃ ይምረጡ፦</b></label>
      <select id="attProgClass">
        <option value="1ኛ ክፍል">1ኛ ክፍል</option>
        <option value="2ኛ ክፍል">2ኛ ክፍል</option>
        <option value="3ኛ ክፍል">3ኛ ክፍል</option>
        <option value="4ኛ ክፍል">4ኛ ክፍል</option>
        <option value="5ኛ ክፍል">5ኛ ክፍል</option>
        <option value="6ኛ ክፍል">6ኛ ክፍል</option>
        <option value="7ኛ ክፍል">7ኛ ክፍል</option>
        <option value="8ኛ ክፍል">8ኛ ክፍል</option>
        <option value="9ኛ ክፍል">9ኛ ክፍል</option>
        <option value="10ኛ ክፍል">10ኛ ክፍል</option>
        <option value="11ኛ ክፍል">11ኛ ክፍል</option>
        <option value="12ኛ ክፍል">12ኛ ክፍል</option>
        <option value="ያጠናቀቁ">ያጠናቀቁ</option>
        <option value="ሌላ">ሌላ</option>
      </select>

      <button type="button" onclick="loadAttendanceList()"
        style="width:100%; margin-top:15px; padding:10px; background:#2563eb; color:white; border:none; border-radius:8px;">
        📋 ተማሪዎችን አሳይ
      </button>
    </div>

    <div id="attendanceSheet" class="hidden card">
      <h3>የአቴንዳንስ ፎርም</h3>

      <input id="attSearchBox"
             placeholder="በስም ፈልግ..."
             onkeyup="filterAttendanceListOnly()">

      <div id="attStudentList" style="margin-top:15px;"></div>

      <button class="add"
              onclick="saveAttendanceSheet()"
              style="margin-top:15px;">
        💾 የአቴንዳንስ ሪከርድ አስቀምጥ
      </button>
    </div>

    <button class="cancel"
            onclick="closeCurrentPage()"
            style="margin-top:15px;">
      ተመለስ (Back)
    </button>
  </div>
</div>
        
        <body>
      <p class="design-by">Design By: 7@MH@ll,wende | 📞 0919484894</p>
    </div>
  </div>

  <div id="addStudentPage" class="app-page">
    <div class="page-content">
      <h3 id="formTitle">አዲስ ተማሪ መመዝገቢያ ፎርም</h3>
      
      <input type="text" id="christianName" placeholder="ክርስትና ስም">
      <input type="text" id="name" placeholder="ሙሉ ስም (Required)" required>
      <label style="display:block; margin-top:15px; font-weight:bold;">የትውልድ ቀን፦</label>

<input type="text" id="birthDate" readonly 
   placeholder="የትውልድ ቀን ለመሙላት እዚህ ይጫኑ..." 
   onclick="openGlobalCalendar('birthDate')" 
   onkeydown="return false"
   style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px; cursor:pointer; background:white;">
      <input type="tel" id="phone" placeholder="የግል ስልክ ቁጥር (Required)" required>
      <input type="tel" id="familyPhone" placeholder="የቤተሰብ ስልክ ቁጥር">
      
      <label style="display:block; margin-top:15px; font-weight:bold;">የሚማሩበት ክፍል (Required)፦</label>
      <select id="cls" onchange="checkClsChoice()" required>
        <option value="">ክፍል ይምረጡ</option>
        <option value="1ኛ ክፍል">1ኛ ክፍል</option>
        <option value="2ኛ ክፍል">2ኛ ክፍል</option>
        <option value="3ኛ ክፍል">3ኛ ክፍል</option>
        <option value="4ኛ ክፍል">4ኛ ክፍል</option>
        <option value="5ኛ ክፍል">5ኛ ክፍል</option>
        <option value="6ኛ ክፍል">6ኛ ክፍል</option>
        <option value="7ኛ ክፍል">7ኛ ክፍል</option>
        <option value="8ኛ ክፍል">8ኛ ክፍል</option>
        <option value="9ኛ ክፍል">9ኛ ክፍል</option>
        <option value="10ኛ ክፍል">10ኛ ክፍል</option>
        <option value="11ኛ ክፍል">11ኛ ክፍል</option>
        <option value="12ኛ ክፍል">12ኛ ክፍል</option>
        <option value="የተጠናቀቁ">የተጠናቀቁ</option>
        <option value="ሌላ">ሌላ</option>
      </select>
      <input type="text" id="clsOtherText" placeholder="የክፍሉን ስም እዚህ ይፃፉ..." style="display:none; margin-top:10px;">

   <input type="text" id="regDate" readonly 
   placeholder="ቀን ለመሙላት እዚህ ይጫኑ..." 
   onclick="openGlobalCalendar('regDate')" 
   onkeydown="return false"
   style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px; cursor:pointer; background:white;">

<label style="display:block; margin-top:15px; font-weight:bold;">ማዕረገ ክህነት፦</label>
<input type="text" id="studentRank" placeholder="ምሳሌ፦ ዲያቆን / ቀሲስ / መምህር"
   style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px;">
<label style="display:block; margin-top:15px; font-weight:bold;">
  በሰንበት ት/ቤት ያሉበት መደብ፦
</label>

<input type="text" id="studentLevel"
  placeholder="ምሳሌ፦ኳየር/ የክብር አባል / መደበኛ"
  style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px;">
<label style="display:block; margin-top:15px; font-weight:bold;">የአሁኑ የትምህርት ደረጃ (Current Class)፦</label>
<input type="text" id="currentClass" placeholder="ምሳሌ፦ 10ኛ ክፍል / ማስተርስ">
      <select id="gender" style="margin-top:15px;">
        <option value="">ጾታ ይምረጡ</option>
        <option value="Male">ወንድ</option>
        <option value="Female">ሴት</option>
      </select>

      <label style="display:block; margin-top:15px; font-weight:bold;">አሁን እያገለገሉበት ያለው ክፍል፦</label>
      <input type="text" id="currentServingDept" placeholder="ለምሳሌ፦ መዝሙር ክፍል / ትምህርት ክፍል">

      <div class="settings-item" onclick="toggleElement('prevBox')">📚 ያለፉ ክፍሎችን ለመሙላት <span>⬇</span></div>
      <div id="prevBox" class="card hidden">
        <input type="text" id="p1" placeholder="ያለፉ ክፍል 1">
        <input type="text" id="p2" placeholder="ያለፉ ክፍል 2">
        <input type="text" id="p3" placeholder="ያለፉ ክፍል 3">
        <input type="text" id="p4" placeholder="ያለፉ ክፍል 4">
        <input type="text" id="p5" placeholder="ያለፉ ክፍል 5">
      </div>
<label style="display:block; margin-top:15px; font-weight:bold;">የፀባይ ሁኔታ፦</label>
<input type="text" id="studentBehavior" 
  placeholder="ምሳሌ፦ ጥሩ / መካከለኛ / የሚሻሻል"
  style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px;">
      <div class="settings-item" onclick="toggleElement('addressBox')">📍 አድራሻ ለመሙላት <span>⬇</span></div>
      <div id="addressBox" class="card hidden">
        <input type="text" id="city" placeholder="ከተማ">
        <input type="text" id="subcity" placeholder="ክፍለ ከተማ">
        <input type="text" id="woreda" placeholder="ወረዳ">
፤        <input type="text" id="area" placeholder="ልዩ ቦታ">
        <input type="text" id="house" placeholder="የቤት ቁጥር">
      </div>
<label style="display:block; margin-top:15px; font-weight:bold;">የመራቅ ሁኔታ ካለ ይምረጡ፦</label>
<select id="reason" onchange="checkReason()">
  <option value="የለም">አልራቀም (በአገልግሎት ላይ ያለ)</option>
  <option value="ትምህርት">የራቁበት ምክንያት: ትምህርት</option>
  <option value="ስራ">የራቁበት ምክንያት: ስራ</option>
  <option value="ፈቃድ">የራቁበት ምክንያት: ፈቃድ</option>
  <option value="በእረፍተ ስጋ">የራቁበት ምክንያት: በእረፍተ ስጋ</option>
  <option value="other">ሌላ ምክንያት</option>
</select>

<input type="text" id="reasonText" placeholder="ዝርዝር ምክንያት ይጻፉ..." style="display:none; margin-top:10px; width:100%; padding:8px; border:1px solid #ccc; border-radius:6px;">

<div id="leaveDetailsBox" style="display:none; margin-top:15px; padding:12px; background:#f8fafc; border:1px solid #cbd5e1; border-radius:8px;">
  <p style="margin:0 0 10px 0; font-weight:bold; color:#1e293b; border-bottom:1px solid #cbd5e1; padding-bottom:5px;">📋 የፈቃድ ዝርዝር መረጃዎችን ያስገቡ</p>
  
 <div style="display:flex; gap:10px; margin-bottom:10px;">  <div style="flex:1;">
    <label style="display:block; font-size:13px; font-weight:bold; margin-bottom:4px;">
      ፈቃዱ የሚጀምርበት ቀን፦
    </label>
    <input
      type="text"
      id="leaveStartDate"
      readonly
      placeholder="ቀን ይምረጡ..."
      onclick="openGlobalCalendar('leaveStartDate')"
      style="width:100%; padding:8px; border:1px solid #94a3b8; border-radius:6px; cursor:pointer; background:white;">
  </div>  <div style="flex:1;">
    <label style="display:block; font-size:13px; font-weight:bold; margin-bottom:4px;">
      ፈቃዱ የሚያበቃበት ቀን፦
    </label>
    <input
      type="text"
      id="leaveEndDate"
      readonly
      placeholder="ቀን ይምረጡ..."
      onclick="openGlobalCalendar('leaveEndDate')"
      style="width:100%; padding:8px; border:1px solid #94a3b8; border-radius:6px; cursor:pointer; background:white;">
  </div></div>

  <label style="display:block; font-size:13px; font-weight:bold; margin-bottom:6px;">ፈቃድ ያስፈቀዱባቸው መርሐግብራት (እስከ 7 መምረጥ ይቻላል)፦</label>
  <div style="display:grid; grid-template-columns: 1fr 1fr; gap:6px; background:white; padding:8px; border:1px solid #e2e8f0; border-radius:6px;">
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="ቅዳሴ"> ቅዳሴ</label>
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="ትምህርት ክፍል"> ትምህርት ክፍል</label>
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="ስምሪት ክፍል"> ስምሪት ክፍል</label>
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="መዝሙር ክፍል"> መዝሙር ክፍል</label>
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="ልማት ክፍል"> ልማት ክፍል</label>
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="ሂሳብ ክፍል"> ሂሳብ ክፍል</label>
    <label style="font-size:13px; cursor:pointer;"><input type="checkbox" name="leavePrograms" value="አስተዳደር ክፍል"> አስተዳደር ክፍል</label>
  </div>
</div>
 
<div id="restDateBox" style="display:none; margin-top:10px;">
  <label style="display:block; font-weight:bold; color:#ef4444;">
    በእረፍተ ስጋ የራቁበት ቀን፦
  </label><input
type="text"
id="restInPeaceDate"
readonly
placeholder="ቀን ይምረጡ..."
onclick="openGlobalCalendar('restInPeaceDate')"
style="width:100%; padding:10px; border-radius:6px; border:1px solid #cbd5e1; font-size:14px;">

</div>
      <div id="restDateBox" style="display:none; margin-top:10px;">
        <label style="display:block; font-weight:bold; color:#ef4444;">በእረፍተ ስጋ የራቁበት ቀን፦</label>
        <input type="date" id="restInPeaceDate">
      </div>

      <label style="display:block; margin-top:15px; font-weight:bold;">ፎቶ ይምረጡ (ልክ 4x4 መጠን)፦</label>
      <input type="file" id="photo" accept="image/*">
      <img id="preview" class="preview" alt="የፎቶ ቅድመ እይታ">

      <button class="add" onclick="save()" style="margin-top:25px;">💾 መረጃውን አስቀምጥ (Save)</button>
      <button class="cancel" onclick="closeCurrentPage()">ተመለስ (Back)</button>
    </div>
  </div>

  <div id="allStudentsPage" class="app-page">
    <div class="page-content">
      <h3>👥 የተማሪዎች ዝርዝር መረጃ ማውጫ</h3>
      <input id="search" placeholder="ስም ፣ ስልክ ወይም ክፍል አስገብተው ይፈልጉ..." onkeyup="renderListSearch()">
      <div id="list"></div>
      <button class="cancel" onclick="closeCurrentPage()" style="margin-top:20px;">ተመለስ (Back)</button>
    </div>
  </div>

 <div id="attendancePage" class="app-page">
    <div class="page-content">
      <h2>📅 Attendance & Record System</h2>
      <div style="background:#f8fafc; padding:15px; border-radius:12px; margin-bottom:15px; border:1px solid #cbd5e1;">
  <label><b>1. የመርሀ ግብር ቀን ይምረጡ፦</b></label>
<input type="text" id="attDate" readonly
       value=""
       onclick="openGlobalCalendar('attDate')"
       style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px; background:white; cursor:pointer; box-sizing:border-box; margin-top:5px;">
        <label style="display:block; margin-top:10px;"><b>2. የመርሀ ግብሩ አይነት፦</b></label>
        <select id="attProgramType" onchange="toggleProgClassSelect()">
          <option value="ፀሎት">ፀሎት</option>
          <option value="ልዩ ጉባኤ">ልዩ ጉባኤ</option>
          <option value="ፅዋ">ፅዋ</option>
          <option value="መዝሙር">መዝሙር</option>
          <option value="ትምህርት">ትምህርት</option>
        </select>
        <div id="progClassBox" class="hidden">
          <label style="display:block; margin-top:10px;"><b>የክፍል ደረጃ ይምረጡ፦</b></label>
          <select id="attProgClass">
            <option value="1ኛ ክፍል">1ኛ ክፍል</option>
            <option value="2ኛ ክፍል">2ኛ ክፍል</option>
            <option value="3ኛ ክፍል">3ኛ ክፍል</option>
            <option value="4ኛ ክፍል">4ኛ ክፍል</option>
            <option value="5ኛ ክፍል">5ኛ ክፍል</option>
            <option value="6ኛ ክፍል">6ኛ ክፍል</option>
            <option value="7ኛ ክፍል">7ኛ ክፍል</option>
            <option value="8ኛ ክፍል">8ኛ ክፍል</option>
            <option value="9ኛ ክፍል">9ኛ ክፍል</option>
            <option value="10ኛ ክፍል">10ኛ ክፍል</option>
            <option value="11ኛ ክፍል">11ኛ ክፍል</option>
            <option value="12ኛ ክፍል">12ኛ ክፍል</option>
          </select>
        </div>
        
        <div style="display:flex; flex-direction:row; gap:6px; width:100%; margin-top:15px; justify-content:space-between;">
          <button type="button" onclick="loadAttendanceListCategory('learning')" style="flex:1; padding:8px 4px; font-weight:bold; border-radius:6px; font-size:11px; text-align:center; background:#2563eb; color:white; border:none; cursor:pointer;">📖 የሚማሩ</button>
          <button type="button" onclick="loadAttendanceListCategory('completed')" style="flex:1; padding:8px 4px; font-weight:bold; border-radius:6px; font-size:11px; text-align:center; background:#2563eb; color:white; border:none; cursor:pointer;">🎓 ያጠናቀቁ</button>
          <button type="button" onclick="loadAttendanceListCategory('other')" style="flex:1; padding:8px 4px; font-weight:bold; border-radius:6px; font-size:11px; text-align:center; background:#2563eb; color:white; border:none; cursor:pointer;">✨ ሌላ</button>
        </div>
      </div>

      <div id="attendanceSheet" class="hidden card">
        <h3>የአቴንዳንስ ፎርም መሙያ</h3>
        <input id="attSearchBox" placeholder="በአቴንዳንስ ፎርሙ ላይ ስም ለመፈለግ..." onkeyup="filterAttendanceListOnly()">
        <div id="attStudentList" style="margin-top:15px;"></div>
        <button class="add" onclick="saveAttendanceSheet()" style="margin-top:15px;">💾 የአቴንዳንስ ሪከርድ አስቀምጥ</button>
      </div>
      <button class="cancel" onclick="closeCurrentPage()" style="margin-top:15px;">ተመለስ (Back)</button>
    </div>
  </div>
  <div id="settingsPage" class="app-page">
    <div class="page-content">
      <h2>⚙ Settings (ማስተካከያ ማውጫ)</h2>
<div class="settings-item" onclick="
  openGeneralReportMenu('allReportTableContainer', 'all');
  document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
  let page1 = document.getElementById('allListReportPage');
  if(page1) page1.style.display = 'block';
">
  <span>1. 👥 All Students Report</span> <span>➔</span>
</div>

<div class="settings-item" onclick="
  openGeneralReportMenu('activeReportTableContainer', 'active');
  document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
  let page2 = document.getElementById('activeListReportPage');
  if(page2) page2.style.display = 'block';
">
  <span>2. 🟢 Active Students Report</span> <span>➔</span>
</div>

<div class="settings-item" onclick="
  openGeneralReportMenu('inactiveReportTableContainer', 'inactive');
  document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
  let page3 = document.getElementById('inactiveListReportPage');
  if(page3) page3.style.display = 'block';
">
  <span>3. 🔴 Inactive Students Report</span> <span>➔</span>
</div>
<div class="settings-item" onclick="showRankedStudentsReport(event)">
    <span>9. 🎖 ማዕረገ ክህነት ያላቸው አባላት</span> <span>➔</span>
</div>
<div class="settings-item" onclick="showCategoryReport()">
    <span>9. 📋 የአባላት ምድብ ሪፖርት</span> <span>➔</span>
</div>

      <div class="settings-item" onclick="openSingleStudentAttendancePage()" style="background: #fdf2f8; border-left: 5px solid #ec4899;">
        <span>5. 📅 የተማሪዎች የግል አቴንዳንስ ታሪክ (የየቀን ዝርዝር)</span> <span>➔</span>
      </div>
       <div class="settings-item" onclick="openParticipationStatsPage(); navigateTo('participationStatsPage');" style="background: #fffbeb; border-left: 5px solid #d97706;">
        <span>6. 📊 የተማሪዎች ዝርዝር የተሳትፎ ስታቲስቲክስ (የያዳዱ መርሀግብር በዝርዝር)</span> <span>➔</span>
      </div>
     <div class="settings-item" onclick="openAllAttendanceSummaryReport('completed'); document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); let pComp = document.getElementById('completedSummaryPage'); if(pComp) pComp.style.display = 'block';" style="background: #f0fdf4; border-left: 5px solid #16a34a;">
  <span>7. 🎓 ትምህርት ያጠናቀቁ ተማሪዎች አቴንዳንስ ማጠቃለያ</span> <span>➔</span>
</div>

<div class="settings-item" onclick="openAllAttendanceSummaryReport('learning'); document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); let pLearn = document.getElementById('learningSummaryPage'); if(pLearn) pLearn.style.display = 'block';" style="background: #eff6ff; border-left: 5px solid #2563eb;">
  <span>8. 📖 የሚማሩ ተማሪዎች አቴንዳንስ ማጠቃለያ</span> <span>➔</span>
</div>

<div class="settings-item" onclick="openAllAttendanceSummaryReport('special'); document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); let pSpec = document.getElementById('specialSummaryReportPage'); if(pSpec) pSpec.style.display = 'block';" style="background: #fffbec; border-left: 5px solid #d4af37;">
  <span>9. 📜 ልዩ የትምህርት ሁኔታዎች (ዲቁና...) ማጠቃለያ</span> <span>➔</span>
</div>
     
      <div class="settings-item" onclick="navigateTo('dateRangeAttPage')">
        <span>9. 🔍 የአቴንዳንስ ሪከርድ ዕለታዊ ፍለጋ (በቀን መፈለጊያ)</span> <span>➔</span>
      </div>
    <button onclick="
  document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); 
  let rPage = document.getElementById('engagementReportPage');
  if(rPage) { rPage.style.display = 'block'; }
  openEngagementLevelReportMenu('engagementReportContainer');
" style="background:#1e293b; color:white; padding:14px 12px; border-radius:8px; width:100%; font-weight:bold; margin-bottom:10px; font-size:16px; border:none; cursor:pointer;">
  📊 የተሳትፎ ደረጃ ሪፖርት
</button>
<button onclick="
  document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
  let lPage = document.getElementById('leaveManagementPage'); 
  if(lPage) lPage.style.display = 'block';
" style="/* የእርስዎ የድሮ በተን ስታይል እዚህ ይቀጥላል... */">
  📋 የፈቃድ ቁጥጥር ማዕከልን ክፈት
</button>
<div class="settings-item" onclick="document.querySelectorAll('.app-page').forEach(p=>p.style.display='none'); document.getElementById('programPhotosPage').style.display='block'; renderProgramPhotos();" style="background: #f0fdfa; border-left: 5px solid #0d9488;">
  <span>10. 📸 የመርሃግብር ማስታወሻ ፎቶዎች ማከማቻ</span> <span>➔</span>
</div>
<div class="settings-item" onclick="navigateTo('videoGalleryPage')" style="background: #f0fdfa; border-left: 5px solid #0d9488;">
  <span>11. 🎥 የመርሀ ግብር ማስታወሻ ቪዲዮዎች</span>
  <span>➔</span>
</div> 
  <div class="settings-item" onclick="openPhotoGalleryPage(); navigateTo('photoGalleryPage');" style="background: #0ea5e9; color: white; border-left: 5px solid #facc15;">
        <span>12. 📸 ጠቅላላ ማስታወሻ ፎቶዎች ማዕከለ-ስዕላት (Gallery)</span> <span>➔</span>
      </div>
  <div class="settings-item" onclick="navigateToRipPage()" style="background: #1e293b; border-left: 5px solid #facc15; margin-bottom: 10px; padding: 12px; display: flex; justify-content: space-between; align-items: center; border-radius: 8px; cursor: pointer;">
  <span style="color: white; font-weight: bold;">13. 🪦 በእረፍተ ሥጋ የተለዩ ቅዱሳን ማህደር</span>
  <span style="color: #facc15;">➔</span>
</div>
 <div class="settings-item" onclick="changeLoginPasswordPrompt()">
        <span>14. 🔑 Change Login Password</span> <span>➔</span>
      </div>
      <div class="settings-item" onclick="changeAdminPasswordPrompt()">
        <span>15. 🔒 Change Admin Password</span> <span>➔</span>
      </div>
      <div style="background:#f1f5f9; padding:15px; border-radius:14px; border:2px solid #cbd5e1; margin-top:15px; margin-bottom:15px;">
        <label style="font-weight:bold; font-size:15px; display:block; margin-bottom:5px;">16. 🔐 የአድሚን ፓስወርድ ቁጥጥር (Admin Password Security)፦</label>
        <select id="adminSecurityToggle" onchange="onSecurityToggleChange()" style="background:white; font-weight:bold; border-color:#3b82f6; margin-top:5px;">
          <option value="OFF">📴 ጠፍቷል (No Passwords Required - OFF)</option>
          <option value="ON">🔏 የበራ (Ask Admin Password - ON)</option>
        </select>
      </div>
  
      <button class="cancel" onclick="closeCurrentPage()" style="margin-top:25px;">ተመለስ (Back)</button>
    </div>
  </div>
  <div id="reportPage" class="app-page" style="display:none;">
    <div id="reportContainer"></div>
</div>
<div id="reportPage" class="app-page" style="display:none;">
    <div id="reportContainer"></div>
</div>
  <div id="leaveManagementPage" class="app-page" style="display:none;">
  <div class="page-content" style="font-family: sans-serif; padding: 15px;">
    
    <button onclick="
      document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
      let sPage = document.getElementById('settingsPage'); 
      if(sPage) sPage.style.display = 'block';
    " style="background:#64748b; color:white; border:none; padding:8px 14px; border-radius:6px; cursor:pointer; font-weight:bold; margin-bottom:15px; margin-right:5px; font-size:12px;">
      ⬅️ ወደ ሴቲንግ ተመለስ
    </button>
    <h2 style="margin: 0 0 5px 0; color:#1e293b; font-size:22px; font-weight:bold;">📋 የፈቃድ ቁጥጥር ማዕከል</h2>
    <p style="font-size:13px; color:#64748b; margin:0 0 15px 0;">በፈቃድ ላይ ያሉ አባላትን ሁኔታ እዚህ ይቆጣጠሩ</p>
    
    <div style="margin-bottom:15px;">
      <input type="text" id="leaveSearchInput" onkeyup="searchLeaveStudents()" placeholder="በስም ፈልግ..." style="width:100%; padding:12px; border:2px solid #cbd5e1; border-radius:8px; font-size:15px; box-sizing: border-box;">
    </div>
    
    <div style="margin-bottom:20px;">
      <button onclick="renderLeaveTable()" style="background:#000000; color:#d4af37; border:1px solid #d4af37; padding:14px; border-radius:12px; font-weight:bold; cursor:pointer; font-size:15px; width:100%; text-align:center; box-shadow: 0 4px 6px rgba(0,0,0,0.1);">📋 አጠቃላይ ፈቃድ ላይ ያሉ አባላት ዝርዝር</button>
    </div>
    
    <div id="leaveTableAreaContainer"></div>

  </div>
</div>

 <div id="participationStatsPage" class="app-page">
  <div class="page-content">
    <h2>📊 Student Participation Summary</h2>
    
    <div style="background:#f8fafc; padding:15px; border-radius:12px; margin-bottom:15px; border:1px solid #cbd5e1;">
      <label style="color:#000000; font-weight:bold;">1. የተማሪዎች ምድብ ይምረጡ፦</label>
      
      <div style="display:flex; flex-direction:row; gap:6px; width:100%; margin-top:8px; margin-bottom:15px; justify-content:space-between;">
        <button type="button" onclick="loadPartStatsCategory('learning')" style="flex:1; padding:8px 4px; font-weight:bold; border-radius:6px; font-size:11px; text-align:center; background:#2563eb; color:white; border:none; cursor:pointer;">📖 የሚማሩ</button>
        <button type="button" onclick="loadPartStatsCategory('graduated')" style="flex:1; padding:8px 4px; font-weight:bold; border-radius:6px; font-size:11px; text-align:center; background:#2563eb; color:white; border:none; cursor:pointer;">🎓 ያጠናቀቁ</button>
        <button type="button" onclick="loadPartStatsCategory('other')" style="flex:1; padding:8px 4px; font-weight:bold; border-radius:6px; font-size:11px; text-align:center; background:#2563eb; color:white; border:none; cursor:pointer;">✨ ሌላ</button>
      </div>

      <div style="display:flex; gap:10px; margin-bottom:15px;">
  <div style="flex:1;">
    <label style="font-size:11px; font-weight:bold; color:#475569;">ከቀን፦</label>
    <input type="text" id="partStatsFromDate" readonly 
           placeholder="ቀን ይምረጡ..." 
           onclick="openGlobalCalendar('partStatsFromDate')" 
           style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px; background:white; cursor:pointer;">
  </div>
  <div style="flex:1;">
    <label style="font-size:11px; font-weight:bold; color:#475569;">እስከ፦</label>
    <input type="text" id="partStatsToDate" readonly 
           placeholder="ቀን ይምረጡ..." 
           onclick="openGlobalCalendar('partStatsToDate')" 
           style="width:100%; padding:10px; border:1px solid #cbd5e1; border-radius:8px; background:white; cursor:pointer;">
  </div>
</div>
    </div>

    <div style="background:#f8fafc; padding:15px; border-radius:12px; border:1px solid #cbd5e1;">
      <label style="color:#000000; font-weight:bold;">2. ተማሪ በስም ወይም በክፍል ይፈልጉ፦</label>
      <input id="partStatsSearch" type="text" placeholder="ስም ወይም ክፍል እዚህ ይጻፉ..." onkeyup="filterPartStatsSearch()" style="width:100%; padding:10px; margin-top:5px; border:1px solid #cbd5e1; border-radius:8px; box-sizing:border-box;">
      
      <div id="partStatsNamesListContainer" style="margin-top:10px; max-height:220px; overflow-y:auto; border-radius:8px; background:#f1f5f9; padding:5px;">
        <p style='color:#94a3b8; font-size:13px; text-align:center; padding:20px;'>እባክዎ መጀመሪያ ከላይ ካሉት በተኖች የአንዱን ምድብ ይምረጡ።</p>
      </div>
    </div>
      <div id="partTableActionButtons" class="hidden" style="display:none; gap:8px; margin-bottom:15px; flex-wrap:wrap;">
        <button type="button" class="view" onclick="printIndividualStatsTable()" style="flex:1; padding:10px; font-weight:bold; background:#0284c7; color:white; border:none; border-radius:6px; cursor:pointer;">🖨️ Print Report</button>
        <button type="button" class="add" onclick="downloadIndividualStatsExcel()" style="flex:1; padding:10px; font-weight:bold; background:#ea580c; color:white; border:none; border-radius:6px; cursor:pointer;">📥 Excel (CSV)</button>
      </div>
    <div class="card" style="background:white; padding:15px; border-radius:12px; box-shadow:0 4px 6px -1px rgba(0,0,0,0.1); margin-top:15px;">
      <h3 id="selectedPartStudentTitle" style="color:#1e293b; margin-top:0;">📊 የዕለታት ማጠቃለያ ሰንጠረዥ</h3>
      <div id="partStatsTableContainer" style="overflow-x:auto;">
        <p style='color:#94a3b8; text-align:center; padding:35px;'>እባክዎ ማጠቃለያውን ለማየት የተማሪ ስም ይጫኑ።</p>
      </div>
    </div>
    
    <button type="button" class="cancel" onclick="if(typeof closeCurrentPage === 'function') { closeCurrentPage(); } else { document.querySelectorAll('.app-page').forEach(p=>p.classList.add('hidden')); let d=document.getElementById('mainDashboard'); if(d)d.classList.remove('hidden'); }" style="margin-top:15px; width:100%; padding:12px; font-weight:bold; border-radius:8px; background:#64748b; color:white; border:none; cursor:pointer;">ተመለስ (Back)</button>
  </div>
</div>


<div id="reportPage" style="display:none;">
    <h2>ማዕረገ ክህነት ያላቸው አባላት ዝርዝር</h2>
    <div id="reportContainer"></div>
    <br>
    <button onclick="backToSettings()">⬅️ ተመለስ</button>
</div>
<div id="engagementReportPage" class="app-page" style="display:none; padding:15px; background:#f8fafc; min-height:100vh;">
  
  <button onclick="
    document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
    let sPage = document.getElementById('settingsPage'); 
    if(sPage) sPage.style.display = 'block';
  " style="background:#2563eb; color:white; border:none; padding:8px 16px; border-radius:6px; font-weight:bold; font-size:12px; cursor:pointer; margin-bottom:15px;">
    ⬅️ ወደ ሴቲንግ ተመለስ
  </button>

  <div id="engagementReportContainer"></div>
</div>



<div id="allListReportPage" class="app-page" style="display:none; background: #ffffff !important; box-shadow: none !important; max-width: 100% !important; width: 100% !important; height: 100vh; overflow-y: auto; padding: 10px !important; margin: 0 !important; box-sizing: border-box;">
  <div id="allReportTableContainer" style="width:100%;"></div>
</div>

<div id="activeListReportPage" class="app-page" style="display:none; background: #ffffff !important; box-shadow: none !important; max-width: 100% !important; width: 100% !important; height: 100vh; overflow-y: auto; padding: 10px !important; margin: 0 !important; box-sizing: border-box;">
  <div id="activeReportTableContainer" style="width:100%;"></div>
</div>

<div id="inactiveListReportPage" class="app-page" style="display:none; background: #ffffff !important; box-shadow: none !important; max-width: 100% !important; width: 100% !important; height: 100vh; overflow-y: auto; padding: 10px !important; margin: 0 !important; box-sizing: border-box;">
  <div id="inactiveReportTableContainer" style="width:100%;"></div>
</div>

  <div id="photoGalleryPage" class="app-page">
    <div class="page-content">
      <h2>📸 ማስታወሻ ፎቶዎች ማዕከле-ስዕላት</h2>
      <p style="color:#64748b;">በሲስተሙ ውስጥ የተመዘገቡ ተማሪዎችን ፎቶዎች እያሳለፉ እዚህ ማየትና ማውረድ ይችላሉ።</p>
      
      <div class="gallery-container">
        <div id="galleryInfo" class="gallery-info">ምንም ፎቶ የለም</div>
        <img id="galleryImg" class="gallery-img" src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 24 24' fill='none' stroke='%23cbd5e1' stroke-width='2'><circle cx='12' cy='8' r='4'/><path d='M6 21v-2a4 4 0 0 1 4-4h4a4 4 0 0 1 4 4v2'/></svg>" alt="ማስታወሻ ፎቶ">
        <div id="galleryStudentName" style="color:white; font-size:16px; margin-bottom:15px; font-weight:bold;">-</div>
        
        <div class="gallery-controls">
          <button class="sectionBtn" onclick="navigateGallery(-1)" style="margin-top:0; width:auto; padding:10px 20px;">◀ ወደ ኋላ</button>
          <button class="add" onclick="downloadGalleryPhoto()" style="margin-top:0; width:auto; padding:10px 20px;">📥 አውርድ (Download)</button>
          <button class="sectionBtn" onclick="navigateGallery(1)" style="margin-top:0; width:auto; padding:10px 20px;">ወደ ፊት ▶</button>
        </div>
      </div>
      
      <button class="cancel" onclick="closeCurrentPage()" style="margin-top:20px;">ተመለስ (Back)</button>
    </div>
  </div>
<div id="photoLightbox" class="lightbox" onclick="closeLightbox(event)">
  <button class="lightbox-btn" onclick="changePhoto(-1)" style="position: absolute; left: 20px; font-size: 24px; padding: 15px; background: rgba(255,255,255,0.2); color: white; border-radius: 50%; width: 60px; height: 60px;">❮</button>

  <img id="lightboxImg" src="" alt="Full Screen View" style="max-width: 85%; max-height: 75%; object-fit: contain;">
  <div style="color: white; font-weight: bold; margin-top: 10px; font-size: 18px;" id="lightboxTitle"></div>
  
  <button class="lightbox-btn" onclick="changePhoto(1)" style="position: absolute; right: 20px; font-size: 24px; padding: 15px; background: rgba(255,255,255,0.2); color: white; border-radius: 50%; width: 60px; height: 60px;">❯</button>

  <div class="lightbox-controls" onclick="event.stopPropagation();" style="margin-top: 20px;">
    <button class="lightbox-btn" id="lightboxDownloadBtn" style="background:#22c55e; color:white;">📥 አውርድ</button>
    <button class="lightbox-btn" style="background:#ef4444; color:white;" onclick="closeLightboxDirect()">✖ ዝጋ</button>
  </div>
</div>
<div id="videoGalleryPage" class="app-page">
  <div class="page-content">
    <h2 style="color: #0f172a; margin-bottom: 15px;">🎥 የመርሀ ግብር ቪዲዮዎች</h2>
    
    <div class="v-container">
      <div class="v-group">
        <label>አማራጭ 1፦ ቪዲዮ በኦንላይን ሊንክ (URL)፦</label>
        <input type="url" id="vLinkInput" placeholder="የቪዲዮውን ሊንክ እዚህ ይቅዱ...">
      </div>

      <div class="v-or">-- ወይም --</div>

      <div class="v-group">
        <label>አማራጭ 2፦ ቪዲዮ ከስልክ ማከማቻ፦</label>
        <input type="file" id="vFileInput" accept="video/*" style="border: 1px dashed #cbd5e1; padding: 5px;">
      </div>
      
      <hr style="border: 0; border-top: 1px solid #f1f5f9; margin: 10px 0;">
      
      <div class="v-group">
        <label>የቪዲዮው መግለጫ/ርዕስ፦</label>
        <input type="text" id="vCaptionInput" placeholder="የቪዲዮው ርዕስ...">
      </div>
<div class="v-group">
  <label>የቀረጸበት ቀን፦</label>
  <input
    type="text"
    id="vDateInput"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('vDateInput')"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div>
      
      <button class="add" onclick="saveNewVideo()" style="width: 100%; padding: 10px; font-weight: bold;">🚀 ቪዲዮውን አስቀምጥ (Save)</button>
    </div>

    <div id="vGalleryZone" class="v-grid"></div>
    
    <button class="cancel" onclick="closeCurrentPage()" style="margin-top:20px; width: 100%;">ተመለስ (Back)</button>
  </div>
</div>

<div id="vFullModal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #000000; z-index: 9999; align-items: center; justify-content: center; flex-direction: column;">
  
  <span onclick="closeVFull()" style="position: absolute; top: 20px; right: 25px; color: #ffffff; font-size: 50px; font-weight: bold; cursor: pointer; z-index: 10005; text-shadow: 0 2px 10px rgba(0,0,0,0.8);">&times;</span>
  
  <div style="text-align: center; width: 100%; height: 100%; display: flex; flex-direction: column; justify-content: center; align-items: center; position: relative;">
    
    <video id="vModalPlayer" controls style="width: 100%; height: 100%; object-fit: contain; background: black; display: none;"></video>
    
    <div id="iframeContainer" style="width: 100%; height: 100%; display: none; background: black;"></div>
    
    <div style="position: absolute; bottom: 40px; left: 0; width: 100%; text-align: center; background: linear-gradient(transparent, rgba(0,0,0,0.8)); padding: 20px 10px; pointer-events: none;">
      <p id="vModalCaption" style="color: #facc15; font-size: 18px; font-weight: bold; margin: 0 0 5px 0;"></p>
      <small id="vModalDate" style="color: #cbd5e1; display: block; font-size: 13px;"></small>
    </div>

    <div style="position: absolute; bottom: 120px; right: 20px; z-index: 10002;">
      <a id="vModalDownload" style="background: rgba(34, 197, 94, 0.85); color: white; text-decoration: none; padding: 8px 14px; border-radius: 6px; font-weight: bold; font-size: 12px; backdrop-filter: blur(4px);" download>⬇️ አውርድ</a>
    </div>

  </div>
</div>
  <div id="programPhotosPage" class="app-page" style="display: none;">
  <div class="modal-header" style="background: #0d9488; color: white; padding: 15px; display: flex; align-items: center;">
    <h3 style="margin: 0;">የማስታወሻ ፎቶዎች ማስተዳደሪያ</h3>
  </div>

  <div class="upload-section">
    <h4>አዲስ ፎቶ ይጫኑ</h4>
    <input type="file" id="photoInput" accept="image/*" multiple onchange="previewImages()">
    <div id="previewContainer" class="preview-container"></div>
    
    <input type="text" id="eventTitle" placeholder="የመርሀ ግብሩ ይዘት / ርዕስ (አማራጭ)">
    <input type="date" id="eventDate">
    
    <button class="btn-upload" onclick="savePhotos()">🚀 ፎቶዎችን አፕሎድ አርግ</button>
  </div>

  <div class="gallery-section">
    <h4>የተጫኑ መርሀ ግብሮች</h4>
    <div id="photoGallery" class="photo-gallery"></div>
  </div>

  <button class="cancel" onclick="document.querySelectorAll('.app-page').forEach(p=>p.style.display='none'); document.getElementById('settingsPage').style.display='block';" style="margin-top:25px; width: 100%;">ተመለስ (Back)</button>
</div>

<div id="imageViewerModal" class="viewer-modal">
  <div class="viewer-controls">
    <button class="control-btn close-btn" onclick="closeViewer()">❌ ዝጋ</button>
    <button class="control-btn download-btn" id="downloadBtn">📥 አውርድ</button>
  </div>
  <div class="viewer-content" onclick="toggleZoom(event)">
    <img id="viewerImage" src="" alt="Zoomable Image">
  </div>
  <div id="viewerCaption" class="viewer-caption"></div>
</div>
   <div id="singleStudentAttendancePage" class="app-page">
  <div class="page-content">
    <h2>👤 Single Student Attendance History</h2>
    
    <div style="background:#f8fafc; padding:15px; border-radius:12px; margin-bottom:15px; border:1px solid #cbd5e1;">
      <label><b>1. የተማሪዎች ምድብ ይምረጡ፦</b></label>
      <div style="display:flex; flex-direction:column; gap:10px; width:100%; margin-bottom:15px;">
        <button class="view" onclick="showCategoryInSingleAtt('learning')" style="width:100%; padding:12px; font-weight:bold; border-radius:10px; font-size:14px; text-align:center;">📖 ትምህርት የሚማሩ</button>
        <button class="add" onclick="showCategoryInSingleAtt('graduated')" style="width:100%; padding:12px; font-weight:bold; border-radius:10px; font-size:14px; text-align:center; background:#16a34a;">🎓 ትምህርት ያጠናቀቁ</button>
        <button class="view" onclick="showCategoryInSingleAtt('other')" style="width:100%; padding:12px; font-weight:bold; border-radius:10px; font-size:14px; text-align:center; background:#db2777; color:white; border:none;">✨ ሌላ የትምህርት ሁኔታ</button>
      </div>

      <label><b>2. ተማሪ በስም፣ በክፍል ወይም በስልክ ቁጥር ይፈልጉ፦</b></label>
      <input id="singleAttSearch" placeholder="የመጀመሪያ ፊደል፣ ክፍል ወይም ስልክ ቁጥር እዚህ ይጻፉ..." onkeyup="filterSingleAttStudents()">
      
      <div id="singleAttLearningContainer" style="margin-top:10px; max-height:200px; overflow-y:auto;"></div>
      <div id="singleAttCompletedContainer" style="margin-top:10px; max-height:200px; overflow-y:auto;"></div>
      <div id="singleAttOtherContainer" style="margin-top:10px; max-height:200px; overflow-y:auto;"></div>
    </div>

<div style="background:#f1f5f9; padding:15px; border-radius:12px; margin-bottom:15px; border:1px solid #e2e8f0;">
  <label style="display:block; margin-bottom:8px; font-weight:bold; color:#1e293b;">
    📅 በታሪክ ቀን መፈለጊያ (Date Filter)፦
  </label>

  <div style="display:flex; gap:10px; flex-wrap:wrap; align-items:center;">

    <div style="flex:1; min-width:120px;">
      <span style="font-size:11px; color:#64748b; display:block;">ከቀን (From)</span>
      <input
        type="text"
        id="singleAttFromDateInput"
        readonly
        placeholder="ቀን ይምረጡ..."
        onclick="openGlobalCalendar('singleAttFromDateInput')"
        onchange="onSingleAttDateFilterChange()"
        style="width:100%; padding:8px; border-radius:6px; border:1px solid #cbd5e1; font-size:13px; cursor:pointer; background:white;">
    </div>

    <div style="flex:1; min-width:120px;">
      <span style="font-size:11px; color:#64748b; display:block;">እስከ ቀን (To)</span>
      <input
        type="text"
        id="singleAttToDateInput"
        readonly
        placeholder="ቀን ይምረጡ..."
        onclick="openGlobalCalendar('singleAttToDateInput')"
        onchange="onSingleAttDateFilterChange()"
        style="width:100%; padding:8px; border-radius:6px; border:1px solid #cbd5e1; font-size:13px; cursor:pointer; background:white;">
    </div>

    <button
      onclick="clearSingleAttDateFilter()"
      style="padding:10px 15px; margin-top:15px; font-weight:bold; background:#ef4444; color:white; border:none; border-radius:6px; cursor:pointer; font-size:12px; flex-shrink:0;">
      ❌ Clear
    </button>

  </div>
</div>

    <div class="card">
      <h3 id="selectedStudentTitle" style="color:#1e293b;">የተማሪ አቴንዳንስ ታሪክ</h3>
      
      <div id="singleAttActions" class="hidden" style="display:flex; gap:8px; margin-bottom:15px; flex-wrap:wrap;">
        <button id="toggleEditAttBtn" class="view" onclick="toggleEditAttendanceMode()" style="flex:1; padding:10px; font-weight:bold; background:#475569;">✏️ Edit</button>
        <button id="saveEditedAttBtn" class="add hidden" onclick="saveEditedAttendanceData()" style="flex:1; padding:10px; font-weight:bold; background:#16a34a;">💾 Save Changes</button>
        <button class="view" onclick="printSingleStudentAttendance()" style="flex:1; padding:10px; font-weight:bold; background:#0284c7;">🖨️ Print</button>
        <button class="add" onclick="downloadSingleStudentExcel()" style="flex:1; padding:10px; font-weight:bold; background:#ea580c;">📥 Excel (CSV)</button>
      </div>
<button onclick="deleteStudentAttendanceHistory()"
style="background:#dc2626;color:white;padding:10px 16px;border:none;border-radius:8px;font-weight:bold;cursor:pointer;">
🗑 የአቴንዳንስ ታሪክ ሰርዝ
</button>
      <div id="singleAttTableContainer" style="overflow-x:auto;">
        <p style='color:#94a3b8; text-align:center; padding:35px;'>እባክዎ መጀመሪያ ከላይ ካሉት በተኖች አንዱን መርጠው ከሚመጣው ዝርዝር ላይ የተማሪ ስም ይምረጡ።</p>
      </div>
    </div>
    
    <button class="cancel" onclick="closeCurrentPage()" style="margin-top:15px; width:100%; padding:12px; font-weight:bold; border-radius:8px;">ተመለስ (Back)</button>
  </div>
</div>
<div id="learningSummaryPage" class="app-page" style="display:none;">
  <div class="page-content">
    <h2>📊 የሚማሩ ተማሪዎች አቴንዳንስ ማጠቃለያ</h2>
    <div style="background:#f8fafc; padding:15px; border-radius:14px; margin-bottom:15px; border:1px solid #cbd5e1;">
      <div style="display:grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap:10px;">
        <div>
          <label><b>በስም መፈለጊያ፦</b></label>
          <input id="searchLearningSummary" placeholder="ስም አስገብተው ይፈልጉ..." onkeyup="filterLearningSummaryTable()">
        </div>
        <div>
  <label><b>ከቀን፦</b></label>
  <input
    type="text"
    id="learningSumFrom"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('learningSumFrom')"
    onchange="filterLearningSummaryTable()"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div><div>
  <label><b>እስከ ቀን፦</b></label>
  <input
    type="text"
    id="learningSumTo"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('learningSumTo')"
    onchange="filterLearningSummaryTable()"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div>
      </div>
    </div>
    <button type="button" onclick="applyDateFilter()">🔍 ፈልግ</button>
    <div style="display:flex; gap:10px; margin-bottom:15px;">
      <button class="view" onclick="printAttendanceSummaryTable('learning')">🖨 Print Report</button>
      <button class="add" onclick="downloadAttendanceSummaryExcel('learning')">📥 Download Excel</button>
    </div>
    <div id="learningSummaryTableContainer" style="overflow-x:auto;"></div>
    
    <button class="cancel" onclick="document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); let sPage = document.getElementById('settingsPage'); if(sPage) sPage.style.display = 'block';" style="margin-top:20px;">ተመለስ (Back)</button>
  </div>
</div>

<div id="completedSummaryPage" class="app-page" style="display:none;">
  <div class="page-content">
    <h2>📊 ትምህርት ያጠናቀቁ ተማሪዎች አቴንዳንስ ማጠቃለያ</h2>
    <div style="background:#f8fafc; padding:15px; border-radius:14px; margin-bottom:15px; border:1px solid #cbd5e1;">
      <div style="display:grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap:10px;">
        <div>
          <label><b>በስም መፈለጊያ፦</b></label>
          <input id="searchCompletedSummary" placeholder="ስም አስገብተው ይፈልጉ..." onkeyup="filterCompletedSummaryTable()">
        </div>
        <div>
  <label><b>ከቀን፦</b></label>
  <input
    type="text"
    id="completedSumFrom"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('completedSumFrom')"
    onchange="filterCompletedSummaryTable()"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div><div>
  <label><b>እስከ ቀን፦</b></label>
  <input
    type="text"
    id="completedSumTo"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('completedSumTo')"
    onchange="filterCompletedSummaryTable()"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div>
</div>
</div>
    <div style="display:flex; gap:10px; margin-bottom:15px;">
      <button class="view" onclick="printAttendanceSummaryTable('completed')">🖨 Print Report</button>
      <button class="add" onclick="downloadAttendanceSummaryExcel('completed')">📥 Download Excel</button>
    </div>
    <div id="completedSummaryTableContainer" style="overflow-x:auto;"></div>
    
    <button class="cancel" onclick="document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); let sPage = document.getElementById('settingsPage'); if(sPage) sPage.style.display = 'block';" style="margin-top:20px;">ተመለስ (Back)</button>
  </div>
</div>
<div id="specialSummaryReportPage" class="app-page" style="display:none;">
  <div class="page-content">
    <h2>📊 ልዩ የትምህርት ሁኔታዎች አቴንዳንስ ማጠቃለያ</h2>
    <div style="background:#f8fafc; padding:15px; border-radius:14px; margin-bottom:15px; border:1px solid #cbd5e1;">
      <div style="display:grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap:10px;">
        <div>
          <label><b>በስም መፈለጊያ፦</b></label>
          <input id="searchSpecialSummary" placeholder="ስም አስገብተው ይፈልጉ..." onkeyup="filterSpecialSummaryTable()">
        </div>
        <div>
  <label><b>ከቀን፦</b></label>
  <input
    type="text"
    id="learningSumFrom"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('learningSumFrom')"
    onchange="filterLearningSummaryTable()"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div><div>
  <label><b>እስከ ቀን፦</b></label>
  <input
    type="text"
    id="learningSumTo"
    readonly
    placeholder="ቀን ይምረጡ..."
    onclick="openGlobalCalendar('learningSumTo')"
    onchange="filterLearningSummaryTable()"
    style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">
</div>
</div>
    </div>
    <div style="display:flex; gap:10px; margin-bottom:15px;">
      <button class="view" onclick="printAttendanceSummaryTable('special')">🖨 Print Report</button>
      <button class="add" onclick="downloadAttendanceSummaryExcel('special')">📥 Download Excel</button>
    </div>
    <div id="specialSummaryTableContainer" style="overflow-x:auto;"></div>
    
    <button class="cancel" onclick="document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none'); let sPage = document.getElementById('settingsPage'); if(sPage) sPage.style.display = 'block';" style="margin-top:20px;">ተመለስ (Back)</button>
  </div>
</div>

 
<div id="restInPeacePage" class="app-page" style="display: none;">
  <div class="page-content" style="background:#0f172a; color:white; border-radius:24px; padding: 20px; font-family: sans-serif;">
    
    <h2 style="text-align:center; color:#facc15; border-bottom: 2px dashed #334155; padding-bottom:15px; margin-bottom: 20px;">🪦 በእረፍተ ስጋ የተለዩ ቅዱሳን አባላት መታሰቢያ ማህደር</h2>

    <div style="display: flex; gap: 10px; margin-bottom: 20px; justify-content: space-between;">
      <div style="flex: 1; background: #1e293b; border: 1px solid #334155; padding: 10px; border-radius: 12px; text-align: center;">
        <span style="font-size: 11px; color: #94a3b8; display: block;">ጠቅላላ ቁጥር</span>
        <strong id="ripTotalCount" style="font-size: 20px; color: #facc15;">0</strong>
      </div>
      <div style="flex: 1; background: #1e293b; border: 1px solid #334155; padding: 10px; border-radius: 12px; text-align: center;">
        <span style="font-size: 11px; color: #94a3b8; display: block;">ወንድ</span>
        <strong id="ripMaleCount" style="font-size: 20px; color: #38bdf8;">0</strong>
      </div>
      <div style="flex: 1; background: #1e293b; border: 1px solid #334155; padding: 10px; border-radius: 12px; text-align: center;">
        <span style="font-size: 11px; color: #94a3b8; display: block;">ሴት</span>
        <strong id="ripFemaleCount" style="font-size: 20px; color: #f472b6;">0</strong>
      </div>
    </div>

    <div style="margin-bottom: 20px;">
      <input type="text" id="ripSearchInput" oninput="searchRipStudents()" placeholder="🔍 በስም ወይም በክርስትና ስም ይፈልጉ..." style="width: 100%; padding: 12px; border: 1px solid #334155; border-radius: 8px; font-size: 14px; background: #1e293b; color: white; outline: none;">
    </div>

    <div style="display: flex; gap: 10px; margin-bottom: 20px;">
      <button type="button" onclick="toggleRipSection('list')" style="flex: 1; padding: 12px; background: #0d9488; color: white; border: none; border-radius: 8px; font-weight: bold; cursor: pointer; font-size: 13px;">🖼️ አጠቃላይ ሊስት</button>
      <button type="button" onclick="toggleRipSection('table')" style="flex: 1; padding: 12px; background: #2563eb; color: white; border: none; border-radius: 8px; font-weight: bold; cursor: pointer; font-size: 13px;">📊 የሁሉም ስም ዝርዝር በአንድ ላይ</button>
    </div>

    <div class="rip-grid" id="ripContainer" style="display: none; grid-template-columns: repeat(auto-fill, minmax(100px, 1fr)); gap: 12px; margin-bottom: 20px;"></div>

    <div id="ripTableSection" style="display: none; background: #1e293b; padding: 15px; border-radius: 12px; border: 1px solid #334155;">
      <div style="display: flex; gap: 8px; margin-bottom: 15px; justify-content: flex-end;">
        <button onclick="exportRipToExcel()" style="background: #16a34a; color: white; border: none; padding: 6px 12px; border-radius: 6px; font-size: 12px; font-weight: bold; cursor: pointer;">Excel አውርድ</button>
        <button onclick="printRipTable()" style="background: #475569; color: white; border: none; padding: 6px 12px; border-radius: 6px; font-size: 12px; font-weight: bold; cursor: pointer;">ፕሪንት (Print)</button>
      </div>
      <div style="overflow-x: auto;">
        <table id="ripReportTable" style="width: 100%; border-collapse: collapse; text-align: left; font-size: 13px; color: white;">
          <thead>
            <tr style="background: #0f172a; border-bottom: 2px solid #334155; color: #facc15;">
              <th style="padding: 10px; border-right: 1px solid #334155;">ተ.ቁ</th>
              <th style="padding: 10px; border-right: 1px solid #334155;">ሙሉ ስም</th>
              <th style="padding: 10px; border-right: 1px solid #334155;">የክርስትና ስም</th>
              <th style="padding: 10px; border-right: 1px solid #334155;">የተመዘገቡበት ቀን</th>
              <th style="padding: 10px; border-right: 1px solid #334155;">ያረፉበት ቀን</th>
              <th style="padding: 10px; border-right: 1px solid #334155;">ያገለገሉበት ክፍል</th>
              <th style="padding: 10px;">የትምህርት ደረጃ</th>
            </tr>
          </thead>
          <tbody id="ripTableBody"></tbody>
        </table>
      </div>
    </div>

    <button class="cancel" onclick="closeCurrentPage()" style="margin-top:30px; background:#334155; width: 100%; padding: 12px; color: white; border: none; border-radius: 8px; font-weight: bold;">ተመለስ (Back)</button>
  </div>
</div>

<div id="ripDetailModal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 99999; align-items: center; justify-content: center; padding: 20px;">
  <div style="background: #1e293b; color: white; border-radius: 16px; width: 100%; max-width: 350px; padding: 20px; position: relative; border: 1px solid #334155; max-height: 90vh; overflow-y: auto;">
    <span onclick="closeRipDetailModal()" style="position: absolute; top: 10px; right: 15px; font-size: 28px; font-weight: bold; color: #94a3b8; cursor: pointer;">&times;</span>
    
    <h3 style="color: #facc15; text-align: center; margin-top: 5px; margin-bottom: 15px;">የአባል ሙሉ መረጃ</h3>
    
    <div style="text-align: center; margin-bottom: 15px;">
      <img id="modalRipPhoto" src="" style="width: 130px; height: 130px; object-fit: cover; border: 3px solid #facc15; border-radius: 8px; background: #0f172a;">
    </div>

    <div id="modalRipDetails" style="font-size: 13px; line-height: 1.8; background: #0f172a; padding: 15px; border-radius: 10px; border: 1px solid #334155; margin-bottom: 15px;"></div>
    
    <button type="button" id="modalRipNavBtn" style="width: 100%; padding: 12px; background: #facc15; color: #0f172a; border: none; border-radius: 8px; font-weight: bold; cursor: pointer;">👤 ወደ ዋናው ፕሮፋይል ሂድ</button>
  </div>
</div>

<div id="dateRangeAttPage" class="app-page">
  <div class="page-content">
    <h2>🔍 የአቴንዳንስ ሪከርድ ዕለታዊ ፍለጋ (በቀን መፈለጊያ)</h2>

    <label>ከቀን (From Date)፦</label>
    <input
      type="text"
      id="searchFromDate"
      readonly
      placeholder="ቀን ይምረጡ..."
      onclick="openGlobalCalendar('searchFromDate')"
      style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">

    <label>እስከ ቀን (To Date)፦</label>
    <input
      type="text"
      id="searchToDate"
      readonly
      placeholder="ቀን ይምረጡ..."
      onclick="openGlobalCalendar('searchToDate')"
      style="width:100%; padding:8px; border:1px solid #cbd5e1; border-radius:6px; cursor:pointer; background:white;">

    <button class="view" onclick="searchAttendanceRange()" style="margin-top:15px;">
      🔍 ፈልግ
    </button>
      <div id="rangeResultSection" class="hidden" style="margin-top:20px;">
        <div style="display:flex; gap:10px; margin-bottom:15px;">
          <button class="edit" onclick="printRangeReport()">🖨 አትም</button>
          <button class="add" onclick="downloadRangeReportExcel()">📥 Excel አውርድ</button>
        </div>
        <div id="rangeTableContainer" style="overflow-x:auto;"></div>
      </div>
      <button class="cancel" onclick="closeCurrentPage()" style="margin-top:25px;">ተመለስ (Back)</button>
    </div>
  </div>

  <div id="profilePage" class="app-page" style="z-index: 500;">
    <div class="page-content" style="max-width: 850px;">
      <div id="printableProfileArea" style="background: white; color: #111827; border-radius: 24px;">
        <img id="pImg" src="" alt="Profile" style="width: 150px; height: 150px; border-radius: 8px; object-fit: cover; display: block; margin: auto; margin-bottom: 18px; border: 4px solid #3b82f6;">
        <p id="pChristian" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px; font-weight:bold; color:#2563eb;"></p>
        <p id="pName" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <p id="pGender" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <p id="pBirthDate" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <p id="pPhone" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <p id="pFamily" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
<p id="pDate" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>

<p id="pRank" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
<p id="pLevel" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
<p id="pClass" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <p id="pCurrent" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <p id="pCurrentServing" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        
        <div class="settings-item" onclick="toggleElement('prevBox2')">📚 Previous Classes <span>⬇</span></div>
        <div id="prevBox2" class="hidden card">
          <ul id="pPrev" style="list-style:none; padding:0; margin:0;"></ul>
        </div>
        <div class="settings-item" onclick="toggleElement('addressView')">📍 Address <span>⬇</span></div>
        <div id="addressView" class="hidden card">
          <p id="pCity"></p><p id="pSub"></p><p id="pWoreda"></p><p id="pArea"></p><p id="pHouse"></p>
        </div>
        <p id="pBehavior" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px;"></p>
        <h3>📊 Extra Metrics</h3>
        <p id="pPart" style="background: #f0fdf4; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #bbf7d0; font-size:15px; font-weight:bold; color: #16a34a;"></p>
        <p id="pStatus" style="background: #eff6ff; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #bfdbfe; font-size:15px; font-weight:bold; color: #2563eb;"></p>
        
        <div id="pReasonContainer" style="background: #f8fafc; padding:12px; border-radius:10px; margin-top:5px; border:1px solid #e5e7eb; font-size:15px; display:none;">
          <p id="pReason" style="margin:0;"></p>
          <p id="pReasonDetail" style="margin:5px 0 0 0; font-weight:bold; color:#2563eb;"></p>
        </div>
      </div>
        
      <div style="margin-top: 20px; display: flex; gap: 10px; flex-wrap:wrap;">
        <button class="cancel" onclick="closeProfile()" style="flex:1;">Back (ተመለስ)</button>
        <button class="view" id="printProfileBtn" style="flex:1;">🖨 Print Profile</button>
        <button class="edit" id="editBtn" style="flex:1;">Edit (አስተካክል)</button>
        <button class="del" id="idDelBtn" style="flex:1;">Delete (ሰርዝ)</button>
      </div>
    </div>
  </div>

  <div id="printArea" class="hidden"></div>
<div id="globalEthioCalendarModal" style="display:none; position:fixed; z-index:999999; background:white; border-radius:12px; width:280px; box-shadow:0 10px 30px rgba(0,0,0,0.3); padding:15px; top:50%; left:50%; transform:translate(-50%, -50%); border:1px solid #cbd5e1;">
  <div style="display:flex; gap:5px; margin-bottom:10px;">
    <select id="ethioMonthSelect" onchange="renderCalendar()" style="flex:2; padding:8px;">
      <option value="1">መስከረም</option><option value="2">ጥቅምት</option><option value="3">ህዳር</option>
      <option value="4">ታህሳስ</option><option value="5">ጥር</option><option value="6">የካቲት</option>
      <option value="7">መጋቢት</option><option value="8">ሚያዚያ</option><option value="9">ግንቦት</option>
      <option value="10">ሰኔ</option><option value="11">ሐምሌ</option><option value="12">ነሐሴ</option>
      <option value="13">ጳጉሜ</option>
    </select>
    <select id="ethioYearSelect" onchange="renderCalendar()" style="flex:1; padding:8px;"></select>
  </div>
  <div id="calendarGrid" style="display:grid; grid-template-columns:repeat(5, 1fr); gap:4px; max-height:200px; overflow-y:auto; padding:5px;"></div>
  <button type="button" onclick="document.getElementById('globalEthioCalendarModal').style.display='none'" style="width:100%; margin-top:10px; padding:8px; background:#64748b; color:white; border:none; border-radius:6px;">ዝጋ</button>
</div>
  <script>
    const DEFAULT_LOGIN_PASS = "1234";
    const DEFAULT_ADMIN_PASS = "7216";
    
    let students = JSON.parse(localStorage.getItem("students")) || [];
    let attendanceRecords = JSON.parse(localStorage.getItem("attendanceRecords")) || [];
    let adminSecurityMode = localStorage.getItem("ADMIN_SECURITY_MODE") || "OFF";
    let currentPartStatsCategory = ""; 
    let currentAttCategoryChoice = ""; 
    let editId = null; let photoData = ""; let pageHistory = [];
    let isEditAttendanceMode = false;
    let selectedSingleStudentId = "";
    
    // ለጋለሪ አገልግሎት የሚውሉ ተለዋዋጮች
    let galleryStudents = [];
    let galleryIndex = 0;

    window.onload = function() {
      if(sessionStorage.getItem("isLoggedIn") === "true") {
        document.getElementById("loginPage").style.display = "none";
        document.getElementById("app").style.display = "block";
      }
      if(document.getElementById("adminSecurityToggle")) {
        document.getElementById("adminSecurityToggle").value = adminSecurityMode;
      }
      let today = new Date().toISOString().split('T')[0];
      if(document.getElementById("regDate")) document.getElementById("regDate").value = today;
      if(document.getElementById("attDate")) document.getElementById("attDate").value = today;
      recalculateAllMetrics();

      document.getElementById("photo").addEventListener("change", function(e) {
        let file = e.target.files[0];
        if(file) {
          let reader = new FileReader();
          reader.onload = function(event) {
            photoData = event.target.result;
            document.getElementById("preview").src = photoData;
            document.getElementById("preview").style.display = "block";
          };
          reader.readAsDataURL(file);
        }
      });
    }

    function getLoginPassword(){ return localStorage.getItem("LOGIN_PASS") || DEFAULT_LOGIN_PASS; }
    function getAdminPassword(){ return localStorage.getItem("ADMIN_PASS") || DEFAULT_ADMIN_PASS; }
    
    function checkLoginPass() {
      let val = document.getElementById("loginPassInput").value;
      if(val === getLoginPassword()) {
        sessionStorage.setItem("isLoggedIn", "true");
        document.getElementById("loginPage").style.display = "none";
        document.getElementById("app").style.display = "block";
      } else {
        alert("የተሳሳተ የሎጊን ፓስወርድ ነው! እባክዎ እንደገና ይሞክሩ።");
      }
    }

    function changeLoginPasswordPrompt() {
      let oldP = prompt("እባክዎ የድሮውን ሎጊን ፓስወርድ ያስገቡ፦");
      if(oldP !== getLoginPassword()){ alert("የድሮው ሎጊን ፓስወርድ ስህተት ነው!"); return; }
      let newP = prompt("እባክዎ አዲሱን ሎጊን ፓስወርድ ያስገቡ፦");
      if(!newP) { alert("ትክክለኛ ፓስወርድ አልገባቸውም!"); return; }
      localStorage.setItem("LOGIN_PASS", newP);
      alert("የሎጊን ፓስወርድ በተሳካ ሁኔታ ተቀይሯል!");
    }

    function askAdminPassword(){
      if (adminSecurityMode === "OFF") return true;
      let p = prompt("ስራውን ለመፈጸም የAdmin ፓስወርድ ያስገቡ (Enter Admin Password):");
      return p === getAdminPassword();
    }

    function onSecurityToggleChange() {
      let selectedVal = document.getElementById("adminSecurityToggle").value;
      if (selectedVal === "ON") {
        let p = prompt("የአድሚን ፓስወርድ መቆለፊያውን ለማብራት እባክዎ የአሁኑን ፓስወርድ ያስገቡ፦");
        if (p === getAdminPassword()) {
          adminSecurityMode = "ON";
          localStorage.setItem("ADMIN_SECURITY_MODE", "ON");
          alert("የአድሚን ፓስወርድ መቆለፊያ በርቷል (ON)!");
        } else {
          alert("ፓስወርድ የተሳሳተ ነው!");
          document.getElementById("adminSecurityToggle").value = "OFF";
        }
      } else {
        adminSecurityMode = "OFF";
        localStorage.setItem("ADMIN_SECURITY_MODE", "OFF");
        alert("የአድሚን ፓስወርድ ቁጥጥር ጠፍቷል (OFF)!");
      }
    }

    function changeAdminPasswordPrompt() {
      let oldP = prompt("እባክዎ የድሮውን አድሚን ፓስወርድ ያስገቡ፦");
      if(oldP !== getAdminPassword()){ alert("የድሮው አድሚን ፓስወርድ ስህተት ነው!"); return; }
      let newP = prompt("እባክዎ አዲሱን አድሚን ፓስወርድ ያስገቡ፦");
      if(!newP) return;
      localStorage.setItem("ADMIN_PASS", newP);
      alert("የአድሚን ፓስወርድ በተሳካ ሁኔታ ተቀይሯል!");
    }

    function navigateTo(pageId) {
      if (pageId === 'addStudentPage' && editId === null) {
        if(!askAdminPassword()){ alert("ፓስወርድ የተሳሳተ ነው!"); return; }
        clearForm();
        document.getElementById("formTitle").innerText = "አዲስ ተማሪ መመዝገቢያ ፎርም";
      }
      if(pageId === 'attendancePage') {
        document.getElementById("attendanceSheet").classList.add("hidden");
        currentAttCategoryChoice = ""; 
      }
      let pages = document.querySelectorAll('.app-page');
      pages.forEach(p => p.style.display = 'none');
      document.getElementById(pageId).style.display = 'block';
      pageHistory.push(pageId);
    }

    function closeCurrentPage() {
      pageHistory.pop();
      let currentPages = document.querySelectorAll('.app-page');
      currentPages.forEach(p => p.style.display = 'none');
      if (pageHistory.length > 0) {
        document.getElementById(pageHistory[pageHistory.length - 1]).style.display = 'block';
      } else {
        recalculateAllMetrics();
      }
    }

    function openAllStudentsPage() { navigateTo('allStudentsPage'); showAllStudents(); }
    function toggleElement(id) { document.getElementById(id).classList.toggle("hidden"); }
    function togglePartStats() { document.getElementById("partStats").classList.toggle("hidden"); }
    function toggleProgClassSelect() {
      let type = document.getElementById("attProgramType").value;
      document.getElementById("progClassBox").className = (type === "ትምህርት") ? "" : "hidden";
    }

    function checkClsChoice(){
      let val = document.getElementById("cls").value;
      if(val === "ሌላ") document.getElementById("clsOtherText").style.display = "block";
      else { document.getElementById("clsOtherText").style.display = "none"; document.getElementById("clsOtherText").value = ""; }
    }

    // 💡 1. ምርጫው ሲቀየር ሳጥኖቹን ብቅ/ድብቅ የሚያደርግ ፈንክሽን
function checkReason(){
  let val = document.getElementById("reason").value;
  
  if(val == "ፈቃድ" || val == "other") {
    document.getElementById("reasonText").style.display = "block";
  } else { 
    document.getElementById("reasonText").style.display = "none"; 
    document.getElementById("reasonText").value = ""; 
  }
  
  if(val == "ፈቃድ") {
    if(document.getElementById("leaveDetailsBox")) {
      document.getElementById("leaveDetailsBox").style.display = "block";
    }
  } else {
    // ፈቃድ ካልሆነ ሳጥኑን በራስ-ሰር ይሰበስባል (ይደብቃል)
    if(document.getElementById("leaveDetailsBox")) {
      document.getElementById("leaveDetailsBox").style.display = "none";
      if(document.getElementById("leaveStartDate")) document.getElementById("leaveStartDate").value = "";
      if(document.getElementById("leaveEndDate")) document.getElementById("leaveEndDate").value = "";
      document.querySelectorAll('input[name="leavePrograms"]').forEach(cb => cb.checked = false);
    }
  }
  
  if(val == "በእረፍተ ስጋ") {
    document.getElementById("restDateBox").style.display = "block";
  } else { 
    document.getElementById("restDateBox").style.display = "none"; 
    document.getElementById("restInPeaceDate").value = ""; 
  }
}

// 💡 2. ምዝገባ ሲያልቅ ፎርሙን በራስ-ሰር ሰብስቦ ወደ መደበኛ የሚመልስ ፈንክሽን (ይህንን ኮድ የእርስዎ ሴቭ ማድረጊያ መጨረሻ ላይ ያክሉት)
function resetLeaveFormFields() {
  document.getElementById("reason").value = "የለም";
  document.getElementById("reasonText").value = "";
  document.getElementById("reasonText").style.display = "none";
  
  if(document.getElementById("leaveDetailsBox")) {
    document.getElementById("leaveDetailsBox").style.display = "none"; // ሳጥኑን በራስ-ሰር ይሰበስባል
  }
  if(document.getElementById("leaveStartDate")) document.getElementById("leaveStartDate").value = "";
  if(document.getElementById("leaveEndDate")) document.getElementById("leaveEndDate").value = "";
  
  document.querySelectorAll('input[name="leavePrograms"]').forEach(cb => {
    cb.checked = false;
  });
}

    function clearForm(){
  document.getElementById("name").value = "";
  document.getElementById("christianName").value = "";
  document.getElementById("phone").value = "";
  document.getElementById("familyPhone").value = "";
  document.getElementById("studentRank").value = "";
  document.getElementById("studentLevel").value = "";
  document.getElementById("cls").value = "";
  document.getElementById("clsOtherText").value = "";
  document.getElementById("clsOtherText").style.display = "none";
      document.getElementById("currentClass").value = "";
      document.getElementById("gender").value = "";
      document.getElementById("birthDate").value = "";
      document.getElementById("studentBehavior").value = "";
      document.getElementById("currentServingDept").value = "";
      document.getElementById("p1").value = ""; document.getElementById("p2").value = "";
      document.getElementById("p3").value = ""; document.getElementById("p4").value = "";
      document.getElementById("p5").value = "";
      document.getElementById("city").value = ""; document.getElementById("subcity").value = "";
      document.getElementById("woreda").value = ""; document.getElementById("area").value = "";
      document.getElementById("house").value = "";
      document.getElementById("reason").value = "የለም";
      document.getElementById("reasonText").value = "";
      document.getElementById("reasonText").style.display = "none";
      document.getElementById("restInPeaceDate").value = "";
      document.getElementById("restDateBox").style.display = "none";
      document.getElementById("photo").value = "";
      document.getElementById("preview").src = "";
      document.getElementById("preview").style.display = "none";
      photoData = "";
    }

    function save(){
  let name = document.getElementById("name").value.trim();
  let phone = document.getElementById("phone").value.trim();
  let clsValue = document.getElementById("cls").value;

  if(!name || !phone || !clsValue){
    alert("እባክዎ ግዴታ የሆኑ መረጃዎችን በትክክል ይሙሉ!");
    return;
  }

  if(clsValue === "ሌላ"){
    let ot = document.getElementById("clsOtherText").value.trim();
    if(!ot){
      alert("እባክዎ የሌላ ክፍሉን ስም ይፃፉ!");
      return;
    }
    clsValue = ot;
  }

  let stObj = {
    id: editId ? editId : Date.now().toString(),
    name: name,
    christianName: document.getElementById("christianName").value.trim(),
    phone: phone,
    familyPhone: document.getElementById("familyPhone").value.trim(),
    rank: document.getElementById("studentRank").value.trim(),
    cls: clsValue,
    level: document.getElementById("studentLevel").value.trim(),
    regDate: document.getElementById("regDate").value,
    behavior: document.getElementById("studentBehavior").value.trim(),
    currentClass: document.getElementById("currentClass").value.trim(),
        gender: document.getElementById("gender").value,
        birthDate: document.getElementById("birthDate").value,
        currentServingDept: document.getElementById("currentServingDept").value.trim(),
        prevClasses: [
          document.getElementById("p1").value.trim(), document.getElementById("p2").value.trim(),
          document.getElementById("p3").value.trim(), document.getElementById("p4").value.trim(),
          document.getElementById("p5").value.trim()
        ].filter(x => x !== ""),
        address: {
          city: document.getElementById("city").value.trim(),
          subcity: document.getElementById("subcity").value.trim(),
          woreda: document.getElementById("woreda").value.trim(),
          area: document.getElementById("area").value.trim(),
          house: document.getElementById("house").value.trim()
        },
        reason: document.getElementById("reason").value,
reasonDetail: document.getElementById("reasonText").value.trim(),
// 💡 አዲሶቹን መረጃዎች በጀርባ ማኅደር ውስጥ ያቆያል
leaveStartDate: document.getElementById("leaveStartDate") ? document.getElementById("leaveStartDate").value : "",
leaveEndDate: document.getElementById("leaveEndDate") ? document.getElementById("leaveEndDate").value : "",
leavePrograms: (() => {
  let checkedProgs = [];
  let checkboxes = document.querySelectorAll('input[name="leavePrograms"]:checked');
  checkboxes.forEach(cb => checkedProgs.push(cb.value));
  return checkedProgs; // የመረጣቸውን እስከ 7 መርሐግብራት ዝርዝር ይይዛል
})(),
        restInPeaceDate: document.getElementById("restInPeaceDate").value,
        photo: photoData
      };

      if(editId){
        let idx = students.findIndex(s => s.id === editId);
        if(idx !== -1) students[idx] = stObj;
        alert("የተማሪው መረጃ ተስተካክሏል!");
      } else {
        students.push(stObj);
        alert("አዲስ ተማሪ ተመዝግቧል!");
      }
      localStorage.setItem("students", JSON.stringify(students));
      editId = null;
      clearForm();
      closeCurrentPage();
    }

    function sortAmharic(arr) {
      return arr.sort((a, b) => a.name.localeCompare(b.name, 'am'));
    }

    function showAllStudents(){
      let html = "";
      if(students.length === 0){
        document.getElementById("list").innerHTML = "<p style='text-align:center;'>ምንም የተመዘገበ ተማሪ የለም!</p>";
        return;
      }
      let sorted = sortAmharic([...students]);
      sorted.forEach(s => {
        html += `
          <div class="studentCard">
            <div style="display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:10px;">
              <div>
                <strong>👤 ስም፦ ${s.name} ${s.christianName ? '('+s.christianName+')':''}</strong><br>
                📞 ስልክ፦ ${s.phone} | 📚 ክፍል፦ ${s.cls} | ⛪ ክፍል ማህደር፦ ${s.currentServingDept || '-'}
              </div>
              <div>
                <button class="view" style="width:auto; padding:6px 14px; margin-top:0;" onclick="viewStudentProfile('${s.id}')">👁 Profile</button>
              </div>
            </div>
          </div>
        `;
      });
      document.getElementById("list").innerHTML = html;
    }

    function renderListSearch(){
      let query = document.getElementById("search").value.toLowerCase();
      let filtered = students.filter(s => 
        s.name.toLowerCase().includes(query) || 
        (s.christianName && s.christianName.toLowerCase().includes(query)) ||
        s.phone.includes(query) || s.cls.toLowerCase().includes(query) ||
        (s.currentServingDept && s.currentServingDept.toLowerCase().includes(query))
      );
      let html = "";
      if(filtered.length === 0){
        document.getElementById("list").innerHTML = "<p style='text-align:center;'>የፈለጉት ተማሪ አልተገኘም!</p>";
        return;
      }
      let sorted = sortAmharic(filtered);
      sorted.forEach(s => {
        html += `
          <div class="studentCard">
            <div style="display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:10px;">
              <div>
                <strong>👤 ስም፦ ${s.name} ${s.christianName ? '('+s.christianName+')':''}</strong><br>
                📞 ስልክ፦ ${s.phone} | 📚 ክፍል፦ ${s.cls} | ⛪ ክፍል ማህደር፦ ${s.currentServingDept || '-'}
              </div>
              <div>
                <button class="view" style="width:auto; padding:6px 14px; margin-top:0;" onclick="viewStudentProfile('${s.id}')">👁 Profile</button>
              </div>
            </div>
          </div>
        `;
      });
      document.getElementById("list").innerHTML = html;
    }
function viewStudentProfile(id){
  let s = students.find(x => x.id === id);
  if(!s) return;
  document.getElementById("pImg").src = s.photo ? s.photo : "";
  document.getElementById("pImg").style.display = s.photo ? "block" : "none";
  
  document.getElementById("pChristian").innerHTML = `<b>⛪ ክርስትና ስም፦</b> ${s.christianName || 'የለም'}`;
  document.getElementById("pName").innerHTML = `<b>👤 ሙሉ ስም፦</b> ${s.name}`;
  document.getElementById("pGender").innerHTML = `<b>👫 ጾታ፦</b> ${s.gender === 'Male' ? 'ወንድ' : 'ሴት'}`;
  document.getElementById("pPhone").innerHTML = `<b>📞 የግል ስልክ፦</b> ${s.phone}`;
  document.getElementById("pFamily").innerHTML = `<b>📞 የቤተሰብ ስልክ፦</b> ${s.familyPhone || 'የለም'}`;
  document.getElementById("pDate").innerHTML = `<b>📅 የምዝገባ ቀን፦</b> ${s.regDate || 'የለም'}`;
document.getElementById("pRank").innerHTML = `<b>🎖 ማዕረገ ክህነት፦</b> ${s.rank || 'የለም'}`;
if(document.getElementById("pBirthDate")){
  document.getElementById("pBirthDate").innerHTML =
    `<b>🎂 የትውልድ ቀን፦</b> ${s.birthDate ? s.birthDate : "የለም"}`;
}
document.getElementById("pBehavior").innerHTML = `<b>🌿 የፀባይ ሁኔታ፦</b> ${s.behavior || 'የለም'}`;
document.getElementById("pLevel").innerHTML = `<b>📘 በሰንበት ት/ቤት ያሉበት መደብ፦</b> ${s.level || 'የለም'}`;
  document.getElementById("pClass").innerHTML = `<b>📚 ክፍል፦</b> ${s.cls}`;
  document.getElementById("pCurrent").innerHTML = `<b>🎓 የውጭ ትምህርት ደረጃ፦</b> ${s.currentClass || 'የለም'}`;
  document.getElementById("pCurrentServing").innerHTML = `<b>⛪ አሁን እያገለገሉበት ያለው ክፍል፦</b> ${s.currentServingDept || 'የለም'}`;

  let pPrevLi = "";
  if(s.prevClasses && s.prevClasses.length > 0){
    s.prevClasses.forEach(c => { pPrevLi += `<li>🔹 ${c}</li>`; });
  } else { pPrevLi = "<li>ምንም የለም</li>"; }
  document.getElementById("pPrev").innerHTML = pPrevLi;

  // የአድራሻ መረጃዎችን ማውጫ
  let city = s.address?.city || (s.city || '-');
  let subcity = s.address?.subcity || (s.subcity || '-');
  let woreda = s.address?.woreda || (s.woreda || '-');
  let area = s.address?.area || (s.area || '-');
  let house = s.address?.house || (s.house || '-');

  document.getElementById("pCity").innerHTML = `<b>ከተማ፦</b> ${city}`;
  document.getElementById("pSub").innerHTML = `<b>ክፍለ ከተማ፦</b> ${subcity}`;
  document.getElementById("pWoreda").innerHTML = `<b>ወረዳ፦</b> ${woreda}`;
  document.getElementById("pArea").innerHTML = `<b>ልዩ ቦታ፦</b> ${area}`;
  document.getElementById("pHouse").innerHTML = `<b>የቤት ቁጥር፦</b> ${house}`;

  let metrics = calculateSingleStudentMetrics(id);
  document.getElementById("pPart").innerHTML = `📈 አጠቃላይ ተሳትፎ፦ ${metrics.rate}% (${metrics.level})`;
  document.getElementById("pStatus").innerHTML = `🟢 ሁኔታ (Status)፦ ${metrics.status}`;

  if(s.reason && s.reason !== "የለም"){
  document.getElementById("pReasonContainer").style.display = "block";
  
  if(s.reason === "ፈቃድ") {
  let statusBadge = "";
  let countdownText = "";
  let programsList =
    (s.leavePrograms && s.leavePrograms.length > 0)
      ? s.leavePrograms.join(", ")
      : "አልተጠቀሰም";

  if(s.leaveStartDate && s.leaveEndDate) {

  let endParts = s.leaveEndDate.split("/");

  let endNum =
    (parseInt(endParts[2]) * 365) +
    (parseInt(endParts[1]) * 30) +
    parseInt(endParts[0]);

  // 💡 ዛሬን በኢትዮጵያ ቀን አስገባ
  let todayDay = 17;   // ሰኔ 16
  let todayMonth = 10; // ሰኔ = 10
  let todayYear = 2018;

  let todayNum =
    (todayYear * 365) +
    (todayMonth * 30) +
    todayDay;

  let daysLeft = endNum - todayNum;

  if(daysLeft < 0) {

      statusBadge = `<span style="color:#ef4444; font-weight:bold; background:#fee2e2; padding:2px 6px; border-radius:4px;">❌ ፈቃዱ አብቅቷል!</span>`;
      countdownText = `<p style="margin:5px 0; color:#ef4444;"><b>የማብቂያ ሁኔታ፦</b> ፈቃዱ ካለፈ ${Math.abs(daysLeft)} ቀን ሆኗል።</p>`;
    } 
    else if(daysLeft <= 10) {
      statusBadge = `<span style="color:#d97706; font-weight:bold; background:#fef3c7; padding:2px 6px; border-radius:4px;">⚠️ የመመለሻ ጊዜ ደርሷል</span>`;
      countdownText = `<p style="margin:5px 0; color:#d97706;"><b>ቀሪ ቀናት፦</b> ${daysLeft} ቀን ቀርቷል</p>`;
    } 
    else {
      statusBadge = `<span style="color:#16a34a; font-weight:bold; background:#dcfce7; padding:2px 6px; border-radius:4px;">🟢 በፈቃድ ላይ ያለ</span>`;
      countdownText = `<p style="margin:5px 0; color:#16a34a;"><b>ቀሪ ቀናት፦</b> ${daysLeft} ቀናት ይቀራሉ</p>`;
    }

  document.getElementById("pReason").innerHTML =
    `⚠️ <b>የራቁበት ምክንያት፦</b> ${s.reason} ${statusBadge}`;

  document.getElementById("pReasonDetail").innerHTML = `
    <div style="margin-top:8px;">
      <button onclick="document.getElementById('toggleLeaveDetails').style.display =
        (document.getElementById('toggleLeaveDetails').style.display === 'none'
        ? 'block' : 'none')"
        style="background:#f1f5f9; color:#1e293b; border:1px solid #cbd5e1;
        padding:4px 8px; border-radius:4px; font-size:12px; font-weight:bold; cursor:pointer;">
        📋 የፈቃድ ዝርዝር ሁኔታን
      </button>

      <div id="toggleLeaveDetails"
        style="display:none; margin-top:8px; padding:8px; background:#fafafa;
        border-left:3px solid #000; font-size:13px; line-height:1.6;">

        <p><b>📝 ዝርዝር ምክንያት፦</b> ${s.reasonDetail || "የለም"}</p>
        <p><b>📅 የጀመረበት ቀን፦</b> ${s.leaveStartDate || "-"}</p>
        <p><b>📅 የሚያበቃበት ቀን፦</b> ${s.leaveEndDate || "-"}</p>
        <p><b>📌 የተፈቀዱ መርሐግብራት፦</b> ${programsList}</p>

        ${countdownText}
      </div>
    </div>
  `;
}
    
  } else {
    // ፈቃድ ካልሆነ (ትምህርት፣ ሥራ፣ በእረфተ ስጋ...) የድሮው አሠራር እንዳለ ይቀጥላል
    document.getElementById("pReason").innerHTML = `⚠️ <b>የራቁበት ምክንያት፦</b> ${s.reason}`;
    document.getElementById("pReasonDetail").innerHTML = `📝 <b>ዝርዝር ምክንያት፦</b> ${s.reasonDetail || ''} ${s.restInPeaceDate ? ' [ቀን: '+s.restInPeaceDate+']' : ''}`;
  }
} else {
  document.getElementById("pReasonContainer").style.display = "none";
}

  // የአይዲ (ID) አያያዥ - የተማሪውን ኦብጀክት ለፕሪንት ፈንክሽን በትክክል ያስተላልፋል
  document.getElementById("printProfileBtn").onclick = function() { printSingleProfile(s); };
  document.getElementById("editBtn").onclick = function(){ editStudent(id); };
  document.getElementById("idDelBtn").onclick = function(){ deleteStudent(id); };
  navigateTo('profilePage');
}

// 🖨️ ማተሚያ ፈንክሽን - የቀድሞ ክፍሎችን ቁልቁል በየተራ የሚደረድር
function printSingleProfile(student) {
  let imgHtml = student.photo ? `<div style="text-align:center; margin-bottom:15px;"><img src="${student.photo}" style="width:110px; height:110px; object-fit:cover; border-radius:6px; border:2px solid #000000; display:inline-block;"></div>` : '';
  
  let city = student.address?.city || (student.city || '-');
  let subcity = student.address?.subcity || (student.subcity || '-');
  let woreda = student.address?.woreda || (student.woreda || '-');
  let area = student.address?.area || (student.area || '-');
  let house = student.address?.house || (student.house || '-');

  // የ5ቱ ተጨማሪ የአገልግሎት ክፍሎች መሰብሰቢያ
  let depts = [];
  if (student.currentServingDept) depts.push(student.currentServingDept);
  if (student.servingDept2) depts.push(student.servingDept2);
  if (student.servingDept3) depts.push(student.servingDept3);
  if (student.servingDept4) depts.push(student.servingDept4);
  if (student.servingDept5) depts.push(student.servingDept5);
  let allDeptsText = depts.length > 0 ? depts.join("፣ ") : "-";

  // የቀድሞ ያገለገሉበት ክፍል ወደ ታች በየተራ በጥቁር ነጥብ (•) እንዲደረደር (HTML Line Breaks)
  let prevClassesHtml = "-";
  if (student.prevClasses && student.prevClasses.length > 0) {
    prevClassesHtml = student.prevClasses.map(c => `• ${c}`).join("<br>");
  }

  let html = `
    <div class="print-wps-box" style="padding:15px; font-family:sans-serif; background:white !important; color:#000000 !important; max-width:500px; margin:0 auto;">
      <h2 style="text-align:center; margin-bottom:5px; color:#000000 !important; font-weight:bold; font-size:15px; line-height:1.4;">የእንጦጦ መንበረስብሐት ቅድስት ስላሴ ቤተክርስቲያን<br>ውሉደ ብርሐን ሰ/ቤት</h2>
      <h4 style="text-align:center; margin-top:0; margin-bottom:15px; color:#000000 !important; font-weight:normal; border-bottom:2px solid #000000; padding-bottom:8px;">የተማሪ መረጃ ማኅደር</h4>
      
      ${imgHtml}
      
      <table style="width:100%; border-collapse:collapse; margin-top:10px; color:#000000 !important; font-size:14px; border:1px solid #000000;">
        <tbody>
          <tr>
          
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">ክርስትና ስም</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.christianName || '-'}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; width:40%; background:#f8fafc;">ሙሉ ስም</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.name || '-'}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">ጾታ</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.gender === 'Male' ? 'ወንድ' : 'ሴት'}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">
    የትውልድ ቀን
  </td>
  <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">
    ${student.birthDate || '-'}
  </td>
</tr>

<tr>
<td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">
    ማዕረገ ክህነት
  </td>
  <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">
    ${student.rank || '-'}
  </td>
</tr>

<tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">የግል ስልክ ቁጥር</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.phone || '-'}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">የቤተሰብ ስልክ ቁጥር</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.familyPhone || '-'}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">የሰንበት ት/ቤት ክፍል</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.cls || '-'}</td>
          </tr>
            <tr>
                      <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">የቀለም ትምህርት ደረጃ</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${student.currentClass || '-'}</td>
          </tr>
          <tr>
          <tr>


  <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">
    የፀባይ ሁኔታ
  </td>
  <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">
    ${student.behavior || '-'}
  </td>
</tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc; vertical-align: top;">አሁን የሚያገለግሉበት  ክፍል</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important; line-height: 1.5;">${prevClassesHtml}</td>
          </tr>

          <tr>

            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">የሚያገለግሉበት ክፍል (ቦታዎች)</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${allDeptsText}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">መኖሪያ ከተማ</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${city}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">ክፍለ ከተማ</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${subcity}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">ወረዳ</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${woreda}</td>
          </tr>
          <tr>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#000000 !important; background:#f8fafc;">ልዩ ቦታ</td>
            <td style="padding:8px; border:1px solid #000000; color:#000000 !important;">${area}</td>
          </tr>
          <tr class="print-red-row">
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#dc2626 !important; background:#fff5f5;">የቤት ቁጥር</td>
            <td style="padding:8px; border:1px solid #000000; font-weight:bold; color:#dc2626 !important; font-size:15px;">${house}</td>
          </tr>
        </tbody>
      </table>
    </div>
  `;
  
  let pArea = document.getElementById("printArea");
  if(pArea) {
    pArea.innerHTML = html;
    pArea.style.display = "block";
  }
  
  let originalTitle = document.title;
  document.title = "ማኅደር - " + (student.name || "ተማሪ");
  
  window.print();
  document.title = originalTitle;
}
  function editStudent(id){
      if(!askAdminPassword()){ alert("የAdmin ፓስወርድ ስህተት ነው!"); return; }
      let s = students.find(x => x.id === id);
      if(!s) return;
      editId = id;
      navigateTo('addStudentPage');
      document.getElementById("formTitle").innerText = "የተማሪ መረጃ ማስተካከያ ፎርም";
      document.getElementById("name").value = s.name;
      document.getElementById("christianName").value = s.christianName || "";
      document.getElementById("phone").value = s.phone;
      document.getElementById("familyPhone").value = s.familyPhone || "";
      document.getElementById("cls").value = ["1ኛ ክፍል","2ኛ ክፍል","3ኛ ክፍል","4ኛ ክፍል","5ኛ ክፍል","6ኛ ክፍል","7ኛ ክፍል","8ኛ ክፍል","9ኛ ክፍል","10ኛ ክፍል","11ኛ ክፍል","12ኛ ክፍል","የተጠናቀቁ"].includes(s.cls) ? s.cls : "ሌላ";
      if(document.getElementById("cls").value === "ሌላ"){
        document.getElementById("clsOtherText").style.display = "block";
        document.getElementById("clsOtherText").value = s.cls;
      } else { document.getElementById("clsOtherText").style.display = "none"; }
      document.getElementById("regDate").value = s.regDate || "";
      if(document.getElementById("birthDate")){
  document.getElementById("birthDate").value =
    s.birthDate ? s.birthDate : "";
}
document.getElementById("studentRank").value = s.rank || "";
document.getElementById("studentLevel").value = s.level || "";
document.getElementById("currentClass").value = s.currentClass || "";
document.getElementById("gender").value = s.gender || "";
document.getElementById("studentBehavior").value = s.behavior || "";
      document.getElementById("currentServingDept").value = s.currentServingDept || "";
      document.getElementById("p1").value = s.prevClasses?.[0] || "";
      document.getElementById("p2").value = s.prevClasses?.[1] || "";
      document.getElementById("p3").value = s.prevClasses?.[2] || "";
      document.getElementById("p4").value = s.prevClasses?.[3] || "";
      document.getElementById("p5").value = s.prevClasses?.[4] || "";
      document.getElementById("city").value = s.address?.city || "";
      document.getElementById("subcity").value = s.address?.subcity || "";
      document.getElementById("woreda").value = s.address?.woreda || "";
      document.getElementById("area").value = s.address?.area || "";
      document.getElementById("house").value = s.address?.house || "";
      document.getElementById("reason").value = s.reason || "የለም";
      checkReason();
      document.getElementById("reasonText").value = s.reasonDetail || "";
      document.getElementById("restInPeaceDate").value = s.restInPeaceDate || "";
      photoData = s.photo || "";
      if(photoData){
        document.getElementById("preview").src = photoData;
        document.getElementById("preview").style.display = "block";
      } else { document.getElementById("preview").style.display = "none"; }
    }

    function deleteStudent(id){
      if(!askAdminPassword()){ alert("የAdmin ፓስወርድ ስህተት ነው!"); return; }
      if(confirm("ለመሰረዝ እርግጠኛ ነዎት?")){
        students = students.filter(x => x.id !== id);
        localStorage.setItem("students", JSON.stringify(students));
        alert("ተማሪው ተሰርዟል!");
        closeProfile();
        if(pageHistory[pageHistory.length-1] === 'allStudentsPage') showAllStudents();
      }
    }

    function closeProfile(){ closeCurrentPage(); }
///
function openLeaveManagementCenter() {
  if (document.getElementById("leaveSearchInput")) {
    document.getElementById("leaveSearchInput").value = "";
  }

  document.getElementById("leaveTableAreaContainer").innerHTML =
    "<p style='padding:15px; color:#64748b; text-align:center;'>እባክዎ አጠቃላይ ዝርዝሩን ለማየት ከላይ ያለውን በተን ይጫኑ ወይም በስም ይፈልጉ።</p>";
}

// =====================
// 2. LEAVE TABLE RENDER
// =====================
function renderLeaveTable(searchQuery = "") {
  let tableContainer = document.getElementById("leaveTableAreaContainer");
  if (!tableContainer) return;

  let leaveList = students.filter(s => s.reason === "ፈቃድ");

  if (searchQuery.trim() !== "") {
    leaveList = leaveList.filter(s =>
      (s.name || "").toLowerCase().includes(searchQuery.toLowerCase())
    );
  }

  if (leaveList.length === 0) {
    tableContainer.innerHTML =
      "<p style='padding:15px; color:red; font-weight:bold; text-align:center;'>⚠️ በዚህ ምድብ ምንም ዳታ አልተገኘም!</p>";
    return;
  }

  let sortedList = [...leaveList].sort((a, b) =>
    (a.name || "").localeCompare(b.name || "", "am")
  );

  let html = `
  <div style="width:100%; overflow-x:auto; border:2px solid #000; border-radius:8px; margin-top:10px;">
    <table style="width:100%; min-width:900px; border-collapse:collapse; background:#fff;">
      <thead>
        <tr style="background:#000; color:#fff;">
          <th style="padding:10px;">ተ.ቁ</th>
          <th style="padding:10px;">ስም</th>
          <th style="padding:10px;">ክፍል</th>
          <th style="padding:10px;">የሚያገለግሉበት</th>
          <th style="padding:10px;">ስልክ</th>
          <th style="padding:10px;">ጀመረበት</th>
          <th style="padding:10px;">ያበቃበት</th>
          <th style="padding:10px;">ሁኔታ</th>
          <th style="padding:10px;">እርምጃ</th>
        </tr>
      </thead>
      <tbody>
  `;

  sortedList.forEach((s, index) => {

    let statusMarkup = "";

    if (s.leaveStartDate && s.leaveEndDate) {

      let endParts = s.leaveEndDate.replace("ዓ.ም", "").trim().split("/");
      let todayStr = document.getElementById("todayEthioDate")
        ? document.getElementById("todayEthioDate").value
        : "16/10/2018";

      let todayParts = todayStr.replace("ዓ.ም", "").trim().split("/");

      let endNum =
        (parseInt(endParts[2]) * 365) +
        (parseInt(endParts[1]) * 30) +
        parseInt(endParts[0]);

      let todayNum =
        (parseInt(todayParts[2]) * 365) +
        (parseInt(todayParts[1]) * 30) +
        parseInt(todayParts[0]);

      let daysLeft = endNum - todayNum;

      if (daysLeft < 0) {
        let passedDays = Math.abs(daysLeft);
        statusMarkup = `
          <span style="color:#ef4444; font-weight:bold; background:#fee2e2; padding:3px 8px; border-radius:6px;">
            ❌ አልቋል (${passedDays} ቀን አልፏል)
          </span>`;
      } else if (daysLeft <= 10) {
        statusMarkup = `
          <span style="color:#d97706; font-weight:bold; background:#fef3c7; padding:3px 8px; border-radius:6px;">
            ⚠️ ቀሪ ${daysLeft} ቀን
          </span>`;
      } else {
        statusMarkup = `
          <span style="color:#16a34a; font-weight:bold; background:#dcfce7; padding:3px 8px; border-radius:6px;">
            🟢 በፈቃድ (${daysLeft} ቀን)
          </span>`;
      }

    } else {
      statusMarkup = "-";
    }

    let actionButton = `
      <button onclick="returnStudentToActive('${s.id}', '${s.name}')"
        style="background:#16a34a; color:#fff; border:none; padding:5px 10px; border-radius:6px;">
        🔄 መልስ
      </button>
    `;

    html += `
      <tr>
        <td style="text-align:center;">${index + 1}</td>
        <td style="color:#0284c7; cursor:pointer;"
            onclick="viewStudentFromLeave('${s.id}')">
          🔗 ${s.name}
        </td>
        <td>${s.cls || "-"}</td>
        <td>${s.currentServingDept || "-"}</td>
        <td>${s.phone || "-"}</td>
        <td style="text-align:center;">${s.leaveStartDate || "-"}</td>
        <td style="text-align:center;">${s.leaveEndDate || "-"}</td>
        <td style="text-align:center;">${statusMarkup}</td>
        <td style="text-align:center;">${actionButton}</td>
      </tr>
    `;
  });

  html += `
      </tbody>
    </table>
  </div>
  `;

  tableContainer.innerHTML = html;
}

// =====================
// 3. SEARCH
// =====================
function searchLeaveStudents() {
  let query = document.getElementById("leaveSearchInput").value;
  renderLeaveTable(query);
}

// =====================
// 4. RETURN TO ACTIVE
// =====================
function returnStudentToActive(studentId, studentName) {
  let confirmAction = confirm(
    `እርግጠኛ ነዎት አባል "${studentName}" ወደ አገልግሎት ተመልሷል?`
  );

  if (!confirmAction) return;

  let studentObj = students.find(s => s.id === studentId);

  if (studentObj) {
    studentObj.reason = "የለም";
    studentObj.reasonDetail = "";
    studentObj.leaveStartDate = "";
    studentObj.leaveEndDate = "";
    studentObj.leavePrograms = [];

    if (typeof saveToLocalStorage === "function") saveToLocalStorage();
    else if (typeof saveStudentsData === "function") saveStudentsData();
    else if (typeof saveData === "function") saveData();

    alert(`"${studentName}" ተሳክቷል ወደ አክቲቭ ተመልሷል!`);

    let query = document.getElementById("leaveSearchInput")
      ? document.getElementById("leaveSearchInput").value
      : "";

    renderLeaveTable(query);
  }
}

// =====================
// 5. VIEW PROFILE
// =====================
function viewStudentFromLeave(studentId) {
  document.querySelectorAll(".app-page").forEach(p => (p.style.display = "none"));

  if (typeof viewStudentProfile === "function") {
    viewStudentProfile(studentId);
  }
}
let tempAttList = [];

function loadAttendanceList() {
  let d = document.getElementById("attDate").value;
  if (!d) {
    alert("እባክዎ ቀን ይምረጡ!");
    return;
  }

  let type = document.getElementById("attProgramType").value;
  let pClass = document.getElementById("attProgClass").value;

  let existing = attendanceRecords.find(r =>
    r.date === d &&
    r.type === type &&
    r.progClass === pClass
  );

  let activeStudents = students.filter(s => s.reason !== "በእረፍተ ስጋ");

  if (pClass === "ያጠናቀቁ") {
    activeStudents = activeStudents.filter(s => {
      let c = s.cls ? s.cls.toString().trim() : "";
      return c.includes("ያጠናቀቁ") || c.includes("የተጠናቀቁ");
    });
  }
  else if (pClass === "ሌላ") {
    activeStudents = activeStudents.filter(s => {
      let c = s.cls ? s.cls.toString().trim() : "";
      let hasNumber = /\d+/.test(c);
      let graduated =
        c.includes("ያጠናቀቁ") || c.includes("የተጠናቀቁ");
      return !hasNumber && !graduated && c !== "";
    });
  }
  else {
    activeStudents = activeStudents.filter(s => {
      let c = s.cls ? s.cls.toString().trim() : "";
      return c === pClass;
    });
  }

  if (activeStudents.length === 0) {
    document.getElementById("attStudentList").innerHTML =
      "<p style='color:red;font-weight:bold;text-align:center;'>በዚህ ክፍል ምንም ንቁ ተማሪ አልተገኘም!</p>";

    document.getElementById("attendanceSheet").classList.remove("hidden");
    return;
  }

  tempAttList = activeStudents.map(s => {
    let statusVal = "P";

    if (existing) {
      if (existing.presents?.includes(s.id)) statusVal = "P";
      else if (existing.leaves?.includes(s.id)) statusVal = "L";
      else statusVal = "A";
    }

    return {
      id: s.id,
      name: s.name,
      cls: s.cls,
      status: statusVal
    };
  });

  renderTempAttendanceList();
  document.getElementById("attendanceSheet").classList.remove("hidden");
}

function renderTempAttendanceList() {
  let html = `
    <div style="width:100%; overflow-x:auto;">
      <table style="width:100%; border-collapse:collapse;">
        <thead>
          <tr style="background:#0f172a; color:white;">
            <th style="padding:10px;">ተማሪ</th>
            <th style="padding:10px;">ክፍል</th>
            <th style="padding:10px;">አቴንዳንስ</th>
          </tr>
        </thead>
        <tbody>
  `;

  tempAttList.forEach(item => {
    html += `
      <tr>
        <td style="padding:10px;">${item.name}</td>
        <td style="padding:10px;">${item.cls}</td>
        <td style="padding:10px;">
          <input type="radio" name="rad_${item.id}" ${item.status==="P"?"checked":""}
          onchange="updateTempAtt('${item.id}','P')"> 🟢

          <input type="radio" name="rad_${item.id}" ${item.status==="L"?"checked":""}
          onchange="updateTempAtt('${item.id}','L')"> 🟡

          <input type="radio" name="rad_${item.id}" ${item.status==="A"?"checked":""}
          onchange="updateTempAtt('${item.id}','A')"> 🔴
        </td>
      </tr>
    `;
  });

  html += `</tbody></table></div>`;
  document.getElementById("attStudentList").innerHTML = html;
}

function updateTempAtt(id, statusValue) {
  let idx = tempAttList.findIndex(x => x.id === id);
  if (idx !== -1) tempAttList[idx].status = statusValue;
}

function filterAttendanceListOnly() {
  let q = document.getElementById("attSearchBox").value.toLowerCase();
  let rows = document.querySelectorAll("#attStudentList tbody tr");

  rows.forEach(tr => {
    let name = tr.cells[0].innerText.toLowerCase();
    tr.style.display = name.includes(q) ? "" : "none";
  });
}

function calculateSingleStudentMetrics(id) {
  let sObj = students.find(x => x.id === id);

  if (!sObj) {
    return {
      presentCount: 0,
      absentCount: 0,
      leaveCount: 0,
      rate: 0,
      status: "Inactive",
      level: "ዝቅተኛ",
      totalEvents: 0
    };
  }

  let presentCount = 0;
  let leaveCount = 0;
  let totalEvents = 0;

  let currentClass = (sObj.cls || "").toString().trim();
  let regDate = normalizeDate(sObj.regDate || "");

  attendanceRecords.forEach(r => {
    let recDate = normalizeDate(r.date);

    // ✅ ከምዝገባ ቀን በፊት አይቆጠር
    if (regDate && recDate < regDate) return;

    let isCompleted =
      currentClass.includes("ያጠናቀቁ") ||
      currentClass.includes("የተጠናቀቁ");

    let isSpecial =
      isNaN(parseInt(currentClass)) &&
      !isCompleted;

    let isRegular =
      !isNaN(parseInt(currentClass));

    // ✅ class matching logic
    if (isRegular) {
      if (r.progClass !== currentClass) return;
    }

    if (isCompleted) {
      if (
        r.progClass !== "የተጠናቀቁ" &&
        r.progClass !== "ያጠናቀቁ"
      ) return;
    }

    if (isSpecial) {
      if (r.progClass !== "ሌላ" && r.progClass !== currentClass) return;
    }

    totalEvents++;

    if (r.presents?.includes(id)) {
      presentCount++;
    } else if (r.leaves?.includes(id)) {
      leaveCount++;
    }
  });

  let totalAttended = presentCount + leaveCount;
  let absentCount = totalEvents - totalAttended;

  let rate = totalEvents > 0
    ? Math.round((totalAttended / totalEvents) * 100)
    : 0;

  let status =
    (!sObj.reason || sObj.reason === "የለም")
      ? "Active"
      : "Inactive";

  let level =
    rate >= 75 ? "ከፍተኛ" :
    rate >= 50 ? "መካከለኛ" :
    "ዝቅተኛ";

  return {
    presentCount,
    absentCount,
    leaveCount,
    rate,
    status,
    totalEvents,
    level
  };
}
function recalculateAllMetrics() {
  let validStudents = students.filter(s => s.reason !== "በእረፍተ ስጋ");

  document.getElementById("total").innerText = validStudents.length;

  document.getElementById("male").innerText =
    validStudents.filter(x => x.gender === "Male").length;

  document.getElementById("female").innerText =
    validStudents.filter(x => x.gender === "Female").length;

  let act = 0;
  let inact = 0;
  let h = 0;
  let m = 0;
  let l = 0;

  validStudents.forEach(s => {
    let metrics = calculateSingleStudentMetrics(s.id);

    // ✅ Active / Inactive (FIXED LOGIC)
    if (!s.reason || s.reason === "የለም") {
      act++;
    } else {
      inact++;
    }

    // ✅ Attendance Level (FIXED SAFE CHECK)
    let rate = metrics.rate || 0;

    if (rate >= 75) h++;
    else if (rate >= 50) m++;
    else l++;
  });

  document.getElementById("active").innerText = act;
  document.getElementById("inactive").innerText = inact;

  document.getElementById("high").innerText = h;
  document.getElementById("medium").innerText = m;
  document.getElementById("low").innerText = l;
}
function saveAttendanceSheet() {
  let d = document.getElementById("attDate").value;
  let type = document.getElementById("attProgramType").value;
  let pClass = document.getElementById("attProgClass").value;

  let presents = tempAttList.filter(x => x.status === "P").map(x => x.id);
  let leaves = tempAttList.filter(x => x.status === "L").map(x => x.id);

  attendanceRecords = attendanceRecords.filter(r =>
    !(r.date === d && r.type === type && r.progClass === pClass)
  );

  attendanceRecords.push({
    date: d,
    type: type,
    progClass: pClass,
    presents: presents,
    leaves: leaves
  });

  localStorage.setItem("attendanceRecords", JSON.stringify(attendanceRecords));

  alert("አቴንዳንስ በተሳካ ሁኔታ ተቀምጧል!");
  document.getElementById("attendanceSheet").classList.add("hidden");

  recalculateAllMetrics();
}
function openParticipationStatsPage() {
  let searchBox = document.getElementById("partStatsSearch");
  if(searchBox) searchBox.value = "";
  currentPartStatsCategory = ""; 
  currentlySelectedPartStudentId = "";
  
  // ቀኖቹን እና ቫሪያብሎችን ባዶ ማድረግ
  partStatsFromDate = "";
  partStatsToDate = "";
  
  let fInput = document.getElementById("participationStatsPage_date_from");
  let tInput = document.getElementById("participationStatsPage_date_to");
  if(fInput) fInput.value = "";
  if(tInput) tInput.value = "";
  
  // ገጹ ሲከፈት ስም ሊስቱ እንዲታይ ማድረግ
  let listContainer = document.getElementById("partStatsNamesListContainer");
  if(listContainer) listContainer.style.display = "block";
  
  let containerId = "participationStatsPage";
  if (!document.getElementById(`${containerId}_date_wrapper`)) {
    let dateHtml = `
      <div id="${containerId}_date_wrapper" style="background:#f8fafc; padding:10px; border-radius:8px; border:1px solid #cbd5e1; margin-top:10px; margin-bottom:10px;">
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:5px;">
          <p style="margin:0; font-size:12px; font-weight:bold; color:#000000;">📅 በቀን ማጣሪያ (ዓ.ም)፦</p>
          <button type="button" onclick="clearPartStatsDateFilter()" style="padding:4px 10px; background:#ef4444; color:white; border:none; border-radius:4px; font-size:11px; font-weight:bold; cursor:pointer;">❌ Clear</button>
        </div>
        <div style="display:flex; gap:10px; justify-content:space-between;">
          <div style="flex:1;">
            <label style="font-size:11px; font-weight:bold; color:#000000;">ከቀን፦</label>
            <input type="date" id="${containerId}_date_from" onchange="refreshStatsIfSelected()" style="width:100%; padding:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:12px; color:#000000; background:white;">
          </div>
          <div style="flex:1;">
            <label style="font-size:11px; font-weight:bold; color:#000000;">እስከ ቀን፦</label>
            <input type="date" id="${containerId}_date_to" onchange="refreshStatsIfSelected()" style="width:100%; padding:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:12px; color:#000000; background:white;">
          </div>
        </div>
      </div>
    `;
    let searchLabel = document.querySelector(`#${containerId} label:nth-of-type(2)`);
    if (searchLabel) {
      searchLabel.insertAdjacentHTML('beforebegin', dateHtml);
    }
  }

  let tableContainer = document.getElementById("partStatsTableContainer");
  let titleText = document.getElementById("selectedPartStudentTitle");
  let actionsBox = document.getElementById("partTableActionButtons");

  if(listContainer) listContainer.innerHTML = "<p style='color:#94a3b8; font-size:13px; text-align:center; padding:20px;'>እባክዎ መጀመሪያ ከላይ ካሉት በተኖች የአንዱን ምድብ ይምረጡ።</p>";
  if(tableContainer) tableContainer.innerHTML = "<p style='color:#94a3b8; text-align:center; padding:35px;'>እባክዎ ማጠቃለያውን ለማየት ከላይ ከሚመጣው ዝርዝር ላይ የተማሪ ስም ይጫኑ።</p>";
  if(titleText) titleText.innerText = "📊 የዕለታት ማጠቃለያ ሰንጠረዥ";
  if(actionsBox) {
    actionsBox.style.display = "none";
    actionsBox.classList.add("hidden");
  }
}

// 🔄 ቀን ሲቀየር እዛው እያሉ ቴብሉን ወዲያው የሚያድስ ፈንክሽን
function refreshStatsIfSelected() {
  let fInput = document.getElementById("participationStatsPage_date_from");
  let tInput = document.getElementById("participationStatsPage_date_to");
  partStatsFromDate = fInput ? fInput.value : "";
  partStatsToDate = tInput ? tInput.value : "";

  if (typeof currentlySelectedPartStudentId !== 'undefined' && currentlySelectedPartStudentId) {
    showIndividualStudentStats(currentlySelectedPartStudentId);
  }
}

// ❌ የቀን ማጣሪያውን ማጽጃ አዲስ ፈንክሽን
function clearPartStatsDateFilter() {
  partStatsFromDate = "";
  partStatsToDate = "";
  let fInput = document.getElementById("participationStatsPage_date_from");
  let tInput = document.getElementById("participationStatsPage_date_to");
  if(fInput) fInput.value = "";
  if(tInput) tInput.value = "";
  
  if (typeof currentlySelectedPartStudentId !== 'undefined' && currentlySelectedPartStudentId) {
    showIndividualStudentStats(currentlySelectedPartStudentId);
  }
}

function loadPartStatsCategory(cat) {
  currentPartStatsCategory = cat;
  buildPartStatsNamesList();
  let listContainer = document.getElementById("partStatsNamesListContainer");
  if(listContainer) listContainer.style.display = "block";
}

function filterPartStatsSearch() {
  if(!currentPartStatsCategory) return;
  buildPartStatsNamesList();
}

function buildPartStatsNamesList() {
  let searchBox = document.getElementById("partStatsSearch");
  let q = searchBox ? searchBox.value.toLowerCase().trim() : "";
  
  if (typeof students === 'undefined') return;
  
  let valid = students.filter(s => {
    if(!s.reason) return true;
    let r = s.reason.toString();
    return !r.includes("እረፍተ") && !r.includes("ስጋ");
  });
  
  let filtered = [];
  
  if(currentPartStatsCategory === 'learning') {
    filtered = valid.filter(s => {
      let currentClass = s.cls ? s.cls.toString().trim() : "";
      let isGraduated = currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");
      let numMatch = currentClass.match(/\d+/);
      let isGrade1to12 = numMatch ? (parseInt(numMatch[0]) >= 1 && parseInt(numMatch[0]) <= 12) : false;
      return !isGraduated && (isGrade1to12 || currentClass === "");
    });
    
  } else if(currentPartStatsCategory === 'graduated') {
    filtered = valid.filter(s => {
      let currentClass = s.cls ? s.cls.toString().trim() : "";
      return currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");
    });
    
  } else if(currentPartStatsCategory === 'other') {
    filtered = valid.filter(s => {
      let currentClass = s.cls ? s.cls.toString().trim() : "";
      let isGraduated = currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");
      let numMatch = currentClass.match(/\d+/);
      let isGrade1to12 = numMatch ? (parseInt(numMatch[0]) >= 1 && parseInt(numMatch[0]) <= 12) : false;
      return !isGraduated && !isGrade1to12 && currentClass !== "";
    });
  }

  if(q) {
    filtered = filtered.filter(s => {
      let name = (s.name || "").toLowerCase();
      let phone = (s.phone || "").toString().toLowerCase();
      let cls = (s.cls || "").toLowerCase();
      return name.startsWith(q) || name.includes(q) || phone.includes(q) || cls.includes(q);
    });
  }

  let listContainer = document.getElementById("partStatsNamesListContainer");
  if(!listContainer) return;

  if(filtered.length === 0) {
    listContainer.innerHTML = "<p style='color:#64748b; font-size:13px; text-align:center; padding:15px;'>⚠️ በዚህ ምድብ ምንም ተማሪ አልተገኘም!</p>";
    return;
  }

  let sorted = [...filtered];
  sorted.sort((a, b) => (a.name || "").localeCompare((b.name || ""), 'am'));

  let html = "";
  sorted.forEach(s => {
    let borderStyle = "border:1px solid #cbd5e1;";
    if(currentPartStatsCategory === 'graduated') borderStyle = "border:1px solid #bbf7d0;";
    if(currentPartStatsCategory === 'other') borderStyle = "border:1px solid #fbcfe8;";

    html += `
      <div onclick="showIndividualStudentStats('${s.id}')" style="background:white; padding:12px; margin-bottom:6px; border-radius:10px; cursor:pointer; ${borderStyle} font-size:13px; font-weight:bold; color:#000000; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
        👤 ${s.name} <span style="color:#64748b; font-size:11px; font-weight:normal;">(${s.cls || 'ክፍል የለውም'})</span>
      </div>
    `;
  });
  listContainer.innerHTML = html;
}
function convertEthioDateToNumber(dateStr) {
  if (!dateStr) return 0;

  dateStr = dateStr.replace(" ዓ.ም", "").trim();

  let parts = dateStr.split("/");
  if (parts.length !== 3) return 0;

  let d = parseInt(parts[0]);
  let m = parseInt(parts[1]);
  let y = parseInt(parts[2]);

  if (isNaN(d) || isNaN(m) || isNaN(y)) return 0;

  return y * 10000 + m * 100 + d;
}
function onPartStatsDateFilterChange() {
  let fromInput = document.getElementById("partStatsFromDate");
  let toInput = document.getElementById("partStatsToDate");

  partStatsFromDate = fromInput ? fromInput.value : "";
  partStatsToDate = toInput ? toInput.value : "";

  console.log("PartStats FROM:", partStatsFromDate);
  console.log("PartStats TO:", partStatsToDate);

  // ተማሪ ከተመረጠ ማጠቃለያውን እንደገና አሳይ
  if (currentlySelectedPartStudentId) {
    showIndividualStudentStats(currentlySelectedPartStudentId);
  }
}
function showIndividualStudentStats(studentId) {
  currentlySelectedPartStudentId = studentId;

  if (typeof students === 'undefined' || typeof attendanceRecords === 'undefined') return;

  let s = students.find(x => x.id === studentId);
  if (!s) return;

  let listContainer = document.getElementById("partStatsNamesListContainer");
  if (listContainer) listContainer.style.display = "none";

  let studentRegistrationDate = s.regDate || "";

  let tCount = 0;
  let pCount = 0;
  let lCount = 0;

  let sClass = s.cls ? s.cls.toString().trim() : "";

  let isCompleted =
    sClass.includes("ያጠናቀቁ") ||
    sClass.includes("የተጠናቀቁ");

  let isSpecial =
    isNaN(parseInt(sClass)) &&
    !isCompleted;

  // ===============================
  // 📊 Overall Stats
  // ===============================
  attendanceRecords.forEach(r => {
    let recordDateNum = convertEthioDateToNumber(r.date);
    let regDateNum = convertEthioDateToNumber(studentRegistrationDate);
    let fromDateNum = convertEthioDateToNumber(partStatsFromDate);
    let toDateNum = convertEthioDateToNumber(partStatsToDate);

    if (regDateNum && recordDateNum < regDateNum) return;
    if (fromDateNum && recordDateNum < fromDateNum) return;
    if (toDateNum && recordDateNum > toDateNum) return;

    // ✅ fixed class matching
    if (r.progClass !== sClass) {
      if (!(isCompleted && r.progClass === "የተጠናቀቁ")) {
        if (!(isSpecial && r.progClass === "ሌላ")) {
          return;
        }
      }
    }

    tCount++;

    if (r.presents?.includes(studentId)) pCount++;
    else if (r.leaves?.includes(studentId)) lCount++;
  });

  let totalAtt = pCount + lCount;
  let finalRate = tCount > 0 ? Math.round((totalAtt / tCount) * 100) : 0;
  let finalLevel =
    finalRate >= 75 ? "ከፍተኛ" :
    finalRate >= 50 ? "መካከለኛ" : "ዝቅተኛ";

  let finalStatus =
    (s.reason && s.reason !== "የለም") ? "የራቀ (Inactive)" : "ንቁ (Active)";

  let titleText = document.getElementById("selectedPartStudentTitle");
  let actionsBox = document.getElementById("partTableActionButtons");

  if (titleText)
    titleText.innerText = `📊 ማጠቃለያ፦ ${s.name} (${s.cls || 'የለውም'})`;

  if (actionsBox) {
    actionsBox.style.display = "flex";
    actionsBox.style.flexDirection = "row";
    actionsBox.style.gap = "10px";
    actionsBox.style.width = "100%";
    actionsBox.classList.remove("hidden");
  }

  let ripReasonInfo = (s.reason && s.reason !== "የለም")
    ? ` <span style="color:red; font-weight:bold;">(የራቁበት ምክንያት፦ ${s.reason} ${s.reasonDetail ? '- ' + s.reasonDetail : ''})</span>`
    : "";

  let dateRangeInfo = (partStatsFromDate || partStatsToDate)
    ? ` <br>📅 <b>የሪፖርቱ ጊዜ፦</b> <span style="color:#d97706; font-weight:bold;">(${partStatsFromDate ? partStatsFromDate+' ' : 'መጀመሪያ'} እስከ ${partStatsToDate ? partStatsToDate+' ' : 'ዛሬ'})</span>`
    : "";

  let joinedDateText = studentRegistrationDate
    ? `<br>📅 <b>የምዝገባ ቀን፦</b> <span style="color:#854d0e;">${studentRegistrationDate}</span>`
    : "";

  let backToListButton = `
    <button type="button" onclick="showNamesListAgain()"
      style="width:100%; padding:10px; margin-bottom:12px; background:#2563eb; color:white; font-weight:bold; border:none; border-radius:8px; cursor:pointer;">
      ⬅️ የተማሪዎች ዝርዝርን መልሰህ አሳይ
    </button>
  `;

  let infoHeaderHtml = `
    <div style="background:#f8fafc; padding:12px; border-radius:10px; border:1px solid #e5e7eb; margin-bottom:15px; font-size:14px; line-height:1.6; color:#000000;">
      🟢 <b>ሁኔታ (Status)፦</b>
      <span style="font-weight:bold; color:#2563eb;">${finalStatus}</span>
      ${ripReasonInfo}
      ${joinedDateText}
      ${dateRangeInfo}
      <br>
      📈 <b>አጠቃላይ ተሳትፎ (ከተመዘገበበት ቀን ጀምሮ)፦</b>
      <span style="font-weight:bold; color:#16a34a;">${finalRate}% (${finalLevel})</span>
    </div>
  `;

  let progs = ["💖 ፀሎት", "📖 ትምህርት", "🥛 ፅዋ", "✨ ልዩ ጉባኤ", "🎶 መዝሙር"];

  let tableHtml = `
  <table id="individualStatsTable" style="width:100%; border-collapse:collapse; background:white; font-family:sans-serif; border:2px solid #000000;">
    <thead>
      <tr style="background:#ffffff; color:#000000; border-bottom:3px solid #000000;">
        <th style="padding:10px; border:1px solid #000;">የመርሀ ግብር አይነት</th>
        <th style="padding:10px; border:1px solid #000;">ጠቅላላ ቀን</th>
        <th style="padding:10px; border:1px solid #000;">P</th>
        <th style="padding:10px; border:1px solid #000;">A</th>
        <th style="padding:10px; border:1px solid #000;">L</th>
        <th style="padding:10px; border:1px solid #000;">%</th>
        <th style="padding:10px; border:1px solid #000;">ደረጃ</th>
      </tr>
    </thead>
    <tbody>`;

  // ===============================
  // 📊 Program Stats
  // ===============================
  progs.forEach(progWithEmoji => {
    let progType = progWithEmoji.replace(
      /[\uE000-\uF8FF]|\uD83C[\uDC00-\uDFFF]|\uD83D[\uDC00-\uDFFF]|\uD83E[\uDD00-\uDFFF]|[✨📖💖🥛🎶]/g,
      ""
    ).trim();

    let total = 0;
    let present = 0;
    let leave = 0;

    attendanceRecords.forEach(r => {
      if (r.type !== progType) return;

      let recordDateNum = convertEthioDateToNumber(r.date);
      let regDateNum = convertEthioDateToNumber(studentRegistrationDate);
      let fromDateNum = convertEthioDateToNumber(partStatsFromDate);
      let toDateNum = convertEthioDateToNumber(partStatsToDate);

      if (regDateNum && recordDateNum < regDateNum) return;
      if (fromDateNum && recordDateNum < fromDateNum) return;
      if (toDateNum && recordDateNum > toDateNum) return;

      // ✅ fixed class matching here too
      if (r.progClass !== sClass) {
        if (!(isCompleted && r.progClass === "የተጠናቀቁ")) {
          if (!(isSpecial && r.progClass === "ሌላ")) {
            return;
          }
        }
      }

      total++;

      if (r.presents?.includes(studentId)) present++;
      else if (r.leaves?.includes(studentId)) leave++;
    });

    let absent = total - present - leave;
    let totalAttended = present + leave;
    let progRate = total > 0 ? Math.round((totalAttended / total) * 100) : 100;

    let progLevel =
      progRate >= 75 ? "ከፍተኛ" :
      progRate >= 50 ? "መካከለኛ" : "ዝቅተኛ";

    tableHtml += `
      <tr style="border-bottom:2px solid #000000; font-weight:900;">
        <td style="padding:10px; border:1px solid #000;"><b>${progWithEmoji}</b></td>
        <td style="padding:10px; border:1px solid #000; text-align:center;">${total} ቀን</td>
        <td style="padding:10px; border:1px solid #000; text-align:center; color:green;">${present}</td>
        <td style="padding:10px; border:1px solid #000; text-align:center; color:red;">${absent}</td>
        <td style="padding:10px; border:1px solid #000; text-align:center; color:#d97706;">${leave}</td>
        <td style="padding:10px; border:1px solid #000; text-align:center;">${progRate}%</td>
        <td style="padding:10px; border:1px solid #000; text-align:center;">${progLevel}</td>
      </tr>
    `;
  });

  tableHtml += "</tbody></table>";

  let container = document.getElementById("partStatsTableContainer");
  if (container) {
    container.innerHTML = backToListButton + infoHeaderHtml + tableHtml;
  }
}

function showNamesListAgain() {
  let listContainer = document.getElementById("partStatsNamesListContainer");
  if(listContainer) {
    listContainer.style.display = "block";
  }
}

// 🎯 ማሻሻያ፦ ፕሪንት ሲደረግ ሄዲንጉ ላይ ቀኖቹን በዓ.ም አሳይቶ ያትማል
function printIndividualStatsTable() {
  if (typeof students === 'undefined') return;
  let s = students.find(x => x.id === currentlySelectedPartStudentId);
  if(!s) return;
  
    let fromDate = document.getElementById("participationStatsPage_date_from") ? document.getElementById("participationStatsPage_date_from").value : "";
  let toDate = document.getElementById("participationStatsPage_date_to") ? document.getElementById("participationStatsPage_date_to").value : "";
  
  let dateTextHeader = "አጠቃላይ ታሪክ";
  if(fromDate || toDate) {
    dateTextHeader = `ከ ${fromDate || 'መጀመሪያ'} እስከ ${toDate || 'ዛሬ'} `;
  } else if (s.regDate) {
    dateTextHeader = `ከምዝገባ ቀን (${s.regDate}) ጀምሮ`;
  }
  let tableCont = document.getElementById("partStatsTableContainer");
  let tempDiv = document.createElement("div");
  tempDiv.innerHTML = tableCont ? tableCont.innerHTML : "";
  let btnInPrint = tempDiv.querySelector("button");
  if(btnInPrint) btnInPrint.remove();

  let printTemplate = `
    <div style="text-align:center; font-family:sans-serif; margin-bottom:20px; border-bottom:3px double #000; padding-bottom:10px;">
      <h2 style="margin:5px 0; font-size:18px;">የእንጦጦ መንበረ ስብሐት ቅድስት ሥላሴ ቤተክርስቲያን</h2>
      <h2 style="margin:5px 0; font-size:20px; color:#2563eb;">ውሉደ ብርሀን ሰንበት ትምህርት ቤት</h2>
      <h3 style="margin:8px 0; font-size:15px; background:#f1f5f9; padding:5px; display:inline-block; border-radius:5px;">📊 የተማሪ መርሐ-ግብር ተሳትፎ ስታቲስቲክስ ማጠቃለያ</h3>
      <p style="text-align:left; margin-top:15px; font-size:14px; line-height:1.8;">
        <b>የተማሪ ስም፦</b> ${s.name} &nbsp;&nbsp;&nbsp;&nbsp; <b>የአሁኑ ክፍል፦</b> ${s.cls || 'የለውም'}<br>
        <b>የሪፖርቱ ጊዜ፦</b> <span style="color:#ea580c; font-weight:bold;">${dateTextHeader}</span>
      </p>
    </div>
    ${tempDiv.innerHTML}
  `;
  
  let printArea = document.getElementById("printArea");
  if(printArea) {
    printArea.innerHTML = printTemplate; window.print();
  } else {
    let w = window.open(); w.document.write(printTemplate); w.print(); w.close();
  }
}

function downloadIndividualStatsExcel() {
  if (typeof students === 'undefined') return;
  let s = students.find(x => x.id === currentlySelectedPartStudentId);
  let table = document.getElementById("individualStatsTable");
  if(!table || !s) return;
  
  let csv = "\ufeff" + `"የተማሪ ስም: ${s.name}","ክፍል: ${s.cls || 'የለውም'}"\n\n`;
  for (let row of table.rows) {
    let rData = [];
    for (let cell of row.cells) rData.push(`"${cell.innerText}"`);
    csv += rData.join(",") + "\n";
  }
  let blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
  let link = document.createElement("a"); link.href = URL.createObjectURL(blob);
  link.download = `${s.name}_Participation_Stats.csv`; link.click();
}
// ========================================================
// 📊 ፍጹም የተስተካከለ የተማሪዎች ተሳትፎ ደረጃ ሙሉ ስክሪፕት
// ========================================================

function openEngagementLevelReportMenu(containerId) {
  resetEngagementPageHeader(containerId);

  let html = `
  <div style="margin-bottom: 15px; padding: 5px 5px; font-family: sans-serif;">
    <div id="${containerId}_main_filter_section" style="display:block;">
      <h3 style="margin:0 0 5px 0; color:#1e293b; font-size:20px; font-weight:bold;">📊 የተማሪዎች ተሳትፎ ደረጃ ሪፖርት</h3>
      <p style="font-size:13px; color:#64748b; margin:0 0 12px 0;">እባክዎ መጀመሪያ የትምህርት ሁኔታ ይምረጡ፦</p>
      
      <div style="display:flex; flex-direction:row; gap:6px; width:100%; margin-bottom:15px; justify-content:space-between;">
        <button onclick="renderEngagementStatusMenu('${containerId}', 'የሚማሩ')" style="background:#2563eb; color:white; border:none; padding:8px 4px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:11px; flex:1; text-align:center;">📖 የሚማሩ</button>
        <button onclick="renderEngagementStatusMenu('${containerId}', 'ያጠናቀቁ')" style="background:#2563eb; color:white; border:none; padding:8px 4px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:11px; flex:1; text-align:center;">🎓 ያጠናቀቁ</button>
        <button onclick="renderEngagementStatusMenu('${containerId}', 'ሌላ')" style="background:#2563eb; color:white; border:none; padding:8px 4px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:11px; flex:1; text-align:center;">✨ ሌላ</button>
      </div>
      
      <div id="${containerId}_engagement_buttons_area" style="display:none; flex-direction:row; gap:6px; margin-bottom:15px; width:100%; justify-content:space-between;"></div>
    </div>
    
    <div id="${containerId}_engagement_table_area" style="display:none;"></div>
  </div>`;
  
  document.getElementById(containerId).innerHTML = html;
}

// 2. የትምህርት ሁኔታው ሲመረጥ የደረጃ በተኖችን የሚያወጣ ፈንክሽን
function renderEngagementStatusMenu(containerId, eduStatus) {
  document.getElementById(`${containerId}_engagement_table_area`).style.display = "none";
  document.getElementById(`${containerId}_engagement_table_area`).innerHTML = "";
  
  let buttonArea = document.getElementById(`${containerId}_engagement_buttons_area`);
  buttonArea.style.display = "flex"; 
  
  let html = `
  <div style="width:100%;">
    <p style="font-size:13px; color:#64748b; margin:5px 0 10px 0;">አሁን ማየት የሚፈልጉትን የተሳትፎ ደረጃ ይምረጡ፦</p>
    <div style="display:flex; flex-direction:row; gap:6px; width:100%; justify-content:space-between;">
      <button onclick="renderEngagementFinalTable('${containerId}', '${eduStatus}', 'high')" style="background:#2563eb; color:white; border:none; padding:8px 2px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:10px; flex:1; text-align:center;">🥇 ከፍተኛ (>=75%)</button>
      <button onclick="renderEngagementFinalTable('${containerId}', '${eduStatus}', 'medium')" style="background:#2563eb; color:white; border:none; padding:8px 2px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:10px; flex:1; text-align:center;">🥈 መካከለኛ (50-74%)</button>
      <button onclick="renderEngagementFinalTable('${containerId}', '${eduStatus}', 'low')" style="background:#2563eb; color:white; border:none; padding:8px 2px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:10px; flex:1; text-align:center;">🥉 ዝቅተኛ (<50%)</button>
    </div>
  </div>`;
  
  buttonArea.innerHTML = html;
}

// 3. መረጃዎችን አውጥቶ ሰንጠረዡን (Table) የሚሥራው ዋና ፈንክሽን
function renderEngagementFinalTable(containerId, eduStatus, levelType) {
  let list = [];
  
  list = students.filter(s => s.reason !== "በእረፍተ ስጋ");

  list = list.filter(s => {
    let currentClass = s.cls ? s.cls.toString().trim() : "";
    let isGraduated = currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");

    let isGrade1to12 = false;
    let numMatch = currentClass.match(/\d+/); 
    if (numMatch) {
      let gradeNum = parseInt(numMatch[0]);
      if (gradeNum >= 1 && gradeNum <= 12) isGrade1to12 = true;
    }

    if (eduStatus === 'የሚማሩ') {
      if (isGraduated) return false;
      return isGrade1to12 || currentClass === "";
    } 
    else if (eduStatus === 'ያጠናቀቁ') {
      return isGraduated;
    } 
    else if (eduStatus === 'ሌላ') {
      if (isGraduated) return false;
      return !isGrade1to12 && currentClass !== "";
    }
  });

  list = list.filter(s => {
    let m = calculateSingleStudentMetrics(s.id);
    let rate = m && m.rate ? parseFloat(m.rate) : 0;
    if (levelType === 'high') return rate >= 75;
    if (levelType === 'medium') return rate >= 50 && rate < 75;
    if (levelType === 'low') return rate < 50;
    return false;
  });

  // 🛠️ ማስተካከያ፦ እዚህ ጋር ሰንጠረዡ ሲመጣ የላይኛው በተን ወደ ማጣሪያው እንዲመልስ ትክክለኛው የክሊክ ትዕዛዝ ተቀምጧል!
  let pageBtn = document.querySelector("#engagementReportPage button");
  if (pageBtn) {
    pageBtn.innerHTML = "⬅️ ወደ ማጣሪያው ተመለስ";
    pageBtn.setAttribute("onclick", `backToEngagementFilters('${containerId}')`);
    pageBtn.style.background = "#2563eb"; 
  }

  let tableArea = document.getElementById(`${containerId}_engagement_table_area`);
  if (!tableArea) return;

  if (list.length === 0) {
    tableArea.innerHTML = `<p style='padding:15px; color:red; font-weight:bold; font-size:14px; text-align:center;'>⚠️ በዚህ ምድብ ምንም የተማሪ ዳታ አልተገኘም!</p>`;
    document.getElementById(`${containerId}_main_filter_section`).style.display = "none";
    tableArea.style.display = "block";
    return;
  }

  let sorted = [];
  if (eduStatus === 'የሚማሩ') {
    sorted = [...list].sort((a, b) => {
      let clsA = a.cls || ""; let clsB = b.cls || "";
      let numA = clsA.match(/\d+/) ? parseInt(clsA.match(/\d+/)[0]) : 999;
      let numB = clsB.match(/\d+/) ? parseInt(clsB.match(/\d+/)[0]) : 999;
      if (numA !== numB) return numA - numB;
      return (a.name || "").localeCompare((b.name || ""), 'am');
    });
  } else {
    if (typeof sortAmharic === 'function') { sorted = sortAmharic([...list]); } 
    else { sorted = [...list].sort((a, b) => (a.name || "").localeCompare((b.name || ""), 'am')); }
  }

  let levelTitle = levelType === 'high' ? 'ከፍተኛ ተሳትፎ ያላቸው' : levelType === 'medium' ? 'መካከለኛ ተሳትፎ ያላቸው' : 'ዝቅተኛ ተሳትፎ ያላቸው';

  document.getElementById(`${containerId}_main_filter_section`).style.display = "none";
  tableArea.style.display = "block";

  let html = `
  <div style="margin-top:2px; display:flex; flex-direction:row; gap:6px; margin-bottom:8px; width:100%; justify-content:space-between;">
    <button onclick="printEngagementTable('${containerId}')" style="background:#2563eb; color:white; border:none; padding:8px 4px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:11px; flex:1; text-align:center;">🖨️ Print ሪፖርት</button>
    <button onclick="downloadEngagementExcel('${containerId}', '${eduStatus}_${levelType}')" style="background:#2563eb; color:white; border:none; padding:8px 4px; border-radius:6px; font-weight:bold; cursor:pointer; font-size:11px; flex:1; text-align:center;">📊 Excel አውርድ</button>
  </div>
  
  <div style="width:100%; max-height:430px; overflow-y:auto; overflow-x:auto; border:2px solid #000000; border-radius:6px;">
    <table id="${containerId}_final_engagement_table" data-title="${eduStatus} (${levelTitle}) ተማሪዎች ሪፖርት" style="width:100%; min-width:100%; border-collapse:collapse; background:white;">
      <thead style="position: sticky; top: 0; z-index: 10;">
        <tr style="background:#ffffff !important; border-bottom:2.5px solid #000000;">
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:left; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>ሙሉ ስም</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:left; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>ስልክ ቁጥር</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:left; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>የሚያገለግሉበት ክፍል</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:left; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>ክፍል</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:center; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>ሁኔታ</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:left; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>የራቁበት ምክንያት ካለ</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:center; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>ተሳትፎ (%)</b></th>
          <th style="padding:6px 6px; border:1.5px solid #000000; text-align:center; font-weight:900; font-size:14px; background-color:#ffffff !important; color:#000000 !important; white-space:nowrap;"><b>ደረጃ</b></th>
        </tr>
      </thead>
      <tbody>`;

  sorted.forEach(s => {
    let m = calculateSingleStudentMetrics(s.id);
    let isInactive = s.reason && s.reason !== "የለም" && s.reason !== "";
    let statusText = isInactive ? "Inactive" : "Active";
    let statusColor = isInactive ? "red" : "green";
    let reasonText = isInactive ? `${s.reason} ${s.reasonDetail ? '('+s.reasonDetail+')' : ''}` : "-";
    
    html += `<tr style="color:#000000; background:white; font-weight:900; border-bottom:1px solid #000000;">
      <td style="padding:6px 6px; border:1px solid #000000; font-weight:900; font-size:13px;">${s.name}</td>
      <td style="padding:6px 6px; border:1px solid #000000; font-weight:900; font-size:13px;">${s.phone || '-'}</td>
      <td style="padding:6px 6px; border:1px solid #000000; font-weight:900; font-size:13px;">${s.currentServingDept || '-'}</td>
      <td style="padding:6px 6px; border:1px solid #000000; font-weight:900; font-size:13px;">${s.cls}</td>
      <td style="padding:6px 6px; border:1px solid #000000; font-weight:900; font-size:13px; color:${statusColor}; text-align:center;"><b>${statusText}</b></td>
      <td style="padding:6px 6px; border:1px solid #000000; font-weight:900; font-size:13px; color:${isInactive ? 'red' : '#000000'};">${reasonText}</td>
      <td style="padding:6px 6px; border:1px solid #000000; text-align:center; font-weight:900; font-size:13px;">${m.rate}%</td>
      <td style="padding:6px 6px; border:1px solid #000000; text-align:center; font-weight:900; font-size:13px;">${m.level}</td>
    </tr>`;
  });
  html += "</tbody></table></div>";
  tableArea.innerHTML = html;
}

function backToEngagementFilters(containerId) {
  document.getElementById(`${containerId}_engagement_table_area`).style.display = "none";
  document.getElementById(`${containerId}_main_filter_section`).style.display = "block";
  resetEngagementPageHeader(containerId);
}

// 4. ወደ ሴቲንግ መመለሻን በትክክል የሚያስተካክለው ፈንክሽን
function resetEngagementPageHeader(containerId) {
  let pageBtn = document.querySelector("#engagementReportPage button");
  if (pageBtn) {
    pageBtn.innerHTML = "⬅️ ወደ ሴቲንግ ተመለስ";
    pageBtn.style.background = "#2563eb"; 
    
    // ማስተካከያ፦ ወደ ዋናው ገጽ እንዳይወስድ ራሱን የቻለ የክሊክ ትዕዛዝ በትክክል ተሰጥቶታል!
    pageBtn.onclick = function() {
      document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
      let sPage = document.getElementById('settingsPage'); 
      if(sPage) sPage.style.display = 'block';
    };
  }
}

function printEngagementTable(containerId) {
  let originalTable = document.getElementById(`${containerId}_final_engagement_table`);
  if (!originalTable) { alert("እባክዎ መጀመሪያ ሰንጠረዡን ይክፈቱት!"); return; }
  
  let clonedTable = originalTable.cloneNode(true); 
  clonedTable.removeAttribute('style');
  clonedTable.setAttribute('style', 'width:100%; border-collapse:collapse; font-size:12px; color:#000000; border:2px solid #000000; background:white;');
  
  clonedTable.querySelectorAll('thead th').forEach(th => { 
    th.setAttribute('style', 'padding:6px 5px; border:1.5px solid #000000; background-color:#ffffff !important; color:#000000 !important; font-weight:900; font-size:12px;'); 
  });
  clonedTable.querySelectorAll('tbody td').forEach(td => { 
    let currentColor = td.style.color;
    td.setAttribute('style', `padding:6px 5px; border:1px solid #000000; font-size:11px; font-weight:900; color:${currentColor || '#000000'};`); 
  });
  
  let subTitle = originalTable.getAttribute('data-title') || "የተማሪዎች የተሳትፎ ሪፖርት";
  document.getElementById("printArea").innerHTML = `<div style="text-align:center; margin-bottom:15px; font-family:sans-serif; color:#000000;"><h2 style="margin:3px 0; font-size:18px;">እንጦጦ መንበረ ስብሐት ቅድስት ሥላሴ ቤተክርስቲያን ውሉደ ብርሐን ሰንበት ትምህርት ቤት</h2><h3 style="margin:3px 0; font-size:14px; color:#334155;">${subTitle}</h3><p style="font-size:12px; margin:3px 0;">ቀን፦ ${new Date().toLocaleDateString('eb-ET')}</p><hr style="border:1px solid #000000; margin-top:8px; margin-bottom:10px;"></div>${clonedTable.outerHTML}`;
  window.print();
}

function downloadEngagementExcel(containerId, fileName) {
  let table = document.getElementById(`${containerId}_final_engagement_table`);
  if (!table) { alert("እባክዎ መጀመሪያ ሰንጠረዡን ይክፈቱት!"); return; }
  
  let csv = "\ufeff"; 
  for (let row of table.rows) {
    let rData = [];
    for (let i = 0; i < row.cells.length; i++) {
      if (row.cells[i].classList.contains('hide-on-export')) continue;
      let cellText = row.cells[i].innerText.replace(/\r?\n|\r/g, " ").trim();
      rData.push(`"${cellText}"`);
    }
    csv += rData.join(",") + "\n";
  }
  
  let blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
  let link = document.createElement("a"); 
  link.href = URL.createObjectURL(blob); 
  link.download = `ተሳትፎ_${fileName}.csv`; 
  link.click();
}
// ========================================================
// 📊 እጅግ ዘመናዊ፦ የAll List፣ Active እና Inactive ሪፖርቶች ስክሪፕት
// ========================================================

// 1. ዋናው ማጣሪያውን የሚያወጣው ፈንክሽን
// 1. የሪፖርት ዋና ማጣሪያ ምናሌ
function openGeneralReportMenu(containerId, reportType) {
  let titleText = "📊 የሁሉም ተማሪዎች ዝርዝር ሪፖርት";
  if (reportType === 'active') titleText = "🟢 የንቁ (Active) ተማሪዎች ሪፖርት";
  if (reportType === 'inactive') titleText = "🔴 የራቁ (Inactive) ተማሪዎች ሪፖርት";

  let html = `
  <div style="padding: 10px; font-family: sans-serif; width: 100%; box-sizing: border-box;">
    <div id="${containerId}_top_nav_area" style="margin-bottom:15px; width: 100%;">
      <button onclick="backToSettingsFromGeneral()" style="width:100%; padding:14px; font-weight:bold; border-radius:8px; font-size:14px; background:#000000; color:#FFD700; border:2px solid #FFD700; cursor:pointer; text-align:center; box-shadow: 0 4px 6px rgba(0,0,0,0.2);">⬅️ ወደ ሴቲንግ ተመለስ</button>
    </div>
    <div id="${containerId}_filter_section" style="display:block; width: 100%;">
      <h3 style="margin:0 0 10px 0; color:#1e293b; font-size:18px; font-weight:bold; text-align:center;">${titleText}</h3>
      <p style="font-size:14px; color:#64748b; margin:0 0 15px 0; text-align:center;">እባክዎ ማየት የሚፈልጉትን ሁኔታ ይምረጡ፦</p>
      <div style="display:flex; flex-direction:column; gap:12px; width:100%; max-width:400px; margin:0 auto 15px auto;">
        <button onclick="generateGeneralFinalTable('${containerId}', 'የሚማሩ', '${reportType}')" style="background:#000000; color:#FFD700; border:1.5px solid #FFD700; padding:14px; border-radius:8px; font-weight:bold; cursor:pointer; font-size:14px; text-align:center; box-shadow: 0 2px 4px rgba(0,0,0,0.15);">📖 ትምህርት የሚማሩ (1ኛ-12ኛ)</button>
        <button onclick="generateGeneralFinalTable('${containerId}', 'ያጠናቀቁ', '${reportType}')" style="background:#000000; color:#FFD700; border:1.5px solid #FFD700; padding:14px; border-radius:8px; font-weight:bold; cursor:pointer; font-size:14px; text-align:center; box-shadow: 0 2px 4px rgba(0,0,0,0.15);">🎓 ትምህርት ያጠናቀቁ</button>
        <button onclick="generateGeneralFinalTable('${containerId}', 'ሌላ', '${reportType}')" style="background:#000000; color:#FFD700; border:1.5px solid #FFD700; padding:14px; border-radius:8px; font-weight:bold; cursor:pointer; font-size:14px; text-align:center; box-shadow: 0 2px 4px rgba(0,0,0,0.15);">✨ ልዩ ምድብ (ዲቁና፣ አብነት...)</button>
      </div>
    </div>
    <div id="${containerId}_table_display_area" style="display:none; width:100%; overflow-x:auto; -webkit-overflow-scrolling:touch; margin-top:10px;"></div>
  </div>`;
  document.getElementById(containerId).innerHTML = html;
}

// 2. ሰንጠረዡን ሰርቶ በውብ መልክ የሚያሳየው ፈንክሽን
function generateGeneralFinalTable(containerId, eduStatus, reportType) {
  let list = students.filter(s => s.reason !== "በእረፍተ ስጋ");
  if (reportType === 'active') { list = list.filter(s => s.reason === "የለም" || s.reason === ""); } 
  else if (reportType === 'inactive') { list = list.filter(s => s.reason !== "የለም" && s.reason !== ""); }

  list = list.filter(s => {
    let currentClass = s.cls ? s.cls.toString().trim() : "";
    let classNum = parseInt(currentClass);
    let isGrade1to12 = !isNaN(classNum) && classNum >= 1 && classNum <= 12 && currentClass !== "የተጠናቀቁ";
    if (eduStatus === 'የሚማሩ') return isGrade1to12;
    else if (eduStatus === 'ያጠናቀቁ') return currentClass === "የተጠናቀቁ";
    else return isNaN(classNum) && currentClass !== "የተጠናቀቁ";
  });

  let tableArea = document.getElementById(`${containerId}_table_display_area`);
  if (!tableArea) return;

  if (list.length === 0) {
    tableArea.innerHTML = `<p style='padding:20px; color:red; font-weight:bold; font-size:15px; text-align:center;'>⚠️ በዚህ ምድብ ምንም የተማሪ ዳታ አልተገኘም!</p>`;
    document.getElementById(`${containerId}_filter_section`).style.display = "none";
    tableArea.style.display = "block";
    document.getElementById(`${containerId}_top_nav_area`).innerHTML = `<button onclick="backToGeneralFilters('${containerId}', '${reportType}')" style="width:100%; padding:14px; font-weight:bold; border-radius:8px; font-size:14px; background:#000000; color:#FFD700; border:2px solid #FFD700; cursor:pointer; text-align:center;">⬅️ ወደ ማጣሪያው ተመለስ</button>`;
    return;
  }

  let sorted = eduStatus === 'የሚማሩ' ? [...list].sort((a,b) => (parseInt(a.cls)||999) - (parseInt(b.cls)||999)) : (typeof sortAmharic === 'function' ? sortAmharic([...list]) : [...list].sort((a, b) => (a.name || "").localeCompare((b.name || ""), 'am')));

  document.getElementById(`${containerId}_filter_section`).style.display = "none";
  tableArea.style.display = "block";
  document.getElementById(`${containerId}_top_nav_area`).innerHTML = `<button onclick="backToGeneralFilters('${containerId}', '${reportType}')" style="width:100%; padding:14px; font-weight:bold; border-radius:8px; font-size:14px; background:#000000; color:#FFD700; border:2px solid #FFD700; cursor:pointer; text-align:center; box-shadow: 0 4px 6px rgba(0,0,0,0.2);">⬅️ ወደ ማጣሪያው ተመለስ</button>`;

  let displayTitle = (reportType === 'active' ? `የ${eduStatus} ንቁ (Active) አባላት ዝርዝር` : `የ${eduStatus} ከሰንበት ትምህርት ቤት የራቁ (Inactive) አባላት ዝርዝር`);

  let html = `
  <div style="display:flex; flex-direction:row; gap:10px; margin-bottom:15px; width:100%; justify-content:space-between;">
    <button onclick="printGeneralTable('${containerId}')" style="background:#000000; color:#FFD700; border:1.5px solid #FFD700; padding:12px 10px; border-radius:8px; font-weight:bold; cursor:pointer; font-size:13px; flex:1; text-align:center; box-shadow: 0 2px 4px rgba(0,0,0,0.15);">🖨️ Print ሪፖርት</button>
    <button onclick="downloadGeneralExcel('${containerId}', '${eduStatus}_${reportType}')" style="background:#000000; color:#FFD700; border:1.5px solid #FFD700; padding:12px 10px; border-radius:8px; font-weight:bold; cursor:pointer; font-size:13px; flex:1; text-align:center; box-shadow: 0 2px 4px rgba(0,0,0,0.15);">📊 Excel አውርድ</button>
  </div>
  <div style="width:100%; overflow-x:auto; border:2.5px solid #000000; border-radius:6px; background:white;">
    <table id="${containerId}_final_built_table" data-title="${displayTitle}" style="width:100%; min-width:1000px; border-collapse:collapse;">
      <thead><tr style="background:#ffffff !important; border-bottom:3px solid #000000;">
        <th style="padding:12px 6px; border:2px solid #000000; text-align:center; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ተ.ቁ</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:left; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ሙሉ ስም</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:center; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ክፍል</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:left; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ስልክ ቁጥር</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:left; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">የሚያገለግሉበት ክፍል</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:center; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ሁኔታ</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:left; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">የራቁበት ምክንያት</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:center; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ፐርሰንት (%)</th>
        <th style="padding:12px 8px; border:2px solid #000000; text-align:center; font-weight:900; font-size:14px; color:#000000; background:#ffffff;">ደረጃ</th>
        <th class="hide-on-print" style="padding:12px 6px; border:2px solid #000000; text-align:center; font-weight:900; font-size:14px; color:#000000; background:#ffffff; width:90px;">ማኅደር</th>
      </tr></thead><tbody>`;

  sorted.forEach((s, index) => {
    let m = calculateSingleStudentMetrics(s.id); 
    let isInactive = s.reason && s.reason !== "የለም" && s.reason !== "";
    let reasonText = isInactive ? `${s.reason}${s.reasonDetail ? ' (' + s.reasonDetail + ')' : ''}` : "-";
    
    html += `<tr style="color:#000000; background:white; font-weight:900; border-bottom:2px solid #000000;">
      <td style="padding:11px 6px; border:2px solid #000000; font-weight:900; font-size:13px; text-align:center;">${index + 1}</td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px;">${s.name}</td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px; text-align:center;">${s.cls}</td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px;">${s.phone || '-'}</td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px;">${s.department || s.currentServingDept || "-"}</td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px; color:${isInactive ? 'red' : 'green'}; text-align:center;"><b>${isInactive ? 'Inactive' : 'Active'}</b></td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px;">${reasonText}</td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px; text-align:center;"><b>${m.rate}%</b></td>
      <td style="padding:11px 8px; border:2px solid #000000; font-weight:900; font-size:13px; text-align:center;"><b>${m.level}</b></td>
      <td class="hide-on-print" style="padding:6px; border:2px solid #000000; text-align:center;">
        <button onclick="if(typeof viewStudentProfile === 'function') viewStudentProfile('${s.id}');" style="background:#2563eb; color:white; padding:6px 10px; border:none; border-radius:4px; cursor:pointer; font-size:11px; font-weight:bold;">👁️ ማኅደር</button>
      </td>
    </tr>`;
  });
  html += "</tbody></table></div>";
  tableArea.innerHTML = html;
}

// 3. ከሰንጠረዥ ወደ ማጣሪያ መመለሻ
function backToGeneralFilters(containerId, reportType) {
  document.getElementById(`${containerId}_table_display_area`).style.display = "none";
  document.getElementById(`${containerId}_filter_section`).style.display = "block";
  document.getElementById(`${containerId}_top_nav_area`).innerHTML = `<button onclick="backToSettingsFromGeneral()" style="width:100%; padding:14px; font-weight:bold; border-radius:8px; font-size:14px; background:#000000; color:#FFD700; border:2px solid #FFD700; cursor:pointer; text-align:center; box-shadow: 0 4px 6px rgba(0,0,0,0.2);">⬅️ ወደ ሴቲንግ ተመለስ</button>`;
}

// 4. ወደ ሴቲንግ መመለሻ
function backToSettingsFromGeneral() {
  document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
  let sPage = document.getElementById('settingsPage');
  if(sPage) sPage.style.display = 'block';
}

// 5. የፕሪንት ሥራ
function printGeneralTable(containerId) {
  let originalTable = document.getElementById(`${containerId}_final_built_table`);
  if (!originalTable) return;
  let clonedTable = originalTable.cloneNode(true);
  clonedTable.removeAttribute('style');
  clonedTable.setAttribute('style', 'width:100%; border-collapse:collapse; font-size:15px; color:#000000; border:3px solid #000000; background:white;');
  clonedTable.querySelectorAll('.hide-on-print').forEach(el => el.remove());
  clonedTable.querySelectorAll('tbody tr').forEach(tr => { if(tr.cells.length > 9) { tr.cells[9].remove(); } });
  clonedTable.querySelectorAll('thead th').forEach(th => { th.setAttribute('style', 'padding:14px 8px; border:2.5px solid #000000; background-color:#ffffff !important; color:#000000 !important; font-weight:900; font-size:15px; text-align:center;'); });
  clonedTable.querySelectorAll('tbody td').forEach(td => { let currentColor = td.style.color; td.setAttribute('style', `padding:12px 10px; border:2px solid #000000; font-size:14px; font-weight:900; color:${currentColor || '#000000'};`); });
  let subTitle = originalTable.getAttribute('data-title') || "የአባላት የተሳትፎ ደረጃ እሪፖርት";
  document.getElementById("printArea").innerHTML = `<div style="text-align:center; margin-bottom:20px; color:#000000; font-family:sans-serif;"><h2 style="margin:5px 0; font-size:22px; font-weight:bold;">የእንጦጦ መንበረ ስብሐት ቅድስት ሥላሴ ቤተክርስቲያን ውሉደ ብርሐን ሰ/ትቤት</h2><h3 style="margin:5px 0; font-size:17px; font-weight:bold;">${subTitle}</h3><hr style="border:1.5px solid #000000; margin-top:10px;"></div>${clonedTable.outerHTML}`;
  window.print();
}

// 6. የኤክሴል ማውረጃ ሥራ
function downloadGeneralExcel(containerId, fileName) {
  let table = document.getElementById(`${containerId}_final_built_table`);
  if (!table) return;
  let csv = "\ufeff";
  for (let row of table.rows) {
    let rData = [];
    let limit = row.cells.length;
    if (row.cells[limit-1].classList.contains('hide-on-print') || row.cells[limit-1].innerText.includes('ማኅደር')) { limit = limit - 1; }
    for (let i = 0; i < limit; i++) { rData.push(`"${row.cells[i].innerText.replace(/\r?\n|\r/g, " ").trim()}"`); }
    csv += rData.join(",") + "\n";
  }
  let blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
  let link = document.createElement("a");
  link.href = URL.createObjectURL(blob);
  link.download = `ሪፖርት_${fileName}.csv`;
  link.click();
}

    // ማስታወሻ ፎቶ ማዕከለ-ስዕላት (Gallery) ሎጂክ
    function openPhotoGalleryPage() {
      galleryStudents = students.filter(s => s.photo && s.photo !== "");
      galleryIndex = 0;
      updateGalleryView();
    }

    function updateGalleryView() {
      if(galleryStudents.length === 0) {
        document.getElementById("galleryInfo").innerText = "0/0";
        document.getElementById("galleryStudentName").innerText = "ምንም የተመዘገበ ፎቶ የለም";
        document.getElementById("galleryImg").src = "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 24 24' fill='none' stroke='%23cbd5e1' stroke-width='2'><circle cx='12' cy='8' r='4'/><path d='M6 21v-2a4 4 0 0 1 4-4h4a4 4 0 0 1 4 4v2'/></svg>";
        return;
      }
      let s = galleryStudents[galleryIndex];
      document.getElementById("galleryInfo").innerText = `${galleryIndex + 1} / ${galleryStudents.length}`;
      document.getElementById("galleryStudentName").innerText = `${s.name} (${s.cls}) ${s.christianName ? '['+s.christianName+']' : ''}`;
      document.getElementById("galleryImg").src = s.photo;
    }

    function navigateGallery(direction) {
      if(galleryStudents.length === 0) return;
      galleryIndex += direction;
      if(galleryIndex >= galleryStudents.length) galleryIndex = 0;
      if(galleryIndex < 0) galleryIndex = galleryStudents.length - 1;
      updateGalleryView();
    }

    function downloadGalleryPhoto() {
      if(galleryStudents.length === 0) { alert("የሚወርድ ፎቶ የለም!"); return; }
      let s = galleryStudents[galleryIndex];
      let link = document.createElement("a");
      link.href = s.photo;
      link.download = `${s.name}_ማስታወሻ_ፎቶ.png`;
      link.click();
    }
// 1. መረጃዎችን ከLocalStorage መጫኛ
let appPhotos = JSON.parse(localStorage.getItem('app_marha_gibir_photos')) || [];
let selectedFilesBase64 = [];

// 2. 📸 ፎቶ ሲመረጥ መጠኑን አሳንሶ (Compress) በስክሪኑ ላይ ወዲያው ማሳያ
function previewImages() {
  const fileInput = document.getElementById('photoInput');
  const container = document.getElementById('previewContainer');
  
  if (!fileInput || !container) return;
  
  container.innerHTML = ''; // የድሮውን ማጽጃ
  selectedFilesBase64 = []; // ዝርዝሩን ከአዲስ መጀመሪያ

  const files = fileInput.files;
  if (files.length === 0) return;

  Array.from(files).forEach(file => {
    const reader = new FileReader();
    reader.onload = function(e) {
      const imgElement = new Image();
      imgElement.src = e.target.result;
      
      imgElement.onload = function() {
        // ⚡️ ስልኩ እንዳይዘጋ የፎቶ መጠን ማሳነሻ (Canvas)
        const canvas = document.createElement('canvas');
        const MAX_WIDTH = 800; 
        let width = imgElement.width;
        let height = imgElement.height;

        if (width > MAX_WIDTH) {
          height *= MAX_WIDTH / width;
          width = MAX_WIDTH;
        }

        canvas.width = width;
        canvas.height = height;
        const ctx = canvas.getContext('2d');
        ctx.drawImage(imgElement, 0, 0, width, height);

        // ፎቶውን በ 70% ጥራት ያቀልለዋል
        const compressedBase64 = canvas.toDataURL('image/jpeg', 0.7);
        selectedFilesBase64.push(compressedBase64);

        // ትናንሽ ምስሎችን (Preview) መፍጠሪያ
        const previewImg = document.createElement('img');
        previewImg.src = compressedBase64;
        previewImg.style.width = '70px';
        previewImg.style.height = '70px';
        previewImg.style.objectFit = 'cover';
        previewImg.style.borderRadius = '6px';
        previewImg.style.border = '1px solid #cbd5e1';
        container.appendChild(previewImg);
      };
    };
    reader.readAsDataURL(file);
  });
}

// 3. 🚀 ፎቶዎችን ከመግለጫ ጋር አብሮ በሴፍቲ የማስቀመጫ ህግ
function savePhotos() {
  if (selectedFilesBase64.length === 0) {
    alert("እባክዎ መጀመሪያ ፎቶ ይምረጡ ወይም ፎቶው ሙሉ በሙሉ እስኪነበብ 1 ሰከንድ ይጠብቁ!");
    return;
  }

  const title = document.getElementById('eventTitle').value;
  const date = document.getElementById('eventDate').value;

  selectedFilesBase64.forEach(base64Data => {
    appPhotos.push({
      id: Date.now() + Math.random(),
      src: base64Data,
      title: title || '',
      date: date || ''
    });
  });

  try {
    localStorage.setItem('app_marha_gibir_photos', JSON.stringify(appPhotos));
    
    // ፎርሙን ማጽጃ
    document.getElementById('photoInput').value = '';
    document.getElementById('eventTitle').value = '';
    document.getElementById('eventDate').value = '';
    document.getElementById('previewContainer').innerHTML = '';
    
    renderProgramPhotos(); // ማሳያውን ማደሻ
    alert("ፎቶዎቹ በተሳካ ሁኔታ ተጭነዋል!");
  } catch (error) {
    alert("ስህተት፦ የማከማቻ ቦታው ስለሞላ እባክዎ አንዳንድ አሮጌ ፎቶዎችን ያጥፉ!");
  }
}

// 4. 🖼 የተጫኑትን ፎቶዎች በሙሉ አውጥቶ በሳጥኑ (photoGallery) ላይ ማሳያ
function renderProgramPhotos() {
  const gallery = document.getElementById('photoGallery');
  if (!gallery) return;
  gallery.innerHTML = '';

  appPhotos.forEach(photo => {
    const item = document.createElement('div');
    item.className = 'gallery-item';
    
    let infoHTML = '';
    if (photo.title || photo.date) {
      infoHTML = `<div class="item-info" style="padding: 8px; font-size: 12px; color: #334155;">
                    ${photo.title ? `<b>${photo.title}</b><br>` : ''}
                    ${photo.date ? `<small>📅 ${photo.date}</small>` : ''}
                  </div>`;
    }

    item.innerHTML = `
      <img src="${photo.src}" style="width: 100%; height: 120px; object-fit: cover; cursor: pointer;" onclick="viewImage('${photo.src}', '${photo.title}', '${photo.date}')">
      <button class="btn-delete" onclick="deletePhoto(${photo.id})">❌</button>
      ${infoHTML}
    `;
    gallery.appendChild(item);
  });
}

// 5. ❌ ፎቶ ማጥፊያ
function deletePhoto(id) {
  if (confirm("ይህንን ፎቶ ማጥፋት ይፈልጋሉ?")) {
    appPhotos = appPhotos.filter(p => p.id !== id);
    localStorage.setItem('app_marha_gibir_photos', JSON.stringify(appPhotos));
    renderProgramPhotos();
  }
}

// 6. 🔍 ፎቶውን በሙሉ ገጽ ማሳያ እና ማውረጃ (Download)
function viewImage(src, title, date) {
  const viewer = document.getElementById('imageViewerModal');
  const img = document.getElementById('viewerImage');
  const caption = document.getElementById('viewerCaption');
  const dlBtn = document.getElementById('downloadBtn');

  if (!viewer || !img) return;

  img.src = src;
  img.classList.remove('zoomed');
  
  if (title || date) {
    caption.style.display = 'block';
    caption.innerHTML = `<b>${title}</b> ${date ? `<br><small>ቀን፦ ${date}</small>` : ''}`;
  } else {
    caption.style.display = 'none';
  }

  dlBtn.onclick = function() {
    const link = document.createElement('a');
    link.href = src;
    link.download = (title || 'marha_gibir_photo') + '.jpg';
    link.click();
  };

  viewer.style.display = 'flex';
}

// 7. 👆 ዙም ማድረጊያ እና መልሶ ማነስያ (Toggle Zoom)
function toggleZoom(event) {
  const img = document.getElementById('viewerImage');
  if (!img) return;
  if (img.classList.contains('zoomed')) {
    img.classList.remove('zoomed');
  } else {
    img.classList.add('zoomed');
  }
}

function closeViewer() {
  document.getElementById('imageViewerModal').style.display = 'none';
}

// ገጹ መጀመሪያ ሲከፈት የቆዩ ፎቶዎች ካሉ እንዲያወጣ
document.addEventListener("DOMContentLoaded", () => {
  renderProgramPhotos();
});
// 🎥 የቪዲዮ ማስታወሻዎች ዝርዝር (የዩቲዩብ ሾርትስ ማስተካከያ የተደረገበት)
let myOnlineVideos = JSON.parse(localStorage.getItem('my_online_links_db')) || [];
let db;

// የ IndexedDB ዳታቤዝ መክፈቻ
const request = indexedDB.open("SecureVideoAppDB", 1);
request.onupgradeneeded = function(e) {
  db = e.target.result;
  if (!db.objectStoreNames.contains("local_videos")) {
    db.createObjectStore("local_videos", { keyPath: "vId" });
  }
};
request.onsuccess = function(e) {
  db = e.target.result;
  renderMyVideos();
};

// ቪዲዮ ለመጫንና ለማስቀመጥ
function saveNewVideo() {
  const lnk = document.getElementById('vLinkInput');
  const fl = document.getElementById('vFileInput');
  const cap = document.getElementById('vCaptionInput');
  const dt = document.getElementById('vDateInput');

  const title = cap.value.trim() || "ያለ ርዕስ";
  const date = dt.value || new Date().toISOString().split('T')[0];

  // 🌐 አማራጭ 1፦ በኦንላይን ሊንክ ከሆነ
  if (lnk.value.trim() !== "") {
    let rawUrl = lnk.value.trim();
    let finalUrl = rawUrl;
    let linkType = "direct"; 

    // 💡 1. የዩቲዩብ መደበኛ ሊንክ ከሆነ (watch?v=)
    if (rawUrl.includes("youtube.com/watch?v=")) {
      let videoId = rawUrl.split("v=")[1].split("&")[0];
      finalUrl = `https://www.youtube.com/embed/${videoId}`;
      linkType = "youtube";
    } 
    // 💡 2. የዩቲዩብ አጭር ሊንክ ከሆነ (youtu.be/)
    else if (rawUrl.includes("youtu.be/")) {
      let videoId = rawUrl.split("youtu.be/")[1].split("?")[0];
      finalUrl = `https://www.youtube.com/embed/${videoId}`;
      linkType = "youtube";
    } 
    // 💡 3. የዩቲዩብ ሾርትስ ከሆነ (youtube.com/shorts/) - አዲሱ ማስተካከያ!
    else if (rawUrl.includes("youtube.com/shorts/")) {
      let videoId = rawUrl.split("/shorts/")[1].split("?")[0];
      finalUrl = `https://www.youtube.com/embed/${videoId}`;
      linkType = "youtube";
    }
    // 💡 4. የቴሌግራም ሊንክ ከሆነ
    else if (rawUrl.includes("t.me/") && !rawUrl.endsWith("?embed=1")) {
      finalUrl = rawUrl + "?embed=1";
      linkType = "telegram";
    }

    const videoObj = {
      vId: Date.now(),
      vSrc: finalUrl,
      vTitle: title,
      vDate: date,
      vIsLink: true,
      vLinkType: linkType 
    };

    myOnlineVideos.push(videoObj);
    localStorage.setItem('my_online_links_db', JSON.stringify(myOnlineVideos));
    
    lnk.value = "";
    cap.value = "";
    alert("ቪዲዮው ከተጫነ ምስሉ ተጭኗል");
    renderMyVideos();
  } 
  // 📱 አማራጭ 2፦ ከስልክ ፋይል ከሆነ
  else if (fl.files.length > 0) {
    const file = fl.files[0];
    const originalBtnText = document.querySelector('.add').innerText;
    document.querySelector('.add').innerText = "⏳ ቪዲዮው እየተጫነ ነው...";
    document.querySelector('.add').disabled = true;

    const reader = new FileReader();
    reader.onload = function(e) {
      const videoObj = {
        vId: Date.now(),
        vSrc: e.target.result,
        vTitle: title,
        vDate: date,
        vIsLink: false,
        vLinkType: "local"
      };

      const transaction = db.transaction(["local_videos"], "readwrite");
      const store = transaction.objectStore("local_videos");
      store.add(videoObj);

      transaction.oncomplete = function() {
        fl.value = "";
        cap.value = "";
        document.querySelector('.add').innerText = originalBtnText;
        document.querySelector('.add').disabled = false;
        alert("ቪዲዮው ከተጫነ ምስሉ ተጭኗል");
        renderMyVideos();
      };
    };
    reader.readAsDataURL(file);
  } else {
    alert("እባክህ የቪዲዮ ሊንክ አስገባ ወይም ፋይል ምረጥ!");
  }
}

// ቪዲዮዎችን በገጹ ላይ ማሳየት
function renderMyVideos() {
  const zone = document.getElementById('vGalleryZone');
  if (!zone || !db) return;
  zone.innerHTML = '';

  const store = db.transaction("local_videos", "readonly").objectStore("local_videos");
  const getAllRequest = store.getAll();

  getAllRequest.onsuccess = function() {
    const localVideos = getAllRequest.result;
    const allVideos = [...localVideos, ...myOnlineVideos];

    if (allVideos.length === 0) {
      zone.innerHTML = `<p style="color:#94a3b8; text-align:center; grid-column:1/-1; padding:20px;">እስካሁን የተጫነ ቪዲዮ የለም!</p>`;
      return;
    }

    allVideos.sort((a, b) => b.vId - a.vId);

    allVideos.forEach(vid => {
      const card = document.createElement('div');
      card.className = 'v-card';
      
      let bdgColor = vid.vIsLink ? "#2563eb" : "#eab308";
      let bdgText = vid.vIsLink ? `🌐 ኦንላይን` : `📱 ስልክ`;
      if(vid.vLinkType === "youtube") bdgText = "🔴 YouTube";
      if(vid.vLinkType === "telegram") bdgText = "🔵 Telegram";

      card.innerHTML = `
        <div class="v-thumb" style="height: 120px;" onclick="openVFull('${vid.vSrc}', '${vid.vTitle}', '${vid.vDate}', '${vid.vLinkType}')">
          <span class="v-badge" style="background:${bdgColor}; color:white;">${bdgText}</span>
          <div class="v-play-btn" style="color: white;">▶️</div>
        </div>
        <div style="padding: 10px; font-size: 13px; color: #1e293b; display: flex; align-items: center; justify-content: space-between;">
          <div style="max-width: 85%; overflow: hidden;">
            <strong style="display:block; white-space:nowrap; text-overflow:ellipsis;">${vid.vTitle}</strong>
            <span style="color:#64748b; font-size:11px;">📅 ${vid.vDate}</span>
          </div>
          <button style="background:none; color:#ef4444; border:none; font-size:16px; cursor:pointer; padding: 5px;" onclick="event.stopPropagation(); deleteMyVideo(${vid.vId}, ${vid.vIsLink})">❌</button>
        </div>
      `;
      zone.appendChild(card);
    });
  };
}

// ቪዲዮ ለመሰረዝ
function deleteMyVideo(id, isLink) {
  if (confirm("ይህንን ቪዲዮ በእርግጥ ማጥፋት ይፈልጋሉ?")) {
    closeVFull();
    if (isLink) {
      myOnlineVideos = myOnlineVideos.filter(v => v.vId !== id);
      localStorage.setItem('my_online_links_db', JSON.stringify(myOnlineVideos));
      renderMyVideos();
    } else {
      const transaction = db.transaction(["local_videos"], "readwrite");
      transaction.objectStore("local_videos").delete(id);
      transaction.oncomplete = function() { renderMyVideos(); };
    }
  }
}

// ፉል ስክሪን መክፈቻ
function openVFull(src, title, date, linkType) {
  const modal = document.getElementById('vFullModal');
  const plyr = document.getElementById('vModalPlayer');
  const ifrmContainer = document.getElementById('iframeContainer');
  
  document.getElementById('vModalCaption').innerText = title;
  document.getElementById('vModalDate').innerText = "📅 ቀን፦ " + date;
  
  plyr.style.display = "none";
  plyr.src = "";
  ifrmContainer.style.display = "none";
  ifrmContainer.innerHTML = "";

  if (linkType === "youtube" || linkType === "telegram") {
    ifrmContainer.style.display = "block";
    // 💡 ማስተካከያ፦ የዩቲዩብን የደህንነት ስህተት (Error 153) ለመስበር የተጨመረ መመዘኛ (Origin & Sandbox)
    ifrmContainer.innerHTML = `<iframe src="${src}?autoplay=1&rel=0&modestbranding=1" style="width:100%; height:100%; border:none;" allow="autoplay; encrypted-media" allowfullscreen></iframe>`;
  } else {
    plyr.style.display = "block";
    plyr.src = src;
    plyr.play().catch(e => console.log("Auto play blocked"));
  }
  
  const dwn = document.getElementById('vModalDownload');
  dwn.href = src;
  dwn.download = `${title}.mp4`;
  dwn.style.display = (linkType === "youtube" || linkType === "telegram") ? "none" : "inline-block";

  modal.style.display = 'flex';
}

// ፉል ስክሪን መዝጊያ
function closeVFull() {
  const modal = document.getElementById('vFullModal');
  const plyr = document.getElementById('vModalPlayer');
  const ifrmContainer = document.getElementById('iframeContainer');
  
  if(plyr) { plyr.pause(); plyr.src = ""; }
  if(ifrmContainer) { ifrmContainer.innerHTML = ""; }
  
  modal.style.display = 'none';
}
// ==================================================
function openSingleStudentAttendancePage() {
  if(typeof navigateTo === "function") navigateTo('singleStudentAttendancePage');
  isEditAttendanceMode = false;
  
  let editBtn = document.getElementById("toggleEditAttBtn");
  let saveBtn = document.getElementById("saveEditedAttBtn");
  if(editBtn) editBtn.innerText = "✏️ Edit";
  if(saveBtn) saveBtn.classList.add("hidden");
  
  // ቀኖቹን ባዶ ማድረግ
  singleAttFromDate = "";
  singleAttToDate = "";
  let fInput = document.getElementById("singleAttFromDateInput");
  let tInput = document.getElementById("singleAttToDateInput");
  if(fInput) fInput.value = "";
  if(tInput) tInput.value = "";
  
  if(document.getElementById("singleAttLearningContainer")) document.getElementById("singleAttLearningContainer").innerHTML = "";
  if(document.getElementById("singleAttCompletedContainer")) document.getElementById("singleAttCompletedContainer").innerHTML = "";
  if(document.getElementById("singleAttOtherContainer")) document.getElementById("singleAttOtherContainer").innerHTML = "";
  
  let tableCont = document.getElementById("singleAttTableContainer");
  if(tableCont) tableCont.innerHTML = "<p style='color:#94a3b8; text-align:center; padding:35px;'>እባክዎ መጀመሪያ ከላይ ካሉት በተኖች አንዱን መርጠው ከሚመጣው ዝርዝር ላይ የተማሪ ስም ይምረጡ።</p>";
  
  let actions = document.getElementById("singleAttActions");
  if(actions) actions.classList.add("hidden");
  selectedSingleStudentId = "";
}

function showCategoryInSingleAtt(category) {
  let searchBox = document.getElementById("singleAttSearch");
  if(searchBox) searchBox.value = "";
  
  if (typeof students === 'undefined') return;
  let valid = students.filter(s => s.reason !== "በእረፍተ ስጋ");
  
  if(category === 'learning') {
    let learning = valid.filter(s => {
      let currentClass = s.cls ? s.cls.toString().trim() : "";
      let isGraduated = currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");
      let numMatch = currentClass.match(/\d+/);
      let isGrade1to12 = numMatch ? (parseInt(numMatch[0]) >= 1 && parseInt(numMatch[0]) <= 12) : false;
      return !isGraduated && (isGrade1to12 || currentClass === "");
    });
    renderSingleAttSubLists(learning, 'learning');
    if(document.getElementById("singleAttCompletedContainer")) document.getElementById("singleAttCompletedContainer").innerHTML = "";
    if(document.getElementById("singleAttOtherContainer")) document.getElementById("singleAttOtherContainer").innerHTML = "";
    
  } else if(category === 'graduated') {
    let completed = valid.filter(s => {
      let currentClass = s.cls ? s.cls.toString().trim() : "";
      return currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");
    });
    renderSingleAttSubLists(completed, 'graduated');
    if(document.getElementById("singleAttLearningContainer")) document.getElementById("singleAttLearningContainer").innerHTML = "";
    if(document.getElementById("singleAttOtherContainer")) document.getElementById("singleAttOtherContainer").innerHTML = "";
    
  } else if(category === 'other') {
    let other = valid.filter(s => {
      let currentClass = s.cls ? s.cls.toString().trim() : "";
      let isGraduated = currentClass.includes("ያጠናቀቁ") || currentClass.includes("የተጠናቀቁ") || currentClass.includes("ጨረሱ");
      let numMatch = currentClass.match(/\d+/);
      let isGrade1to12 = numMatch ? (parseInt(numMatch[0]) >= 1 && parseInt(numMatch[0]) <= 12) : false;
      return !isGraduated && !isGrade1to12 && currentClass !== "";
    });
    renderSingleAttSubLists(other, 'other');
    if(document.getElementById("singleAttLearningContainer")) document.getElementById("singleAttLearningContainer").innerHTML = "";
    if(document.getElementById("singleAttCompletedContainer")) document.getElementById("singleAttCompletedContainer").innerHTML = "";
  }
}

function renderSingleAttSubLists(arr, currentTab) {
  let sorted = [...arr];
  sorted.sort((a, b) => (a.name || "").localeCompare((b.name || ""), 'am'));

  if (currentTab === 'learning' || currentTab === 'all') {
    let hLearn = "";
    let learningArr = currentTab === 'all' ? sorted.filter(s => {
      let c = s.cls ? s.cls.toString() : "";
      return !c.includes("ያጠናቀቁ") && !c.includes("የተጠናቀቁ") && !c.includes("ጨረሱ") && (c.match(/\d+/) || c === "");
    }) : sorted;
    learningArr.forEach(s => {
      hLearn += `<div onclick="generateSingleStudentTable('${s.id}')" style="background:white; padding:10px; margin-bottom:5px; border-radius:8px; cursor:pointer; border:1px solid #cbd5e1; font-size:13px; font-weight:bold; color:#000000;">👤 ${s.name} <span style="color:#64748b; font-size:11px;">(${s.cls || 'ክፍል የለውም'})</span></div>`;
    });
    let c = document.getElementById("singleAttLearningContainer");
    if(c) c.innerHTML = hLearn || (currentTab === 'all' ? "" : "<p style='font-size:11px;color:#94a3b8;'>በዚህ ምድብ ምንም የለም</p>");
  }

  if (currentTab === 'completed' || currentTab === 'all') {
    let hComp = "";
    let completedArr = currentTab === 'all' ? sorted.filter(s => {
      let c = s.cls ? s.cls.toString() : "";
      return c.includes("ያጠናቀቁ") || c.includes("የተጠናቀቁ") || c.includes("ጨረሱ");
    }) : sorted;
    completedArr.forEach(s => {
      hComp += `<div onclick="generateSingleStudentTable('${s.id}')" style="background:white; padding:10px; margin-bottom:5px; border-radius:8px; cursor:pointer; border:1px solid #bbf7d0; font-size:13px; font-weight:bold; color:#000000;">👤 ${s.name} <span style="color:#16a34a; font-size:11px;">(${s.cls})</span></div>`;
    });
    let c = document.getElementById("singleAttCompletedContainer");
    if(c) c.innerHTML = hComp || (currentTab === 'all' ? "" : "<p style='font-size:11px;color:#94a3b8;'>በዚህ ምድብ ምንም የለም</p>");
  }

  if (currentTab === 'other' || currentTab === 'all') {
    let hOther = "";
    let otherArr = currentTab === 'all' ? sorted.filter(s => {
      let c = s.cls ? s.cls.toString() : "";
      let isGrad = c.includes("ያጠናቀቁ") || c.includes("የተጠናቀቁ") || c.includes("ጨረሱ");
      let isG1to12 = c.match(/\d+/);
      return !isGrad && !isG1to12 && c !== "";
    }) : sorted;
    otherArr.forEach(s => {
      hOther += `<div onclick="generateSingleStudentTable('${s.id}')" style="background:white; padding:10px; margin-bottom:5px; border-radius:8px; cursor:pointer; border:1px solid #fbcfe8; font-size:13px; font-weight:bold; color:#000000;">👤 ${s.name} <span style="color:#db2777; font-size:11px;">(${s.cls})</span></div>`;
    });
    let c = document.getElementById("singleAttOtherContainer");
    if(c) c.innerHTML = hOther || (currentTab === 'all' ? "" : "<p style='font-size:11px;color:#94a3b8;'>በዚህ ምድብ ምንም የለም</p>");
  }
}

// 🎯 ማሻሻያ 1፦ በስም መጀመሪያ ፊደል፣ በስልክ ቁጥር (phone) እና በክፍል (cls) የሚፈልግ ሰርች ባር
function filterSingleAttStudents() {
  let q = document.getElementById("singleAttSearch").value.toLowerCase().trim();
  if(q === "") {
    if(document.getElementById("singleAttLearningContainer")) document.getElementById("singleAttLearningContainer").innerHTML = "";
    if(document.getElementById("singleAttCompletedContainer")) document.getElementById("singleAttCompletedContainer").innerHTML = "";
    if(document.getElementById("singleAttOtherContainer")) document.getElementById("singleAttOtherContainer").innerHTML = "";
    return;
  }
  if (typeof students === 'undefined') return;
  let valid = students.filter(s => s.reason !== "በእረፍተ ስጋ");
  
  let filtered = valid.filter(s => {
    let name = (s.name || "").toLowerCase();
    let cls = (s.cls || "").toLowerCase();
    let phone = (s.phone || "").toLowerCase(); // ተማሪው ስልክ ቁጥር ካለው
    
    // በስም መጀመሪያ ፊደል ወይም ሙሉ ስም፣ በክፍል፣ ወይም በስልክ ቁጥር ማመሳከሪያ
    return name.startsWith(q) || name.includes(q) || cls.includes(q) || phone.includes(q);
  });
  
  renderSingleAttSubLists(filtered, 'all'); 
}

function generateSingleStudentTable(studentId) {
  selectedSingleStudentId = studentId;
  isEditAttendanceMode = false;
  
  let editBtn = document.getElementById("toggleEditAttBtn");
  let saveBtn = document.getElementById("saveEditedAttBtn");
  if(editBtn) editBtn.innerText = "✏️ Edit";
  if(saveBtn) saveBtn.classList.add("hidden");
  
  if (typeof students === 'undefined') return;
  let s = students.find(x => x.id === studentId);
  if(document.getElementById("selectedStudentTitle")) document.getElementById("selectedStudentTitle").innerText = `📅 አቴንዳንስ ታሪክ፦ ${s.name}`;
  if(document.getElementById("singleAttActions")) document.getElementById("singleAttActions").classList.remove("hidden");
  renderSingleStudentTableView();
}

// 🎯 ማሻሻያ 2፦ ቀኖቹ ሲቀያየሩ ውጤቱ አብሮ እንዲቀየር የሚያደርጉ ፈንክሽኖች
function onSingleAttDateFilterChange() {
  let fInput = document.getElementById("singleAttFromDateInput");
  let tInput = document.getElementById("singleAttToDateInput");

  singleAttFromDate = fInput ? fInput.value.trim() : "";
  singleAttToDate = tInput ? tInput.value.trim() : "";

  if (selectedSingleStudentId) {
    renderSingleStudentTableView();
  }
}

function normalizeDate(dateStr) {
  if (!dateStr) return "";

  let parts = dateStr.split(/[\/\-]/);

  // YYYY-MM-DD
  if (parts[0].length === 4) {
    return parts[0] + parts[1].padStart(2, "0") + parts[2].padStart(2, "0");
  }

  // DD/MM/YYYY
  return parts[2] + parts[1].padStart(2, "0") + parts[0].padStart(2, "0");
}

function renderSingleStudentTableView() {
  if (typeof students === "undefined" || typeof attendanceRecords === "undefined") return;

  let s = students.find(x => x.id === selectedSingleStudentId);
  if (!s) return;

  let from = singleAttFromDate ? normalizeDate(singleAttFromDate) : "";
  let to = singleAttToDate ? normalizeDate(singleAttToDate) : "";

  let html = `
    <table style="width:100%; border-collapse:collapse; background:white;">
      <thead>
        <tr style="background:#1e293b;color:white;">
          <th>ቀን</th>
          <th>መርሀግብር</th>
          <th>P</th>
          <th>L</th>
          <th>A</th>
        </tr>
      </thead>
      <tbody>
  `;

  let hasHistory = false;

  attendanceRecords.forEach((r) => {
    if (r.type !== "ትምህርት" || s.cls === r.progClass) {
      let recDate = normalizeDate(r.date);

      if (from && recDate < from) return;
      if (to && recDate > to) return;

      let isPresent = r.presents?.includes(selectedSingleStudentId);
      let isLeave = r.leaves?.includes(selectedSingleStudentId);

      hasHistory = true;

      html += `
        <tr>
          <td>${r.date}</td>
          <td>${r.type} ${r.progClass ? "- " + r.progClass : ""}</td>
          <td>${isPresent ? "🟢" : ""}</td>
          <td>${isLeave ? "🟡" : ""}</td>
          <td>${(!isPresent && !isLeave) ? "🔴" : ""}</td>
        </tr>
      `;
    }
  });

  html += `</tbody></table>`;

  let container = document.getElementById("singleAttTableContainer");
  if (container) {
    container.innerHTML = hasHistory
      ? html
      : "<p style='color:red;text-align:center;'>በዚህ የቀን ክልል ውስጥ ምንም መረጃ የለም</p>";
  }
}

function clearSingleAttDateFilter() {
  singleAttFromDate = "";
  singleAttToDate = "";
  let fInput = document.getElementById("singleAttFromDateInput");
  let tInput = document.getElementById("singleAttToDateInput");
  if(fInput) fInput.value = "";
  if(tInput) tInput.value = "";
  
  if(selectedSingleStudentId) {
    renderSingleStudentTableView();
  }
}

// 🎯 ማሻሻያ 3፦ የቀን መፈለጊያውን ታሳቢ ያደረገው የሰንጠረዥ ማውጫ
// ===============================
// 📅 DATE NORMALIZER
// ===============================
function normalizeDate(dateStr) {
  if (!dateStr) return "";

  let parts = dateStr.split(/[\/\-]/);
  if (parts.length !== 3) return dateStr;

  // YYYY-MM-DD
  if (parts[0].length === 4) {
    return parts[0] + parts[1].padStart(2, "0") + parts[2].padStart(2, "0");
  }

  // DD/MM/YYYY or DD-MM-YYYY
  let day = parts[0].padStart(2, "0");
  let month = parts[1].padStart(2, "0");
  let year = parts[2];

  return year + month + day;
}

// ===============================
// 🎯 SINGLE STUDENT TABLE VIEW
// ===============================
function renderSingleStudentTableView() {
  if (typeof students === 'undefined' || typeof attendanceRecords === 'undefined') return;

  let s = students.find(x => x.id === selectedSingleStudentId);
  if (!s) return;

  let studentRegistrationDate = s.regDate ? normalizeDate(s.regDate) : "";
  let fromDate = singleAttFromDate ? normalizeDate(singleAttFromDate) : "";
  let toDate = singleAttToDate ? normalizeDate(singleAttToDate) : "";

  let studentClass = s.cls ? s.cls.toString().trim() : "";

  let html = `
    <table style="width:100%; border-collapse:collapse; background:white; font-family:sans-serif; border:1px solid #cbd5e1; border-radius:8px;">
      <thead>
        <tr style="background:#1e293b; color:white;">
          <th style="padding:10px;">ቀን</th>
          <th style="padding:10px;">መርሀግብር</th>
          <th style="padding:10px;">P</th>
          <th style="padding:10px;">L</th>
          <th style="padding:10px;">A</th>
        </tr>
      </thead>
      <tbody>
  `;

  let hasHistory = false;

  attendanceRecords.forEach((r, rIdx) => {
    let recordClass = r.progClass ? r.progClass.toString().trim() : "";

    let matchStudent = false;

    // 1-12 ክፍል
    if (studentClass === recordClass) {
      matchStudent = true;
    }

    // ያጠናቀቁ
    else if (
      (studentClass.includes("ያጠናቀቁ") || studentClass.includes("የተጠናቀቁ")) &&
      recordClass === "ያጠናቀቁ"
    ) {
      matchStudent = true;
    }

    // ሌላ
    else {
      let hasNumber = /\d+/.test(studentClass);
      let graduated =
        studentClass.includes("ያጠናቀቁ") ||
        studentClass.includes("የተጠናቀቁ");

      if (!hasNumber && !graduated && recordClass === "ሌላ") {
        matchStudent = true;
      }
    }

    if (!matchStudent) return;

    let recDate = normalizeDate(r.date);

    if (studentRegistrationDate && recDate < studentRegistrationDate) return;
    if (fromDate && recDate < fromDate) return;
    if (toDate && recDate > toDate) return;

    hasHistory = true;

    let isPresent = r.presents && r.presents.includes(selectedSingleStudentId);
    let isLeave = r.leaves && r.leaves.includes(selectedSingleStudentId);
    let currentStatus = isPresent ? "P" : (isLeave ? "L" : "A");

    if (isEditAttendanceMode) {
      html += `
        <tr style="border-bottom:1px solid #e2e8f0;">
          <td style="padding:10px;">${r.date}</td>
          <td style="padding:10px;">${r.type} - ${r.progClass}</td>
          <td colspan="3" style="padding:10px; text-align:center;">
            <label><input type="radio" name="edit_rad_${rIdx}" value="P" ${currentStatus==="P"?"checked":""}> 🟢</label>
            <label><input type="radio" name="edit_rad_${rIdx}" value="L" ${currentStatus==="L"?"checked":""}> 🟡</label>
            <label><input type="radio" name="edit_rad_${rIdx}" value="A" ${currentStatus==="A"?"checked":""}> 🔴</label>
            <input type="hidden" class="edit-record-index" value="${rIdx}">
          </td>
        </tr>
      `;
    } else {
      html += `
        <tr style="border-bottom:1px solid #e2e8f0;">
          <td style="padding:10px;">${r.date}</td>
          <td style="padding:10px;">${r.type} - ${r.progClass}</td>
          <td style="padding:10px; text-align:center;">${isPresent ? "🟢 መጥቷል" : ""}</td>
          <td style="padding:10px; text-align:center;">${isLeave ? "🟡 ፈቃድ" : ""}</td>
          <td style="padding:10px; text-align:center;">${(!isPresent && !isLeave) ? "🔴 ቀርቷል" : ""}</td>
        </tr>
      `;
    }
  });

  html += "</tbody></table>";

  let container = document.getElementById("singleAttTableContainer");

  if (container) {
    container.innerHTML = hasHistory
      ? html
      : "<p style='text-align:center; padding:20px; color:red;'>⚠️ ምንም ታሪክ አልተገኘም</p>";
  }
}

function toggleEditAttendanceMode() {
  if(typeof askAdminPassword === "function") {
    if(!askAdminPassword()){ alert("የAdmin ፓስወርድ ስህተት ነው!"); return; }
  }
  isEditAttendanceMode = !isEditAttendanceMode;
  
  let editBtn = document.getElementById("toggleEditAttBtn");
  let saveBtn = document.getElementById("saveEditedAttBtn");
  if(editBtn) editBtn.innerText = isEditAttendanceMode ? "❌ Cancel" : "✏️ Edit";
  if(saveBtn) {
    if(isEditAttendanceMode) saveBtn.classList.remove("hidden");
    else saveBtn.classList.add("hidden");
  }
  renderSingleStudentTableView();
}

function saveEditedAttendanceData() {
  if (typeof attendanceRecords === 'undefined') return;
  let rows = document.querySelectorAll("#singleAttTableContainer tbody tr");
  rows.forEach(tr => {
    let hiddenInput = tr.querySelector(".edit-record-index");
    if(!hiddenInput) return;
    let rIdx = parseInt(hiddenInput.value);
    let rad = tr.querySelector(`input[name="edit_rad_${rIdx}"]:checked`);
    if(!rad) return;
    
    let newStatus = rad.value;
    let record = attendanceRecords[rIdx];
    if(record.presents) record.presents = record.presents.filter(id => id !== selectedSingleStudentId);
    if(record.leaves) record.leaves = record.leaves.filter(id => id !== selectedSingleStudentId);

    if(newStatus === "P") record.presents.push(selectedSingleStudentId);
    else if(newStatus === "L") record.leaves.push(selectedSingleStudentId);
  });
  localStorage.setItem("attendanceRecords", JSON.stringify(attendanceRecords));
  alert("📝 ሪከርዱ በተሳካ ሁኔታ ተስተካክሏል!");
  isEditAttendanceMode = false;
  
  let editBtn = document.getElementById("toggleEditAttBtn");
  let saveBtn = document.getElementById("saveEditedAttBtn");
  if(editBtn) editBtn.innerText = "✏️ Edit";
  if(saveBtn) saveBtn.classList.add("hidden");
  
  renderSingleStudentTableView();
  if(typeof recalculateAllMetrics === "function") recalculateAllMetrics();
}

function printSingleStudentAttendance() {
  if (typeof students === 'undefined') return;
  let s = students.find(x => x.id === selectedSingleStudentId);
  if(!s) return;
  let tableCont = document.getElementById("singleAttTableContainer");
  let content = tableCont ? tableCont.innerHTML : "";
  
  let printTemplate = `
    <div style="text-align:center; font-family:sans-serif; margin-bottom:20px; border-bottom:3px double #000; padding-bottom:10px;">
      <h2 style="margin:5px 0; font-size:18px;">የእንጦጦ መንበረ ስብሐት ቅድስት ሥላሴ ቤተክርስቲያን</h2>
      <h2 style="margin:5px 0; font-size:20px; color:#2563eb;">ውሉደ ብርሀን ሰንበት ትምህርት ቤት</h2>
      <h3 style="margin:8px 0; font-size:15px; background:#f1f5f9; padding:5px; display:inline-block; border-radius:5px;">📋 የአባላት የግል አቴዳስ ታሪክ ሪፖርት</h3>
      <p style="text-align:left; margin-top:15px; font-size:14px;"><b>የተማሪ ስም፦</b> ${s.name} &nbsp;&nbsp;&nbsp;&nbsp; <b>ክፍል፦</b> ${s.cls || 'የለውም'}</p>
    </div>
    ${content}
  `;
  
  let printArea = document.getElementById("printArea");
  if(printArea) {
    printArea.innerHTML = printTemplate;
    window.print();
  }
}

function downloadSingleStudentExcel() {
  if (typeof students === 'undefined' || typeof attendanceRecords === 'undefined') return;
  let s = students.find(x => x.id === selectedSingleStudentId);
  if(!s) return;
  
  let studentRegistrationDate = s.regDate || "";
  let csv = "\ufeff" + "ቀን,መርሀግብር,ሁኔታ\n";
  
  attendanceRecords.forEach(r => {
    if (r.type !== "ትምህርት" || s.cls === r.progClass) {
      
      if (studentRegistrationDate && r.date < studentRegistrationDate) return;
      if (singleAttFromDate && r.date < singleAttFromDate) return;
      if (singleAttToDate && r.date > singleAttToDate) return;
      
      let isP = r.presents && r.presents.includes(selectedSingleStudentId);
      let isL = r.leaves && r.leaves.includes(selectedSingleStudentId);
      csv += `"${r.date}","${r.type}${r.progClass ? ' ('+r.progClass+')' : ''}","${isP?'መጥቷል':(isL?'ፈቃድ':'ቀርቷል')}"\n`;
    }
  });
  let blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
  let link = document.createElement("a"); link.href = URL.createObjectURL(blob);
  link.download = `${s.name}_Attendance_History.csv`; link.click();
}
    function openAllAttendanceSummaryReport(type) {
  let valid = students.filter(s => s.reason !== "በእረፍተ ስጋ");
  
  if (type === 'learning') {
    // 1ኛ-12ኛ ክፍል (ቁጥር ያላቸውን ብቻ) ነጥሎ ማውጫ ሕግ
    let base = valid.filter(s => {
      let classNum = parseInt(s.cls);
      return !isNaN(classNum) && classNum >= 1 && classNum <= 12 && s.cls !== "የተጠናቀቁ";
    });
    buildSummaryTableRaw(base, "learningSummaryTableContainer", null, null);
    
  } else if (type === 'completed') {
    // በትክክል "የተጠናቀቁ" የሆኑትን ብቻ ማውጫ ሕግ
    let base = valid.filter(s => s.cls === "የተጠናቀቁ");
    buildSummaryTableRaw(base, "completedSummaryTableContainer", null, null);
    
  } else if (type === 'special') {
    // ቁጥር ያልሆኑ እና "የተጠናቀቁ" ያልሆኑትን (አድሚኑ የጻፋቸውን ልዩ ክፍሎች) ማውጫ ሕግ
    let base = valid.filter(s => {
      let classNum = parseInt(s.cls);
      return isNaN(classNum) && s.cls !== "የተጠናቀቁ";
    });
    buildSummaryTableRaw(base, "specialSummaryTableContainer", null, null);
  }
}

function buildSummaryTableRaw(studentArray, containerId, fromDate, toDate) {
  let html = `<table><thead><tr>
    <th>ተማሪ ስም</th>
    <th>ክፍል</th>
    <th>ስልክ ቁጥር</th>
    <th>የሚያገለግሉበት ክፍል</th>
    <th>ሁኔታ</th>
    <th>ጠቅላላ ቀን</th>
    <th>P</th>
    <th>L</th>
    <th>A</th>
    <th>ፐርሰንት</th>
    <th>ደረጃ</th>
  </tr></thead><tbody>`;

  if (studentArray.length === 0) {
    document.getElementById(containerId).innerHTML =
      "<p style='text-align:center;'>ምንም ተማሪ የለም</p>";
    return;
  }

  let sorted = sortAmharic([...studentArray]);

  sorted.forEach(s => {
    let presentCount = 0;
    let leaveCount = 0;
    let totalEvents = 0;

    let studentRegistrationDate = normalizeDate(s.regDate || "");

    attendanceRecords.forEach(r => {
      let recDate = normalizeDate(r.date);

      // ✅ 1. ከምዝገባ በፊት አትቆጠር
      if (studentRegistrationDate && recDate < studentRegistrationDate) return;

      // ✅ 2. የቀን ማጣሪያ
      if (fromDate && recDate < normalizeDate(fromDate)) return;
      if (toDate && recDate > normalizeDate(toDate)) return;

      // ✅ 3. ትምህርት ONLY በክፍል መቆጣጠር (SAFE FIX)
      if (r.type === "ትምህርት") {
        if (!r.progClass || r.progClass !== s.cls) return;
      }

      totalEvents++;

      if (r.presents?.includes(s.id)) {
        presentCount++;
      } else if (r.leaves?.includes(s.id)) {
        leaveCount++;
      }
    });

    let absentCount = totalEvents - presentCount - leaveCount;

    let totalAttended = presentCount + leaveCount;

    let rate = totalEvents > 0
      ? Math.round((totalAttended / totalEvents) * 100)
      : 100;

    let level =
      rate >= 75 ? "ከፍተኛ" :
      rate >= 50 ? "መካከለኛ" :
      "ዝቅተኛ";

    let statusText =
      (s.reason === "የለም" || s.reason === "")
        ? "Active"
        : "Inactive";

    html += `
      <tr>
        <td><b>${s.name}</b></td>
        <td>${s.cls}</td>
        <td><b>${s.phone || "-"}</b></td>
        <td><b>${s.currentServingDept || "-"}</b></td>
        <td style="font-weight:bold; color:${statusText === "Active" ? "green" : "red"};">
          ${statusText}
        </td>
        <td>${totalEvents}</td>
        <td>${presentCount}</td>
        <td>${leaveCount}</td>
        <td>${absentCount}</td>
        <td><b>${rate}%</b></td>
        <td><b>${level}</b></td>
      </tr>
    `;
  });

  html += "</tbody></table>";
  document.getElementById(containerId).innerHTML = html;
}
function filterLearningSummaryTable() {
  let q = document.getElementById("searchLearningSummary").value.toLowerCase();
  let fromDate = document.getElementById("learningSumFrom").value;
  let toDate = document.getElementById("learningSumTo").value;
  let base = students.filter(s => {
    let classNum = parseInt(s.cls);
    return s.reason !== "በእረፍተ ስጋ" && !isNaN(classNum) && classNum >= 1 && classNum <= 12 && s.cls !== "የተጠናቀቁ";
  });
  let filtered = base.filter(s => s.name.toLowerCase().includes(q));
  buildSummaryTableRaw(filtered, "learningSummaryTableContainer", fromDate, toDate);
}

function filterCompletedSummaryTable() {
  let q = document.getElementById("searchCompletedSummary").value.toLowerCase();
  let fromDate = document.getElementById("completedSumFrom").value;
  let toDate = document.getElementById("completedSumTo").value;
  let base = students.filter(s => s.reason !== "በእረፍተ ስጋ" && s.cls === "የተጠናቀቁ");
  let filtered = base.filter(s => s.name.toLowerCase().includes(q));
  buildSummaryTableRaw(filtered, "completedSummaryTableContainer", fromDate, toDate);
}

function filterSpecialSummaryTable() {
  let q = document.getElementById("searchSpecialSummary").value.toLowerCase();
  let fromDate = document.getElementById("specialSumFrom").value;
  let toDate = document.getElementById("specialSumTo").value;
  let base = students.filter(s => {
    let classNum = parseInt(s.cls);
    return s.reason !== "በእረፍተ ስጋ" && isNaN(classNum) && s.cls !== "የተጠናቀቁ";
  });
  let filtered = base.filter(s => s.name.toLowerCase().includes(q));
  buildSummaryTableRaw(filtered, "specialSummaryTableContainer", fromDate, toDate);
}

// 🎯 ማሻሻያ 2፦ ፕሪንት ሲደረግ ቀኖቹን መጨረሻቸው ላይ «ዓ.ም» እያደረገ ሄዲንግ ላይ ያትማል
function printAttendanceSummaryTable(type) {
  let containerId = '';
  let reportTitle = '';
  let fromDate = '';
  let toDate = '';
  
  if (type === 'learning') {
    containerId = 'learningSummaryTableContainer';
    reportTitle = 'በትምህርት ላይ ያሉ አባላት ማጠቃለያ አቴንዳንስ';
    fromDate = document.getElementById("learningSumFrom") ? document.getElementById("learningSumFrom").value : "";
    toDate = document.getElementById("learningSumTo") ? document.getElementById("learningSumTo").value : "";
  } else if (type === 'completed') {
    containerId = 'completedSummaryTableContainer';
    reportTitle = 'ትምህርት ያጠናቀቁ አባላት ማጠቃለያ አቴንዳንስ';
    fromDate = document.getElementById("completedSumFrom") ? document.getElementById("completedSumFrom").value : "";
    toDate = document.getElementById("completedSumTo") ? document.getElementById("completedSumTo").value : "";
  } else if (type === 'special') {
    containerId = 'specialSummaryTableContainer';
    reportTitle = 'ልዩ የትምህርት ሁኔታዎች ማጠቃለያ አቴንዳንስ';
    fromDate = document.getElementById("specialSumFrom") ? document.getElementById("specialSumFrom").value : "";
    toDate = document.getElementById("specialSumTo") ? document.getElementById("specialSumTo").value : "";
  }
  
  // 💡 የፕሪንት ቀኑን ታሪክ በዓ.ም የማሳያ ጽሑፍ ሎጂክ
  let printDateInfoText = "የአጠቃላይ ቀናት ማጠቃለያ ሪፖርት";
  if (fromDate || toDate) {
    printDateInfoText = `የሪፖርቱ ጊዜ፦ ከ ${fromDate ? fromDate + ' ዓ.ም' : 'መጀመሪያ'} እስከ ${toDate ? toDate + ' ዓ.ም' : 'ዛሬ'}`;
  }

  let content = document.getElementById(containerId).innerHTML;
  
  document.getElementById("printArea").innerHTML = `
    <div style="text-align:center; font-family: 'Arial', sans-serif; margin-bottom: 20px; padding: 10px;">
      <h2 style="margin:0; font-size:20px; color:#1e293b;">የእንጦጦ መንበረ ስብሐት ቅድስት ሥላሴ ቤተክርስቲያን ውሉደ ብርሐን ሰ/ትቤት</h2>
      <h3 style="margin:5px 0 5px 0; font-size:16px; color:#475569; font-weight:normal;">${reportTitle}</h3>
      <p style="margin:0; font-size:13px; font-weight:bold; color:#ea580c; border-bottom:2px solid #cbd5e1; padding-bottom:10px;">${printDateInfoText}</p>
    </div>
    ${content}
  `;
  window.print();
}

function downloadAttendanceSummaryExcel(type) {
  let containerId = '';
  if (type === 'learning') containerId = 'learningSummaryTableContainer';
  else if (type === 'completed') containerId = 'completedSummaryTableContainer';
  else if (type === 'special') containerId = 'specialSummaryTableContainer';
  
  let table = document.querySelector(`#${containerId} table`);
  if(!table) return;
  let csv = "\ufeff";
  for (let row of table.rows) {
    let rData = [];
    for (let cell of row.cells) rData.push(`"${cell.innerText}"`);
    csv += rData.join(",") + "\n";
  }
  let blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
  let link = document.createElement("a"); link.href = URL.createObjectURL(blob);
  link.download = `${type}_Summary.csv`; link.click();
}
// 1. ዋናው የገጽ መክፈቻ
function openRestInPeacePage() {
    const allPages = document.querySelectorAll('.app-page');
    allPages.forEach(p => p.style.display = 'none');
    const ripPage = document.getElementById('restInPeacePage');
    if (ripPage) ripPage.style.display = 'block';

    let ripList = students.filter(s => s.reason === "በእረፍተ ስጋ");
    let sorted = (typeof sortAmharic === 'function') ? sortAmharic([...ripList]) : ripList;

    // ማጠቃለያዎችን ማሳየት
    if(document.getElementById('ripTotalCount')) document.getElementById('ripTotalCount').innerText = sorted.length;
    if(document.getElementById('ripMaleCount')) document.getElementById('ripMaleCount').innerText = sorted.filter(s => s.gender === "Male").length;
    if(document.getElementById('ripFemaleCount')) document.getElementById('ripFemaleCount').innerText = sorted.filter(s => s.gender === "Female").length;

    document.getElementById('ripContainer').style.display = 'flex';
    document.getElementById('ripTableSection').style.display = 'none';

    buildRipCardUI(sorted);
    buildRipTableUI(sorted);
}

function navigateToRipPage() { openRestInPeacePage(); }

// 2. የካርድ እና የቴብል እይታ መቀያየሪያ
function toggleRipSection(viewType) {
    document.getElementById('ripContainer').style.display = (viewType === 'list') ? 'flex' : 'none';
    document.getElementById('ripTableSection').style.display = (viewType === 'table') ? 'block' : 'none';
}

// 3. 🖼️ የካርድ ዝርዝር ማሳያ (ከፕሪንት እና ኤክሴል ጋር)
function buildRipCardUI(dataArray) {
    const container = document.getElementById('ripContainer');
    container.innerHTML = `
        <div style="width:100%; padding:10px; text-align:center;">
            <button onclick="printRipTable()" style="padding:10px; background:#000; color:#FFD700; border-radius:5px;">🖨️ ፕሪንት</button>
            <button onclick="exportRipToExcel()" style="padding:10px; background:#000; color:#FFD700; border-radius:5px;">📊 ኤክሴል</button>
        </div>
    `;

    dataArray.forEach((s, index) => {
        const card = document.createElement('div');
        card.style.cssText = 'flex: 0 0 250px; border: 1px solid #cbd5e1; padding: 15px; margin: 10px; border-radius: 8px; text-align: center; background:white;';
        
        // ፎቶ 8*10 (80px * 100px)
        let img = s.photo ? s.photo : "data:image/svg+xml;utf8,<svg width='80' height='100'><rect width='80' height='100' fill='#eee'/></svg>";
        
        card.innerHTML = `
            <img src="${img}" style="width:80px; height:100px; object-fit:cover; border-radius:4px;">
            <p><b>ስም:</b> ${s.name}</p>
            <p><b>ክፍል:</b> ${s.eduLevel || '-'}</p>
            <p style="color:red;"><b>ያረፉበት:</b> ${s.restInPeaceDate || '-'}</p>
            <button onclick="viewStudentProfile('${s.id}')" style="background:#2563eb; color:white; padding:5px 10px; border:none; border-radius:4px;">ማኅደር</button>
        `;
        container.appendChild(card);
    });
}

// 4. 📊 የቴብል ዝርዝር ማሳያ
function buildRipTableUI(dataArray) {
    const table = document.getElementById('ripReportTable');
    table.innerHTML = `
        <thead>
            <tr style="background-color: #1e293b; color: white;">
                <th style="padding:10px;">ተ.ቁ</th><th>ክርስትና ስም</th><th>ሙሉ ስም</th><th>ክፍል</th><th>ያረፉበት ቀን</th>
            </tr>
        </thead>
        <tbody id="ripTableBody"></tbody>
    `;
    const tbody = document.getElementById('ripTableBody');
    dataArray.forEach((s, i) => {
        tbody.innerHTML += `
            <tr style="border-bottom:1px solid #ccc;">
                <td style="padding:10px;">${i+1}</td>
                <td>${s.christianName || '---'}</td>
                <td>${s.name}</td>
                <td>${s.eduLevel || '---'}</td>
                <td style="color:red;">${s.restInPeaceDate || '---'}</td>
            </tr>
        `;
    });
}

// 5. 📄 ፕሪንት ማድረጊያ (አዲስ ዊንዶው ስለሚጠቀም ዳታ አይጠፋም)
function printRipTable() {
    const tableHTML = document.getElementById('ripReportTable').outerHTML;
    const win = window.open('', '_blank');
    win.document.write(`<html><body><h2 style="text-align:center;">የዕረፍተ ሥጋ አባላት መታሰቢያ</h2>${tableHTML}</body></html>`);
    win.document.close();
    win.print();
}

// 6. 🟢 Excel ማውረጃ
function exportRipToExcel() {
    let csv = "ተ.ቁ,ክርስትና ስም,ሙሉ ስም,ክፍል,ያረፉበት ቀን\n";
    let rows = document.querySelectorAll("#ripReportTable tr");
    rows.forEach(row => {
        let cols = row.querySelectorAll("td, th");
        let arr = Array.from(cols).map(c => c.innerText);
        csv += arr.join(",") + "\n";
    });
    let blob = new Blob([csv], { type: 'text/csv' });
    let url = window.URL.createObjectURL(blob);
    let a = document.createElement("a");
    a.href = url;
    a.download = "የዕረፍተ_ሥጋ_መዝገብ.csv";
    a.click();
}
// 🚀 1. ሴቲንግ ውስጥ ያለው በተን ሲነካ ገጹን የሚከፍተው ዋናው ፈንክሽን
function openRestInPeacePage() {
  // ገጹን መቀየር
  const allPages = document.querySelectorAll('.app-page');
  allPages.forEach(p => p.style.display = 'none');
  const ripPage = document.getElementById('restInPeacePage');
  if (ripPage) ripPage.style.display = 'block';

  // 🎯 2. ካንተ እውነተኛ ዳታቤዝ (students) ላይ «በእረፍተ ስጋ» የተለዩትን ማጣራት
  let ripList = students.filter(s => s.reason === "በእረፍተ ስጋ");
  
  // 3. በአማርኛ የፊደል ተራ መደርደር
  let sorted = sortAmharic([...ripList]);

  // 📊 4. የቁጥር ማጠቃለያዎችን ማስላት
  document.getElementById('ripTotalCount').innerText = sorted.length;
  
  let males = sorted.filter(s => s.gender === "Male").length;
  let females = sorted.filter(s => s.gender === "Female").length;
  
  document.getElementById('ripMaleCount').innerText = males;
  document.getElementById('ripFemaleCount').innerText = females;

  // ገጹ ሲከፈት መጀመሪያ ካርዶቹ በስላይደር እንዲታዩ ማድረግ
  document.getElementById('ripContainer').style.display = 'flex';
  document.getElementById('ripTableSection').style.display = 'none';
  document.getElementById('ripSearchInput').value = '';

  // ካርዶቹ ወደ ጎን እንዲያልፉ ምቹ ማድረግ
  const container = document.getElementById('ripContainer');
  container.style.overflowX = 'auto';
  container.style.display = 'flex';
  container.style.gap = '15px';
  container.style.padding = '10px 5px';
  container.style.scrollSnapType = 'x mandatory';
  container.style.webkitOverflowScrolling = 'touch';

  // 5. ለሁለቱም እይታዎች ዳታውን ሰርቶ ማዘጋጀት
  buildRipCardUI(sorted);
  buildRipTableUI(sorted);
}

// 🚀 ለሰላማዊ አሰሳ ተጨማሪ ፈንክሽን
function navigateToRipPage() {
  openRestInPeacePage();
}

// =========================================================
// 🕹️ ረዳት ፈንክሽኖች
// =========================================================

// ሀ) የካርድ እና የቴብል እይታ መቀያየሪያ በተን
function toggleRipSection(viewType) {
  const container = document.getElementById('ripContainer');
  const tableSection = document.getElementById('ripTableSection');

  if (viewType === 'list') {
    container.style.display = 'flex'; // ስላይደር ካርዶችን ማሳየት
    tableSection.style.display = 'none';
  } else if (viewType === 'table') {
    container.style.display = 'none';
    tableSection.style.display = 'block'; // ቴብሉን ማሳየት
  }
}

// ለ) 🔍 የፍለጋ ሳጥን (Search Bar) ሎጂክ
function searchRipStudents() {
  let query = document.getElementById('ripSearchInput').value.trim().toLowerCase();
  let ripList = students.filter(s => s.reason === "በእረፍተ ስጋ");
  
  let result = ripList.filter(s => 
    s.name.toLowerCase().includes(query) || 
    (s.christianName && s.christianName.toLowerCase().includes(query))
  );

  let sortedResult = sortAmharic([...result]);

  document.getElementById('ripContainer').style.display = 'flex';
  document.getElementById('ripTableSection').style.display = 'none';

  buildRipCardUI(sortedResult);
}

// ሐ) 🖼️ የካርድ ዝርዝር ማሳያ (ፎቶው 4x5 በሆነ ሳይዝ እንዲመጣ የተስተካከለ)
function buildRipCardUI(dataArray) {
  const container = document.getElementById('ripContainer');
  container.innerHTML = '';

  if (dataArray.length === 0) {
    container.innerHTML = `<p style="text-align:center; color:#94a3b8; padding:20px; width:100%;">ምንም የተመዘገበ አባል አልተገኘም!</p>`;
    return;
  }

  dataArray.forEach((s, index) => {
    const card = document.createElement('div');
    card.className = 'rip-card'; 
    card.style.flex = '0 0 280px'; 
    card.style.scrollSnapAlign = 'center';
    card.style.boxSizing = 'border-box';
    card.style.padding = '15px';
    card.style.position = 'relative';

    // SVG አይኮኑም መታወቂያ መልክ እንዲይዝ ሬክታንግል ተደርጓል
    let img = s.photo ? s.photo : "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='100' height='125' viewBox='0 0 24 24' fill='none' stroke='%23cbd5e1' stroke-width='2'><rect x='4' y='3' width='16' height='18' rx='2'/><circle cx='12' cy='10' r='3'/><path d='M7 21v-1a3 3 0 0 1 3-3h4a3 3 0 0 1 3 3v1'/></svg>";
    let genderAmharic = s.gender === "Male" ? "ወንድ" : (s.gender === "Female" ? "ሴት" : "-");

    card.innerHTML = `
      <div style="text-align: center; margin-bottom: 10px;">
        <img src="${img}" style="width:100px; height:125px; object-fit:cover; border-radius:6px; border:2px solid #cbd5e1;">
        <span style="position: absolute; top: 10px; left: 15px; background: #334155; color: white; padding: 2px 8px; border-radius: 10px; font-size: 11px;">ተ.ቁ፦ ${index + 1}</span>
      </div>
      <p style="color:#facc15; font-weight:bold; margin:4px 0; font-size:13px;">☦️ የክርስትና ስም፦ ${s.christianName || '-'}</p>
      <p style="color:#ffffff; font-weight:bold; margin:4px 0; font-size:13px;">👤 ሙሉ ስም፦ ${s.name}</p>
      <p style="color:#cbd5e1; margin:4px 0; font-size:12px;">👫 ጾታ፦ ${genderAmharic}</p>
      <p style="color:#cbd5e1; margin:4px 0; font-size:12px;">📅 የተመዘገቡበት ቀን፦ ${s.regDate || '-'}</p>
      <p style="color:#cbd5e1; margin:4px 0; font-size:12px;">🎓 ክፍል፦ ${s.eduLevel || '-'}</p>
      <p style="color:#cbd5e1; margin:4px 0; font-size:12px;">🛠️ ያገለገሉበት ክፍል፦ ${s.currentServingDept || '-'}</p>
      <p style="color:#ef4444; font-weight:bold; margin:6px 0; font-size:12px;">🕊️ ያረፉበት ቀን፦ <span style="color:#ef4444;">${s.restInPeaceDate || '-'}</span></p>
      
      <button onclick="event.stopPropagation(); if(typeof viewStudentProfile === 'function') viewStudentProfile('${s.id}');" 
              style="width: 100%; margin-top: 10px; background-color: #2563eb; color: white; padding: 8px; border: none; border-radius: 6px; cursor: pointer; font-weight: bold; font-size: 12px;">
         👁️ ወደ ማኅደር/ፕሮፋይል ሂድ
      </button>
    `;
    container.appendChild(card);
  });
}

// መ) 📊 የቴብል (ሰንጠረዥ) ዝርዝር ማሳያ - 💡 ርዕሶቹን ወደ ጎን፣ ስም ዝርዝሩን ወደታች በራስ-ሰር የሚያስተካክል ፈንክሽን
function buildRipTableUI(dataArray) {
  const table = document.getElementById('ripReportTable');
  if (!table) return;

  table.innerHTML = `
    <thead>
      <tr style="background-color: #1e293b; color: white; font-size: 13px;">
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:center;">ተ.ቁ</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:left;">የክርስትና ስም</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:left;">ሙሉ ስም</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:center;">ጾታ</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:left;">የተመዘገቡበት ቀን</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:left;">ክፍል</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:left;">ያገለገሉበት ክፍል</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:left; color: #f87171;">ያረፉበት ቀን</th>
        <th style="padding: 12px; border: 1px solid #cbd5e1; text-align:center;">ማኅደር</th>
      </tr>
    </thead>
    <tbody id="ripTableBody" style="font-size: 13px; color: #1e293b;"></tbody>
  `;

  const tbody = document.getElementById('ripTableBody');

  if (dataArray.length === 0) {
    tbody.innerHTML = `<tr><td colspan="9" style="text-align:center; padding:20px; color:#1e293b; background:#ffffff;">ምንም ዝርዝር መረጃ የለም</td></tr>`;
    return;
  }

  dataArray.forEach((s, index) => {
    const tr = document.createElement('tr');
    tr.style.borderBottom = '1px solid #cbd5e1';
    tr.style.backgroundColor = '#ffffff'; 

    let genderAmharic = s.gender === "Male" ? "ወንድ" : (s.gender === "Female" ? "ሴት" : "-");

    tr.innerHTML = `
      <td style="padding: 12px; border: 1px solid #cbd5e1; text-align:center;">${index + 1}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1; font-weight:bold;">${s.christianName || '---'}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1; font-weight:bold;">${s.name}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1; text-align:center;">${genderAmharic}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1;">${s.regDate || '---'}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1;">${s.eduLevel || '---'}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1;">${s.currentServingDept || '---'}</td>
      <td style="padding: 12px; border: 1px solid #cbd5e1; color:#ef4444; font-weight:bold;">${s.restInPeaceDate || '---'}</td>
      <td style="padding: 6px; border: 1px solid #cbd5e1; text-align:center;">
        <button onclick="if(typeof viewStudentProfile === 'function') viewStudentProfile('${s.id}');" 
                style="background-color: #2563eb; color: white; padding: 6px 12px; border: none; border-radius: 4px; cursor: pointer; font-weight: bold; font-size: 11px;">
           👁️ ማኅደር
        </button>
      </td>
    `;
    tbody.appendChild(tr);
  });
}

// 📄 ፕሪንት ማድረጊያ
function printRipTable() {
  const printContents = document.getElementById('ripTableSection').innerHTML;
  const originalContents = document.body.innerHTML;

  document.body.innerHTML = `
    <div style="padding:30px; font-family:sans-serif; background: white; color: black;">
      <h1 style="text-align:center;">የሰንበት ትምህርት ቤት የዕረፍተ ሥጋ አባላት መታሰቢያ መዝገብ</h1>
      <hr style="margin-bottom:20px;">
      ${printContents}
    </div>
  `;
  window.print();
  document.body.innerHTML = originalContents;
  window.location.reload(); 
}

// 🟢 Excel (.csv) ማውረጃ
function exportRipToExcel() {
  let csv = [];
  const rows = document.querySelectorAll("#ripReportTable tr");
  
  for (let i = 0; i < rows.length; i++) {
    let row = [], cols = rows[i].querySelectorAll("td, th");
    for (let j = 0; j < cols.length; j++) {
      let text = cols[j].innerText.replace(/,/g, ' ');
      row.push(text);
    }
    csv.push(row.join(","));
  }

  let csvContent = "data:text/csv;charset=utf-8,\uFEFF" + csv.join("\n");
  let encodedUri = encodeURI(csvContent);
  let link = document.createElement("a");
  link.setAttribute("href", encodedUri);
  link.setAttribute("download", "የዕረፍተ_ሥጋ_ቅዱሳን_መዝገብ.csv");
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
}
// ⌨️ በኪቦርድ ቀስት ቁልፎች ካርዶቹን ማሳለፊያ ኮድ
document.addEventListener('keydown', function(event) {
  const container = document.getElementById('ripContainer');
  // የሪፕ ገጽ ክፍት መሆኑን እና ስክሪን ላይ መታየቱን ማረጋገጫ
  if (container && container.style.display === 'flex') {
    if (event.key === 'ArrowRight') {
      container.scrollBy({ left: 200, behavior: 'smooth' }); // ወደ ቀኝ ያሳልፋል
    } else if (event.key === 'ArrowLeft') {
      container.scrollBy({ left: -200, behavior: 'smooth' }); // ወደ ግራ ይመልሳል
    }
  }
});
// ለ) 🔍 የፍለጋ ሳጥን (Search Bar) ሎጂክ
function searchRipStudents() {
  let query = document.getElementById('ripSearchInput').value.trim().toLowerCase();
  let ripList = students.filter(s => s.reason === "በእረፍተ ስጋ");
  
  let result = ripList.filter(s => 
    s.name.toLowerCase().includes(query) || 
    (s.christianName && s.christianName.toLowerCase().includes(query))
  );

  let sortedResult = sortAmharic([...result]);

  document.getElementById('ripContainer').style.display = 'flex';
  document.getElementById('ripTableSection').style.display = 'none';

  buildRipCardUI(sortedResult);
}

// 
// 🟢 Excel (.csv) ማውረጃ
function exportRipToExcel() {
  let csv = [];
  const rows = document.querySelectorAll("#ripReportTable tr");
  
  for (let i = 0; i < rows.length; i++) {
    let row = [], cols = rows[i].querySelectorAll("td, th");
    for (let j = 0; j < cols.length; j++) {
      let text = cols[j].innerText.replace(/,/g, ' ');
      row.push(text);
    }
    csv.push(row.join(","));
  }

  let csvContent = "data:text/csv;charset=utf-8,\uFEFF" + csv.join("\n");
  let encodedUri = encodeURI(csvContent);
  let link = document.createElement("a");
  link.setAttribute("href", encodedUri);
  link.setAttribute("download", "የዕረፍተ_ሥጋ_ቅዱሳን_መዝገብ.csv");
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
}
// ⌨️ በኪቦርድ ቀስት ቁልፎች ካርዶቹን ማሳለፊያ ኮድ
document.addEventListener('keydown', function(event) {
  const container = document.getElementById('ripContainer');
  // የሪፕ ገጽ ክፍት መሆኑን እና ስክሪን ላይ መታየቱን ማረጋገጫ
  if (container && container.style.display === 'flex') {
    if (event.key === 'ArrowRight') {
      container.scrollBy({ left: 200, behavior: 'smooth' }); // ወደ ቀኝ ያሳልፋል
    } else if (event.key === 'ArrowLeft') {
      container.scrollBy({ left: -200, behavior: 'smooth' }); // ወደ ግራ ይመልሳል
    }
  }
});
    function searchAttendanceRange(){
      let fromDate = document.getElementById("searchFromDate").value;
      let toDate = document.getElementById("searchToDate").value;
      if(!fromDate || !toDate) { alert("እባክዎ ቀኖችን ይምረጡ!"); return; }

      let filtered = attendanceRecords.filter(r => r.date >= fromDate && r.date <= toDate);
      let html = "<table><thead><tr><th>ቀን</th><th>የመርሀ ግብር አይነት</th><th>ክፍል ደረጃ</th><th>የተገኙ</th><th>ፈቃድ</th></tr></thead><tbody>";
      if(filtered.length === 0){
        document.getElementById("rangeTableContainer").innerHTML = "<p style='color:red;padding:15px;'>ምንም ሪከርድ አልተገኘም!</p>";
        document.getElementById("rangeResultSection").classList.remove("hidden");
        return;
      }
      filtered.forEach(r => {
        html += `<tr><td><b>${r.date}</b></td><td>${r.type}</td><td>${r.progClass || 'ጠቅላላ'}</td><td style='color:green;'>${r.presents?.length || 0} ተማሪ</td><td style='color:#f59e0b;'>${r.leaves?.length || 0} ተማሪ</td></tr>`;
      });
      html += "</tbody></table>";
      document.getElementById("rangeTableContainer").innerHTML = html;
      document.getElementById("rangeResultSection").classList.remove("hidden");
    }

    function printRangeReport(){
      let content = document.getElementById("rangeTableContainer").innerHTML;
      document.getElementById("printArea").innerHTML = `<h3>የዕለታዊ አቴንዳንስ ፍለጋ ሪፖርት</h3>${content}`;
      window.print();
    }

    function downloadRangeReportExcel(){
      let fromDate = document.getElementById("searchFromDate").value;
      let toDate = document.getElementById("searchToDate").value;
      let filtered = attendanceRecords.filter(r => r.date >= fromDate && r.date <= toDate);
      let csv = "\ufeff" + "ቀን,የመርሀ ግብር አይነት,ክፍል,የተገኙ,ፈቃድ\n";
      filtered.forEach(r => { csv += `"${r.date}","${r.type}","${r.progClass || 'ጠቅላላ'}","${r.presents?.length || 0}","${r.leaves?.length || 0}"\n`; });
      let blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
      let link = document.createElement("a"); link.href = URL.createObjectURL(blob);
      link.download = "DailyReport.csv"; link.click();
    }
    // ካላንደር መክፈቻ
function openGlobalCalendar(inputId) {
  activeInputId = inputId; // የትኛው ሳጥን እንደተጫነ ይይዛል
  populateYears(); 
  document.getElementById("globalEthioCalendarModal").style.display = "block";
  renderCalendar();
}

// ዓመታትን በራሱ ለመሙላት
function populateYears() {
  const yearSelect = document.getElementById("ethioYearSelect");
  if (yearSelect.innerHTML !== "") return; // አንዴ ከሞላህ አትድገም
  const currentYear = 2018; 
  for (let y = currentYear - 100; y <= currentYear + 150; y++) {
    let opt = document.createElement("option");
    opt.value = y;
    opt.innerHTML = y;
    if (y === currentYear) opt.selected = true;
    yearSelect.appendChild(opt);
  }
}

// ካላንደሩን መሳል
function renderCalendar() {
  const m = document.getElementById("ethioMonthSelect").value;
  const y = document.getElementById("ethioYearSelect").value;
  const grid = document.getElementById("calendarGrid");
  grid.innerHTML = "";

  let days = (m == 13) ? 6 : 30;

  for (let d = 1; d <= days; d++) {
    let btn = document.createElement("button");
    btn.innerText = d;
    btn.style.padding = "10px";
    btn.style.background = "#fff";
    btn.style.border = "1px solid #e2e8f0";
    btn.style.borderRadius = "4px";
    btn.style.cursor = "pointer";

    btn.onclick = () => {
      let selectedDate = `${d}/${m}/${y} ዓ.ም`;
      document.getElementById(activeInputId).value = selectedDate;

      // Single Student Attendance
      if (
        activeInputId === "singleAttFromDateInput" ||
        activeInputId === "singleAttToDateInput"
      ) {
        onSingleAttDateFilterChange();
      }

      // Learning Summary
      if (
        activeInputId === "learningSumFrom" ||
        activeInputId === "learningSumTo"
      ) {
        filterLearningSummaryTable();
      }

      // Completed Summary
      if (
        activeInputId === "completedSumFrom" ||
        activeInputId === "completedSumTo"
      ) {
        filterCompletedSummaryTable();
      }

      // Special Summary
      if (
        activeInputId === "specialSumFrom" ||
        activeInputId === "specialSumTo"
      ) {
        filterSpecialSummaryTable();
      }

      // Participation Stats
      if (
        activeInputId === "partStatsFromDate" ||
        activeInputId === "partStatsToDate"
      ) {
        onPartStatsDateFilterChange();
      }

      document.getElementById("globalEthioCalendarModal").style.display = "none";
    };

    grid.appendChild(btn);
  }
}

function convertDate(dateStr) {
  if (!dateStr) return 0;

  dateStr = dateStr.replace(" ዓ.ም", "").trim();
  let parts = dateStr.split("/");

  if (parts.length !== 3) return 0;

  let d = parseInt(parts[0]);
  let m = parseInt(parts[1]);
  let y = parseInt(parts[2]);

  return y * 10000 + m * 100 + d;
}
  // ወደ ሪፖርት ገጽ የሚወስድ እና ቴብል የሚሰራ ተግባር
function showRankedStudentsReport(event) {
    // 1. መረጃውን ማጣራት
    let rankedStudents = students.filter(s => 
        s.rank && s.rank.trim() !== "" && 
        s.reason !== "በእረፍተ ስጋ"
    );

    // 2. አባላት ከሌሉ ምንም አይነት ገጽ ሳንቀይር መልእክት ብቻ እናሳይ
    if (rankedStudents.length === 0) {
        alert("ምንም ማዕረገ ክህነት ያለው አባል አልተገኘም!");
        return; // እዚህ ጋር ስንወጣ ምንም ገጽ አልተቀየረም፣ ስለዚህ ሴቲንግ ላይ ትቀራለህ
    }

    // 3. አባላት ካሉ ብቻ ገጾችን መቀያየር እንጀምር
    document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
    
    let reportPage = document.getElementById('reportPage');
    if (reportPage) {
        reportPage.style.display = 'block';
        
        // 4. ቴብሉን መገንባት
        let container = document.getElementById("reportContainer");
        container.innerHTML = ""; 
        
        let displayTitle = "የማዕረገ ክህነት ያላቸው አባላት ዝርዝር";
        let html = `
        <div style="padding:10px;">
            <button onclick="
                document.getElementById('reportPage').style.display = 'none';
                document.getElementById('settingsPage').style.display = 'block';
            " style="width:100%; padding:14px; font-weight:bold; border-radius:8px; background:#000000; color:#FFD700; border:2px solid #FFD700; margin-bottom:15px;">⬅️ ወደ ሴቲንግ ተመለስ</button>
            
            <div style="display:flex; gap:10px; margin-bottom:15px;">
                <button onclick="printGeneralTable('reportContainer')" style="background:#000000; color:#FFD700; padding:12px; border-radius:8px; flex:1;">🖨️ Print</button>
                <button onclick="downloadGeneralExcel('reportContainer', 'Ranked_Members')" style="background:#000000; color:#FFD700; padding:12px; border-radius:8px; flex:1;">📊 Excel</button>
            </div>

            <div style="width:100%; overflow-x:auto; border:2.5px solid #000000; border-radius:6px; background:white;">
                <table id="reportContainer_final_built_table" data-title="${displayTitle}" style="width:100%; min-width:800px; border-collapse:collapse;">
                    <thead><tr style="background:#ffffff; border-bottom:3px solid #000000;">
                        <th style="padding:12px; border:2px solid #000000;">ተ.ቁ</th>
                        <th style="padding:12px; border:2px solid #000000;">ስም</th>
                        <th style="padding:12px; border:2px solid #000000;">ማዕረገ ክህነት</th>
                        <th style="padding:12px; border:2px solid #000000;">ክፍል</th>
                        <th style="padding:12px; border:2px solid #000000;">ስልክ</th>
                        <th style="padding:12px; border:2px solid #000000;">የሚያገለግሉበት ክፍል</th>
                        <th style="padding:12px; border:2px solid #000000;">ሁኔታ</th>
                        <th style="padding:12px; border:2px solid #000000;">የራቁበት ምክንያት</th>
                    </tr></thead><tbody>
        `;

        rankedStudents.forEach((s, i) => {
            let isInactive = s.reason && s.reason !== "የለም" && s.reason !== "";
            let dept = s.department || s.currentServingDept || "-";
            let reason = isInactive ? (s.reason || s.leaveReason || "-") : "-";

            html += `<tr style="border-bottom:2px solid #000000;">
                <td style="padding:10px; border:2px solid #000000; text-align:center;">${i + 1}</td>
                <td style="padding:10px; border:2px solid #000000;">${s.name || ""}</td>
                <td style="padding:10px; border:2px solid #000000;">${s.rank || ""}</td>
                <td style="padding:10px; border:2px solid #000000; text-align:center;">${s.cls || ""}</td>
                <td style="padding:10px; border:2px solid #000000;">${s.phone || ""}</td>
                <td style="padding:10px; border:2px solid #000000;">${dept}</td>
                <td style="padding:10px; border:2px solid #000000; color:${isInactive ? 'red' : 'green'}; text-align:center;"><b>${isInactive ? 'Inactive' : 'Active'}</b></td>
                <td style="padding:10px; border:2px solid #000000;">${reason}</td>
            </tr>`;
        });

        html += "</tbody></table></div></div>";
        container.innerHTML = html;
    }
}
function showCategoryReport() {
    let container = document.getElementById("reportContainer");
    let list = students.filter(s => s.reason !== "በእረፍተ ስጋ");
    
    // በ "level" ቅደም ተከተል sort ማድረግ
    list.sort((a, b) => (a.level || "").localeCompare(b.level || ""));

    if (list.length === 0) {
        alert("ምንም አባል አልተገኘም!");
        return;
    }

    document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
    document.getElementById('reportPage').style.display = 'block';

    let displayTitle = "የአባላት ምድብ ዝርዝር ሪፖርት";
    let html = `
    <div style="padding:10px;">
        <button onclick="document.getElementById('reportPage').style.display='none'; document.getElementById('settingsPage').style.display='block';" 
        style="width:100%; padding:14px; font-weight:bold; border-radius:8px; background:#000000; color:#FFD700; border:2px solid #FFD700; margin-bottom:15px;">⬅️ ወደ ሴቲንግ ተመለስ</button>
        
        <div style="display:flex; gap:10px; margin-bottom:15px;">
            <button onclick="printGeneralTable('reportContainer')" style="background:#000000; color:#FFD700; padding:12px; border-radius:8px; flex:1;">🖨️ Print</button>
            <button onclick="downloadGeneralExcel('reportContainer', 'Category_Report')" style="background:#000000; color:#FFD700; padding:12px; border-radius:8px; flex:1;">📊 Excel</button>
        </div>

        <div style="width:100%; overflow-x:auto; border:2.5px solid #000000; border-radius:6px; background:white;">
            <table id="reportContainer_final_built_table" data-title="${displayTitle}" style="width:100%; min-width:800px; border-collapse:collapse;">
                <thead><tr style="background:#ffffff; border-bottom:3px solid #000000;">
                    <th style="padding:12px; border:2px solid #000000;">ተ.ቁ</th>
                    <th style="padding:12px; border:2px solid #000000;">ስም</th>
                    <th style="padding:12px; border:2px solid #000000;">አባላት ያሉበት መደብ</th>
                    <th style="padding:12px; border:2px solid #000000;">ክፍል</th>
                    <th style="padding:12px; border:2px solid #000000;">ስልክ</th>
                    <th style="padding:12px; border:2px solid #000000;">ሁኔታ</th>
                    <th style="padding:12px; border:2px solid #000000;">የራቁበት ምክንያት</th>
                </tr></thead><tbody>`;

    list.forEach((s, i) => {
        let isInactive = s.reason && s.reason !== "የለም" && s.reason !== "";
        let userLevel = s.level || "ያልተመደበ";
        let leaveReason = isInactive ? (s.reason || "-") : "-";

        html += `<tr style="border-bottom:2px solid #000000;">
            <td style="padding:10px; border:2px solid #000000; text-align:center;">${i + 1}</td>
            <td style="padding:10px; border:2px solid #000000;">${s.name || ""}</td>
            <td style="padding:10px; border:2px solid #000000; font-weight:bold;">${userLevel}</td>
            <td style="padding:10px; border:2px solid #000000; text-align:center;">${s.cls || ""}</td>
            <td style="padding:10px; border:2px solid #000000;">${s.phone || ""}</td>
            <td style="padding:10px; border:2px solid #000000; color:${isInactive ? 'red' : 'green'}; text-align:center;"><b>${isInactive ? 'Inactive' : 'Active'}</b></td>
            <td style="padding:10px; border:2px solid #000000;">${leaveReason}</td>
        </tr>`;
    });

    html += "</tbody></table></div></div>";
    container.innerHTML = html;
}
// ዋናው የሪፖርት ገጽን የሚያሳይ እና ማጣሪያዎችን የሚቆጣጠር ተግባር
function showCategoryReport() {
    renderCategoryTable("ሁሉም"); 
}

// ቴብሉን የሚገነባ እና እንደ መደቡ የሚያጣራ ተግባር
function renderCategoryTable(filterLevel) {
    let container = document.getElementById("reportContainer");
    let list = students.filter(s => s.reason !== "በእረፍተ ስጋ");
    
    // ማጣሪያ (Filter)
    if (filterLevel !== "ሁሉም") {
        list = list.filter(s => (s.level || "ያልተመደበ") === filterLevel);
    }
    
    // በ "level" ቅደም ተከተል sort ማድረግ
    list.sort((a, b) => (a.level || "").localeCompare(b.level || ""));

    // ለፕሪንት እና ለርዕስ የሚሆን ርዕስ
    let displayTitle = (filterLevel === "ሁሉም") ? "የአባላት ምድብ ዝርዝር ሪፖርት" : `የአባላት ምድብ ሪፖርት - ${filterLevel}`;

    document.querySelectorAll('.app-page').forEach(p => p.style.display = 'none');
    document.getElementById('reportPage').style.display = 'block';

    let html = `
    <div style="padding:10px;">
        <button onclick="document.getElementById('reportPage').style.display='none'; document.getElementById('settingsPage').style.display='block';" 
        style="width:100%; padding:14px; font-weight:bold; border-radius:8px; background:#000000; color:#FFD700; border:2px solid #FFD700; margin-bottom:15px;">⬅️ ወደ ሴቲንግ ተመለስ</button>
        
        <div style="display:flex; gap:10px; margin-bottom:15px;">
            <button onclick="printGeneralTable('reportContainer')" style="background:#000000; color:#FFD700; padding:12px; border-radius:8px; flex:1;">🖨️ Print</button>
            <button onclick="downloadGeneralExcel('reportContainer', 'Category_Report_${filterLevel}')" style="background:#000000; color:#FFD700; padding:12px; border-radius:8px; flex:1;">📊 Excel</button>
        </div>

        <div style="display:flex; gap:5px; margin-bottom:15px; flex-wrap:wrap;">
            <button onclick="renderCategoryTable('ሁሉም')" style="background:${filterLevel=='ሁሉም'?'#FFD700':'#333'}; color:${filterLevel=='ሁሉም'?'#000':'#fff'}; padding:8px; border-radius:5px; flex:1;">ሁሉም</button>
            <button onclick="renderCategoryTable('መደበኛ')" style="background:${filterLevel=='መደበኛ'?'#FFD700':'#333'}; color:${filterLevel=='መደበኛ'?'#000':'#fff'}; padding:8px; border-radius:5px; flex:1;">መደበኛ</button>
            <button onclick="renderCategoryTable('ልዩ መደበኛ')" style="background:${filterLevel=='ልዩ መደበኛ'?'#FFD700':'#333'}; color:${filterLevel=='ልዩ መደበኛ'?'#000':'#fff'}; padding:8px; border-radius:5px; flex:1;">ልዩ መደበኛ</button>
            <button onclick="renderCategoryTable('የክብር አባል')" style="background:${filterLevel=='የክብር አባል'?'#FFD700':'#333'}; color:${filterLevel=='የክብር አባል'?'#000':'#fff'}; padding:8px; border-radius:5px; flex:1;">የክብር አባል</button>
        </div>

        <h3 style="text-align:center; color:#000;">${displayTitle}</h3>

        <div style="width:100%; overflow-x:auto; border:2.5px solid #000000; border-radius:6px; background:white;">
            <table id="reportContainer_final_built_table" data-title="${displayTitle}" style="width:100%; min-width:800px; border-collapse:collapse;">
                <thead><tr style="background:#ffffff; border-bottom:3px solid #000000;">
                    <th style="padding:12px; border:2px solid #000000;">ተ.ቁ</th>
                    <th style="padding:12px; border:2px solid #000000;">ስም</th>
                    <th style="padding:12px; border:2px solid #000000;">መደብ</th>
                    <th style="padding:12px; border:2px solid #000000;">ክፍል</th>
                    <th style="padding:12px; border:2px solid #000000;">ስልክ</th>
                    <th style="padding:12px; border:2px solid #000000;">ሁኔታ</th>
                    <th style="padding:12px; border:2px solid #000000;">የራቁበት ምክንያት</th>
                </tr></thead><tbody>`;

    list.forEach((s, i) => {
        let isInactive = s.reason && s.reason !== "የለም" && s.reason !== "";
        let userLevel = s.level || "ያልተመደበ";
        let leaveReason = isInactive ? (s.reason || "-") : "-";

        html += `<tr style="border-bottom:2px solid #000000;">
            <td style="padding:10px; border:2px solid #000000; text-align:center;">${i + 1}</td>
            <td style="padding:10px; border:2px solid #000000;">${s.name || ""}</td>
            <td style="padding:10px; border:2px solid #000000; font-weight:bold;">${userLevel}</td>
            <td style="padding:10px; border:2px solid #000000; text-align:center;">${s.cls || ""}</td>
            <td style="padding:10px; border:2px solid #000000;">${s.phone || ""}</td>
            <td style="padding:10px; border:2px solid #000000; color:${isInactive ? 'red' : 'green'}; text-align:center;"><b>${isInactive ? 'Inactive' : 'Active'}</b></td>
            <td style="padding:10px; border:2px solid #000000;">${leaveReason}</td>
        </tr>`;
    });

    html += "</tbody></table></div></div>";
    container.innerHTML = html;
}
function resetAllData() {
  localStorage.clear();
  alert("ሁሉም ዳታ ተሰርዟል!");
  location.reload();
}
  </script>
</body>
</html>
