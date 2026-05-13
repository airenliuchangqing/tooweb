<QingYuanLiu>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人简历 - 体系工程师 | 刘先生</title>
    <style>
        :root {
            --bg-deep: #060612;
            --bg-card: rgba(14, 14, 30, 0.78);
            --border-glow: rgba(0, 200, 255, 0.22);
            --accent-cyan: #00d4ff;
            --accent-blue: #3b82f6;
            --accent-purple: #8b5cf6;
            --accent-gold: #f0a500;
            --accent-green: #10b981;
            --text-primary: #e8e8f0;
            --text-secondary: #b0b0c0;
            --text-muted: #7a7a90;
            --font-mono: 'SF Mono', 'Cascadia Code', 'Consolas', 'Monaco', 'Courier New', monospace;
            --font-sans: 'Inter', 'PingFang SC', 'Microsoft YaHei', 'Helvetica Neue', sans-serif;
            --transition-fast: 0.2s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-smooth: 0.35s cubic-bezier(0.4, 0, 0.2, 1);
            --glow-cyan: 0 0 18px rgba(0, 212, 255, 0.3);
            --glow-blue: 0 0 18px rgba(59, 130, 246, 0.3);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-sans);
            background: var(--bg-deep);
            color: var(--text-primary);
            min-height: 100vh;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            position: relative;
        }

        /* 粒子画布 */
        #particleCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        /* 网格背景 */
        .grid-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            background-image:
                linear-gradient(rgba(0, 180, 255, 0.018) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 180, 255, 0.018) 1px, transparent 1px);
            background-size: 56px 56px;
            background-position: center center;
            mask-image: radial-gradient(ellipse 70% 55% at 50% 35%, black 28%, transparent 72%);
            -webkit-mask-image: radial-gradient(ellipse 70% 55% at 50% 35%, black 28%, transparent 72%);
        }

        /* 顶部装饰线 */
        .top-line {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            z-index: 10;
            pointer-events: none;
            background: linear-gradient(90deg,
                    transparent 0%,
                    rgba(0, 200, 255, 0.12) 12%,
                    var(--accent-cyan) 28%,
                    var(--accent-blue) 48%,
                    var(--accent-purple) 65%,
                    var(--accent-cyan) 80%,
                    rgba(0, 200, 255, 0.12) 90%,
                    transparent 100%);
            animation: topLineFlow 7s ease-in-out infinite;
        }
        @keyframes topLineFlow {
            0%,
            100% {
                opacity: 0.65;
            }
            50% {
                opacity: 1;
            }
        }

        /* 主容器 */
        .main-container {
            position: relative;
            z-index: 1;
            max-width: 1300px;
            margin: 0 auto;
            padding: 36px 20px 70px;
            display: flex;
            flex-direction: column;
            gap: 26px;
        }

        /* ========== 头部区域 ========== */
        .header-section {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
            padding: 34px 38px;
            background: var(--bg-card);
            border-radius: 18px;
            border: 1px solid var(--border-glow);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            position: relative;
            overflow: hidden;
            box-shadow: 0 6px 36px rgba(0, 0, 0, 0.5), var(--glow-cyan), inset 0 1px 0 rgba(255, 255, 255, 0.02);
            animation: headerGlow 5s ease-in-out infinite;
        }
        @keyframes headerGlow {
            0%,
            100% {
                box-shadow: 0 6px 36px rgba(0, 0, 0, 0.5), 0 0 18px rgba(0, 212, 255, 0.3), inset 0 1px 0 rgba(255, 255, 255, 0.02);
            }
            50% {
                box-shadow: 0 6px 36px rgba(0, 0, 0, 0.5), 0 0 30px rgba(0, 212, 255, 0.5), 0 0 50px rgba(59, 130, 246, 0.18), inset 0 1px 0 rgba(255, 255, 255, 0.04);
            }
        }
        .header-section::before {
            content: '';
            position: absolute;
            top: -45%;
            right: -12%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(59, 130, 246, 0.07) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }
        .header-section::after {
            content: '';
            position: absolute;
            bottom: -35%;
            left: 8%;
            width: 260px;
            height: 260px;
            background: radial-gradient(circle, rgba(0, 200, 255, 0.05) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }
        .header-left {
            display: flex;
            flex-direction: column;
            gap: 6px;
            position: relative;
            z-index: 1;
        }
        .header-left .name {
            font-size: 2.6rem;
            font-weight: 700;
            letter-spacing: 0.04em;
            background: linear-gradient(135deg, #ffffff 0%, #c8e6ff 35%, #a0d0f8 65%, #e0e8ff 100%);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }
        .header-left .subtitle-row {
            display: flex;
            align-items: center;
            gap: 10px;
            flex-wrap: wrap;
            margin-top: 2px;
        }
        .header-left .badge {
            font-size: 0.85rem;
            font-weight: 500;
            padding: 6px 14px;
            border-radius: 22px;
            letter-spacing: 0.04em;
            white-space: nowrap;
            border: 1px solid rgba(0, 212, 255, 0.4);
            background: rgba(0, 212, 255, 0.06);
            color: var(--accent-cyan);
        }
        .header-left .badge.purple {
            border-color: rgba(139, 92, 246, 0.4);
            background: rgba(139, 92, 246, 0.06);
            color: #c4b5fd;
        }
        .header-left .badge.gold {
            border-color: rgba(240, 165, 0, 0.4);
            background: rgba(240, 165, 0, 0.06);
            color: #fcd34d;
        }
        .header-left .tagline {
            font-size: 0.9rem;
            color: var(--text-secondary);
            letter-spacing: 0.03em;
            margin-top: 4px;
        }
        .header-right {
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            gap: 8px;
            position: relative;
            z-index: 1;
        }
        .stat-badge {
            display: flex;
            align-items: baseline;
            gap: 5px;
            padding: 12px 20px;
            border-radius: 14px;
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.08);
            position: relative;
        }
        .stat-badge .stat-num {
            font-family: var(--font-mono);
            font-size: 3.2rem;
            font-weight: 800;
            letter-spacing: -0.02em;
            background: linear-gradient(180deg, #00e5ff 0%, #3b82f6 100%);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1;
        }
        .stat-badge .stat-label {
            font-size: 0.82rem;
            color: var(--text-secondary);
            letter-spacing: 0.04em;
            writing-mode: vertical-rl;
            text-orientation: mixed;
        }
        .stat-badge::after {
            content: '';
            position: absolute;
            inset: -1px;
            border-radius: 14px;
            padding: 1px;
            background: linear-gradient(135deg, rgba(0, 229, 255, 0.5), rgba(59, 130, 246, 0.5), rgba(139, 92, 246, 0.3));
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            pointer-events: none;
        }

        /* ========== 五列卡片网格 ========== */
        .cards-grid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
            gap: 18px;
        }
        @media (max-width: 1400px) {
            .cards-grid {
                grid-template-columns: 1fr 1fr 1fr;
            }
        }
        @media (max-width: 1024px) {
            .cards-grid {
                grid-template-columns: 1fr 1fr;
            }
        }
        @media (max-width: 700px) {
            .cards-grid {
                grid-template-columns: 1fr;
            }
            .header-section {
                flex-direction: column;
                align-items: flex-start;
                padding: 22px 18px;
            }
            .header-right {
                align-items: flex-start;
            }
            .header-left .name {
                font-size: 1.9rem;
            }
            .stat-badge .stat-num {
                font-size: 2.4rem;
            }
            .main-container {
                padding: 18px 10px 50px;
                gap: 16px;
            }
        }

        /* ========== 通用卡片 ========== */
        .card {
            background: var(--bg-card);
            border-radius: 16px;
            border: 1px solid var(--border-glow);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            padding: 24px 20px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 4px 26px rgba(0, 0, 0, 0.4);
            transition: var(--transition-smooth);
            display: flex;
            flex-direction: column;
            gap: 14px;
        }
        .card:hover {
            box-shadow: 0 6px 32px rgba(0, 0, 0, 0.5), 0 0 20px rgba(0, 200, 255, 0.18);
            border-color: rgba(0, 200, 255, 0.4);
            transform: translateY(-2px);
        }
        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.06), transparent);
            pointer-events: none;
        }
        .card-title {
            font-size: 0.95rem;
            font-weight: 600;
            letter-spacing: 0.06em;
            color: var(--accent-cyan);
            display: flex;
            align-items: center;
            gap: 9px;
            text-transform: uppercase;
            flex-shrink: 0;
        }
        .card-title .dot {
            width: 7px;
            height: 7px;
            border-radius: 50%;
            background: var(--accent-cyan);
            box-shadow: 0 0 8px var(--accent-cyan), 0 0 16px rgba(0, 212, 255, 0.45);
            animation: dotPulse 2s ease-in-out infinite;
        }
        @keyframes dotPulse {
            0%,
            100% {
                box-shadow: 0 0 7px var(--accent-cyan), 0 0 14px rgba(0, 212, 255, 0.35);
            }
            50% {
                box-shadow: 0 0 14px var(--accent-cyan), 0 0 26px rgba(0, 212, 255, 0.65);
            }
        }

        /* ========== 卡片1：基本信息 ========== */
        .card-info .info-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .card-info .info-item {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.85rem;
            color: var(--text-secondary);
            padding: 9px 12px;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.015);
            transition: var(--transition-fast);
            border: 1px solid transparent;
        }
        .card-info .info-item:hover {
            background: rgba(255, 255, 255, 0.035);
            border-color: rgba(255, 255, 255, 0.05);
        }
        .card-info .info-icon {
            font-size: 1rem;
            flex-shrink: 0;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 6px;
            background: rgba(0, 200, 255, 0.07);
            color: var(--accent-cyan);
        }
        .card-info .info-value {
            flex: 1;
            word-break: break-all;
        }
        .highlight-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-top: 4px;
        }
        .highlight-tag {
            font-size: 0.73rem;
            padding: 4px 10px;
            border-radius: 16px;
            background: rgba(240, 165, 0, 0.1);
            color: #fcd34d;
            border: 1px solid rgba(240, 165, 0, 0.25);
            letter-spacing: 0.03em;
            white-space: nowrap;
        }

        /* ========== 卡片2：行业经验 ========== */
        .card-industry .industry-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .card-industry .industry-item {
            padding: 11px 14px;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.015);
            border-left: 3px solid var(--accent-blue);
            transition: var(--transition-fast);
            position: relative;
        }
        .card-industry .industry-item:nth-child(1) {
            border-left-color: var(--accent-cyan);
        }
        .card-industry .industry-item:nth-child(2) {
            border-left-color: var(--accent-purple);
        }
        .card-industry .industry-item:nth-child(3) {
            border-left-color: var(--accent-gold);
        }
        .card-industry .industry-item:hover {
            background: rgba(255, 255, 255, 0.03);
            box-shadow: 0 0 16px rgba(0, 200, 255, 0.06);
        }
        .card-industry .ind-title {
            font-weight: 600;
            font-size: 0.88rem;
            color: #e0e0f0;
            margin-bottom: 3px;
            letter-spacing: 0.02em;
        }
        .card-industry .ind-desc {
            font-size: 0.78rem;
            color: var(--text-muted);
            line-height: 1.45;
        }

        /* ========== 卡片3：工作业绩 ========== */
        .card-achievements .achieve-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .card-achievements .achieve-item {
            padding: 10px 12px;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.015);
            font-size: 0.82rem;
            color: var(--text-secondary);
            line-height: 1.5;
            display: flex;
            align-items: flex-start;
            gap: 8px;
            transition: var(--transition-fast);
        }
        .card-achievements .achieve-item:hover {
            background: rgba(255, 255, 255, 0.03);
            color: #d0d0e0;
        }
        .card-achievements .achieve-icon {
            flex-shrink: 0;
            font-size: 1rem;
            margin-top: 1px;
        }
        .card-achievements .highlight-num {
            color: var(--accent-cyan);
            font-weight: 700;
            font-family: var(--font-mono);
        }

        /* ========== 卡片4：认证经验 ========== */
        .card-cert .cert-section {
            margin-bottom: 8px;
        }
        .card-cert .cert-section:last-child {
            margin-bottom: 0;
        }
        .card-cert .cert-label {
            font-size: 0.75rem;
            font-weight: 600;
            color: var(--accent-blue);
            letter-spacing: 0.05em;
            margin-bottom: 5px;
            text-transform: uppercase;
        }
        .card-cert .cert-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
        }
        .card-cert .cert-tag {
            font-size: 0.7rem;
            padding: 3px 9px;
            border-radius: 12px;
            background: rgba(59, 130, 246, 0.08);
            color: #93c5fd;
            border: 1px solid rgba(59, 130, 246, 0.2);
            letter-spacing: 0.02em;
            white-space: nowrap;
            transition: var(--transition-fast);
        }
        .card-cert .cert-tag:hover {
            background: rgba(59, 130, 246, 0.16);
            border-color: rgba(59, 130, 246, 0.4);
            color: #bfdbfe;
        }
        .card-cert .cert-tag.green {
            background: rgba(16, 185, 129, 0.08);
            border-color: rgba(16, 185, 129, 0.2);
            color: #6ee7b7;
        }
        .card-cert .cert-tag.green:hover {
            background: rgba(16, 185, 129, 0.16);
            border-color: rgba(16, 185, 129, 0.4);
            color: #a7f3d0;
        }
        .card-cert .cert-tag.purple {
            background: rgba(139, 92, 246, 0.08);
            border-color: rgba(139, 92, 246, 0.2);
            color: #c4b5fd;
        }
        .card-cert .cert-tag.purple:hover {
            background: rgba(139, 92, 246, 0.16);
            border-color: rgba(139, 92, 246, 0.4);
            color: #ddd6fe;
        }
        .card-cert .cert-tag.gold {
            background: rgba(240, 165, 0, 0.08);
            border-color: rgba(240, 165, 0, 0.2);
            color: #fcd34d;
        }
        .card-cert .cert-tag.gold:hover {
            background: rgba(240, 165, 0, 0.16);
            border-color: rgba(240, 165, 0, 0.4);
            color: #fde68a;
        }

        /* ========== 卡片5：个人技能 ========== */
        .card-skills .skill-category {
            margin-bottom: 8px;
        }
        .card-skills .skill-cat-label {
            font-size: 0.73rem;
            font-weight: 600;
            color: var(--accent-purple);
            letter-spacing: 0.04em;
            margin-bottom: 4px;
        }
        .card-skills .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
        }
        .card-skills .skill-tag {
            font-size: 0.72rem;
            padding: 4px 10px;
            border-radius: 14px;
            background: rgba(139, 92, 246, 0.08);
            color: #c4b5fd;
            border: 1px solid rgba(139, 92, 246, 0.2);
            letter-spacing: 0.03em;
            white-space: nowrap;
            transition: var(--transition-fast);
        }
        .card-skills .skill-tag:hover {
            background: rgba(139, 92, 246, 0.16);
            border-color: rgba(139, 92, 246, 0.4);
            color: #ddd6fe;
            box-shadow: 0 0 8px rgba(139, 92, 246, 0.15);
        }
    </style>
</head>
<body>

    <!-- 顶部装饰线 -->
    <div class="top-line"></div>
    <!-- 网格背景 -->
    <div class="grid-bg"></div>
    <!-- 粒子画布 -->
    <canvas id="particleCanvas"></canvas>

    <!-- 主容器 -->
    <div class="main-container">

        <!-- ========== 头部区域 ========== -->
        <section class="header-section">
            <div class="header-left">
                <h1 class="name">刘先生</h1>
                <div class="subtitle-row">
                    <span class="badge">体系工程师</span>
                    <span class="badge purple">注册体系审核员</span>
                    <span class="badge gold">人工智能训练师</span>
                </div>
                <p class="tagline">药学专业 · 理学学士 · 7年质量管理经验 · 期望城市：珠海 </p>
            </div>
            <div class="header-right">
                <div class="stat-badge">
                    <span class="stat-num">7</span>
                    <span class="stat-label">年工作经验</span>
                </div>
                <div style="font-size:0.78rem;color:var(--text-muted);letter-spacing:0.04em;">📧 2461480547@qq.com · 📱 15755211200</div>
            </div>
        </section>

        <!-- ========== 五列卡片区 ========== -->
        <div class="cards-grid">

            <!-- 卡片1：个人基本信息 -->
            <div class="card card-info">
                <div class="card-title"><span class="dot"></span>基本信息</div>
                <ul class="info-list">
                    <li class="info-item">
                        <span class="info-icon">👤</span>
                        <span class="info-value">26岁 · 男</span>
                    </li>
                    <li class="info-item">
                        <span class="info-icon">🎓</span>
                        <span class="info-value">药学专业 · 理学学士</span>
                    </li>
                    <li class="info-item">
                        <span class="info-icon">📜</span>
                        <span class="info-value">CCAA注册体系审核员</span>
                    </li>
                    <li class="info-item">
                        <span class="info-icon">🤖</span>
                        <span class="info-value">人工智能训练师</span>
                    </li>
                    <li class="info-item">
                        <span class="info-icon">📍</span>
                        <span class="info-value">广东 · 珠海</span>
                    </li>
                </ul>
                <div class="highlight-tags">
                    <span class="highlight-tag">沈阳药科大学</span>
                    <span class="highlight-tag">6年质量管理</span>
                    <span class="highlight-tag">5年体系工作</span>
                </div>
            </div>

            <!-- 卡片2：行业经验 -->
            <div class="card card-industry">
                <div class="card-title"><span class="dot"></span>行业经验</div>
                <ul class="industry-list">
                    <li class="industry-item">
                        <div class="ind-title">🏥 医药行业</div>
                        <div class="ind-desc">无菌注射剂、粉针剂、片剂生产质量管理
                        GMP合规监控</div>
                    </li>
                    <li class="industry-item">
                        <div class="ind-title">⚗️ 化工行业</div>
                        <div class="ind-desc">、汽车粉末材料（化学合成）
                        食品添加剂（生物发酵）</div>
                    </li>
                    <li class="industry-item">
                        <div class="ind-title">🪑 家具行业</div>
                        <div class="ind-desc">办公家具
                        民用家具
                        特殊场所家具</div>
                    </li>
                </ul>
            </div>

            <!-- 卡片3：工作业绩 -->
            <div class="card card-achievements">
                <div class="card-title"><span class="dot"></span>工作业绩</div>
                <ul class="achieve-list">
                    <li class="achieve-item">
                        <span class="achieve-icon">✅</span>
                        <span>客户方、监管部门、第三方审核一次性通过率<span class="highlight-num">100%</span></span>
                    </li>
                     <li class="achieve-item">
                        <span class="achieve-icon">💰</span>
                        <span>年度认证认可检验检测综合成本较上一年度<span class="highlight-num">降低15万元</span></span>
                    </li>
                     <li class="achieve-item">
                        <span class="achieve-icon">🏆</span>
                        <span>企业体系缺陷项较上年度降低<span class="highlight-num">300%</span></span>
                    </li>
                     <li class="achieve-item">
                        <span class="achieve-icon">🎯</span>
                        <span>客方、监管方、第三方改进项完成率<span class="highlight-num">100%</span></span>
                    </li>
                    <li class="achieve-item">
                        <span class="achieve-icon">📋</span>
                        <span>全年证书新增、扩项、变更完成率<span class="highlight-num">95%</span></span>
                    </li>
                    <li class="achieve-item">
                        <span class="achieve-icon">🔄</span>
                        <span>全年内部体系纠正与改进项完成率<span class="highlight-num">85%</span></span>
                    </li>
                </ul>
            </div>

            <!-- 卡片4：认证经验 -->
            <div class="card card-cert">
                <div class="card-title"><span class="dot"></span>认证经验</div>
                <div class="cert-section">
                    <div class="cert-label">📋 体系认证</div>
                    <div class="cert-tags">
                        <span class="cert-tag">ISO9001</span>
                        <span class="cert-tag">ISO14001</span>
                        <span class="cert-tag">ISO45001</span>
                        <span class="cert-tag">ISO50001</span>
                        <span class="cert-tag">ISO17025</span>
                        <span class="cert-tag">FSC</span>
                        <span class="cert-tag green">绿色工厂</span>
                        <span class="cert-tag green">绿色供应链</span>
                        <span class="cert-tag">社会责任</span>
                        <span class="cert-tag purple">BRCGS</span>
                        <span class="cert-tag purple">ISO22000</span>
                        <span class="cert-tag">HACCP</span>
                        <span class="cert-tag">CQTA品质保证</span>
                    </div>
                </div>
                <div class="cert-section">
                    <div class="cert-label">🏷️ 产品认证</div>
                    <div class="cert-tags">
                        <span class="cert-tag gold">UL认证</span>
                        <span class="cert-tag gold">有害物质</span>
                        <span class="cert-tag gold">中国环保产品</span>
                        <span class="cert-tag gold">环境标志</span>
                        <span class="cert-tag gold">低VOCS</span>
                        <span class="cert-tag gold">绿色产品</span>
                        <span class="cert-tag gold">生态产品</span>
                        <span class="cert-tag gold">碳中和</span>
                        <span class="cert-tag gold">碳足迹</span>
                        <span class="cert-tag gold">人体功效学</span>
                        <span class="cert-tag gold">Halal清真</span>
                        <span class="cert-tag gold">Kosher犹太</span>
                        <span class="cert-tag gold">采用国际标准产品认证</span>
                    </div>
                </div>
                <div class="cert-section">
                    <div class="cert-label">🎯 服务认证</div>
                    <div class="cert-tags">
                        <span class="cert-tag green">售后服务</span>
                        <span class="cert-tag green">顾客满意度</span>
                        <span class="cert-tag green">售后完善程度</span>
                    </div>
                </div>
                <div class="cert-section">
                    <div class="cert-label">📝 工商资质</div>
                    <div class="cert-tags">
                        <span class="cert-tag purple">食品生产经营许可证</span>
                        <span class="cert-tag purple">第一类医疗器械经营资质</span>
                        <span class="cert-tag purple">第二类医疗器械经营资质</span>
                    </div>
                </div>
            </div>

            <!-- 卡片5：个人技能 -->
            <div class="card card-skills">
                <div class="card-title"><span class="dot"></span>个人技能</div>
                <div class="skill-category">
                    <div class="skill-cat-label">🔧 质量管理工具</div>
                    <div class="skill-tags">
                        <span class="skill-tag">APQP</span>
                        <span class="skill-tag">MSA</span>
                        <span class="skill-tag">FMEA</span>
                        <span class="skill-tag">SPC</span>
                        <span class="skill-tag">CP</span>
                        <span class="skill-tag">PDCA</span>
                        <span class="skill-tag">CAPA</span>
                        <span class="skill-tag">8D</span>
                        <span class="skill-tag">AQL</span>
                    </div>
                </div>
                <div class="skill-category">
                    <div class="skill-cat-label">📊 体系管理能力</div>
                    <div class="skill-tags">
                        <span class="skill-tag">多体系整合</span>
                        <span class="skill-tag">体系0-1搭建</span>
                        <span class="skill-tag">体系落地推行</span>
                        <span class="skill-tag">团队建设</span>
                        <span class="skill-tag">业务流程优化</span>
                        <span class="skill-tag">风险管理</span>
                    </div>
                </div>
                <div class="skill-category">
                    <div class="skill-cat-label">💻 技术技能</div>
                    <div class="skill-tags">
                        <span class="skill-tag">Python编程</span>
                        <span class="skill-tag">AIGC大模型应用</span>
                        <span class="skill-tag">CNN卷积网络</span>
                        <span class="skill-tag">数据清洗</span>
                        <span class="skill-tag">深度神经网络</span>
                        <span class="skill-tag">数据标注</span>
                    </div>
                </div>
                <div class="skill-category">
                    <div class="skill-cat-label">📜 证书资质</div>
                    <div class="skill-tags">
                        <span class="skill-tag">ISO9001内审员</span>
                        <span class="skill-tag">ISO14001内审员</span>
                        <span class="skill-tag">ISO45001内审员</span>
                        <span class="skill-tag">ISO50001内审员</span>
                        <span class="skill-tag">QMS注册审核员</span>
                        <span class="skill-tag">FSMS注册审核员</span>
                        <span class="skill-tag">EMS注册审核员</span>
                        <span class="skill-tag">OHSMS注册审核员</span>
                        <span class="skill-tag">高级人工智能训练师</span>
                    </div>
                </div>
            </div>

        </div>
    </div>

    <script>
        (function() {
            // ==================== 粒子背景动画（仅保留视觉特效） ====================
            const canvas = document.getElementById('particleCanvas');
            const ctx = canvas.getContext('2d');
            let particles = [];
            const particleCount = 80;
            let mouseX = -1000;
            let mouseY = -1000;
            let animationId;

            function resizeCanvas() {
                canvas.width = window.innerWidth;
                canvas.height = window.innerHeight;
            }
            resizeCanvas();
            window.addEventListener('resize', () => {
                resizeCanvas();
                initParticles();
            });

            class Particle {
                constructor() {
                    this.reset();
                    this.y = Math.random() * canvas.height;
                    this.x = Math.random() * canvas.width;
                }
                reset() {
                    this.x = Math.random() * canvas.width;
                    this.y = Math.random() * canvas.height;
                    this.vx = (Math.random() - 0.5) * 0.5;
                    this.vy = (Math.random() - 0.5) * 0.5;
                    this.radius = Math.random() * 1.6 + 0.6;
                    this.opacity = Math.random() * 0.45 + 0.2;
                }
                update() {
                    const dx = mouseX - this.x;
                    const dy = mouseY - this.y;
                    const distToMouse = Math.sqrt(dx * dx + dy * dy);
                    const influenceRadius = 160;
                    if (distToMouse < influenceRadius && mouseX > 0 && mouseY > 0) {
                        const force = (influenceRadius - distToMouse) / influenceRadius;
                        const angle = Math.atan2(dy, dx);
                        this.vx += Math.cos(angle) * force * 0.025;
                        this.vy += Math.sin(angle) * force * 0.025;
                    }
                    const maxSpeed = 1.0;
                    const speed = Math.sqrt(this.vx * this.vx + this.vy * this.vy);
                    if (speed > maxSpeed) {
                        this.vx = (this.vx / speed) * maxSpeed;
                        this.vy = (this.vy / speed) * maxSpeed;
                    }
                    this.x += this.vx;
                    this.y += this.vy;
                    const margin = 35;
                    if (this.x < -margin) this.x = canvas.width + margin;
                    if (this.x > canvas.width + margin) this.x = -margin;
                    if (this.y < -margin) this.y = canvas.height + margin;
                    if (this.y > canvas.height + margin) this.y = -margin;
                }
                draw(ctx) {
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
                    ctx.fillStyle = `rgba(170,210,255,${this.opacity})`;
                    ctx.fill();
                    ctx.beginPath();
                    ctx.arc(this.x, this.y, this.radius * 2.2, 0, Math.PI * 2);
                    ctx.fillStyle = `rgba(0,190,255,${this.opacity * 0.22})`;
                    ctx.fill();
                }
            }

            function initParticles() {
                particles = [];
                for (let i = 0; i < particleCount; i++) {
                    particles.push(new Particle());
                }
            }
            initParticles();

            function drawConnections() {
                const maxDist = 130;
                for (let i = 0; i < particles.length; i++) {
                    for (let j = i + 1; j < particles.length; j++) {
                        const dx = particles[i].x - particles[j].x;
                        const dy = particles[i].y - particles[j].y;
                        const dist = Math.sqrt(dx * dx + dy * dy);
                        if (dist < maxDist) {
                            const alpha = (1 - dist / maxDist) * 0.18;
                            ctx.beginPath();
                            ctx.moveTo(particles[i].x, particles[i].y);
                            ctx.lineTo(particles[j].x, particles[j].y);
                            ctx.strokeStyle = `rgba(0,180,255,${alpha})`;
                            ctx.lineWidth = 0.5;
                            ctx.stroke();
                        }
                    }
                }
            }

            function animate() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                for (const p of particles) {
                    p.update();
                    p.draw(ctx);
                }
                drawConnections();
                animationId = requestAnimationFrame(animate);
            }
            animate();

            document.addEventListener('mousemove', (e) => {
                mouseX = e.clientX;
                mouseY = e.clientY;
            });
            document.addEventListener('mouseleave', () => { mouseX = -1000; mouseY = -1000; });
            document.addEventListener('touchmove', (e) => {
                if (e.touches.length > 0) { mouseX = e.touches[0].clientX; mouseY = e.touches[0].clientY; }
            }, { passive: true });
            document.addEventListener('touchend', () => { mouseX = -1000; mouseY = -1000; });
        })();
    </script>
</body>
</html>
