<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <style>
        :root {
            color-scheme: dark;
            --background: #111111;
            --text: #f5f5f5;
            --muted: #b3b3b3;
            --line: #444444;
            --button-background: #f5f5f5;
            --button-text: #111111;
        }

        body {
            background: var(--background);
            color: var(--text);
            font-family: "Segoe UI", sans-serif;
            margin: 0;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        .site-width {
            width: min(920px, calc(100% - 48px));
            margin-inline: auto;
        }

        header {
            padding-top: 76px;
            padding-bottom: 36px;
        }

        h1 {
            font-family: Georgia, serif;
            font-size: 48px;
            font-weight: 400;
            line-height: 1.1;
            margin: 0 0 14px;
        }

        header p {
            color: var(--muted);
            font-size: 17px;
            line-height: 1.6;
            margin: 0;
        }

        main {
            flex: 1;
            display: grid;
            grid-template-columns: minmax(0, 0.9fr) minmax(0, 1fr);
            gap: 24px;
            align-items: center;
            padding-top: 24px;
            padding-bottom: 64px;
        }

        .project-summary {
            color: var(--muted);
            font-family: Georgia, serif;
            font-size: 26px;
            line-height: 1.5;
            margin: 0;
            max-width: 26ch;
        }

        .card {
            border-left: 1px solid var(--line);
            max-width: 680px;
            padding: 20px 0 20px 28px;
        }

        h2 {
            font-size: 15px;
            font-weight: 600;
            margin: 0 0 18px;
        }

        #message {
            color: #e2e2e2;
            font-family: Georgia, serif;
            font-size: 28px;
            line-height: 1.35;
            margin: 0;
        }

        button {
            background: var(--button-background);
            color: var(--button-text);
            border: none;
            padding: 12px 20px;
            font: inherit;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 160ms ease;
        }

        button:hover:not(:disabled) {
            background: #d9d9d9;
        }

        button:focus-visible {
            outline: 2px solid var(--text);
            outline-offset: 4px;
        }

        button:disabled {
            background: #555555;
            color: #cccccc;
            cursor: default;
        }

        footer {
            border-top: 1px solid var(--line);
            color: var(--muted);
            font-size: 13px;
            padding-top: 18px;
            padding-bottom: 24px;
        }

        footer p {
            margin: 0;
        }

        @media (max-width: 600px) {
            header {
                padding-top: 52px;
                padding-bottom: 24px;
            }

            h1 {
                font-size: 38px;
            }

            main {
                grid-template-columns: 1fr;
                align-content: center;
                gap: 20px;
                padding-top: 16px;
                padding-bottom: 48px;
            }

            .card {
                border-left: 0;
                border-top: 1px solid var(--line);
                padding: 22px 0 16px;
            }

            .project-summary {
                font-size: 22px;
                max-width: 24ch;
            }

            #message {
                font-size: 24px;
            }
        }
    </style>
</head>
<body>

    <header class="site-width">
        <h1>Why you should hire me</h1>
        <p>A few reasons I’d be a strong addition to your team.</p>
    </header>

    <main class="site-width">
        <p class="project-summary">I built and deployed this interactive page using HTML, CSS, and JavaScript.</p>
        <div class="card">
            <h2 id="reason">Reason number 1</h2>
            <p id="message">I made this website.</p>
            <button id="next-button" onclick="changeText()">Next</button>
        </div>
    </main>

    <footer class="site-width">
        <p>Works on mobile and desktop.</p>
    </footer>

    <script>
        const reasons = [
            { title: 'Reason number 1', message: 'I made this website.' },
            { title: 'Reason number 2', message: 'I am a hard worker.' },
            { title: 'Reason number 3', message: "I'm ready to get to work!" }
        ];
        let currentReasonIndex = 0;

        function changeText() {
            currentReasonIndex++;
            document.getElementById('reason').textContent = reasons[currentReasonIndex].title;
            document.getElementById('message').textContent = reasons[currentReasonIndex].message;

            if (currentReasonIndex === reasons.length - 1) {
                document.getElementById('next-button').disabled = true;
            }
        }
    </script>

</body>
</html>
