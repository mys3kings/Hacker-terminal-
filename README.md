# Hacker-terminal-
David’s cyberpunk-style hacker terminal — totally safe, fully dramatic.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacker Terminal</title>
    <style>
        body {
            background-color: #000000;
            color: #00ff00;
            font-family: 'Courier New', monospace;
            padding: 20px;
        }

        #terminal {
            max-width: 800px;
            margin: 0 auto;
            border: 2px solid #00ff00;
            padding: 20px;
            background-color: #111111;
            box-shadow: 0 0 20px #00ff00;
        }

        .red-alert {
            color: #ff3333;
            font-weight: bold;
        }

        .yellow-alert {
            color: #ffff33;
            font-weight: bold;
        }

        .cyan {
            color: #33ffff;
        }

        .green {
            color: #00ff00;
        }

        .line {
            white-space: pre;
        }
    </style>
</head>
<body>
    <div id="terminal"></div>

    <script>
        const terminal = document.getElementById("terminal");

        const lines = [
            "\x1b[32m┌──────────────────────────────────────────────┐\x1b[0m",
            "\x1b[32m│    ACADEMIC MATRIX - SECURE TERMINAL        │\x1b[0m",
            "\x1b[32m│    USER: DAVID_AYINDE                        │\x1b[0m",
            "\x1b[32m└──────────────────────────────────────────────┘\x1b[0m",
            "\nlogin: david",
            "password: ********",
            "\n> accessing academic_profile...",
            "> scanning weak modules...",
            "\nCURRENT_GPA :: 2.90",
            "TARGET_GPA  :: 3.90",
            "\n[!] \x1b[31mRED ALERT: HIGH EFFORT REQUIRED\x1b[0m",
            "[+] Installing FocusEngine",
            "[+] Rewriting StudySchedule.conf",
            "[+] Boosting Consistency.kernel",
            "[-] Removing Procrastination.exe",
            "\nCompiling new academic build...",
            "████░░░░░░░░░░░░ 20%",
            "████████░░░░░░░░ 50%",
            "████████████░░░░ 75%",
            "████████████████ 100%",
            "\n>>> SYSTEM RECOMPILED",
            "OLD_BUILD :: 2.90",
            "NEW_BUILD :: 3.90",
            "\necho \"System not breached.\"",
            "echo \"Limits overridden.\"",
            "\nroot@self_mastery:~# _"
        ];

        let i = 0;

        function typeLine() {
            if (i < lines.length) {
                const line = document.createElement("div");
                line.className = "line";
                // Add color classes
                if(line.textContent.includes("RED ALERT")) line.className = "line red-alert";
                if(line.textContent.includes("FocusEngine") || line.textContent.includes("Rewriting") || line.textContent.includes("Boosting")) line.className = "line cyan";
                if(line.textContent.includes("Compiling")) line.className = "line yellow-alert";
                terminal.appendChild(line);
                
                let j = 0;
                function typeChar() {
                    if (j < lines[i].length) {
                        line.textContent += lines[i][j];
                        j++;
                        setTimeout(typeChar, 20); // typing speed
                    } else {
                        line.textContent += "\n";
                        i++;
                        setTimeout(typeLine, 200);
                    }
                }
                typeChar();
            }
        }

        typeLine();
    </script>
</body>
</html>
