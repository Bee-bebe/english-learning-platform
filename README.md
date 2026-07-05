<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>🌟 English Learning Pro - ฝึกภาษาอังกฤษกับเรื่องสั้น</title>
    <style>
        /* ================================================================
           CSS VARIABLES & RESET
           ================================================================ */
        :root {
            --bg-primary: #f0f7ff;
            --bg-secondary: #ffffff;
            --bg-card: #ffffff;
            --bg-card-alt: #f8fafc;
            --bg-nav: #ffffff;
            --text-primary: #0f172a;
            --text-secondary: #334155;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --shadow: 0 4px 24px rgba(0, 20, 50, 0.08);
            --shadow-lg: 0 12px 48px rgba(0, 20, 50, 0.12);
            --radius: 20px;
            --radius-sm: 12px;
            --radius-full: 9999px;
            --primary: #1e3a6f;
            --primary-hover: #0f2a52;
            --primary-light: #e8edf6;
            --accent: #f59e0b;
            --accent-light: #fef3c7;
            --success: #10b981;
            --danger: #ef4444;
            --transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --font: 'Inter', 'Sarabun', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        /* Dark Mode */
        [data-theme="dark"] {
            --bg-primary: #0f172a;
            --bg-secondary: #1e293b;
            --bg-card: #1e293b;
            --bg-card-alt: #2d3a4f;
            --bg-nav: #1e293b;
            --text-primary: #f1f5f9;
            --text-secondary: #cbd5e1;
            --text-muted: #94a3b8;
            --border-color: #334155;
            --shadow: 0 4px 24px rgba(0, 0, 0, 0.4);
            --shadow-lg: 0 12px 48px rgba(0, 0, 0, 0.5);
            --primary-light: #2d3a4f;
            --accent-light: #4a3a1a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font);
            background: var(--bg-primary);
            color: var(--text-primary);
            transition: background var(--transition), color var(--transition);
            min-height: 100vh;
            padding: 16px;
            line-height: 1.6;
        }

        /* ================================================================
           SCROLLBAR
           ================================================================ */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 10px;
        }

        /* ================================================================
           LAYOUT
           ================================================================ */
        .app {
            max-width: 1100px;
            margin: 0 auto;
        }

        /* ================================================================
           HEADER
           ================================================================ */
        .header {
            background: var(--bg-secondary);
            border-radius: var(--radius);
            padding: 20px 28px;
            box-shadow: var(--shadow);
            margin-bottom: 20px;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 16px;
            transition: background var(--transition), box-shadow var(--transition);
            border: 1px solid var(--border-color);
        }

        .header-left {
            display: flex;
            align-items: center;
            gap: 14px;
        }
        .header-left .logo {
            font-size: 30px;
        }
        .header-left h1 {
            font-size: 22px;
            font-weight: 700;
            color: var(--text-primary);
        }
        .header-left h1 span {
            color: var(--primary);
        }
        .header-left .badge {
            background: var(--primary);
            color: #fff;
            font-size: 12px;
            font-weight: 600;
            padding: 2px 14px;
            border-radius: var(--radius-full);
            margin-left: 6px;
        }

        .header-right {
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }

        /* --- Search --- */
        .search-box {
            position: relative;
            display: flex;
            align-items: center;
        }
        .search-box input {
            padding: 8px 16px 8px 38px;
            border-radius: var(--radius-full);
            border: 2px solid var(--border-color);
            background: var(--bg-primary);
            color: var(--text-primary);
            font-size: 14px;
            width: 200px;
            transition: var(--transition);
            outline: none;
        }
        .search-box input:focus {
            border-color: var(--primary);
            width: 260px;
            box-shadow: 0 0 0 4px rgba(30, 58, 111, 0.1);
        }
        .search-box .icon {
            position: absolute;
            left: 12px;
            color: var(--text-muted);
            font-size: 16px;
        }

        /* --- Theme Toggle --- */
        .theme-toggle {
            background: var(--bg-primary);
            border: 2px solid var(--border-color);
            border-radius: var(--radius-full);
            padding: 8px 16px;
            cursor: pointer;
            font-size: 18px;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 6px;
            color: var(--text-primary);
        }
        .theme-toggle:hover {
            border-color: var(--primary);
        }
        .theme-toggle .label {
            font-size: 13px;
            font-weight: 500;
        }

        /* --- Stats --- */
        .stats {
            display: flex;
            gap: 16px;
            font-size: 13px;
            color: var(--text-muted);
            background: var(--bg-primary);
            padding: 6px 16px;
            border-radius: var(--radius-full);
            border: 1px solid var(--border-color);
        }
        .stats span {
            font-weight: 600;
            color: var(--text-primary);
        }

        /* ================================================================
           TABS (Navigation)
           ================================================================ */
        .tabs {
            display: flex;
            gap: 4px;
            background: var(--bg-secondary);
            border-radius: var(--radius);
            padding: 6px;
            margin-bottom: 20px;
            border: 1px solid var(--border-color);
            flex-wrap: wrap;
            transition: background var(--transition);
        }
        .tab-btn {
            padding: 10px 22px;
            border: none;
            border-radius: var(--radius-sm);
            background: transparent;
            color: var(--text-secondary);
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
            font-family: var(--font);
            flex: 1 1 auto;
            justify-content: center;
        }
        .tab-btn:hover {
            background: var(--bg-primary);
            color: var(--text-primary);
        }
        .tab-btn.active {
            background: var(--primary);
            color: #fff;
            box-shadow: 0 4px 12px rgba(30, 58, 111, 0.3);
        }
        .tab-btn .count {
            font-size: 12px;
            background: rgba(255, 255, 255, 0.2);
            padding: 0 10px;
            border-radius: var(--radius-full);
        }
        .tab-btn.active .count {
            background: rgba(255, 255, 255, 0.25);
        }

        /* ================================================================
           MAIN CONTENT
           ================================================================ */
        .main-content {
            background: var(--bg-secondary);
            border-radius: var(--radius);
            padding: 24px;
            box-shadow: var(--shadow);
            border: 1px solid var(--border-color);
            transition: background var(--transition), box-shadow var(--transition);
            min-height: 480px;
        }

        /* --- Tab Panels --- */
        .tab-panel {
            display: none;
            animation: fadeIn 0.35s ease;
        }
        .tab-panel.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ================================================================
           STORY LIST (ในแท็บ Stories)
           ================================================================ */
        .story-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 10px;
            margin-bottom: 24px;
        }
        .story-grid .story-btn {
            padding: 12px 16px;
            border: 2px solid var(--border-color);
            background: var(--bg-card);
            border-radius: var(--radius-sm);
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: var(--transition);
            color: var(--text-secondary);
            text-align: center;
            font-family: var(--font);
        }
        .story-grid .story-btn:hover {
            border-color: var(--primary);
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }
        .story-grid .story-btn.active {
            border-color: var(--primary);
            background: var(--primary);
            color: #fff;
            box-shadow: 0 4px 16px rgba(30, 58, 111, 0.3);
        }
        .story-grid .story-btn .story-id {
            font-size: 11px;
            opacity: 0.6;
            display: block;
            font-weight: 400;
            margin-top: 2px;
        }
        .story-grid .story-btn.active .story-id {
            opacity: 0.8;
        }

        /* ================================================================
           STORY DISPLAY
           ================================================================ */
        .story-display {
            background: var(--bg-card-alt);
            border-radius: var(--radius-sm);
            padding: 24px;
            border-left: 5px solid var(--primary);
            transition: background var(--transition);
        }

        .story-title {
            font-size: 24px;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: wrap;
        }
        .story-title .story-id-badge {
            font-size: 13px;
            background: var(--primary-light);
            padding: 0 14px;
            border-radius: var(--radius-full);
            font-weight: 600;
            color: var(--primary);
        }

        /* --- Content with highlight --- */
        .story-content {
            font-size: 18px;
            line-height: 2;
            background: var(--bg-card);
            padding: 20px 24px;
            border-radius: var(--radius-sm);
            box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.03);
            margin-bottom: 18px;
            border: 1px solid var(--border-color);
            transition: background var(--transition), border-color var(--transition);
        }
        .story-content .highlight {
            background: var(--accent-light);
            padding: 0 4px;
            border-radius: 6px;
            cursor: help;
            transition: var(--transition);
            font-weight: 500;
            color: var(--text-primary);
        }
        .story-content .highlight:hover {
            background: var(--accent);
            color: #fff;
            transform: scale(1.02);
        }

        /* --- Sentence mode --- */
        .sentence-mode {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 16px;
        }
        .sentence-mode .sentence-btn {
            padding: 6px 16px;
            border-radius: var(--radius-full);
            border: 2px solid var(--border-color);
            background: var(--bg-card);
            cursor: pointer;
            font-size: 13px;
            font-weight: 500;
            transition: var(--transition);
            color: var(--text-secondary);
            font-family: var(--font);
        }
        .sentence-mode .sentence-btn:hover {
            border-color: var(--primary);
            background: var(--primary-light);
        }
        .sentence-mode .sentence-btn.active {
            border-color: var(--primary);
            background: var(--primary);
            color: #fff;
        }
        .sentence-mode .sentence-btn .sentence-index {
            font-weight: 400;
            opacity: 0.6;
            font-size: 11px;
        }

        /* ================================================================
           AUDIO CONTROLS
           ================================================================ */
        .audio-controls {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 14px;
            background: var(--bg-card);
            padding: 14px 20px;
            border-radius: var(--radius-full);
            border: 1px solid var(--border-color);
            margin-bottom: 18px;
            transition: background var(--transition), border-color var(--transition);
        }
        .btn-speaker {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px 28px;
            background: var(--primary);
            color: #fff;
            border: none;
            border-radius: var(--radius-full);
            cursor: pointer;
            font-size: 15px;
            font-weight: 600;
            transition: var(--transition);
            font-family: var(--font);
            flex-shrink: 0;
        }
        .btn-speaker:hover {
            background: var(--primary-hover);
            transform: scale(1.02);
        }
        .btn-speaker:active {
            transform: scale(0.96);
        }
        .btn-speaker.speaking {
            background: var(--danger);
            animation: pulse 0.9s infinite;
        }
        .btn-speaker svg {
            width: 20px;
            height: 20px;
            fill: currentColor;
            flex-shrink: 0;
        }
        @keyframes pulse {
            0%,
            100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }

        /* Loop button */
        .loop-btn {
            padding: 8px 16px;
            border-radius: var(--radius-full);
            border: 2px solid var(--border-color);
            background: var(--bg-card);
            cursor: pointer;
            font-size: 18px;
            transition: var(--transition);
            color: var(--text-secondary);
            display: flex;
            align-items: center;
            gap: 4px;
        }
        .loop-btn:hover {
            border-color: var(--primary);
        }
        .loop-btn.active {
            border-color: var(--success);
            background: var(--success);
            color: #fff;
        }
        .loop-btn .label {
            font-size: 12px;
            font-weight: 600;
        }

        /* Speed controls */
        .speed-group {
            display: flex;
            align-items: center;
            gap: 6px;
            flex-wrap: wrap;
            margin-left: auto;
        }
        .speed-group label {
            font-size: 13px;
            font-weight: 600;
            color: var(--text-muted);
        }
        .speed-btn {
            padding: 5px 14px;
            border-radius: var(--radius-full);
            border: 2px solid var(--border-color);
            background: var(--bg-card);
            cursor: pointer;
            font-size: 13px;
            font-weight: 600;
            transition: var(--transition);
            color: var(--text-secondary);
            font-family: var(--font);
        }
        .speed-btn:hover {
            border-color: var(--primary);
        }
        .speed-btn.active {
            border-color: var(--primary);
            background: var(--primary);
            color: #fff;
        }

        /* Volume */
        .volume-control {
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .volume-control input[type="range"] {
            width: 80px;
            accent-color: var(--primary);
            cursor: pointer;
        }
        .volume-control .vol-label {
            font-size: 13px;
            color: var(--text-muted);
            min-width: 32px;
            text-align: center;
        }

        /* Status */
        .status-text {
            font-size: 13px;
            color: var(--text-muted);
            min-width: 100px;
            text-align: center;
        }

        /* Progress bar */
        .speech-progress {
            width: 100%;
            height: 4px;
            background: var(--border-color);
            border-radius: 4px;
            overflow: hidden;
            margin-top: 6px;
        }
        .speech-progress .bar {
            height: 100%;
            width: 0%;
            background: var(--primary);
            border-radius: 4px;
            transition: width 0.1s linear;
        }

        /* ================================================================
           VOCAB TABLE
           ================================================================ */
        .vocab-section {
            margin-top: 6px;
            padding-top: 18px;
            border-top: 2px dashed var(--border-color);
        }
        .vocab-section .section-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 12px;
        }
        .vocab-section .section-header h3 {
            color: var(--text-primary);
            font-size: 18px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .vocab-section .section-header .favorite-all {
            font-size: 13px;
            color: var(--text-muted);
            cursor: pointer;
            background: none;
            border: none;
            font-family: var(--font);
            transition: var(--transition);
        }
        .vocab-section .section-header .favorite-all:hover {
            color: var(--accent);
        }

        .vocab-table-wrap {
            overflow-x: auto;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border-color);
        }
        .vocab-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 15px;
            min-width: 380px;
        }
        .vocab-table th {
            background: var(--primary);
            color: #fff;
            padding: 12px 16px;
            text-align: left;
            font-weight: 600;
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        .vocab-table td {
            padding: 10px 16px;
            border-bottom: 1px solid var(--border-color);
            color: var(--text-secondary);
            transition: background var(--transition);
        }
        .vocab-table tr:nth-child(even) td {
            background: var(--bg-card-alt);
        }
        .vocab-table tr:hover td {
            background: var(--primary-light);
        }
        .vocab-table .type-badge {
            display: inline-block;
            background: var(--primary-light);
            padding: 2px 14px;
            border-radius: var(--radius-full);
            font-size: 12px;
            font-weight: 600;
            color: var(--primary);
        }
        .vocab-table .fav-btn {
            background: none;
            border: none;
            cursor: pointer;
            font-size: 18px;
            transition: var(--transition);
            padding: 4px;
        }
        .vocab-table .fav-btn:hover {
            transform: scale(1.2);
        }
        .vocab-table .fav-btn.is-fav {
            color: var(--accent);
        }

        /* ================================================================
           ALL VOCAB TAB
           ================================================================ */
        .all-vocab-controls {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 18px;
            align-items: center;
        }
        .all-vocab-controls select,
        .all-vocab-controls input {
            padding: 8px 16px;
            border-radius: var(--radius-full);
            border: 2px solid var(--border-color);
            background: var(--bg-card);
            color: var(--text-primary);
            font-size: 14px;
            font-family: var(--font);
            outline: none;
            transition: var(--transition);
        }
        .all-vocab-controls select:focus,
        .all-vocab-controls input:focus {
            border-color: var(--primary);
        }
        .all-vocab-controls .filter-label {
            font-size: 14px;
            font-weight: 500;
            color: var(--text-muted);
        }
        .all-vocab-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 10px;
            max-height: 500px;
            overflow-y: auto;
            padding-right: 4px;
        }
        .all-vocab-item {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-sm);
            padding: 12px 16px;
            display: flex;
            flex-direction: column;
            transition: var(--transition);
        }
        .all-vocab-item:hover {
            border-color: var(--primary);
            box-shadow: var(--shadow);
        }
        .all-vocab-item .word {
            font-size: 16px;
            font-weight: 700;
            color: var(--text-primary);
        }
        .all-vocab-item .type {
            font-size: 12px;
            color: var(--text-muted);
            font-weight: 500;
        }
        .all-vocab-item .meaning {
            font-size: 14px;
            color: var(--text-secondary);
            margin-top: 4px;
        }
        .all-vocab-item .from-story {
            font-size: 11px;
            color: var(--text-muted);
            margin-top: 6px;
            border-top: 1px dashed var(--border-color);
            padding-top: 6px;
        }

        /* ================================================================
           QUIZ TAB
           ================================================================ */
        .quiz-container {
            text-align: center;
            padding: 20px 0;
        }
        .quiz-question {
            font-size: 22px;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--text-primary);
        }
        .quiz-hint {
            font-size: 14px;
            color: var(--text-muted);
            margin-bottom: 20px;
        }
        .quiz-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 12px;
            max-width: 600px;
            margin: 0 auto 20px;
        }
        .quiz-options button {
            padding: 14px 20px;
            border-radius: var(--radius-sm);
            border: 2px solid var(--border-color);
            background: var(--bg-card);
            cursor: pointer;
            font-size: 16px;
            font-weight: 500;
            transition: var(--transition);
            font-family: var(--font);
            color: var(--text-primary);
        }
        .quiz-options button:hover {
            border-color: var(--primary);
            transform: scale(1.02);
        }
        .quiz-options button.correct {
            border-color: var(--success);
            background: #d1fae5;
            color: #065f46;
        }
        .quiz-options button.wrong {
            border-color: var(--danger);
            background: #fecaca;
            color: #991b1b;
        }
        .quiz-options button:disabled {
            cursor: not-allowed;
            opacity: 0.7;
        }
        .quiz-result {
            font-size: 18px;
            font-weight: 600;
            margin-top: 12px;
            min-height: 40px;
        }
        .quiz-score {
            font-size: 14px;
            color: var(--text-muted);
            margin-top: 8px;
        }
        .quiz-next-btn {
            padding: 10px 32px;
            border-radius: var(--radius-full);
            border: none;
            background: var(--primary);
            color: #fff;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            font-family: var(--font);
            margin-top: 12px;
        }
        .quiz-next-btn:hover {
            background: var(--primary-hover);
            transform: scale(1.02);
        }

        /* ================================================================
           FAVORITES TAB
           ================================================================ */
        .favorites-empty {
            text-align: center;
            padding: 60px 20px;
            color: var(--text-muted);
        }
        .favorites-empty .big-icon {
            font-size: 64px;
            margin-bottom: 16px;
        }

        /* ================================================================
           KEYBOARD SHORTCUT HINT
           ================================================================ */
        .shortcuts-hint {
            font-size: 12px;
            color: var(--text-muted);
            text-align: center;
            margin-top: 12px;
            border-top: 1px solid var(--border-color);
            padding-top: 12px;
        }
        .shortcuts-hint kbd {
            background: var(--bg-primary);
            padding: 2px 10px;
            border-radius: 4px;
            font-size: 11px;
            border: 1px solid var(--border-color);
            font-family: var(--font);
        }

        /* ================================================================
           LOADING / ERROR
           ================================================================ */
        .loading {
            text-align: center;
            padding: 60px 20px;
            color: var(--text-muted);
        }
        .loading .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid var(--border-color);
            border-top-color: var(--primary);
            border-radius: 50%;
            animation: spin 0.8s linear infinite;
            margin: 0 auto 16px;
        }
        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }

        .error {
            text-align: center;
            padding: 40px 20px;
            color: var(--danger);
        }
        .error small {
            display: block;
            margin-top: 8px;
            color: var(--text-muted);
            font-size: 14px;
        }

        /* ================================================================
           RESPONSIVE
           ================================================================ */
        @media (max-width: 768px) {
            body {
                padding: 10px;
            }
            .header {
                padding: 16px 18px;
                flex-direction: column;
                align-items: stretch;
            }
            .header-left h1 {
                font-size: 18px;
            }
            .header-right {
                flex-direction: column;
                align-items: stretch;
            }
            .search-box input {
                width: 100%;
            }
            .search-box input:focus {
                width: 100%;
            }
            .stats {
                justify-content: center;
                font-size: 12px;
            }
            .tabs {
                flex-wrap: wrap;
            }
            .tab-btn {
                font-size: 13px;
                padding: 8px 14px;
                flex: 1 1 auto;
            }
            .main-content {
                padding: 16px;
            }
            .story-grid {
                grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            }
            .story-content {
                font-size: 16px;
                padding: 14px 16px;
            }
            .audio-controls {
                border-radius: var(--radius-sm);
                flex-direction: column;
                align-items: stretch;
            }
            .btn-speaker {
                justify-content: center;
            }
            .speed-group {
                margin-left: 0;
                justify-content: center;
            }
            .volume-control input[type="range"] {
                width: 60px;
            }
            .all-vocab-grid {
                grid-template-columns: 1fr 1fr;
            }
            .quiz-options {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 480px) {
            .header-left h1 {
                font-size: 16px;
            }
            .header-left .badge {
                font-size: 10px;
                padding: 0 10px;
            }
            .story-grid {
                grid-template-columns: 1fr 1fr;
            }
            .story-grid .story-btn {
                font-size: 12px;
                padding: 8px 10px;
            }
            .story-content {
                font-size: 15px;
                padding: 12px;
            }
            .story-title {
                font-size: 20px;
            }
            .all-vocab-grid {
                grid-template-columns: 1fr;
            }
            .quiz-options {
                grid-template-columns: 1fr;
            }
            .vocab-table {
                font-size: 13px;
                min-width: 300px;
            }
            .speed-btn {
                font-size: 12px;
                padding: 4px 10px;
            }
            .status-text {
                font-size: 12px;
                min-width: 70px;
            }
        }
    </style>
</head>
<body>

    <div class="app" id="app">

        <!-- ============================================================
        HEADER
        ============================================================ -->
        <header class="header">
            <div class="header-left">
                <span class="logo">🌟</span>
                <h1>English <span>Pro</span></h1>
                <span class="badge">BETA</span>
            </div>
            <div class="header-right">
                <div class="search-box">
                    <span class="icon">🔍</span>
                    <input type="text" id="globalSearch" placeholder="ค้นหาเรื่องหรือคำศัพท์..." />
                </div>
                <div class="stats">
                    📚 <span id="totalWords">0</span> คำ
                </div>
                <button class="theme-toggle" id="themeToggle" aria-label="Toggle theme">
                    <span id="themeIcon">🌙</span>
                    <span class="label" id="themeLabel">มืด</span>
                </button>
            </div>
        </header>

        <!-- ============================================================
        TABS
        ============================================================ -->
        <nav class="tabs" id="tabNav">
            <button class="tab-btn active" data-tab="stories">📖 เรื่องสั้น <span class="count" id="storyCount">0</span></button>
            <button class="tab-btn" data-tab="vocab">📚 คำศัพท์ทั้งหมด <span class="count" id="vocabCount">0</span></button>
            <button class="tab-btn" data-tab="quiz">🧠 ทดสอบ <span class="count">Quiz</span></button>
            <button class="tab-btn" data-tab="favorites">⭐ คำที่ชอบ <span class="count" id="favCount">0</span></button>
        </nav>

        <!-- ============================================================
        MAIN CONTENT
        ============================================================ -->
        <main class="main-content">

            <!-- ===== TAB: STORIES ===== -->
            <section class="tab-panel active" id="panel-stories">
                <div class="story-grid" id="storyGrid"></div>
                <div class="story-display" id="storyDisplay">
                    <div class="loading"><div class="spinner"></div>กำลังโหลดเรื่องราว...</div>
                </div>
                <div class="shortcuts-hint">
                    ⌨️ <kbd>Space</kbd> เล่น/หยุดเสียง · <kbd>→</kbd> เรื่องถัดไป · <kbd>←</kbd> เรื่องก่อนหน้า
                </div>
            </section>

            <!-- ===== TAB: ALL VOCAB ===== -->
            <section class="tab-panel" id="panel-vocab">
                <div class="all-vocab-controls">
                    <span class="filter-label">🔎 กรองตามชนิด:</span>
                    <select id="vocabTypeFilter">
                        <option value="all">ทั้งหมด</option>
                        <option value="noun">Noun (คำนาม)</option>
                        <option value="verb">Verb (คำกริยา)</option>
                        <option value="adjective">Adjective (คำคุณศัพท์)</option>
                        <option value="adverb">Adverb (คำวิเศษณ์)</option>
                        <option value="phrasal verb">Phrasal Verb</option>
                    </select>
                    <input type="text" id="vocabSearchFilter" placeholder="ค้นหาคำศัพท์..." />
                </div>
                <div class="all-vocab-grid" id="allVocabGrid">
                    <div class="loading">กำลังโหลด...</div>
                </div>
            </section>

            <!-- ===== TAB: QUIZ ===== -->
            <section class="tab-panel" id="panel-quiz">
                <div class="quiz-container" id="quizContainer">
                    <div class="loading"><div class="spinner"></div>กำลังเตรียมแบบทดสอบ...</div>
                </div>
            </section>

            <!-- ===== TAB: FAVORITES ===== -->
            <section class="tab-panel" id="panel-favorites">
                <div id="favoritesContainer">
                    <div class="loading">กำลังโหลด...</div>
                </div>
            </section>

        </main>

        <div class="shortcuts-hint" style="margin-top:16px; border-top: none; padding-top: 8px;">
            🇹🇭 เรียนภาษาอังกฤษอย่างมืออาชีพ · พัฒนาด้วย Google Sheets
        </div>
    </div>

    <script>
        // ================================================================
        //  1. CONFIG
        // ================================================================
        const SHEET_ID = '13PC7nCFwM02IsZlBjgvOfHWiw-qizrW72z5LM0zZOU4';
        const SHEET_NAME = 'stories';
        const CSV_URL =
            `https://docs.google.com/spreadsheets/d/${SHEET_ID}/gviz/tq?tqx=out:csv&sheet=${SHEET_NAME}`;

        // ================================================================
        //  2. STATE
        // ================================================================
        let allStories = []; // [{ id, title, content, vocab: [{word, type, meaning}] }]
        let allVocab = []; // [{ word, type, meaning, storyId, storyTitle }]
        let currentStoryId = null;
        let currentSentenceIndex = -1; // -1 = whole story
        let favorites = JSON.parse(localStorage.getItem('engProFavorites') || '[]');
        let isLoop = false;
        let currentSpeed = 1.0;
        let currentVolume = 1.0;

        // Speech
        const speech = window.speechSynthesis;
        let currentUtterance = null;
        let isSpeaking = false;
        let speechTimer = null;

        // Quiz
        let quizQuestions = [];
        let quizIndex = 0;
        let quizScore = 0;
        let quizAnswered = false;

        // ================================================================
        //  3. DOM REFS
        // ================================================================
        const $ = id => document.getElementById(id);
        const storyGrid = $('storyGrid');
        const storyDisplay = $('storyDisplay');
        const globalSearch = $('globalSearch');
        const totalWords = $('totalWords');
        const storyCount = $('storyCount');
        const vocabCount = $('vocabCount');
        const favCount = $('favCount');
        const allVocabGrid = $('allVocabGrid');
        const vocabTypeFilter = $('vocabTypeFilter');
        const vocabSearchFilter = $('vocabSearchFilter');
        const quizContainer = $('quizContainer');
        const favoritesContainer = $('favoritesContainer');
        const themeToggle = $('themeToggle');
        const themeIcon = $('themeIcon');
        const themeLabel = $('themeLabel');

        // ================================================================
        //  4. THEME
        // ================================================================
        function initTheme() {
            const saved = localStorage.getItem('engProTheme') || 'light';
            document.documentElement.setAttribute('data-theme', saved);
            updateThemeUI(saved);
        }

        function toggleTheme() {
            const current = document.documentElement.getAttribute('data-theme');
            const next = current === 'dark' ? 'light' : 'dark';
            document.documentElement.setAttribute('data-theme', next);
            localStorage.setItem('engProTheme', next);
            updateThemeUI(next);
        }

        function updateThemeUI(theme) {
            if (theme === 'dark') {
                themeIcon.textContent = '☀️';
                themeLabel.textContent = 'สว่าง';
            } else {
                themeIcon.textContent = '🌙';
                themeLabel.textContent = 'มืด';
            }
        }

        themeToggle.addEventListener('click', toggleTheme);
        initTheme();

        // ================================================================
        //  5. FAVORITES
        // ================================================================
        function saveFavorites() {
            localStorage.setItem('engProFavorites', JSON.stringify(favorites));
            updateFavCount();
        }

        function toggleFavorite(word, type, meaning, storyId, storyTitle) {
            const key = word + '|' + type;
            const idx = favorites.findIndex(f => f.key === key);
            if (idx > -1) {
                favorites.splice(idx, 1);
            } else {
                favorites.push({ key, word, type, meaning, storyId, storyTitle });
            }
            saveFavorites();
            renderAllVocab();
            renderFavorites();
            // Refresh current story vocab
            if (currentStoryId) showStory(currentStoryId);
        }

        function isFav(word, type) {
            const key = word + '|' + type;
            return favorites.some(f => f.key === key);
        }

        function updateFavCount() {
            favCount.textContent = favorites.length;
        }

        // ================================================================
        //  6. LOAD DATA
        // ================================================================
        async function loadData() {
            try {
                const resp = await fetch(CSV_URL);
                if (!resp.ok) throw new Error(`HTTP ${resp.status}`);
                const csvText = await resp.text();
                const rows = parseCSV(csvText);
                if (rows.length < 2) throw new Error('ไม่พบข้อมูลในชีต');

                allStories = buildStories(rows);
                allVocab = buildAllVocab(allStories);

                // Update counts
                storyCount.textContent = allStories.length;
                vocabCount.textContent = allVocab.length;
                totalWords.textContent = allVocab.length;
                updateFavCount();

                // Render
                renderStoryGrid();
                renderAllVocab();
                renderFavorites();
                initQuiz();

                // Restore last story
                const lastId = localStorage.getItem('engProLastStory');
                if (lastId && allStories.some(s => s.id === parseInt(lastId))) {
                    showStory(parseInt(lastId));
                } else if (allStories.length) {
                    showStory(allStories[0].id);
                }

            } catch (err) {
                console.error('Load error:', err);
                storyDisplay.innerHTML =
                    `<div class="error">❌ ไม่สามารถโหลดข้อมูลได้<br><small>${err.message}</small><br><br><small>🔧 ตรวจสอบว่าได้เผยแพร่ชีต "${SHEET_NAME}" เป็น CSV แล้ว</small></div>`;
                allVocabGrid.innerHTML = `<div class="error">❌ ${err.message}</div>`;
                quizContainer.innerHTML = `<div class="error">❌ ${err.message}</div>`;
                favoritesContainer.innerHTML = `<div class="error">❌ ${err.message}</div>`;
            }
        }

        // ================================================================
        //  7. PARSE CSV
        // ================================================================
        function parseCSV(text) {
            const lines = text.split('\n').filter(line => line.trim() !== '');
            return lines.map(line => {
                const cols = [];
                let cur = '';
                let inQuotes = false;
                for (let i = 0; i < line.length; i++) {
                    const ch = line[i];
                    if (ch === '"') {
                        inQuotes = !inQuotes;
                    } else if (ch === ',' && !inQuotes) {
                        cols.push(cur.trim());
                        cur = '';
                    } else {
                        cur += ch;
                    }
                }
                cols.push(cur.trim());
                return cols;
            });
        }

        // ================================================================
        //  8. BUILD STORIES
        // ================================================================
        function buildStories(rows) {
            const header = rows[0].map(h => h.toLowerCase().replace(/ /g, '_'));
            const map = new Map();
            for (let i = 1; i < rows.length; i++) {
                const row = rows[i];
                if (row.length < header.length) continue;
                const get = (key) => {
                    const idx = header.indexOf(key);
                    return (idx !== -1 && idx < row.length) ? row[idx] : '';
                };
                const id = parseInt(get('story_id')) || i;
                const title = get('title') || `เรื่องที่ ${id}`;
                const content = get('content') || '';
                const word = get('vocab_word');
                const type = get('vocab_type');
                const meaning = get('vocab_meaning');
                if (!map.has(id)) {
                    map.set(id, { id, title, content, vocab: [] });
                }
                if (word && type && meaning) {
                    map.get(id).vocab.push({ word, type, meaning });
                }
            }
            return Array.from(map.values());
        }

        // ================================================================
        //  9. BUILD ALL VOCAB
        // ================================================================
        function buildAllVocab(stories) {
            const result = [];
            stories.forEach(s => {
                s.vocab.forEach(v => {
                    result.push({
                        word: v.word,
                        type: v.type,
                        meaning: v.meaning,
                        storyId: s.id,
                        storyTitle: s.title
                    });
                });
            });
            return result;
        }

        // ================================================================
        //  10. RENDER STORY GRID
        // ================================================================
        function renderStoryGrid(filter = '') {
            const search = filter.toLowerCase().trim();
            let filtered = allStories;
            if (search) {
                filtered = allStories.filter(s =>
                    s.title.toLowerCase().includes(search) ||
                    s.content.toLowerCase().includes(search) ||
                    s.vocab.some(v => v.word.toLowerCase().includes(search) || v.meaning.includes(search))
                );
            }
            storyGrid.innerHTML = '';
            if (!filtered.length) {
                storyGrid.innerHTML = `<div style="grid-column:1/-1;text-align:center;color:var(--text-muted);padding:20px;">ไม่พบเรื่องที่ค้นหา</div>`;
                return;
            }
            filtered.forEach(s => {
                const btn = document.createElement('button');
                btn.className = 'story-btn' + (s.id === currentStoryId ? ' active' : '');
                btn.innerHTML = `${s.title} <span class="story-id">#${s.id}</span>`;
                btn.onclick = () => { stopSpeaking();
                    showStory(s.id); };
                storyGrid.appendChild(btn);
            });
        }

        // ================================================================
        //  11. SHOW STORY
        // ================================================================
        function showStory(id) {
            currentStoryId = id;
            localStorage.setItem('engProLastStory', id);
            const story = allStories.find(s => s.id === id);
            if (!story) return;

            // Update grid
            document.querySelectorAll('.story-grid .story-btn').forEach(btn => {
                btn.classList.toggle('active', parseInt(btn.textContent.match(/#(\d+)/)?.[1]) === id);
            });

            // Highlight content
            let highlighted = story.content;
            story.vocab.forEach(v => {
                const safe = v.word.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
                const regex = new RegExp(`\\b${safe}\\b`, 'gi');
                highlighted = highlighted.replace(regex, match =>
                    `<span class="highlight" title="${v.type}: ${v.meaning}">${match}</span>`
                );
            });

            // Build vocab table
            let vocabHTML = '';
            if (story.vocab.length) {
                const rows = story.vocab.map(v => {
                    const fav = isFav(v.word, v.type);
                    return `<tr>
                        <td><strong>${v.word}</strong></td>
                        <td><span class="type-badge">${v.type}</span></td>
                        <td>${v.meaning}</td>
                        <td>
                            <button class="fav-btn ${fav ? 'is-fav' : ''}" 
                                    onclick="toggleFavorite('${v.word}','${v.type}','${v.meaning}',${story.id},'${story.title}')">
                                ${fav ? '⭐' : '☆'}
                            </button>
                        </td>
                    </tr>`;
                }).join('');
                vocabHTML = `
                    <div class="vocab-section">
                        <div class="section-header">
                            <h3>📚 คำศัพท์ในเรื่องนี้ (${story.vocab.length} คำ)</h3>
                            <button class="favorite-all" onclick="toggleAllFav(${story.id})">
                                ${story.vocab.every(v => isFav(v.word, v.type)) ? '⭐ เลิกชอบทั้งหมด' : '☆ ชอบทั้งหมด'}
                            </button>
                        </div>
                        <div class="vocab-table-wrap">
                            <table class="vocab-table">
                                <thead><tr><th>คำศัพท์</th><th>ชนิด</th><th>คำแปล</th><th>⭐</th></tr></thead>
                                <tbody>${rows}</tbody>
                            </table>
                        </div>
                    </div>
                `;
            }

            // Sentences
            const sentences = story.content.match(/[^.!?]+[.!?]+/g) || [story.content];
            let sentenceHTML = `
                <div class="sentence-mode">
                    <button class="sentence-btn active" data-sentence="-1" onclick="selectSentence(${story.id}, -1)">📄 ทั้งเรื่อง</button>
                    ${sentences.map((s, i) => `
                        <button class="sentence-btn" data-sentence="${i}" onclick="selectSentence(${story.id}, ${i})">
                            ${i+1} <span class="sentence-index">/${sentences.length}</span>
                        </button>
                    `).join('')}
                </div>
            `;

            // Build display
            storyDisplay.innerHTML = `
                <div class="story-title">
                    <span>📖 ${story.title}</span>
                    <span class="story-id-badge">#${story.id}</span>
                </div>
                ${sentenceHTML}
                <div class="story-content" id="storyContent">${highlighted}</div>

                <div class="audio-controls">
                    <button class="btn-speaker" id="speakerBtn">
                        <svg viewBox="0 0 24 24"><path d="M3 9v6h4l5 5V4L7 9H3zm13.5 3c0-1.77-1.02-3.29-2.5-4.03v8.05c1.48-.73 2.5-2.25 2.5-4.02zM14 3.23v2.06c2.89.86 5 3.54 5 6.71s-2.11 5.85-5 6.71v2.06c4.01-.91 7-4.49 7-8.77s-2.99-7.86-7-8.77z"/></svg>
                        <span id="speakerLabel">ฟังเสียง</span>
                    </button>

                    <button class="loop-btn ${isLoop ? 'active' : ''}" id="loopBtn" title="เล่นซ้ำ">
                        🔁 <span class="label">${isLoop ? 'ON' : 'OFF'}</span>
                    </button>

                    <div class="speed-group">
                        <label>🐢</label>
                        <button class="speed-btn ${currentSpeed === 0.6 ? 'active' : ''}" data-speed="0.6">ช้า</button>
                        <button class="speed-btn ${currentSpeed === 1.0 ? 'active' : ''}" data-speed="1.0">ปกติ</button>
                        <button class="speed-btn ${currentSpeed === 1.4 ? 'active' : ''}" data-speed="1.4">เร็ว</button>
                    </div>

                    <div class="volume-control">
                        <span style="font-size:14px;">🔊</span>
                        <input type="range" id="volumeSlider" min="0" max="1" step="0.05" value="${currentVolume}" />
                        <span class="vol-label" id="volLabel">${Math.round(currentVolume*100)}%</span>
                    </div>

                    <span class="status-text" id="statusText">⏸ พร้อม</span>
                </div>

                <div class="speech-progress" id="speechProgress">
                    <div class="bar" id="progressBar"></div>
                </div>

                ${vocabHTML}

                <div style="margin-top:14px; font-size:14px; color:var(--text-muted);">
                    💡 คลิกที่คำศัพท์ <span style="background:var(--accent-light);padding:0 6px;border-radius:4px;">สีเหลือง</span> เพื่อดูชนิดและความหมาย
                </div>
            `;

            // --- Bind events ---
            // Speaker
            const speakerBtn = document.getElementById('speakerBtn');
            if (speakerBtn) {
                speakerBtn.addEventListener('click', () => {
                    const text = getCurrentText();
                    toggleSpeech(text);
                });
            }

            // Loop
            const loopBtn = document.getElementById('loopBtn');
            if (loopBtn) {
                loopBtn.addEventListener('click', () => {
                    isLoop = !isLoop;
                    loopBtn.classList.toggle('active');
                    loopBtn.querySelector('.label').textContent = isLoop ? 'ON' : 'OFF';
                });
            }

            // Speed
            document.querySelectorAll('.speed-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    document.querySelectorAll('.speed-btn').forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    currentSpeed = parseFloat(this.dataset.speed);
                    if (currentUtterance) currentUtterance.rate = currentSpeed;
                    updateStatus('⏱ ' + (currentSpeed === 0.6 ? 'ช้า' : currentSpeed === 1.0 ? 'ปกติ' :
                    'เร็ว'));
                });
            });

            // Volume
            const volSlider = document.getElementById('volumeSlider');
            if (volSlider) {
                volSlider.addEventListener('input', function() {
                    currentVolume = parseFloat(this.value);
                    document.getElementById('volLabel').textContent = Math.round(currentVolume * 100) + '%';
                    if (currentUtterance) currentUtterance.volume = currentVolume;
                });
            }

            // Reset sentence selection
            currentSentenceIndex = -1;
            document.querySelectorAll('.sentence-btn').forEach(b => b.classList.remove('active'));
            const firstBtn = document.querySelector('.sentence-btn[data-sentence="-1"]');
            if (firstBtn) firstBtn.classList.add('active');

            // Keyboard shortcuts
            document.onkeydown = (e) => {
                if (e.target.tagName === 'INPUT' || e.target.tagName === 'SELECT') return;
                if (e.key === ' ') { e.preventDefault();
                    toggleSpeech(getCurrentText()); }
                if (e.key === 'ArrowRight') {
                    const next = allStories.find(s => s.id > currentStoryId);
                    if (next) showStory(next.id);
                }
                if (e.key === 'ArrowLeft') {
                    const prev = allStories.filter(s => s.id < currentStoryId).pop();
                    if (prev) showStory(prev.id);
                }
            };
        }

        // ================================================================
        //  12. SENTENCE SELECTION
        // ================================================================
        function selectSentence(storyId, index) {
            currentSentenceIndex = index;
            document.querySelectorAll('.sentence-btn').forEach(b => {
                b.classList.toggle('active', parseInt(b.dataset.sentence) === index);
            });
            // Highlight only that sentence in content
            const story = allStories.find(s => s.id === storyId);
            if (!story) return;
            const sentences = story.content.match(/[^.!?]+[.!?]+/g) || [story.content];
            let highlighted = story.content;
            if (index >= 0 && index < sentences.length) {
                // Rebuild highlight with only that sentence visible
                const parts = [];
                const fullText = story.content;
                let pos = 0;
                for (let i = 0; i < sentences.length; i++) {
                    const s = sentences[i];
                    const start = fullText.indexOf(s, pos);
                    if (start === -1) continue;
                    if (i === index) {
                        parts.push(`<mark style="background:var(--accent-light);padding:0 4px;border-radius:4px;">${s}</mark>`);
                    } else {
                        parts.push(`<span style="opacity:0.3;font-size:0.9em;">${s}</span>`);
                    }
                    pos = start + s.length;
                }
                highlighted = parts.join(' ');
            } else {
                // Whole story - reapply vocab highlights
                highlighted = story.content;
                story.vocab.forEach(v => {
                    const safe = v.word.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
                    const regex = new RegExp(`\\b${safe}\\b`, 'gi');
                    highlighted = highlighted.replace(regex, match =>
                        `<span class="highlight" title="${v.type}: ${v.meaning}">${match}</span>`
                    );
                });
            }
            const contentEl = document.getElementById('storyContent');
            if (contentEl) contentEl.innerHTML = highlighted;
            // Stop any speaking
            stopSpeaking();
        }

        function getCurrentText() {
            if (currentSentenceIndex >= 0) {
                const story = allStories.find(s => s.id === currentStoryId);
                if (!story) return '';
                const sentences = story.content.match(/[^.!?]+[.!?]+/g) || [story.content];
                if (currentSentenceIndex < sentences.length) return sentences[currentSentenceIndex];
                return story.content;
            }
            const story = allStories.find(s => s.id === currentStoryId);
            return story ? story.content : '';
        }

        // ================================================================
        //  13. SPEECH
        // ================================================================
        function toggleSpeech(text) {
            if (isSpeaking) {
                stopSpeaking();
                return;
            }
            startSpeaking(text);
        }

        function startSpeaking(text) {
            if (!text) return;
            if (speech.speaking) speech.cancel();

            const utterance = new SpeechSynthesisUtterance(text);
            utterance.lang = 'en-US';
            utterance.rate = currentSpeed;
            utterance.pitch = 1.0;
            utterance.volume = currentVolume;

            const label = document.getElementById('speakerLabel');
            const btn = document.getElementById('speakerBtn');
            const status = document.getElementById('statusText');
            const bar = document.getElementById('progressBar');

            if (label) label.textContent = '⏹ หยุด';
            if (btn) btn.classList.add('speaking');
            if (status) status.textContent = '🔊 กำลังพูด...';

            // Progress
            let progress = 0;
            if (speechTimer) clearInterval(speechTimer);
            speechTimer = setInterval(() => {
                if (isSpeaking) {
                    progress = Math.min(progress + 2, 100);
                    if (bar) bar.style.width = progress + '%';
                }
            }, 100);

            utterance.onstart = () => {
                isSpeaking = true;
                currentUtterance = utterance;
                if (status) status.textContent = '🔊 กำลังพูด...';
            };

            utterance.onend = () => {
                isSpeaking = false;
                currentUtterance = null;
                if (label) label.textContent = 'ฟังเสียง';
                if (btn) btn.classList.remove('speaking');
                if (status) status.textContent = '✅ เสร็จสิ้น';
                if (bar) bar.style.width = '100%';
                if (speechTimer) clearInterval(speechTimer);
                setTimeout(() => { if (bar) bar.style.width = '0%'; }, 600);

                if (isLoop) {
                    setTimeout(() => startSpeaking(getCurrentText()), 800);
                }
            };

            utterance.onerror = () => {
                isSpeaking = false;
                currentUtterance = null;
                if (label) label.textContent = 'ฟังเสียง';
                if (btn) btn.classList.remove('speaking');
                if (status) status.textContent = '❌ เกิดข้อผิดพลาด';
                if (speechTimer) clearInterval(speechTimer);
            };

            speech.speak(utterance);
        }

        function stopSpeaking() {
            if (speech.speaking) speech.cancel();
            isSpeaking = false;
            currentUtterance = null;
            const label = document.getElementById('speakerLabel');
            const btn = document.getElementById('speakerBtn');
            const status = document.getElementById('statusText');
            if (label) label.textContent = 'ฟังเสียง';
            if (btn) btn.classList.remove('speaking');
            if (status) status.textContent = '⏸ หยุดแล้ว';
            if (speechTimer) clearInterval(speechTimer);
            const bar = document.getElementById('progressBar');
            if (bar) bar.style.width = '0%';
        }

        function updateStatus(msg) {
            const el = document.getElementById('statusText');
            if (el) el.textContent = msg;
        }

        // ================================================================
        //  14. ALL VOCAB
        // ================================================================
        function renderAllVocab() {
            let filtered = [...allVocab];
            const typeFilter = vocabTypeFilter.value;
            const searchFilter = vocabSearchFilter.value.toLowerCase().trim();
            if (typeFilter !== 'all') {
                filtered = filtered.filter(v => v.type.toLowerCase() === typeFilter);
            }
            if (searchFilter) {
                filtered = filtered.filter(v =>
                    v.word.toLowerCase().includes(searchFilter) ||
                    v.meaning.includes(searchFilter) ||
                    v.storyTitle.toLowerCase().includes(searchFilter)
                );
            }

            if (!filtered.length) {
                allVocabGrid.innerHTML = `<div style="grid-column:1/-1;text-align:center;color:var(--text-muted);padding:30px;">ไม่พบคำศัพท์</div>`;
                return;
            }

            allVocabGrid.innerHTML = filtered.map(v => {
                const fav = isFav(v.word, v.type);
                return `<div class="all-vocab-item">
                    <div style="display:flex;justify-content:space-between;align-items:start;">
                        <div>
                            <div class="word">${v.word}</div>
                            <div class="type">${v.type}</div>
                        </div>
                        <button class="fav-btn ${fav ? 'is-fav' : ''}" 
                                onclick="toggleFavorite('${v.word}','${v.type}','${v.meaning}',${v.storyId},'${v.storyTitle}')"
                                style="background:none;border:none;font-size:20px;cursor:pointer;">
                            ${fav ? '⭐' : '☆'}
                        </button>
                    </div>
                    <div class="meaning">${v.meaning}</div>
                    <div class="from-story">📖 ${v.storyTitle}</div>
                </div>`;
            }).join('');
        }

        vocabTypeFilter.addEventListener('change', renderAllVocab);
        vocabSearchFilter.addEventListener('input', renderAllVocab);

        // ================================================================
        //  15. FAVORITES TAB
        // ================================================================
        function renderFavorites() {
            if (!favorites.length) {
                favoritesContainer.innerHTML = `
                    <div class="favorites-empty">
                        <div class="big-icon">⭐</div>
                        <h3>ยังไม่มีคำศัพท์ที่ชอบ</h3>
                        <p>กดปุ่ม ⭐ ข้างคำศัพท์เพื่อบันทึกไว้ทบทวน</p>
                    </div>
                `;
                return;
            }
            favoritesContainer.innerHTML = `
                <div style="margin-bottom:16px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:8px;">
                    <h3 style="color:var(--text-primary);">⭐ คำศัพท์ที่ชอบ (${favorites.length} คำ)</h3>
                    <button onclick="clearFavorites()" style="padding:6px 16px;border-radius:var(--radius-full);border:2px solid var(--danger);background:transparent;color:var(--danger);cursor:pointer;font-family:var(--font);font-weight:600;transition:var(--transition);">
                        🗑 ลบทั้งหมด
                    </button>
                </div>
                <div class="all-vocab-grid">
                    ${favorites.map(f => `
                        <div class="all-vocab-item">
                            <div style="display:flex;justify-content:space-between;align-items:start;">
                                <div>
                                    <div class="word">${f.word}</div>
                                    <div class="type">${f.type}</div>
                                </div>
                                <button class="fav-btn is-fav" 
                                        onclick="toggleFavorite('${f.word}','${f.type}','${f.meaning}',${f.storyId},'${f.storyTitle}')"
                                        style="background:none;border:none;font-size:20px;cursor:pointer;">
                                    ⭐
                                </button>
                            </div>
                            <div class="meaning">${f.meaning}</div>
                            <div class="from-story">📖 ${f.storyTitle}</div>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        function clearFavorites() {
            if (confirm('ลบคำศัพท์ที่ชอบทั้งหมด?')) {
                favorites = [];
                saveFavorites();
                renderAllVocab();
                renderFavorites();
                if (currentStoryId) showStory(currentStoryId);
            }
        }

        function toggleAllFav(storyId) {
            const story = allStories.find(s => s.id === storyId);
            if (!story) return;
            const allFav = story.vocab.every(v => isFav(v.word, v.type));
            story.vocab.forEach(v => {
                const key = v.word + '|' + v.type;
                if (allFav) {
                    const idx = favorites.findIndex(f => f.key === key);
                    if (idx > -1) favorites.splice(idx, 1);
                } else {
                    if (!favorites.some(f => f.key === key)) {
                        favorites.push({ key, word: v.word, type: v.type, meaning: v.meaning, storyId: story.id,
                            storyTitle: story.title });
                    }
                }
            });
            saveFavorites();
            renderAllVocab();
            renderFavorites();
            showStory(storyId);
        }

        // ================================================================
        //  16. QUIZ
        // ================================================================
        function initQuiz() {
            if (!allVocab.length) {
                quizContainer.innerHTML = `<div class="loading">ไม่มีคำศัพท์สำหรับทำแบบทดสอบ</div>`;
                return;
            }
            // Shuffle and pick 10 questions
            const shuffled = [...allVocab].sort(() => Math.random() - 0.5);
            const selected = shuffled.slice(0, Math.min(10, shuffled.length));
            quizQuestions = selected.map(v => ({
                word: v.word,
                type: v.type,
                meaning: v.meaning,
                storyTitle: v.storyTitle,
                // 3 wrong options
                wrongs: allVocab
                    .filter(w => w.meaning !== v.meaning)
                    .sort(() => Math.random() - 0.5)
                    .slice(0, 3)
                    .map(w => w.meaning)
            }));
            quizIndex = 0;
            quizScore = 0;
            quizAnswered = false;
            renderQuiz();
        }

        function renderQuiz() {
            if (!quizQuestions.length || quizIndex >= quizQuestions.length) {
                quizContainer.innerHTML = `
                    <div class="quiz-container">
                        <div class="quiz-result" style="color:var(--success);font-size:24px;">🎉 ทำแบบทดสอบเสร็จแล้ว!</div>
                        <div class="quiz-score">คะแนน: ${quizScore} / ${quizQuestions.length}</div>
                        <button class="quiz-next-btn" onclick="initQuiz()">🔄 ทำใหม่</button>
                    </div>
                `;
                return;
            }

            const q = quizQuestions[quizIndex];
            const options = [q.meaning, ...q.wrongs].sort(() => Math.random() - 0.5);

            quizContainer.innerHTML = `
                <div class="quiz-container">
                    <div class="quiz-question">📝 คำว่า "<strong>${q.word}</strong>" (${q.type}) แปลว่าอะไร?</div>
                    <div class="quiz-hint">📖 จากเรื่อง: ${q.storyTitle}</div>
                    <div class="quiz-options" id="quizOptions">
                        ${options.map((opt, i) => `
                            <button data-index="${i}" data-answer="${opt === q.meaning}">
                                ${opt}
                            </button>
                        `).join('')}
                    </div>
                    <div class="quiz-result" id="quizResult"></div>
                    <div class="quiz-score">ข้อ ${quizIndex + 1} / ${quizQuestions.length} · คะแนน ${quizScore}</div>
                    <button class="quiz-next-btn" id="quizNextBtn" style="display:none;">➡️ ข้อถัดไป</button>
                </div>
            `;

            // Bind quiz options
            document.querySelectorAll('#quizOptions button').forEach(btn => {
                btn.addEventListener('click', function() {
                    if (quizAnswered) return;
                    quizAnswered = true;
                    const correct = this.dataset.answer === 'true';
                    const result = document.getElementById('quizResult');
                    if (correct) {
                        quizScore++;
                        this.classList.add('correct');
                        result.textContent = '✅ ถูกต้อง!';
                        result.style.color = 'var(--success)';
                    } else {
                        this.classList.add('wrong');
                        result.textContent = `❌ ผิด! คำตอบที่ถูกคือ "${q.meaning}"`;
                        result.style.color = 'var(--danger)';
                        // Show correct answer
                        document.querySelectorAll('#quizOptions button').forEach(b => {
                            if (b.dataset.answer === 'true') b.classList.add('correct');
                        });
                    }
                    document.querySelectorAll('#quizOptions button').forEach(b => b.disabled = true);
                    document.getElementById('quizNextBtn').style.display = 'inline-block';
                });
            });

            document.getElementById('quizNextBtn').addEventListener('click', () => {
                quizIndex++;
                quizAnswered = false;
                renderQuiz();
            });
        }

        // ================================================================
        //  17. GLOBAL SEARCH
        // ================================================================
        globalSearch.addEventListener('input', function() {
            const val = this.value.trim();
            if (val) {
                // Switch to stories tab and filter
                switchTab('stories');
                renderStoryGrid(val);
                // Also filter vocab
                vocabSearchFilter.value = val;
                renderAllVocab();
            } else {
                renderStoryGrid('');
                vocabSearchFilter.value = '';
                renderAllVocab();
            }
        });

        // ================================================================
        //  18. TABS
        // ================================================================
        document.querySelectorAll('.tab-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                const tab = this.dataset.tab;
                switchTab(tab);
            });
        });

        function switchTab(tab) {
            document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
            document.querySelector(`.tab-btn[data-tab="${tab}"]`)?.classList.add('active');
            document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
            const panel = document.getElementById('panel-' + tab);
            if (panel) panel.classList.add('active');
            // Refresh content
            if (tab === 'favorites') renderFavorites();
            if (tab === 'quiz') initQuiz();
            if (tab === 'vocab') renderAllVocab();
        }

        // ================================================================
        //  19. START
        // ================================================================
        loadData();
    </script>
</body>
</html>
