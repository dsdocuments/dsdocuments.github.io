
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>U.S. Advanced Manufacturing & Machining Report</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Chosen Palette: Warm neutral background (stone-50), crisp white cards, slate-800 for primary text, and teal-600/teal-700 for data accents and interactive elements. -->
    <!-- Application Structure Plan: A tabbed dashboard interface updated with an AI Insights tab. This allows users to not only view raw data but also use LLM intelligence to interpret that data for specific professional needs like resumes or grant proposals. -->
    <!-- Visualization & Content Choices: Added a dedicated "AI Insight Center" tab. 1. Strategic Summary tool -> Uses Gemini to convert report stats into narrative. 2. Interactive Q&A -> Allows users to probe the data. NO SVG or Mermaid used. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
        body {
            background-color: #fafaf9;
            color: #1e293b;
        }
        .tab-btn.active {
            border-bottom: 4px solid #0f766e;
            color: #0f766e;
            font-weight: 600;
        }
        .tab-content {
            display: none;
            animation: fadeIn 0.4s ease-in-out;
        }
        .tab-content.active {
            display: block;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .loading-spinner {
            border: 3px solid rgba(0, 0, 0, 0.1);
            width: 24px;
            height: 24px;
            border-radius: 50%;
            border-left-color: #0f766e;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="font-sans antialiased min-h-screen flex flex-col">

    <header class="bg-white shadow-sm border-b border-stone-200 py-6 px-4 md:px-8">
        <div class="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
            <div>
                <h1 class="text-2xl md:text-3xl font-bold text-slate-800 tracking-tight">
                    <span class="text-teal-700">&#9881;&#65039;</span> Precision Manufacturing Analysis
                </h1>
                <p class="text-slate-500 mt-1 text-sm md:text-base">Economic & National Significance of Industrial Machining</p>
            </div>
            <div class="text-sm font-medium bg-teal-50 text-teal-800 px-4 py-2 rounded-full border border-teal-100">
                Data Year: 2023 - 2033 Projections
            </div>
        </div>
    </header>

    <main class="flex-grow max-w-6xl mx-auto w-full p-4 md:p-8">
        
        <nav class="flex overflow-x-auto border-b border-stone-300 mb-8 pb-1 scrollbar-hide">
            <button class="tab-btn active px-6 py-3 text-slate-600 hover:text-teal-700 whitespace-nowrap transition-colors" data-target="workforce">
                &#128101; Workforce & Skills Gap
            </button>
            <button class="tab-btn px-6 py-3 text-slate-600 hover:text-teal-700 whitespace-nowrap transition-colors" data-target="market">
                &#128184; Market & Industry Value
            </button>
            <button class="tab-btn px-6 py-3 text-slate-600 hover:text-teal-700 whitespace-nowrap transition-colors" data-target="strategy">
                &#127919; Strategic Importance
            </button>
            <button class="tab-btn px-6 py-3 text-teal-700 whitespace-nowrap transition-colors flex items-center gap-2" data-target="ai-insights">
                <span>✨</span> AI Insights
            </button>
        </nav>

        <!-- Tab: Workforce -->
        <section id="workforce" class="tab-content active">
            <div class="bg-white p-6 md:p-8 rounded-xl shadow-sm border border-stone-100 mb-8">
                <h2 class="text-xl font-semibold text-slate-800 mb-3">The Workforce Engine</h2>
                <p class="text-slate-600 leading-relaxed max-w-4xl">
                    This section details the critical labor metrics surrounding industrial machinery mechanics, maintenance workers, and millwrights. As the manufacturing sector rapidly integrates automation and hybrid processes, understanding these employment figures, wage standards, and the stark contrast in projected growth rates compared to the national average is vital for assessing current and future workforce needs.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <div class="lg:col-span-1 flex flex-col gap-6">
                    <div class="bg-teal-700 text-white p-6 rounded-xl shadow-md transition transform hover:-translate-y-1">
                        <div class="text-teal-100 text-sm font-medium mb-1 uppercase tracking-wider">Total Jobs Held (2023)</div>
                        <div class="text-4xl font-bold mb-2">530,800</div>
                        <div class="text-sm opacity-90">Industrial machinery mechanics, maintenance workers, and millwrights.</div>
                    </div>
                    
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200 transition transform hover:-translate-y-1">
                        <div class="text-slate-500 text-sm font-medium mb-1 uppercase tracking-wider">Median Annual Wage</div>
                        <div class="text-3xl font-bold text-slate-800 mb-2">$61,170</div>
                        <div class="text-sm text-slate-600">Exceeds overall labor force average, reflecting high occupational value.</div>
                    </div>
                </div>

                <div class="lg:col-span-2 bg-white p-6 rounded-xl shadow-sm border border-stone-200">
                    <h3 class="text-lg font-semibold text-slate-800 mb-4 text-center">Projected Job Growth (2023 - 2033)</h3>
                    <div class="chart-container">
                        <canvas id="growthChart"></canvas>
                    </div>
                    <p class="text-center text-sm text-slate-500 mt-4">Data Source: U.S. Bureau of Labor Statistics</p>
                </div>
            </div>
        </section>

        <!-- Tab: Market -->
        <section id="market" class="tab-content">
            <div class="bg-white p-6 md:p-8 rounded-xl shadow-sm border border-stone-100 mb-8">
                <h2 class="text-xl font-semibold text-slate-800 mb-3">Industry Valuation & Expansion</h2>
                <p class="text-slate-600 leading-relaxed max-w-4xl">
                    This section highlights the massive financial footprint and projected economic expansion of the machining sector. By examining the valuation of U.S. machine shop services and the specific exponential growth forecasted for the CNC (Computer Numerical Control) machine tool market, users can comprehend the scale of investment and the critical industrial sectors dependent on these advanced manufacturing capabilities.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200">
                    <h3 class="text-lg font-semibold text-slate-800 mb-4 text-center">Global CNC Machine Tool Market</h3>
                    <div class="chart-container">
                        <canvas id="marketChart"></canvas>
                    </div>
                    <p class="text-center text-sm text-slate-500 mt-4">Projected growth demonstrating sustained future demand.</p>
                </div>

                <div class="flex flex-col gap-6">
                    <div class="bg-stone-800 text-stone-50 p-6 rounded-xl shadow-md">
                        <div class="text-stone-300 text-sm font-medium mb-1 uppercase tracking-wider">U.S. Machine Shop Services</div>
                        <div class="text-4xl font-bold text-teal-400 mb-2">~$44 Billion</div>
                        <div class="text-sm">Estimated industry valuation by 2025.</div>
                    </div>

                    <div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200 flex-grow">
                        <h3 class="text-md font-bold text-slate-800 mb-3 border-b pb-2">Critical Sectors Supported</h3>
                        <ul class="space-y-3 mt-4">
                            <li class="flex items-center text-slate-700">
                                <span class="text-teal-600 mr-3 text-lg">&#9642;</span> Automotive & Electric Vehicles (EVs)
                            </li>
                            <li class="flex items-center text-slate-700">
                                <span class="text-teal-600 mr-3 text-lg">&#9642;</span> Advanced Aerospace Systems
                            </li>
                            <li class="flex items-center text-slate-700">
                                <span class="text-teal-600 mr-3 text-lg">&#9642;</span> National Defense
                            </li>
                            <li class="flex items-center text-slate-700">
                                <span class="text-teal-600 mr-3 text-lg">&#9642;</span> Construction & Heavy Machinery
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tab: Strategy -->
        <section id="strategy" class="tab-content">
            <div class="bg-white p-6 md:p-8 rounded-xl shadow-sm border border-stone-100 mb-8">
                <h2 class="text-xl font-semibold text-slate-800 mb-3">Strategic Resurgence & Technology</h2>
                <p class="text-slate-600 leading-relaxed max-w-4xl">
                    This section synthesizes the qualitative and legislative drivers behind the domestic manufacturing renaissance. It explores how federal investments, reshoring efforts, and the adoption of cutting-edge technologies like AI and hybrid manufacturing are creating an urgent national need for a technologically adept workforce to maintain infrastructure and productive capacity.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-8">
                <div class="bg-white border-t-4 border-teal-600 p-6 rounded-b-xl shadow-sm hover:shadow-md transition">
                    <div class="text-2xl mb-3">&#128220;</div>
                    <h3 class="font-bold text-slate-800 mb-2">Legislative Catalysts</h3>
                    <p class="text-sm text-slate-600">Significant federal investments via the <strong>CHIPS and Science Act</strong> and the <strong>Inflation Reduction Act</strong> are directly fueling a domestic manufacturing resurgence and reshoring efforts.</p>
                </div>

                <div class="bg-white border-t-4 border-teal-600 p-6 rounded-b-xl shadow-sm hover:shadow-md transition">
                    <div class="text-2xl mb-3">&#129302;</div>
                    <h3 class="font-bold text-slate-800 mb-2">Technological Integration</h3>
                    <p class="text-sm text-slate-600">Rapid adoption of Automation, Artificial Intelligence (AI), and Hybrid Manufacturing (HASM) processes necessitates a highly skilled, technology-centered workforce.</p>
                </div>

                <div class="bg-white border-t-4 border-teal-600 p-6 rounded-b-xl shadow-sm hover:shadow-md transition">
                    <div class="text-2xl mb-3">&#128295;</div>
                    <h3 class="font-bold text-slate-800 mb-2">Precision Imperative</h3>
                    <p class="text-sm text-slate-600">Precision machining (CNC and additive techniques) is non-negotiable for producing the complex components required by emerging industries like EVs and national defense.</p>
                </div>
            </div>

            <div class="bg-gradient-to-r from-slate-800 to-slate-700 rounded-xl p-8 text-center text-white shadow-lg relative overflow-hidden">
                <div class="relative z-10">
                    <h3 class="text-lg font-medium text-slate-300 mb-2 uppercase tracking-wide">NIST Aligned Research Finding</h3>
                    <div class="text-5xl md:text-7xl font-extrabold text-teal-400 my-4">20% - 30%</div>
                    <p class="text-xl md:text-2xl font-light">Increase in productivity through the adoption of automation technologies.</p>
                </div>
                <div class="absolute top-0 right-0 opacity-10 text-9xl transform translate-x-8 -translate-y-8 pointer-events-none">&#9881;</div>
            </div>
        </section>

        <!-- Tab: AI Insights -->
        <section id="ai-insights" class="tab-content">
            <div class="bg-white p-6 md:p-8 rounded-xl shadow-sm border border-stone-100 mb-8">
                <h2 class="text-xl font-semibold text-slate-800 mb-3">✨ AI Insight Center</h2>
                <p class="text-slate-600 leading-relaxed max-w-4xl">
                    Utilize advanced machine learning to analyze the manufacturing report data. These tools are designed to help you synthesize strategic justifications for national interest, or evaluate how specific professional skills map to the industry's future.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <!-- Tool 1: Strategic Justification -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200">
                    <h3 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2">
                        <span>📝</span> Strategic Justification Generator
                    </h3>
                    <p class="text-sm text-slate-600 mb-6">Convert the report's complex data into a professional narrative highlighting the national interest of advanced manufacturing.</p>
                    <button id="generateSummaryBtn" class="w-full bg-teal-700 hover:bg-teal-800 text-white font-bold py-3 px-4 rounded-lg transition shadow-md flex items-center justify-center gap-2">
                        ✨ Generate Strategic Narrative
                    </button>
                    <div id="summaryOutput" class="mt-6 hidden">
                        <div class="p-4 bg-teal-50 border border-teal-100 rounded-lg text-slate-800 text-sm leading-relaxed whitespace-pre-wrap"></div>
                    </div>
                </div>

                <!-- Tool 2: Skill-to-Industry Bridge -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-stone-200">
                    <h3 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2">
                        <span>🌉</span> Skills Bridge Evaluator
                    </h3>
                    <p class="text-sm text-slate-600 mb-4">Enter a specific skill or area of expertise to see how it aligns with the trends and growth projected in the report.</p>
                    <input type="text" id="skillInput" placeholder="e.g. Robotics, Data Analysis, CAD Design..." class="w-full p-3 border border-stone-300 rounded-lg mb-4 focus:ring-2 focus:ring-teal-500 focus:outline-none">
                    <button id="evaluateSkillBtn" class="w-full bg-slate-800 hover:bg-slate-900 text-white font-bold py-3 px-4 rounded-lg transition shadow-md flex items-center justify-center gap-2">
                        ✨ Analyze Skill Alignment
                    </button>
                    <div id="skillOutput" class="mt-6 hidden">
                        <div class="p-4 bg-stone-50 border border-stone-200 rounded-lg text-slate-800 text-sm leading-relaxed whitespace-pre-wrap"></div>
                    </div>
                </div>
            </div>

            <!-- Custom Data Query -->
            <div class="mt-8 bg-white p-6 rounded-xl shadow-sm border border-stone-200">
                <h3 class="text-lg font-bold text-slate-800 mb-4 flex items-center gap-2">
                    <span>💬</span> Ask the Report
                </h3>
                <div class="flex gap-2">
                    <input type="text" id="customQueryInput" placeholder="Ask a question about the data..." class="flex-grow p-3 border border-stone-300 rounded-lg focus:ring-2 focus:ring-teal-500 focus:outline-none">
                    <button id="askBtn" class="bg-teal-600 hover:bg-teal-700 text-white font-bold px-6 py-3 rounded-lg transition shadow-md">
                        ✨ Ask
                    </button>
                </div>
                <div id="queryOutput" class="mt-6 hidden">
                    <div class="p-4 bg-slate-50 border border-slate-200 rounded-lg text-slate-800 text-sm italic"></div>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-slate-900 text-slate-400 py-6 text-center text-sm mt-auto">
        <p>Interactive Data Application powered by Advanced Analytics and ✨ Gemini AI</p>
    </footer>

    <!-- Error/Notification Modal -->
    <div id="modalOverlay" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-xl max-w-md w-full p-6 shadow-2xl">
            <h4 id="modalTitle" class="text-xl font-bold text-slate-800 mb-2">Notification</h4>
            <p id="modalBody" class="text-slate-600 mb-6"></p>
            <button id="modalCloseBtn" class="w-full bg-slate-800 text-white font-bold py-2 rounded-lg">Close</button>
        </div>
    </div>

    <script>
        // --- Core Application State & Constants ---
        const apiKey = ""; // Set by runtime
        const tabBtns = document.querySelectorAll('.tab-btn');
        const tabContents = document.querySelectorAll('.tab-content');
        
        let growthChartInstance = null;
        let marketChartInstance = null;

        const reportData = `
            Economic & National Significance:
            - 530,800 jobs in industrial machinery/maintenance in 2023.
            - 15% projected growth (2023-2033), vs 4% national average.
            - Median wage $61,170.
            - U.S. machine shop industry: $44B by 2025.
            - Global CNC market: $91B (2024) to $137B (2031).
            - Key sectors: Aerospace, EV, Defense.
            - Legislation: CHIPS Act, Inflation Reduction Act.
            - NIST alignment: 20-30% productivity increase via automation.
        `;

        // --- Utility Functions ---
        function showModal(title, message) {
            document.getElementById('modalTitle').innerText = title;
            document.getElementById('modalBody').innerText = message;
            document.getElementById('modalOverlay').classList.remove('hidden');
        }

        document.getElementById('modalCloseBtn').onclick = () => {
            document.getElementById('modalOverlay').classList.add('hidden');
        };

        async function callGemini(prompt, systemPrompt = "You are a data analyst expert in U.S. manufacturing.") {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;
            
            const payload = {
                contents: [{ parts: [{ text: prompt }] }],
                systemInstruction: { parts: [{ text: systemPrompt }] }
            };

            let retries = 0;
            const maxRetries = 5;

            while (retries <= maxRetries) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });

                    if (!response.ok) {
                        throw new Error(`API Error: ${response.status}`);
                    }

                    const data = await response.json();
                    return data.candidates?.[0]?.content?.parts?.[0]?.text || "No insights generated.";
                } catch (error) {
                    if (retries === maxRetries) {
                        throw error;
                    }
                    const delay = Math.pow(2, retries) * 1000;
                    await new Promise(res => setTimeout(res, delay));
                    retries++;
                }
            }
        }

        function toggleLoading(btnId, isLoading) {
            const btn = document.getElementById(btnId);
            if (isLoading) {
                btn.disabled = true;
                btn.dataset.originalText = btn.innerHTML;
                btn.innerHTML = `<div class="loading-spinner"></div> Processing...`;
                btn.classList.add('opacity-75', 'cursor-not-allowed');
            } else {
                btn.disabled = false;
                btn.innerHTML = btn.dataset.originalText;
                btn.classList.remove('opacity-75', 'cursor-not-allowed');
            }
        }

        // --- Feature Implementations ---

        // 1. Strategic Summary
        document.getElementById('generateSummaryBtn').addEventListener('click', async () => {
            toggleLoading('generateSummaryBtn', true);
            const output = document.getElementById('summaryOutput');
            const outputText = output.querySelector('div');
            
            try {
                const prompt = `Based on this data: ${reportData}, write a professional executive summary for a 'National Interest Waiver' or 'Strategic Business Proposal'. Focus on how the 15% growth rate and federal legislation make this field critically important to U.S. infrastructure and defense. Keep it around 250 words.`;
                const result = await callGemini(prompt, "You are a strategic policy advisor for U.S. manufacturing.");
                outputText.innerText = result;
                output.classList.remove('hidden');
            } catch (err) {
                showModal("Analysis Error", "Failed to reach AI service. Please check your connection or try again later.");
            } finally {
                toggleLoading('generateSummaryBtn', false);
            }
        });

        // 2. Skill Bridge
        document.getElementById('evaluateSkillBtn').addEventListener('click', async () => {
            const skill = document.getElementById('skillInput').value.trim();
            if (!skill) return showModal("Input Required", "Please enter a skill to evaluate.");

            toggleLoading('evaluateSkillBtn', true);
            const output = document.getElementById('skillOutput');
            const outputText = output.querySelector('div');

            try {
                const prompt = `Data: ${reportData}. User Skill: ${skill}. Analyze how this skill fits into the advanced manufacturing resurgence. Mention specific sectors like EVs, Defense, or CNC technology if relevant. Be encouraging but professional.`;
                const result = await callGemini(prompt, "You are a career consultant for technical industries.");
                outputText.innerText = result;
                output.classList.remove('hidden');
            } catch (err) {
                showModal("Analysis Error", "Failed to generate skill analysis.");
            } finally {
                toggleLoading('evaluateSkillBtn', false);
            }
        });

        // 3. Custom Ask
        document.getElementById('askBtn').addEventListener('click', async () => {
            const query = document.getElementById('customQueryInput').value.trim();
            if (!query) return;

            toggleLoading('askBtn', true);
            const output = document.getElementById('queryOutput');
            const outputText = output.querySelector('div');

            try {
                const prompt = `Report Context: ${reportData}. Question: ${query}. Answer strictly based on the report data if possible, or provide logical industry context.`;
                const result = await callGemini(prompt);
                outputText.innerText = `AI Response: ${result}`;
                output.classList.remove('hidden');
            } catch (err) {
                showModal("Error", "Could not process your question.");
            } finally {
                toggleLoading('askBtn', false);
            }
        });

        // --- Chart & Navigation Logic ---
        function initCharts() {
            const growthCtx = document.getElementById('growthChart');
            if (growthCtx && !growthChartInstance) {
                growthChartInstance = new Chart(growthCtx, {
                    type: 'bar',
                    data: {
                        labels: ['Mechanics & Millwrights', 'National Average (All Occupations)'],
                        datasets: [{
                            label: 'Projected Growth Rate (2023-2033)',
                            data: [15, 4],
                            backgroundColor: ['rgba(15, 118, 110, 0.8)', 'rgba(148, 163, 184, 0.5)'],
                            borderColor: ['rgba(15, 118, 110, 1)', 'rgba(148, 163, 184, 1)'],
                            borderWidth: 1,
                            borderRadius: 4
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: { legend: { display: false } },
                        scales: {
                            y: { beginAtZero: true, title: { display: true, text: 'Percentage (%)' } }
                        }
                    }
                });
            }

            const marketCtx = document.getElementById('marketChart');
            if (marketCtx && !marketChartInstance) {
                marketChartInstance = new Chart(marketCtx, {
                    type: 'bar',
                    data: {
                        labels: ['2024 Valuation', '2031 Projection'],
                        datasets: [{
                            label: 'Market Value (Billions USD)',
                            data: [91, 137],
                            backgroundColor: 'rgba(15, 118, 110, 0.8)',
                            borderColor: 'rgba(15, 118, 110, 1)',
                            borderWidth: 1,
                            borderRadius: 4,
                            barThickness: 60
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: { legend: { display: false } },
                        scales: {
                            y: { beginAtZero: true, title: { display: true, text: 'Billions (USD)' } }
                        }
                    }
                });
            }
        }

        tabBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                tabBtns.forEach(b => b.classList.remove('active'));
                tabContents.forEach(c => c.classList.remove('active'));

                btn.classList.add('active');
                const targetId = btn.getAttribute('data-target');
                document.getElementById(targetId).classList.add('active');

                if (targetId !== 'ai-insights') initCharts();
            });
        });

        window.onload = initCharts;
    </script>
</body>
</html>
