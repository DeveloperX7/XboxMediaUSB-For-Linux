
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>XboxMediaUSB · Prepare USB drives for Xbox Series & One</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #f6f8fa;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif;
            line-height: 1.5;
            color: #1f2328;
            padding: 2rem 1rem;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            background: #ffffff;
            border-radius: 24px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.05), 0 2px 6px rgba(0,0,0,0.03);
            overflow: hidden;
            border: 1px solid #e1e4e8;
        }

        .header {
            background: linear-gradient(135deg, #0b3b2f 0%, #1a5d4a 100%);
            padding: 2rem 2rem 1.8rem;
            color: white;
            text-align: center;
        }

        .header h1 {
            font-size: 2.4rem;
            font-weight: 700;
            letter-spacing: -0.3px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .header h1 span {
            background: rgba(255,255,255,0.15);
            padding: 4px 12px;
            border-radius: 60px;
            font-size: 0.9rem;
            font-weight: 400;
        }

        .badge-container {
            margin-top: 1rem;
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        .badge {
            background: rgba(255,255,255,0.2);
            padding: 6px 14px;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            backdrop-filter: blur(2px);
        }

        .content {
            padding: 2rem 2rem 2.5rem;
        }

        h2 {
            font-size: 1.75rem;
            font-weight: 600;
            margin-top: 2rem;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid #eaeef2;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        h2:first-of-type {
            margin-top: 0;
        }

        h3 {
            font-size: 1.35rem;
            font-weight: 600;
            margin: 1.5rem 0 0.75rem 0;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 12px;
            background: #f9fafb;
            border-radius: 20px;
            padding: 1rem;
            margin: 1rem 0;
        }

        .feature-item {
            background: white;
            padding: 12px 16px;
            border-radius: 16px;
            border: 1px solid #e9ecef;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.02);
        }

        .feature-item span:first-child {
            font-size: 1.5rem;
        }

        .warning-box {
            background: #fff3e0;
            border-left: 5px solid #e67e22;
            padding: 1rem 1.3rem;
            border-radius: 14px;
            margin: 1.2rem 0;
            color: #ad4e00;
            font-weight: 500;
        }

        .note-box {
            background: #eef5ff;
            border-left: 5px solid #2c7da0;
            padding: 1rem 1.3rem;
            border-radius: 14px;
            margin: 1.2rem 0;
            color: #0a4b6e;
        }

        .code-block {
            background: #0d1117;
            color: #e6edf3;
            border-radius: 14px;
            padding: 1rem 1.2rem;
            font-family: 'SF Mono', 'Fira Code', 'Cascadia Code', monospace;
            font-size: 0.9rem;
            overflow-x: auto;
            white-space: pre-wrap;
            word-break: break-all;
            position: relative;
            margin: 1rem 0;
        }

        .code-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #1a212c;
            padding: 8px 16px;
            border-radius: 14px 14px 0 0;
            margin-bottom: -1px;
            font-size: 0.8rem;
            font-family: monospace;
            color: #b9c3d0;
        }

        .copy-btn {
            background: #2d3a4b;
            border: none;
            color: white;
            font-size: 0.75rem;
            padding: 4px 12px;
            border-radius: 40px;
            cursor: pointer;
            transition: 0.2s;
            font-weight: 500;
        }

        .copy-btn:hover {
            background: #3e556b;
        }

        pre {
            margin: 0;
            font-family: inherit;
        }

        .distro-table {
            width: 100%;
            border-collapse: collapse;
            background: #fff;
            border-radius: 18px;
            overflow: hidden;
            margin: 1.2rem 0;
            box-shadow: 0 1px 2px rgba(0,0,0,0.04);
        }

        .distro-table th, .distro-table td {
            text-align: left;
            padding: 12px 16px;
            border-bottom: 1px solid #e9ecef;
            vertical-align: top;
        }

        .distro-table th {
            background: #f2f4f7;
            font-weight: 600;
            width: 28%;
        }

        .distro-table tr:last-child td {
            border-bottom: none;
        }

        .btn-icon {
            background: none;
            border: none;
            font-size: 1rem;
            cursor: pointer;
            margin-left: 8px;
        }

        footer {
            text-align: center;
            padding: 1.5rem;
            background: #fafbfc;
            border-top: 1px solid #eaeef2;
            font-size: 0.85rem;
            color: #5b6876;
        }
        @media (max-width: 700px) {
            .content {
                padding: 1.5rem;
            }
            .header h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
<div class="container">
    <div class="header">
        <h1>
            🎮 XboxMediaUSB 
            <span>v2.1</span>
        </h1>
        <p style="font-size: 1.2rem; margin-top: 12px; opacity: 0.9;">Prepare USB drives for Xbox Series X|S & Xbox One</p>
        <div class="badge-container">
            <div class="badge">🐧 Linux</div>
            <div class="badge">⚡ NTFS + ACLs</div>
            <div class="badge">🔐 Root required</div>
            <div class="badge">🧩 GUI (PyQt5)</div>
        </div>
    </div>

    <div class="content">
        <!-- 1. Description -->
        <h2>📖 1. Application Description</h2>
        <p>This application <strong>formats and prepares</strong> any USB drive (flash drive or external hard drive) to work <strong>fully</strong> with modern Xbox consoles (Xbox Series X|S and Xbox One).</p>

        <div class="feature-grid">
            <div class="feature-item"><span>🧱</span> GPT + single NTFS partition</div>
            <div class="feature-item"><span>⚡</span> Quick format as NTFS</div>
            <div class="feature-item"><span>🔐</span> Xbox‑specific extended ACLs</div>
            <div class="feature-item"><span>📁</span> Essential folders: Games, Apps, Homebrew, Content, System</div>
            <div class="feature-item"><span>📂</span> Browse USB via file manager</div>
            <div class="feature-item"><span>⏏️</span> Safe eject (unmount + power off)</div>
        </div>

        <div class="warning-box">
            ⚠️ <strong>Root privileges required</strong> — the application must be run with <code>sudo</code> to access hardware and low‑level tools.
        </div>

        <!-- 2. How to Use -->
        <h2>🚀 2. How to Use</h2>
        <ol style="margin-left: 1.5rem; margin-bottom: 1rem; display: flex; flex-direction: column; gap: 8px;">
            <li>📥 Download <code>XBOXMEDIAUSB.py</code> (or the Java version if provided).</li>
            <li>🖥️ Open a terminal and navigate to the file's folder.</li>
            <li>🔑 Run the application with: 
                <div class="code-block" style="margin-top: 8px; background: #0d1117; display: inline-block; width: auto; padding: 6px 16px;">sudo python3 XBOXMEDIAUSB.py</div>
            </li>
            <li>🖱️ After the GUI opens:
                <ul style="margin-top: 8px; margin-left: 1.2rem;">
                    <li>Select your USB drive from the dropdown (<strong>double‑check</strong> – all data will be destroyed).</li>
                    <li>Click the <strong>⚠️ FORMAT-Fix ACLs ▲</strong> button to start formatting and applying ACLs.</li>
                    <li>Once done, click <strong>📁 Create Directory Structure...</strong> to create folders.</li>
                    <li>Browse the drive via <strong>📂 Browse USB Contents</strong> to copy games.</li>
                    <li>Finished? Press <strong>⏏️ Eject USB</strong> for safe removal.</li>
                </ul>
            </li>
        </ol>
        <div class="warning-box">
            💀 <strong>Warning:</strong> All data on the selected drive will be <strong>permanently lost</strong>. No recovery possible.
        </div>

        <!-- 3. Dependencies -->
        <h2>📦 3. Dependency Installation per Distribution</h2>
        <p>Before first run, install the following packages:</p>
        <div class="feature-grid" style="grid-template-columns: repeat(2,1fr); background: transparent; padding: 0;">
            <div class="feature-item"><span>💾</span> ntfs-3g – NTFS support</div>
            <div class="feature-item"><span>🏷️</span> attr – setfattr (ACLs)</div>
            <div class="feature-item"><span>🗂️</span> parted – partition editor</div>
            <div class="feature-item"><span>🖼️</span> PyQt5 – GUI framework</div>
        </div>

        <table class="distro-table">
            <thead>
                <tr><th>Distribution</th><th>Installation command</th></tr>
            </thead>
            <tbody>
                <tr><td>🐧 Arch Linux</td><td><div class="code-cmd" style="background:#0d1117; color:#e6edf3; padding:8px 12px; border-radius:12px; font-family:monospace;">sudo pacman -S ntfs-3g attr parted python-pyqt5</div><button class="copy-btn" style="margin-top:6px;" onclick="copyText('sudo pacman -S ntfs-3g attr parted python-pyqt5')">📋 Copy</button></td></tr>
                <tr><td>🐧 Debian / Ubuntu / Linux Mint</td><td><div class="code-cmd" style="background:#0d1117; color:#e6edf3; padding:8px 12px; border-radius:12px; font-family:monospace;">sudo apt update && sudo apt install -y ntfs-3g attr parted python3-pyqt5</div><button class="copy-btn" style="margin-top:6px;" onclick="copyText('sudo apt update && sudo apt install -y ntfs-3g attr parted python3-pyqt5')">📋 Copy</button></td></tr>
                <tr><td>🪶 Fedora (standard)</td><td><div class="code-cmd" style="background:#0d1117; color:#e6edf3; padding:8px 12px; border-radius:12px; font-family:monospace;">sudo dnf install ntfs-3g attr parted python3-qt5</div><button class="copy-btn" style="margin-top:6px;" onclick="copyText('sudo dnf install ntfs-3g attr parted python3-qt5')">📋 Copy</button></td></tr>
                <tr><td>🔄 Fedora Atomic / Silverblue (rpm-ostree)</td><td><div class="code-cmd" style="background:#0d1117; color:#e6edf3; padding:8px 12px; border-radius:12px; font-family:monospace;">rpm-ostree install ntfs-3g attr parted python3-qt5<br># then reboot or run: rpm-ostree reload</div><button class="copy-btn" style="margin-top:6px;" onclick="copyText('rpm-ostree install ntfs-3g attr parted python3-qt5')">📋 Copy (install)</button></td></tr>
                <tr><td>🐧 openSUSE (Leap / Tumbleweed)</td><td><div class="code-cmd" style="background:#0d1117; color:#e6edf3; padding:8px 12px; border-radius:12px; font-family:monospace;">sudo zypper install ntfs-3g attr parted python3-qt5</div><button class="copy-btn" style="margin-top:6px;" onclick="copyText('sudo zypper install ntfs-3g attr parted python3-qt5')">📋 Copy</button></td></tr>
                <tr><td>🌿 Other distributions (generic)</td><td><div class="code-cmd" style="background:#0d1117; color:#e6edf3; padding:8px 12px; border-radius:12px; font-family:monospace;">Install equivalents: ntfs-3g, attr (setfattr), parted, pyqt5</div></td></tr>
            </tbody>
        </table>

        <!-- 4. Additional notes -->
        <h2>📌 4. Additional Notes</h2>
        <ul style="margin-left: 1.5rem; margin-bottom: 1rem;">
            <li>🔍 The application <strong>automatically detects missing packages</strong> and will ask to install them if you run it with root privileges.</li>
            <li>💾 If <strong>no USB drives appear</strong> in the list, make sure the drive is properly connected and try refreshing.</li>
            <li>🔄 On <strong>Fedora Atomic</strong>, after installing packages via rpm-ostree you may need to reboot the system.</li>
            <li>🧪 It is <strong>recommended to run from a terminal</strong> to see any error messages (e.g., <code>sudo python3 XBOXMEDIAUSB.py</code>).</li>
        </ul>

        <div class="note-box">
            💡 <strong>Tip:</strong> If you prefer a standalone binary or Java version, check the <strong>Releases</strong> section. The Python version is fully functional and cross‑distro.
        </div>

        <!-- 5. Version -->
        <h2>🏷️ 5. Application Version</h2>
        <p><strong>Version 2.1</strong> – supports Atomic and rpm-ostree distributions, improved drive detection and ACL handling.</p>

        <!-- Footer note -->
        <hr style="margin: 2rem 0 0.5rem; border:0; height:1px; background:#e1e4e8;">
        <p style="font-size:0.85rem; color:#57606a; margin-top: 1rem;">
            ⚡ XboxMediaUSB – not an official Microsoft tool. Xbox is a registered trademark of Microsoft Corporation.
        </p>
    </div>
    <footer>
        <span>🎮 Made for the Xbox modding & homebrew community · MIT License</span><br>
        <span style="font-size: 0.75rem;">⭐ Report issues or contribute on GitHub</span>
    </footer>
</div>

<script>
    function copyText(text) {
        navigator.clipboard.writeText(text).then(() => {
            // optional micro feedback
            const btns = document.querySelectorAll('.copy-btn');
            let originalText = '';
            for(let btn of btns) {
                if(btn.innerText.includes('Copy') && btn.previousElementSibling?.innerText?.includes(text.substring(0,20))) {
                    originalText = btn.innerText;
                    btn.innerText = '✅ Copied!';
                    setTimeout(() => { btn.innerText = originalText; }, 1800);
                    break;
                }
            }
        }).catch(err => {
            alert('Could not copy manually');
        });
    }
    // attach copy to all .copy-btn inside distro-table (simple approach)
    document.querySelectorAll('.copy-btn').forEach(btn => {
        if(!btn.getAttribute('data-listener')) {
            btn.setAttribute('data-listener','true');
            // we already have onclick in html, but we also need to capture the command text properly.
        }
    });
    // additional for code blocks without button? but all commands already have copy buttons.
</script>
</body>
</html>
