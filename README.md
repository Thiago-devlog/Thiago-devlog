<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thiago dos Anjos | Engenharia de Software</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-main: #0f172a;
            --accent: #8b5cf6;
        }
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #1e293b;
            scroll-behavior: smooth;
        }
        .mono { font-family: 'JetBrains Mono', monospace; }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 320px;
            max-height: 400px;
        }
        .card-shadow {
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            transition: transform 0.2s ease;
        }
        .card-shadow:hover {
            transform: translateY(-4px);
        }
        .nav-link.active {
            border-bottom: 2px solid var(--accent);
            color: var(--accent);
        }
    </style>
</head>
<body class="bg-slate-50">

    <!-- Chosen Palette: Cyberpunk Slate & Violet (Fundo claro para legibilidade, acentos roxos para identidade) -->
    <!-- Application Structure Plan: Dashboard Temático. Escolhi uma estrutura de abas interativas para separar "Competências Consolidadas", "Progresso Acadêmico" e "Visão Open Source". Essa estrutura permite que um recrutador escaneie rapidamente o que você já sabe (Hard Skills) e o que está aprendendo (Roadmap), simulando a transparência de um desenvolvedor moderno. -->
    <!-- Visualization & Content Choices: 
        1. Gráfico de Barras (Chart.js) -> Hard Skills -> Comparar nível de proficiência autoavaliada.
        2. Gráfico de Rosca (Chart.js) -> Roadmap do Semestre -> Informar progresso de aprendizado em tecnologias novas.
        3. Timeline CSS -> Visão Open Source -> Organizar a filosofia de projetos autorais.
        Confirmando: NO SVG/Mermaid utilizado. Interações via Vanilla JS. 
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <!-- Navigation -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-slate-200">
        <div class="max-w-5xl mx-auto px-4 py-3 flex justify-between items-center">
            <span class="mono font-bold text-indigo-600 text-lg">thiago.dev</span>
            <div class="hidden md:flex space-x-8">
                <button onclick="switchTab('overview')" class="nav-link active font-medium hover:text-indigo-600">Visão Geral</button>
                <button onclick="switchTab('skills')" class="nav-link font-medium hover:text-indigo-600">Skills & Tech</button>
                <button onclick="switchTab('roadmap')" class="nav-link font-medium hover:text-indigo-600">Evolução</button>
            </div>
            <a href="mailto:cont.thiagodev@gmail.com" class="bg-indigo-600 text-white px-4 py-2 rounded-lg text-sm font-semibold hover:bg-indigo-700 transition">Contato</a>
        </div>
    </nav>

    <main class="max-w-5xl mx-auto px-4 py-12">
        
        <!-- Tab: Overview -->
        <section id="tab-overview" class="tab-content block">
            <div class="flex flex-col md:flex-row items-center gap-10 mb-16">
                <div class="w-48 h-48 rounded-2xl bg-indigo-100 flex items-center justify-center border-4 border-white shadow-xl overflow-hidden">
                    <div class="text-6xl">👨‍💻</div>
                </div>
                <div class="flex-1 text-center md:text-left">
                    <h1 class="text-4xl font-extrabold text-slate-900 mb-2">Thiago dos Anjos</h1>
                    <p class="text-xl text-indigo-600 font-medium mb-4">Estudante de Engenharia de Software</p>
                    <p class="text-slate-600 leading-relaxed max-w-2xl">
                        Aos 18 anos, foco minha carreira no ecossistema JavaScript e na arquitetura de software escalável. 
                        Atualmente, substituo a experiência comercial por uma dedicação intensa ao **Código Aberto** 
                        e à excelência acadêmica, buscando minha primeira oportunidade como estagiário.
                    </p>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-12">
                <div class="bg-white p-6 rounded-xl card-shadow border border-slate-100">
                    <div class="text-indigo-500 mb-2 font-bold mono uppercase text-xs tracking-widest">Atualmente</div>
                    <div class="text-2xl font-bold">2º Semestre</div>
                    <p class="text-slate-500 text-sm">Engenharia de Software</p>
                </div>
                <div class="bg-white p-6 rounded-xl card-shadow border border-slate-100">
                    <div class="text-indigo-500 mb-2 font-bold mono uppercase text-xs tracking-widest">Foco Técnico</div>
                    <div class="text-2xl font-bold">JavaScript / React</div>
                    <p class="text-slate-500 text-sm">Frontend Development</p>
                </div>
                <div class="bg-white p-6 rounded-xl card-shadow border border-slate-100">
                    <div class="text-indigo-500 mb-2 font-bold mono uppercase text-xs tracking-widest">Disponibilidade</div>
                    <div class="text-2xl font-bold">6h / Diárias</div>
                    <p class="text-slate-500 text-sm">Vagas de Estágio</p>
                </div>
            </div>

            <div class="bg-slate-900 text-white p-8 rounded-2xl shadow-2xl relative overflow-hidden">
                <div class="relative z-10">
                    <h3 class="text-2xl font-bold mb-4">Filosofia Open Source</h3>
                    <p class="text-slate-300 mb-6 leading-relaxed">
                        Acredito que o código público é o currículo mais honesto de um desenvolvedor. 
                        Meus projetos não são apenas exercícios; são soluções pensadas com Git Flow, 
                        Clean Code e documentação técnica para a comunidade.
                    </p>
                    <div class="flex gap-4">
                        <div class="flex items-center gap-2 px-3 py-1 bg-white/10 rounded-full text-xs mono">
                            <span>●</span> Git/GitHub
                        </div>
                        <div class="flex items-center gap-2 px-3 py-1 bg-white/10 rounded-full text-xs mono">
                            <span>●</span> Code Review
                        </div>
                    </div>
                </div>
                <div class="absolute right-0 bottom-0 opacity-10 text-9xl font-black mono pointer-events-none select-none">
                    CODE
                </div>
            </div>
        </section>

        <!-- Tab: Skills -->
        <section id="tab-skills" class="tab-content hidden">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-slate-900 mb-4">Competências Técnicas</h2>
                <p class="text-slate-600 max-w-xl mx-auto">
                    Abaixo, apresento o nível de maturidade em cada tecnologia do meu stack principal, 
                    validado através de projetos práticos e horas de voo em código.
                </p>
            </div>

            <div class="bg-white p-8 rounded-2xl border border-slate-100 shadow-sm mb-12">
                <div class="chart-container">
                    <canvas id="skillsChart"></canvas>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="bg-white p-6 rounded-xl border border-slate-100">
                    <h4 class="font-bold text-slate-800 mb-4 flex items-center gap-2">
                        <span class="w-2 h-2 bg-green-500 rounded-full"></span>
                        Domínio Atual
                    </h4>
                    <ul class="space-y-3 text-slate-600">
                        <li class="flex justify-between"><span>JavaScript (ES6+)</span> <span class="text-xs mono bg-slate-100 px-2 py-1 rounded">Consolidado</span></li>
                        <li class="flex justify-between"><span>CSS3 / Tailwind</span> <span class="text-xs mono bg-slate-100 px-2 py-1 rounded">Consolidado</span></li>
                        <li class="flex justify-between"><span>Git / GitHub Workflows</span> <span class="text-xs mono bg-slate-100 px-2 py-1 rounded">Consolidado</span></li>
                    </ul>
                </div>
                <div class="bg-white p-6 rounded-xl border border-slate-100">
                    <h4 class="font-bold text-slate-800 mb-4 flex items-center gap-2">
                        <span class="w-2 h-2 bg-yellow-500 rounded-full"></span>
                        Ambiente & Infra
                    </h4>
                    <ul class="space-y-3 text-slate-600">
                        <li class="flex justify-between"><span>Linux / Bash</span> <span class="text-xs mono bg-slate-100 px-2 py-1 rounded">Intermediário</span></li>
                        <li class="flex justify-between"><span>Headless OS</span> <span class="text-xs mono bg-slate-100 px-2 py-1 rounded">Intermediário</span></li>
                        <li class="flex justify-between"><span>Arquitetura de PCs</span> <span class="text-xs mono bg-slate-100 px-2 py-1 rounded">Teórico Acadêmico</span></li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Tab: Roadmap -->
        <section id="tab-roadmap" class="tab-content hidden">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-slate-900 mb-4">Evolução do Semestre</h2>
                <p class="text-slate-600 max-w-xl mx-auto">
                    Como engenheiro de software, meu aprendizado é estruturado. Este é o progresso atual das disciplinas e tecnologias que estou integrando ao meu currículo.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="space-y-8">
                    <div class="relative pl-8 border-l-2 border-indigo-200">
                        <div class="absolute -left-[9px] top-0 w-4 h-4 rounded-full bg-indigo-600"></div>
                        <h4 class="font-bold text-lg mb-1">React.js & Ecossistema</h4>
                        <p class="text-slate-500 text-sm mb-4">Criação de interfaces reativas e componentes reutilizáveis.</p>
                        <div class="w-full bg-slate-200 h-2 rounded-full overflow-hidden">
                            <div class="bg-indigo-600 h-full w-[45%]"></div>
                        </div>
                    </div>
                    <div class="relative pl-8 border-l-2 border-indigo-200">
                        <div class="absolute -left-[9px] top-0 w-4 h-4 rounded-full bg-indigo-400"></div>
                        <h4 class="font-bold text-lg mb-1">Estrutura de Dados</h4>
                        <p class="text-slate-500 text-sm mb-4">Listas, Pilhas, Filas e Árvores aplicadas em algoritmos.</p>
                        <div class="w-full bg-slate-200 h-2 rounded-full overflow-hidden">
                            <div class="bg-indigo-400 h-full w-[60%]"></div>
                        </div>
                    </div>
                    <div class="relative pl-8 border-l-2 border-indigo-200">
                        <div class="absolute -left-[9px] top-0 w-4 h-4 rounded-full bg-slate-400"></div>
                        <h4 class="font-bold text-lg mb-1">SQL & Bancos de Dados</h4>
                        <p class="text-slate-500 text-sm mb-4">Modelagem relacional e queries complexas.</p>
                        <div class="w-full bg-slate-200 h-2 rounded-full overflow-hidden">
                            <div class="bg-slate-400 h-full w-[30%]"></div>
                        </div>
                    </div>
                </div>
                <div class="bg-white p-8 rounded-2xl border border-slate-100 shadow-sm">
                    <div class="chart-container">
                        <canvas id="roadmapChart"></canvas>
                    </div>
                    <p class="text-center text-xs text-slate-400 mt-4 mono italic">Distribuição de carga horária semanal por tópico</p>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-white border-t border-slate-200 mt-20 py-10">
        <div class="max-w-5xl mx-auto px-4 text-center">
            <p class="text-slate-500 text-sm mb-4">© 2024 - Desenvolvido por Thiago dos Anjos com JavaScript Vanila e Tailwind.</p>
            <div class="flex justify-center space-x-6">
                <a href="#" class="text-slate-400 hover:text-indigo-600 transition">GitHub</a>
                <a href="#" class="text-slate-400 hover:text-indigo-600 transition">LinkedIn</a>
                <a href="#" class="text-slate-400 hover:text-indigo-600 transition">Email</a>
            </div>
        </div>
    </footer>

    <script>
        // Tab switching logic
        function switchTab(tabId) {
            const contents = document.querySelectorAll('.tab-content');
            const links = document.querySelectorAll('.nav-link');
            
            contents.forEach(content => {
                content.classList.add('hidden');
                content.classList.remove('block');
            });
            
            links.forEach(link => link.classList.remove('active'));
            
            document.getElementById(`tab-${tabId}`).classList.remove('hidden');
            document.getElementById(`tab-${tabId}`).classList.add('block');
            
            event.target.classList.add('active');
            
            // Re-render charts on tab switch to ensure they respect container size
            if(tabId === 'skills') initSkillsChart();
            if(tabId === 'roadmap') initRoadmapChart();
        }

        // Charts Initialization
        let skillsChartInstance = null;
        let roadmapChartInstance = null;

        function initSkillsChart() {
            const ctx = document.getElementById('skillsChart').getContext('2d');
            if (skillsChartInstance) skillsChartInstance.destroy();
            
            skillsChartInstance = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['JavaScript', 'HTML5', 'CSS3', 'Git/GitHub', 'Bootstrap', 'Node.js'],
                    datasets: [{
                        label: 'Nível de Proficiência (%)',
                        data: [85, 95, 90, 80, 70, 40],
                        backgroundColor: 'rgba(99, 102, 241, 0.8)',
                        borderRadius: 8,
                        hoverBackgroundColor: 'rgba(79, 70, 229, 1)'
                    }]
                },
                options: {
                    indexAxis: 'y',
                    maintainAspectRatio: false,
                    responsive: true,
                    plugins: {
                        legend: { display: false }
                    },
                    scales: {
                        x: { beginAtZero: true, max: 100, grid: { display: false } },
                        y: { grid: { display: false } }
                    }
                }
            });
        }

        function initRoadmapChart() {
            const ctx = document.getElementById('roadmapChart').getContext('2d');
            if (roadmapChartInstance) roadmapChartInstance.destroy();

            roadmapChartInstance = new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: ['Front-End (React)', 'Algoritmos/CS', 'Back-End (SQL)', 'Soft Skills'],
                    datasets: [{
                        data: [40, 30, 20, 10],
                        backgroundColor: [
                            '#6366f1',
                            '#818cf8',
                            '#cbd5e1',
                            '#94a3b8'
                        ],
                        borderWidth: 0
                    }]
                },
                options: {
                    maintainAspectRatio: false,
                    responsive: true,
                    plugins: {
                        legend: { position: 'bottom' }
                    },
                    cutout: '70%'
                }
            });
        }

        // Init on load
        window.onload = () => {
            // Initial render not needed as tab is overview, 
            // but we could pre-init if desired.
        };
    </script>
</body>
</html>
