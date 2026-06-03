<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Volunteer Requirements & Application Checklist</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1e3a8a;
            --primary-light: #3b82f6;
            --text-dark: #1f2937;
            --text-muted: #4b5563;
            --bg-light: #f9fafb;
            --border-color: #e5e7eb;
            --accent-blue: #0284c7;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6;
            color: var(--text-dark);
            margin: 0;
            padding: 40px 20px;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            background: #ffffff;
            border-radius: 12px;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.05), 0 8px 10px -6px rgba(0, 0, 0, 0.05);
            padding: 40px;
            border-top: 8px solid var(--primary);
        }

        /* --- CONTROL BAR --- */
        .control-bar {
            display: flex;
            justify-content: flex-end;
            gap: 15px;
            margin-bottom: 30px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 15px;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            padding: 10px 20px;
            font-size: 14px;
            font-weight: 500;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s;
            border: none;
        }

        .btn-primary { background: var(--primary); color: white; }
        .btn-primary:hover { background: #172554; }
        .btn-secondary { background: #e5e7eb; color: var(--text-dark); }
        .btn-secondary:hover { background: #d1d5db; }

        /* --- HEADER STRUCTURE --- */
        .header-section {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 30px;
        }

        .title-area h1 {
            font-size: 20px;
            font-weight: 700;
            color: var(--primary);
            margin: 0 0 4px 0;
            letter-spacing: -0.5px;
        }

        .title-area h2 {
            font-size: 16px;
            font-weight: 600;
            color: var(--text-dark);
            margin: 0 0 4px 0;
        }

        .title-area p {
            font-size: 12px;
            color: var(--text-muted);
            margin: 0;
        }

        .meta-box {
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 12px;
            background: var(--bg-light);
            font-size: 12px;
        }

        /* --- BASIC INFO PANEL --- */
        .info-panel {
            display: grid;
            grid-template-columns: 130px 1fr;
            gap: 25px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 40px;
            background: var(--bg-light);
        }

        .photo-placeholder {
            width: 130px;
            height: 150px;
            border: 2px dashed #cbd5e1;
            border-radius: 6px;
            display: flex;
            align-items: center;
            text-align: center;
            justify-content: center;
            font-size: 12px;
            color: #94a3b8;
            background: #fff;
        }

        .info-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px 25px;
        }

        .info-item {
            display: flex;
            flex-direction: column;
            border-bottom: 1px solid #f3f4f6;
            padding-bottom: 4px;
        }

        .info-label { font-size: 11px; font-weight: 600; color: #6b7280; text-transform: uppercase; }
        .info-value { font-size: 14px; font-weight: 500; color: var(--text-dark); margin-top: 2px; }

        /* --- CHECKLIST INTERFACE --- */
        .checklist-table {
            border: 2px solid var(--primary);
            border-radius: 8px;
            overflow: hidden;
        }

        .table-header {
            background: var(--primary);
            color: white;
            display: grid;
            grid-template-columns: 120px 1fr;
            padding: 12px 20px;
            font-weight: 600;
            font-size: 14px;
        }

        .step-row {
            display: grid;
            grid-template-columns: 120px 1fr;
            border-bottom: 1px solid var(--border-color);
            background: #fff;
        }

        .step-row:last-child { border-bottom: none; }

        .step-cell {
            padding: 20px;
            font-weight: 700;
            font-size: 13px;
            color: var(--primary);
            border-right: 1px solid var(--border-color);
            background: var(--bg-light);
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }

        .step-cell input[type="checkbox"] {
            transform: scale(1.1);
            margin-top: 2px;
        }

        .content-cell {
            padding: 20px;
            font-size: 13px;
            line-height: 1.6;
        }

        .note {
            font-size: 12px;
            color: var(--text-muted);
            margin-top: 6px;
            display: block;
            font-style: italic;
        }

        /* --- SUB-REQUIREMENTS MATRIX --- */
        .sub-requirements {
            margin-top: 12px;
            background: #f8fafc;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 15px;
            display: grid;
            grid-template-columns: 1fr;
            gap: 8px;
        }

        .sub-req-item {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            font-size: 13px;
        }

        /* --- DATE COMPONENT TOOLS --- */
        .date-tool-wrapper {
            margin-top: 15px;
            padding-top: 12px;
            border-top: 1px dashed var(--border-color);
            display: flex;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            font-size: 12px;
        }

        .date-group {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .date-group label { font-weight: 600; color: var(--text-muted); }
        .date-group input[type="date"] {
            border: 1px solid #cbd5e1;
            border-radius: 4px;
            padding: 4px 8px;
            font-family: inherit;
        }

        .interval-badge {
            background: #e0f2fe;
            color: var(--accent-blue);
            padding: 4px 10px;
            border-radius: 20px;
            font-weight: 600;
        }

        /* --- FILE UPLOAD COMPONENT --- */
        .upload-section {
            margin-top: 10px;
        }
        .file-input-label {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            font-size: 11px;
            background: #f1f5f9;
            border: 1px solid #cbd5e1;
            padding: 4px 8px;
            border-radius: 4px;
            cursor: pointer;
        }
        .file-input-label:hover { background: #e2e8f0; }
        .file-input { display: none; }

        /* --- PRINT LOOKS CONFIG --- */
        @media print {
            body { background: white; padding: 0; }
            .container { box-shadow: none; padding: 0; border: none; }
            .control-bar, .upload-section { display: none !important; }
            .date-group input { border: none; background: transparent; pointer-events: none; }
        }
    </style>
</head>
<body>

<div class="container">
    
    <div class="control-bar">
        <button class="btn btn-secondary" onclick="window.print()">Print Document</button>
    </div>

    <div class="header-section">
        <div class="title-area">
            <h1>VOLUNTEER'S REQUIREMENTS AND APPLICATION CHECKLIST</h1>
            <h2>CENTRAL MOTORPOOL DEPARTMENT (CMD)</h2>
            <p>(02) 8981-4311 / (03) 7719-7800 (CMD-HR) LOCAL # 4902</p>
        </div>
        <div class="meta-box">
            <div><strong>REGARDING:</strong> APPLICATION PROCESS</div>
            <div style="margin-top: 4px;">STR: YYMMDD | END: YYMMDD</div>
        </div>
    </div>

    <div class="info-panel">
        <div class="photo-placeholder">Paste Passport<br>Size Photo Here</div>
        <div class="info-grid">
            <div class="info-item"><span class="info-label">Pangalan</span><span class="info-value">ERICSON E. ARCEGA</span></div>
            <div class="info-item"><span class="info-label">Nais Ipaglingkod</span><span class="info-value">HELPER MECHANIC</span></div>
            <div class="info-item"><span class="info-label">Lokal - Distrito</span><span class="info-value">PUNTURIN - CALOOCAN NORTH</span></div>
            <div class="info-item"><span class="info-label">Contact Number</span><span class="info-value">0966-843-3080</span></div>
            <div class="info-item"><span class="info-label">Kapisanan</span><span class="info-value">KADIWA</span></div>
            <div class="info-item"><span class="info-label">Edad / Kapanganakan</span><span class="info-value">36 | 1-Aug-1990</span></div>
            <div class="info-item"><span class="info-label">Bilang ng Taon sa Iglesia</span><span class="info-value">HANDOG</span></div>
            <div class="info-item"><span class="info-label">Tungkulin</span><span class="info-value">FINANCE</span></div>
        </div>
    </div>

    <div class="checklist-table">
        <div class="table-header">
            <div>PROCESS</div>
            <div>REQUIREMENTS CHECKLIST</div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 1</div>
            <div class="content-cell">Pag-ugnay ng nais na maglingkod sa destinado/pastor para sa proseso at requirements checklist.</div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 2</div>
            <div class="content-cell">
                Gagawa ng salaysay ang nais na maglingkod naka-address sa Pamamahala nakasaad na kinikilala na ang paglilingkod ay tungkulin at hindi hanapbuhay.
                <div class="date-tool-wrapper">
                    <div class="date-group"><label>D/S:</label><input type="date" class="start-date" onchange="calculateInterval(this)"></div>
                    <div class="date-group"><label>D/E:</label><input type="date" class="end-date" onchange="calculateInterval(this)"></div>
                    <div class="interval-badge">0 Days</div>
                    <div class="upload-section"><label class="file-input-label">📁 Upload Attachment<input type="file" class="file-input" onchange="uploadToNextcloud(this)"></label></div>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 3</div>
            <div class="content-cell">
                <strong>Pagkuha ng mga patotoo sa Lokal</strong> (naka-address sa Pamamahala) at requirements gaya ng mga sumusunod:
                
                <div class="sub-requirements">
                    <label class="sub-req-item"><input type="checkbox"> 2. Pagkuha sa kalihiman ng R2-01 w/ R201A (printed copy)</label>
                    <label class="sub-req-item"><input type="checkbox"> 3. Pagkuha ng patotoo ng Lokal (nakalagda ang mga pamunuan at destinado/pastor ng Lokal)</label>
                    <label class="sub-req-item"><input type="checkbox"> 4. Pagkuha ng patotoo ng pamunuan ng pangulo ng kapisanan na kinabibilangan.</label>
                    <label class="sub-req-item"><input type="checkbox"> 5. Pagkuha ng patotoo sa katiwala ng grupo na kinabibilangan.</label>
                    <label class="sub-req-item"><input type="checkbox"> 6. Patotoo ng destinado na nakausap ang nais maglingkod at naipaliwanag ang ukol sa "confidentiality."</label>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 4</div>
            <div class="content-cell">
                Isusumite ng destinado o ng aplikante mismo ang mga patotoo ng Lokal sa Kalihim ng Distrito.
                <div class="date-tool-wrapper">
                    <div class="date-group"><label>D/S:</label><input type="date" class="start-date" onchange="calculateInterval(this)"></div>
                    <div class="date-group"><label>D/E:</label><input type="date" class="end-date" onchange="calculateInterval(this)"></div>
                    <div class="interval-badge">0 Days</div>
                    <div class="upload-section"><label class="file-input-label">📁 Upload Attachment<input type="file" class="file-input" onchange="uploadToNextcloud(this)"></label></div>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 5</div>
            <div class="content-cell">
                <strong>Pagkuha ng nais na maglingkod ng PATOTOO NG TAGAPANGASIWA NG DISTRITO.</strong>
                <span class="note">Nota: Ang patotoo ng Tagapangasiwa ay naka-address sa Pamamahala (Pinatutunayang qualified at nasiyasat). Kaya mahalagang ma-interview din ang kapatid na nais na maglingkod.</span>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 6</div>
            <div class="content-cell">
                <strong>Ang Kalihim ng Distrito ang magpapadala ng requirements ng aplikante sa Central Motorpool Department o dalhin mismo ng aplikante sa Motorpool.</strong>
                <span class="note">Nota: Maaaring itawag muna sa telephone number na nasa itaas sa Local 4902 - Motorpool HR.</span>
                <div class="date-tool-wrapper">
                    <div class="date-group"><label>D/S:</label><input type="date" class="start-date" onchange="calculateInterval(this)"></div>
                    <div class="date-group"><label>D/E:</label><input type="date" class="end-date" onchange="calculateInterval(this)"></div>
                    <div class="interval-badge">0 Days</div>
                    <div class="upload-section"><label class="file-input-label">📁 Upload Attachment<input type="file" class="file-input" onchange="uploadToNextcloud(this)"></label></div>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 7</div>
            <div class="content-cell">Hintayin ang tawag ng Personnel's office sa Distrito ukol sa psychological exam schedule.</div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 8</div>
            <div class="content-cell">
                <strong>Pagkuha ng Psychological exam ng nais na maglingkod batay sa atas ng Tanggapan.</strong>
                <span class="note">Nota: Ang makapapasa sa psychological exam ang magtutuloy sa pagkumpleto ng requirements.</span>
                <div class="date-tool-wrapper">
                    <div class="date-group"><label>D/S:</label><input type="date" class="start-date" onchange="calculateInterval(this)"></div>
                    <div class="date-group"><label>D/E:</label><input type="date" class="end-date" onchange="calculateInterval(this)"></div>
                    <div class="interval-badge">0 Days</div>
                    <div class="upload-section"><label class="file-input-label">📁 Upload Attachment<input type="file" class="file-input" onchange="uploadToNextcloud(this)"></label></div>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 9</div>
            <div class="content-cell">
                <strong>Pagkumpleto ng mga sumusunod na requirements:</strong>
                
                <div class="sub-requirements" style="grid-template-columns: repeat(2, 1fr);">
                    <label class="sub-req-item"><input type="checkbox"> 1. Barangay Clearance</label>
                    <label class="sub-req-item"><input type="checkbox"> 2. Police Clearance</label>
                    <label class="sub-req-item"><input type="checkbox"> 3. NBI Clearance</label>
                    <label class="sub-req-item"><input type="checkbox"> 4. Birth Certificate (For single only)</label>
                    <label class="sub-req-item"><input type="checkbox"> 5. Marriage Certificate</label>
                    <label class="sub-req-item"><input type="checkbox"> 6. Transcript of Records / Diploma</label>
                    <label class="sub-req-item"><input type="checkbox"> 7. Drug Test Result (NEGH)</label>
                    <label class="sub-req-item"><input type="checkbox"> 8. Chest X-Ray Result</label>
                    <label class="sub-req-item"><input type="checkbox"> 9. Medical Certificate (FIT TO WORK)</label>
                    <label class="sub-req-item"><input type="checkbox"> 10. 2 pcs. Picture in 3R (Whole Body)</label>
                    <label class="sub-req-item"><input type="checkbox"> 11. 2 pcs. Picture in 2x2</label>
                    <label class="sub-req-item"><input type="checkbox"> 12. 2 pcs. Picture in 1x1</label>
                    <label class="sub-req-item" style="grid-column: span 2;"><input type="checkbox"> 13. Kung driver applicant ay photo copy ng Driver's License</label>
                </div>
                <div class="date-tool-wrapper">
                    <div class="date-group"><label>D/S:</label><input type="date" class="start-date" onchange="calculateInterval(this)"></div>
                    <div class="date-group"><label>D/E:</label><input type="date" class="end-date" onchange="calculateInterval(this)"></div>
                    <div class="interval-badge">0 Days</div>
                    <div class="upload-section"><label class="file-input-label">📁 Upload Attachment<input type="file" class="file-input" onchange="uploadToNextcloud(this)"></label></div>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 10</div>
            <div class="content-cell">
                <strong>Isusumite ng kalihim ng distrito sa Central Office c/o Central Motorpool Department</strong>
                <span class="note">Nota: Maaaring itawag muna sa telephone number na nasa itaas sa Local 4902 - Motorpool HR.</span>
                <div class="date-tool-wrapper">
                    <div class="date-group"><label>D/S:</label><input type="date" class="start-date" onchange="calculateInterval(this)"></div>
                    <div class="date-group"><label>D/E:</label><input type="date" class="end-date" onchange="calculateInterval(this)"></div>
                    <div class="interval-badge">0 Days</div>
                    <div class="upload-section"><label class="file-input-label">📁 Upload Attachment<input type="file" class="file-input" onchange="uploadToNextcloud(this)"></label></div>
                </div>
            </div>
        </div>

        <div class="step-row">
            <div class="step-cell"><input type="checkbox"> STEP 11</div>
            <div class="content-cell">Hintayin ang pagpapatibay at endorsement.</div>
        </div>
    </div>
</div>

<script>
    // Automatically calculates interval duration on the fly
    function calculateInterval(element) {
        const row = element.closest('.date-tool-wrapper');
        const startVal = row.querySelector('.start-date').value;
        const endVal = row.querySelector('.end-date').value;
        const badge = row.querySelector('.interval-badge');

        if (startVal && endVal) {
            const start = new Date(startVal);
            const end = new Date(endVal);
            const diffTime = end - start;
            const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));
            
            if (diffDays >= 0) {
                badge.innerText = diffDays + " Day(s)";
                badge.style.background = "#e0f2fe";
                badge.style.color = "#0284c7";
            } else {
                badge.innerText = "Invalid Range";
                badge.style.background = "#fee2e2";
                badge.style.color = "#ef4444";
            }
        }
    }

    // Handles the asynchronous WebDAV background pipeline transfers to Nextcloud via Java backend
    function uploadToNextcloud(inputElement) {
        const file = inputElement.files[0];
        if (!file) return;

        const label = inputElement.closest('.file-input-label');
        const originalText = label.innerHTML;
        label.innerHTML = "⏳ Uploading...";
        
        const formData = new FormData();
        formData.append("file", file);

        fetch("/upload", {
            method: "POST",
            body: formData
        })
        .then(response => response.text())
        .then(data => {
            alert(data);
            label.innerHTML = "✅ Uploaded";
            label.style.background = "#dcfce7";
            label.style.color = "#15803d";
        })
        .catch(error => {
            console.error("Upload error:", error);
            alert("Upload execution dropped. Verify routing credentials configuration.");
            label.innerHTML = originalText;
        });
    }
</script>
</body>
</html>
