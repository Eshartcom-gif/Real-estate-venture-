
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Capital Build NFT - The Future of Fractionalized Real Estate Development in Ottawa">
    <title>Capital Build | Decentralized Development Protocol</title>
    <style>
        /* =========================================
           CORE VARIABLES & THEME
           ========================================= */
        :root {
            --primary: #00ff9d;
            --primary-dim: rgba(0, 255, 157, 0.1);
            --primary-glow: 0 0 20px rgba(0, 255, 157, 0.4);
            --secondary: #111;
            --surface: #1a1a1a;
            --surface-hover: #252525;
            --border: #333;
            --text-main: #ffffff;
            --text-muted: #888;
            --danger: #ff4444;
            --success: #00cc66;
            --font-main: 'Inter', system-ui, -apple-system, sans-serif;
            --font-mono: 'Courier New', monospace;
            --max-width: 1400px;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; scroll-behavior: smooth; }
        
        body {
            background-color: #050505;
            color: var(--text-main);
            font-family: var(--font-main);
            line-height: 1.7;
            overflow-x: hidden;
        }

        /* =========================================
           UTILITIES & ANIMATIONS
           ========================================= */
        .container { max-width: var(--max-width); margin: 0 auto; padding: 0 2rem; }
        .grid { display: grid; gap: 2rem; }
        .grid-2 { grid-template-columns: repeat(2, 1fr); }
        .grid-3 { grid-template-columns: repeat(3, 1fr); }
        .grid-4 { grid-template-columns: repeat(4, 1fr); }
        .flex { display: flex; align-items: center; }
        .flex-col { flex-direction: column; }
        .justify-between { justify-content: space-between; }
        .text-primary { color: var(--primary); }
        .text-mono { font-family: var(--font-mono); }
        .hidden { display: none !important; }
        .blur-bg { backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px); }
        
        @keyframes pulse { 0% { opacity: 0.8; } 50% { opacity: 1; text-shadow: var(--primary-glow); } 100% { opacity: 0.8; } }
        @keyframes slideUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        
        .animate-up { animation: slideUp 0.6s ease-out forwards; }
        .delay-1 { animation-delay: 0.1s; }
        .delay-2 { animation-delay: 0.2s; }
        .delay-3 { animation-delay: 0.3s; }

        /* =========================================
           UI COMPONENTS
           ========================================= */
        /* Buttons */
        .btn {
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
            border: 1px solid transparent;
        }
        .btn-primary {
            background: var(--primary);
            color: #000;
            box-shadow: 0 0 15px rgba(0,255,157,0.2);
        }
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 25px rgba(0,255,157,0.5);
        }
        .btn-outline {
            background: transparent;
            border: 1px solid var(--primary);
            color: var(--primary);
        }
        .btn-outline:hover {
            background: var(--primary-dim);
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(5, 5, 5, 0.9);
            border-bottom: 1px solid var(--border);
            height: 80px;
        }
        .nav-inner {
            height: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .logo span { color: var(--primary); }
        .nav-links button {
            background: none;
            border: none;
            color: var(--text-muted);
            margin-left: 2rem;
            cursor: pointer;
            font-size: 0.9rem;
            transition: color 0.3s;
        }
        .nav-links button:hover, .nav-links button.active { color: var(--text-main); }

        /* Sections */
        section { padding: 6rem 0; border-bottom: 1px solid #111; }
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, #fff, #888);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .section-subtitle {
            color: var(--primary);
            text-transform: uppercase;
            letter-spacing: 2px;
            font-size: 0.8rem;
            margin-bottom: 1rem;
            display: block;
        }

        /* Cards */
        .card {
            background: var(--surface);
            border: 1px solid var(--border);
            padding: 2rem;
            border-radius: 8px;
            transition: border-color 0.3s;
        }
        .card:hover { border-color: var(--primary); }
        .card-header { border-bottom: 1px solid var(--border); padding-bottom: 1rem; margin-bottom: 1rem; }
        
        /* Tables */
        .data-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.9rem;
        }
        .data-table th { text-align: left; color: var(--text-muted); padding: 1rem; border-bottom: 1px solid var(--border); }
        .data-table td { padding: 1rem; border-bottom: 1px solid #222; }
        .data-table tr:hover { background: var(--surface-hover); }

        /* Dashboard Specifics */
        .dashboard-grid {
            display: grid;
            grid-template-columns: 250px 1fr;
            min-height: 100vh;
            margin-top: 80px;
        }
        .sidebar {
            background: var(--surface);
            border-right: 1px solid var(--border);
            padding: 2rem;
            position: fixed;
            width: 250px;
            height: 100%;
        }
        .sidebar-item {
            display: block;
            padding: 1rem;
            color: var(--text-muted);
            cursor: pointer;
            border-radius: 4px;
            margin-bottom: 0.5rem;
        }
        .sidebar-item:hover, .sidebar-item.active {
            background: var(--primary-dim);
            color: var(--primary);
        }
        .main-content {
            margin-left: 250px;
            padding: 3rem;
            width: calc(100% - 250px);
        }

        /* Modal */
        .modal-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.8);
            display: flex; justify-content: center; align-items: center;
            z-index: 2000;
        }
        .modal-content {
            background: var(--surface);
            padding: 3rem;
            border: 1px solid var(--primary);
            max-width: 500px;
            width: 90%;
            text-align: center;
            border-radius: 10px;
            box-shadow: 0 0 50px rgba(0,255,157,0.2);
        }
        
        /* Loading Bar */
        .progress-track {
            background: #333; height: 10px; width: 100%; border-radius: 5px; overflow: hidden;
            margin: 2rem 0;
        }
        .progress-fill {
            height: 100%; background: var(--primary); width: 0%;
            transition: width 1s ease-out;
        }

        /* ROI Calculator */
        .calc-input {
            width: 100%; background: #000; border: 1px solid #333; color: #fff;
            padding: 1rem; margin-bottom: 1rem; border-radius: 4px;
        }
        .stat-box {
            background: #000; padding: 1.5rem; border-radius: 4px; text-align: center;
        }
        .stat-val { font-size: 2rem; color: var(--primary); font-weight: bold; }

        @media(max-width: 1000px) {
            .grid-2, .grid-3, .grid-4 { grid-template-columns: 1fr; }
            .dashboard-grid { display: block; }
            .sidebar { display: none; } /* Simplified for mobile */
            .main-content { margin-left: 0; width: 100%; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="container nav-inner">
            <div class="logo">
                <svg width="30" height="30" viewBox="0 0 100 100" fill="none" stroke="#00ff9d" stroke-width="8">
                    <rect x="20" y="20" width="60" height="60" />
                    <line x1="20" y1="20" x2="80" y2="80" />
                    <line x1="80" y1="20" x2="20" y2="80" />
                </svg>
                CAPITAL<span>BUILD</span>
            </div>
            <div class="nav-links" id="public-nav">
                <button onclick="setView('home')" class="active">Protocol</button>
                <button onclick="setView('thesis')">Ottawa Thesis</button>
                <button onclick="setView('portfolio')">Portfolio</button>
                <button onclick="setView('governance')">Governance</button>
            </div>
            <button class="btn btn-primary" id="connect-btn" onclick="connectWallet()">Connect Wallet</button>
        </div>
    </nav>

    <div id="public-view">
        
        <header style="padding-top: 150px; padding-bottom: 100px; text-align: center; background: radial-gradient(circle at center, #1a1a1a 0%, #050505 70%);">
            <div class="container animate-up">
                <span class="section-subtitle">The First DAO-Operated Developer in Canada</span>
                <h1 style="font-size: 4.5rem; line-height: 1.1; margin-bottom: 2rem;">Build Houses.<br><span class="text-primary">Fractionalize Profits.</span></h1>
                <p style="font-size: 1.2rem; color: #aaa; max-width: 800px; margin: 0 auto 3rem;">
                    We are raising <strong>$1.2 Million USDC</strong> to exploit the "Bill 23" zoning incentives in Ottawa, Ontario. 
                    Holders receive <strong>18% of all construction profits</strong> via automated Smart Contracts.
                </p>
                <div class="flex" style="justify-content: center; gap: 1rem;">
                    <button class="btn btn-primary" onclick="window.scrollTo(0, 800)">Read The Prospectus</button>
                    <button class="btn btn-outline" onclick="setView('calculator')">Simulate ROI</button>
                </div>
                
                <div class="grid-4" style="margin-top: 5rem; text-align: left;">
                    <div class="card">
                        <div class="text-mono text-muted">RAISE TARGET</div>
                        <div class="text-primary" style="font-size: 2rem; font-weight: bold;">$1,200,000</div>
                    </div>
                    <div class="card">
                        <div class="text-mono text-muted">APY (PROJ)</div>
                        <div class="text-primary" style="font-size: 2rem; font-weight: bold;">24.5%</div>
                    </div>
                    <div class="card">
                        <div class="text-mono text-muted">LOCATION</div>
                        <div style="font-size: 1.5rem; font-weight: bold;">Ottawa, ON</div>
                    </div>
                    <div class="card">
                        <div class="text-mono text-muted">STRATEGY</div>
                        <div style="font-size: 1.5rem; font-weight: bold;">Build-to-Sell</div>
                    </div>
                </div>
            </div>
        </header>

        <section id="thesis" class="container">
            <div class="grid-2">
                <div>
                    <span class="section-subtitle">THE OPPORTUNITY</span>
                    <h2 class="section-title">Why Ottawa? Why Now?</h2>
                    <p style="margin-bottom: 1.5rem;">Ottawa is currently undergoing the most significant zoning overhaul in 50 years. The introduction of <strong>Bill 23 (More Homes Built Faster Act)</strong> and the <strong>Housing Accelerator Fund (HAF)</strong> has created a "Golden Window" for agile developers.</p>
                    
                    <div class="card" style="margin-bottom: 1rem; border-left: 4px solid var(--primary);">
                        <h3>1. As-of-Right Zoning (R4)</h3>
                        <p class="text-muted">We can now build 4-unit multiplexes on standard R1 lots without seeking variance approvals. This cuts our pre-construction timeline from 14 months to 3 months.</p>
                    </div>

                    <div class="card" style="margin-bottom: 1rem; border-left: 4px solid var(--primary);">
                        <h3>2. Development Charge Waivers</h3>
                        <p class="text-muted">For affordable intensification, the City of Ottawa is waiving nearly $40,000 per door in fees. On a 4-unit build, this is $160,000 in instant equity.</p>
                    </div>
                </div>
                <div>
                    <div class="card" style="background: #111; height: 100%;">
                        <h3 style="border-bottom: 1px solid #333; padding-bottom: 1rem; margin-bottom: 1rem;">Fund Allocation ($1.2M)</h3>
                        <table class="data-table">
                            <tr>
                                <td>Land Acquisition (Equity)</td>
                                <td class="text-primary text-mono text-right">$800,000</td>
                            </tr>
                            <tr>
                                <td>Soft Costs (Arch/Eng)</td>
                                <td class="text-primary text-mono text-right">$120,000</td>
                            </tr>
                            <tr>
                                <td>Permits & Legal</td>
                                <td class="text-primary text-mono text-right">$80,000</td>
                            </tr>
                            <tr>
                                <td>Construction Float</td>
                                <td class="text-primary text-mono text-right">$200,000</td>
                            </tr>
                            <tr>
                                <td><strong>TOTAL</strong></td>
                                <td class="text-primary text-mono text-right"><strong>$1,200,000</strong></td>
                            </tr>
                        </table>
                        
                        <div style="margin-top: 2rem;">
                            <h3 style="font-size: 0.9rem; color: #888; text-transform: uppercase;">Profit Waterfall (Smart Contract)</h3>
                            <div style="display: flex; height: 40px; width: 100%; border-radius: 4px; overflow: hidden; margin-top: 0.5rem;">
                                <div style="width: 62%; background: #00ff9d; display: grid; place-items: center; color: #000; font-weight: bold; font-size: 0.8rem;">62% GROWTH</div>
                                <div style="width: 18%; background: #00cc66; display: grid; place-items: center; color: #fff; font-weight: bold; font-size: 0.8rem;">18% YOU</div>
                                <div style="width: 10%; background: #008844; display: grid; place-items: center; color: #ccc; font-size: 0.7rem;">10% TRY</div>
                                <div style="width: 10%; background: #005522; display: grid; place-items: center; color: #ccc; font-size: 0.7rem;">10% LAB</div>
                            </div>
                            <p style="font-size: 0.8rem; color: #666; margin-top: 0.5rem;">*Smart Contract Address: 0x71C...39B2 (Audited by CertiK)</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="portfolio" style="background: #111;">
            <div class="container">
                <span class="section-subtitle">TARGET ACQUISITIONS</span>
                <h2 class="section-title">The Initial Portfolio</h2>
                <div class="grid-3">
                    
                    <div class="card animate-up delay-1">
                        <div style="height: 200px; background: #222; margin: -2rem -2rem 1rem -2rem; display: flex; align-items: center; justify-content: center; color: #555;">
                            [SATELLITE IMAGE: NEPEAN]
                        </div>
                        <div class="flex justify-between" style="margin-bottom: 0.5rem;">
                            <span style="background: var(--primary-dim); color: var(--primary); padding: 2px 8px; font-size: 0.8rem; border-radius: 4px;">NEGOTIATION PHASE</span>
                            <span class="text-mono">Project A-1</span>
                        </div>
                        <h3>1422 Merivale Road Area</h3>
                        <p class="text-muted" style="font-size: 0.9rem;">Deep lot suitable for front/back semi-detached split.</p>
                        <div class="grid-2" style="margin-top: 1rem; border-top: 1px solid #333; padding-top: 1rem;">
                            <div>
                                <small class="text-muted">Land Cost</small>
                                <div class="text-mono">$420,000</div>
                            </div>
                            <div>
                                <small class="text-muted">Proj. Exit</small>
                                <div class="text-mono">$1,150,000</div>
                            </div>
                        </div>
                    </div>

                    <div class="card animate-up delay-2">
                        <div style="height: 200px; background: #222; margin: -2rem -2rem 1rem -2rem; display: flex; align-items: center; justify-content: center; color: #555;">
                            [SATELLITE IMAGE: VANIER]
                        </div>
                        <div class="flex justify-between" style="margin-bottom: 0.5rem;">
                            <span style="background: rgba(255, 165, 0, 0.2); color: orange; padding: 2px 8px; font-size: 0.8rem; border-radius: 4px;">SCOUTING</span>
                            <span class="text-mono">Project B-4</span>
                        </div>
                        <h3>Montreal Road Corridor</h3>
                        <p class="text-muted" style="font-size: 0.9rem;">High density R5 zoning. Potential for 6-unit low rise.</p>
                        <div class="grid-2" style="margin-top: 1rem; border-top: 1px solid #333; padding-top: 1rem;">
                            <div>
                                <small class="text-muted">Land Cost</small>
                                <div class="text-mono">$550,000</div>
                            </div>
                            <div>
                                <small class="text-muted">Proj. Exit</small>
                                <div class="text-mono">$1,800,000</div>
                            </div>
                        </div>
                    </div>

                    <div class="card animate-up delay-3">
                        <div style="height: 200px; background: #222; margin: -2rem -2rem 1rem -2rem; display: flex; align-items: center; justify-content: center; color: #555;">
                            [SATELLITE IMAGE: KANATA]
                        </div>
                        <div class="flex justify-between" style="margin-bottom: 0.5rem;">
                            <span style="background: rgba(255, 68, 68, 0.2); color: #ff6666; padding: 2px 8px; font-size: 0.8rem; border-radius: 4px;">LOCKED</span>
                            <span class="text-mono">Project C-2</span>
                        </div>
                        <h3>March Road Infill</h3>
                        <p class="text-muted" style="font-size: 0.9rem;">Tech park proximity. High rental demand for tech workers.</p>
                        <div class="grid-2" style="margin-top: 1rem; border-top: 1px solid #333; padding-top: 1rem;">
                            <div>
                                <small class="text-muted">Land Cost</small>
                                <div class="text-mono">$380,000</div>
                            </div>
                            <div>
                                <small class="text-muted">Proj. Exit</small>
                                <div class="text-mono">$950,000</div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <section id="calculator" class="container">
            <span class="section-subtitle">PROJECT YOUR RETURNS</span>
            <h2 class="section-title">The "Flywheel" Calculator</h2>
            <p>Our model reinvests 62% of profits to buy bigger land. See how your NFT value grows over 5 years.</p>
            
            <div class="grid-2" style="align-items: center;">
                <div class="card">
                    <label class="text-muted">Initial Investment ($USD)</label>
                    <input type="number" id="calc-amount" class="calc-input" value="5000" oninput="calculateReturns()">
                    
                    <label class="text-muted">Project Success Rate (Conservative to Aggressive)</label>
                    <input type="range" id="calc-rate" class="calc-input" min="15" max="35" value="20" oninput="calculateReturns()">
                    <div class="flex justify-between text-muted" style="font-size: 0.8rem;">
                        <span>15% (Recession)</span>
                        <span id="rate-display">20% (Base)</span>
                        <span>35% (Boom)</span>
                    </div>

                    <button class="btn btn-primary" style="width: 100%; margin-top: 2rem;" onclick="calculateReturns()">Update Projection</button>
                </div>

                <div class="grid-2">
                    <div class="stat-box">
                        <div class="text-muted" style="font-size: 0.9rem;">Year 1 Payout</div>
                        <div class="stat-val" id="res-y1">$900</div>
                    </div>
                    <div class="stat-box">
                        <div class="text-muted" style="font-size: 0.9rem;">Year 3 Payout</div>
                        <div class="stat-val" id="res-y3">$2,140</div>
                    </div>
                    <div class="stat-box" style="grid-column: span 2; border: 1px solid var(--primary);">
                        <div class="text-muted" style="font-size: 0.9rem;">Total 5-Year Value</div>
                        <div class="stat-val" id="res-total" style="font-size: 3rem;">$12,450</div>
                        <p class="text-muted" style="font-size: 0.8rem;">Based on compounding reinvestment of the 62% company share.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="container" style="color: #aaa; font-size: 0.9rem;">
            <h3 style="color: #fff; margin-bottom: 1rem;">Risk Disclosure & Legal Disclaimer</h3>
            <p><strong>1. Nature of the Token:</strong> The "Capital Build NFT" is a governance and reward token utilized within the Capital Build DAO. It represents a membership interest in the Decentralized Autonomous Organization, not a direct deed to real estate property. The underlying real estate assets are held by "Capital Build Dev Corp," a Canadian federally registered corporation, which is contractually obligated to the DAO via legal binding agreements.</p>
            <p><strong>2. Construction Risk:</strong> Construction projects in Ottawa are subject to seasonal delays, particularly in winter months (Nov-March). While we utilize modular components to mitigate this, extreme weather can delay foundation pouring. Furthermore, labor strikes (e.g., LIUNA) or material shortages can impact delivery timelines.</p>
            <p><strong>3. Market Risk:</strong> The Ottawa real estate market has historically been stable due to the high volume of government employment. However, interest rate fluctuations by the Bank of Canada affect mortgage affordability for end-buyers. If rates exceed 6%, we may pivot from a "Build-to-Sell" to a "Build-to-Rent" model, which would change the payout schedule from lump-sum to monthly dividends.</p>
            <p><strong>4. Regulatory Compliance:</strong> This project is structured to comply with OSC (Ontario Securities Commission) regulations regarding utility tokens. Users from the United States or sanctioned countries are prohibited from minting.</p>
        </section>
    </div>

    <div id="dashboard-view" class="hidden">
        <div class="dashboard-grid">
            <aside class="sidebar">
                <div style="margin-bottom: 2rem; padding-bottom: 1rem; border-bottom: 1px solid #333;">
                    <div class="text-muted" style="font-size: 0.8rem;">CONNECTED WALLET</div>
                    <div class="text-primary text-mono" id="wallet-address">0x...</div>
                </div>
                
                <a class="sidebar-item active" onclick="switchDash('dash-overview')">Overview</a>
                <a class="sidebar-item" onclick="switchDash('dash-assets')">My Assets</a>
                <a class="sidebar-item" onclick="switchDash('dash-governance')">Governance (DAO)</a>
                <a class="sidebar-item" onclick="switchDash('dash-payouts')">Claim Payouts</a>
                <a class="sidebar-item" onclick="switchDash('dash-docs')">Legal Docs</a>
                
                <div style="margin-top: auto; padding-top: 2rem;">
                    <button class="btn btn-outline" style="width: 100%;" onclick="disconnectWallet()">Disconnect</button>
                </div>
            </aside>

            <main class="main-content">
                
                <div id="dash-overview" class="dash-section">
                    <h2 style="margin-bottom: 2rem;">Investor Dashboard</h2>
                    
                    <div class="grid-3">
                        <div class="card">
                            <div class="text-muted">TOTAL EARNINGS</div>
                            <div class="stat-val">$0.00</div>
                        </div>
                        <div class="card">
                            <div class="text-muted">NFTS HELD</div>
                            <div class="stat-val">0</div>
                        </div>
                        <div class="card">
                            <div class="text-muted">DAO VOTING POWER</div>
                            <div class="stat-val">0 VP</div>
                        </div>
                    </div>

                    <h3 style="margin-top: 3rem; margin-bottom: 1rem;">Live Project Status</h3>
                    <div class="card">
                        <div class="flex justify-between" style="margin-bottom: 1rem;">
                            <strong>Project A-1 (Nepean)</strong>
                            <span class="text-primary">On Schedule</span>
                        </div>
                        <div class="progress-track">
                            <div class="progress-fill" style="width: 15%;"></div>
                        </div>
                        <div class="flex justify-between text-muted" style="font-size: 0.8rem;">
                            <span>Acquisition</span>
                            <span>Permits</span>
                            <span>Foundation</span>
                            <span>Framing</span>
                            <span>Finishing</span>
                            <span>Sale</span>
                        </div>
                    </div>
                </div>

                <div id="dash-governance" class="dash-section hidden">
                    <h2 style="margin-bottom: 2rem;">Active Proposals</h2>
                    <div class="card" style="margin-bottom: 1rem;">
                        <div class="flex justify-between">
                            <h3>PROP-001: Approve Auditor</h3>
                            <span style="color: var(--primary);">ACTIVE</span>
                        </div>
                        <p class="text-muted">Proposal to hire KPMG Ottawa for Q3 financial auditing.</p>
                        <div class="grid-2" style="gap: 1rem; margin-top: 1rem;">
                            <button class="btn btn-primary" style="opacity: 0.5; cursor: not-allowed;">Vote FOR (Needs NFT)</button>
                            <button class="btn btn-outline" style="opacity: 0.5; cursor: not-allowed;">Vote AGAINST</button>
                        </div>
                    </div>
                </div>

                <div id="dash-payouts" class="dash-section hidden">
                    <h2 style="margin-bottom: 2rem;">Claimable Rewards</h2>
                    <div class="card" style="text-align: center; padding: 4rem;">
                        <div style="font-size: 3rem; color: #333; margin-bottom: 1rem;">$0.00 USDC</div>
                        <p class="text-muted">No rewards available. Project A-1 sale estimated Q4 2026.</p>
                        <button class="btn btn-primary" disabled style="margin-top: 1rem; background: #333; color: #666; cursor: not-allowed;">Claim</button>
                    </div>
                </div>

            </main>
        </div>
    </div>

    <div id="loading-modal" class="modal-overlay hidden">
        <div class="modal-content">
            <h3 class="animate-pulse">Connecting to Ethereum Mainnet...</h3>
            <div class="progress-track" style="background: #222;">
                <div class="progress-fill" id="modal-bar"></div>
            </div>
            <p class="text-mono text-muted">Verifying wallet signature...</p>
        </div>
    </div>

    <script>
        /* =========================================
           LOGIC & INTERACTIVITY
           ========================================= */

        // VIEW ROUTER
        function setView(viewId) {
            // Scroll to section if on public view
            const el = document.getElementById(viewId);
            if(el) el.scrollIntoView();
        }

        // WALLET CONNECTION SIMULATION
        function connectWallet() {
            const modal = document.getElementById('loading-modal');
            const bar = document.getElementById('modal-bar');
            
            modal.classList.remove('hidden');
            
            // Simulate network delay
            setTimeout(() => { bar.style.width = "40%"; }, 100);
            setTimeout(() => { bar.style.width = "80%"; }, 800);
            setTimeout(() => { 
                bar.style.width = "100%"; 
                finishConnection();
            }, 1500);
        }

        function finishConnection() {
            document.getElementById('loading-modal').classList.add('hidden');
            document.getElementById('public-view').classList.add('hidden');
            document.getElementById('public-nav').classList.add('hidden');
            document.getElementById('connect-btn').style.display = 'none';
            document.getElementById('dashboard-view').classList.remove('hidden');
            
            // Generate random wallet
            const randomAddr = "0x71" + Math.random().toString(16).substr(2, 6) + "..." + Math.random().toString(16).substr(2, 4);
            document.getElementById('wallet-address').innerText = randomAddr.toUpperCase();
        }

        function disconnectWallet() {
            location.reload(); // Simple reset
        }

        // DASHBOARD TABS
        function switchDash(tabId) {
            // Hide all dash sections
            document.querySelectorAll('.dash-section').forEach(d => d.classList.add('hidden'));
            // Remove active sidebar
            document.querySelectorAll('.sidebar-item').forEach(i => i.classList.remove('active'));
            
            // Show target
            document.getElementById(tabId).classList.remove('hidden');
            // Highlight sidebar (approximate matching)
            event.target.classList.add('active');
        }

        // ROI CALCULATOR LOGIC
        function calculateReturns() {
            const principal = parseFloat(document.getElementById('calc-amount').value);
            const ratePercent = parseFloat(document.getElementById('calc-rate').value);
            
            // Display rate text
            let rateText = "Base";
            if(ratePercent < 18) rateText = "Bearish";
            if(ratePercent > 25) rateText = "Bullish";
            document.getElementById('rate-display').innerText = `${ratePercent}% (${rateText})`;

            // The Logic: 
            // 18% of profit goes to holder.
            // 62% of profit goes to company equity (increasing future project size).
            // We simulate a project cycle every 12 months.
            
            let currentEquity = principal; // The value of the company backing the NFT
            let yearlyPayout = 0;
            let totalPayouts = 0;

            // Year 1
            let totalProfit = currentEquity * (ratePercent / 100);
            let holderShare = totalProfit * 0.18; 
            let companyReinvest = totalProfit * 0.62;
            
            document.getElementById('res-y1').innerText = "$" + Math.round(holderShare).toLocaleString();

            // Simulate growth loop for 5 years
            for(let i=1; i<=5; i++) {
                totalProfit = currentEquity * (ratePercent / 100);
                holderShare = totalProfit * 0.18;
                companyReinvest = totalProfit * 0.62;
                
                totalPayouts += holderShare;
                currentEquity += companyReinvest; // Compounding the base

                if(i === 3) {
                     document.getElementById('res-y3').innerText = "$" + Math.round(holderShare).toLocaleString();
                }
            }

            // Total Value = Total Cash Payouts + The Final Value of the NFT share (Equity)
            // Or just total payouts for income focus? Let's do Total Value (Asset + Cash)
            let totalValue = totalPayouts + currentEquity;
            
            document.getElementById('res-total').innerText = "$" + Math.round(totalValue).toLocaleString();
        }

        // Initialize Calc on Load
        calculateReturns();

    </script>
</body>
</html>
