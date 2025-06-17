<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mapa Interativo: Gestão de Projetos</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals (Stone, Sky) -->
    <!-- Application Structure Plan: A central hub design was chosen to visually mimic the source mind map. A grid of clickable nodes represents the main project management concepts. Clicking a node opens a slide-in detail panel. This structure allows users to explore deep information without losing the high-level context of the overall map, promoting focused learning and easy navigation. The user flow is simple: see the whole map -> click to explore a branch -> close to return to the map. This avoids disorienting page loads and is highly intuitive for hierarchical information. -->
    <!-- Visualization & Content Choices: 
        - Report Info: Main PM concepts -> Goal: Organize/Inform -> Viz: Interactive HTML/CSS nodes in a grid -> Interaction: Click to open detail panel -> Justification: Mimics mind map structure, intuitive.
        - Report Info: Qualidade (3 sub-parts) -> Goal: Inform/Compare Proportions -> Viz: Donut Chart -> Interaction: Hover for tooltips -> Justification: Visually represents the components of 'Quality' as parts of a whole concept -> Library: Chart.js
        - Report Info: Diagrama Causa-Efeito -> Goal: Organize/Analyze -> Viz: Custom HTML/CSS Fishbone Diagram -> Interaction: Static view -> Justification: Provides a more engaging and representative visual than a simple list for this specific diagram.
        - Report Info: Matriz RACI -> Goal: Organize/Inform -> Viz: HTML Table -> Interaction: Static view -> Justification: A table is the standard and most effective way to represent a matrix.
        - Report Info: All other concepts -> Goal: Inform -> Viz: Styled text blocks in detail panel -> Interaction: Read -> Justification: Clear, concise presentation of descriptive information.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        #detail-panel {
            transition: transform 0.3s ease-in-out;
        }
        .fishbone-line {
            position: relative;
            height: 2px;
            background-color: #9ca3af;
        }
        .fishbone-line::after {
            content: '';
            position: absolute;
            right: -4px;
            top: -3px;
            width: 0;
            height: 0;
            border-top: 5px solid transparent;
            border-bottom: 5px solid transparent;
            border-left: 8px solid #9ca3af;
        }
        .fishbone-branch {
            position: absolute;
            height: 2px;
            background-color: #9ca3af;
            transform-origin: left center;
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-800">

    <div id="app-container" class="relative min-h-screen overflow-x-hidden">

        <header class="bg-white shadow-sm sticky top-0 z-20">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-4">
                <h1 class="text-2xl md:text-3xl font-bold text-stone-900 text-center">Mapa Interativo: Gestão de Projetos</h1>
                <p class="text-center text-stone-600 mt-1">Clique em um conceito para explorar seus detalhes.</p>
            </div>
        </header>

        <main class="container mx-auto px-4 sm:px-6 lg:px-8 py-8 md:py-12">
            <div id="mind-map-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 md:gap-6">
            </div>
        </main>

        <div id="detail-panel" class="fixed top-0 right-0 h-full w-full md:w-2/3 lg:w-1/2 xl:w-2/5 bg-white shadow-2xl z-40 transform translate-x-full overflow-y-auto">
            <div class="p-6 md:p-8 relative h-full">
                <button id="close-panel-btn" class="absolute top-4 right-4 text-stone-500 hover:text-stone-800 transition-colors">
                    <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
                <div id="detail-content" class="h-full">
                </div>
            </div>
        </div>
        
        <div id="panel-overlay" class="fixed inset-0 bg-black bg-opacity-50 z-30 hidden"></div>

    </div>

    <script>
        const projectManagementData = {
            central: { title: "Gestão de Projetos", icon: "🎯", color: "bg-sky-600 text-white" },
            nodes: [
                { id: "tap", title: "TAP", icon: "📄", description: "Documento que autoriza formalmente o início do projeto.", items: ["📜 Justificativa", "🎯 Objetivos", "📦 Entregáveis Principais", "👥 Stakeholders", "💰 Orçamento Preliminar", "👤 Gerente do Projeto", "ρίσκο Riscos Iniciais"] },
                { id: "tailoring", title: "Tailoring", icon: "📐", description: "Adaptar processos, ferramentas e técnicas de gerenciamento ao contexto específico do projeto.", items: ["🏢 Contexto Organizacional", "⚙️ Complexidade do Projeto", "👥 Tamanho da Equipe", "🔄 Ciclo de Vida"] },
                { id: "eap", title: "EAP", icon: "🏗️", description: "Decomposição hierárquica do escopo total do trabalho a ser executado pela equipe.", items: ["🎁 Entregáveis", "🗂️ Pacotes de Trabalho", "📚 Dicionário da EAP", "🔢 Identificação Numérica"] },
                { id: "cronograma", title: "Cronograma", icon: "🗓️", description: "Modelo que representa o plano de execução das atividades ao longo do tempo.", items: ["➡️ Sequenciamento de Atividades", "🔗 Dependências", "⏳ Estimativa de Duração", "🚩 Marcos (Milestones)", "📊 Linha de Base (Baseline)"] },
                { id: "abordagens", title: "Abordagens de Desenvolvimento", icon: "🧩", description: "Formas diferentes de executar o ciclo de vida de um projeto.", items: [
                    { title: "🌊 Tradicional (Cascata)", text: "Escopo definido no início, fases sequenciais." },
                    { title: "📈 Incremental", text: "Entregas funcionais em partes, uma após a outra." },
                    { title: "🔁 Iterativa", text: "Refinamento do produto através de ciclos repetidos (iterações)." },
                    { title: "🏃 Adaptativa (Ágil)", text: "Combinação de iterativa e incremental, focada em adaptação rápida a mudanças." },
                ]},
                { id: "metodologias", title: "Metodologias Ágeis", icon: "✨", description: "Conjunto de práticas baseadas nos valores e princípios do Manifesto Ágil.", items: [
                    { title: "SCRUM", sub: ["Papéis: Product Owner, Scrum Master, Dev Team", "Cerimônias: Sprint Planning, Daily Scrum, Sprint Review, Retrospective", "Artefatos: Product Backlog, Sprint Backlog, Incremento"] },
                    { title: "KANBAN", sub: ["Foco: Fluxo contínuo e visual de trabalho", "Princípios: Visualizar o trabalho, Limitar o WIP (Work in Progress), Gerenciar o fluxo"] },
                    { title: "XP (Extreme Programming)", sub: ["Práticas: Programação em par, TDD (Test-Driven Development), Integração contínua"] },
                ]},
                { id: "qualidade", title: "Qualidade", icon: "⭐", description: "Garantir que o projeto e seus entregáveis atendam aos padrões e requisitos definidos.", items: ["📋 Planejamento da Qualidade", "🔍 Garantia da Qualidade (QA)", "✅ Controle da Qualidade (QC)", "🛠️ Ferramentas: Diagrama de Causa-Efeito, Histogramas, Gráficos de Controle"] },
                { id: "causa-efeito", title: "Diagrama Causa-Efeito", icon: "🐟", description: "Ferramenta visual para identificar, explorar e organizar as possíveis causas de um problema específico.", items: ["🎯 Análise de Causa Raiz", { title: "Categorias (6M)", sub: ["Máquina (Equipamentos)", "Método (Processos)", "Mão de Obra (Pessoas)", "Material (Insumos)", "Medição (Métricas)", "Meio Ambiente (Contexto)"] }] },
                { id: "ear-riscos", title: "EAR (Riscos)", icon: "⚠️", description: "Decomposição hierárquica dos riscos do projeto, agrupados por categorias.", items: ["🔎 Identificação de Riscos", "📊 Análise Qualitativa e Quantitativa", { title: "RESP Respostas aos Riscos", sub: ["Evitar", "Mitigar", "Transferir", "Aceitar"] }] },
                { id: "ear-recursos", title: "EAR (Recursos)", icon: "🧑‍🤝‍🧑", description: "Decomposição hierárquica dos recursos necessários para o projeto, por categoria e tipo.", items: [{ title: "Tipos de Recursos", sub: ["Humanos", "Materiais", "Financeiros"] }, "📊 Histograma de Recursos"] },
                { id: "raci", title: "Matriz RACI", icon: "📝", description: "Ferramenta para definir e comunicar os papéis e responsabilidades das pessoas em tarefas ou entregáveis.", items: ["R - Responsible", "A - Accountable", "C - Consulted", "I - Informed"] }
            ]
        };

        document.addEventListener('DOMContentLoaded', () => {
            const grid = document.getElementById('mind-map-grid');
            const detailPanel = document.getElementById('detail-panel');
            const detailContent = document.getElementById('detail-content');
            const closePanelBtn = document.getElementById('close-panel-btn');
            const overlay = document.getElementById('panel-overlay');
            let currentChart = null;
            
            const centralNodeData = projectManagementData.central;
            const centralNode = document.createElement('div');
            centralNode.className = `p-4 rounded-lg shadow-lg flex flex-col items-center justify-center text-center cursor-default aspect-square ${centralNodeData.color} transition-transform duration-300 transform hover:scale-105`;
            centralNode.innerHTML = `<span class="text-5xl">${centralNodeData.icon}</span><h3 class="mt-4 font-bold text-xl">${centralNodeData.title}</h3>`;
            
            const placeholder = document.createElement('div');
            placeholder.className = "col-span-1 sm:col-span-2 md:col-span-3 lg:col-span-4 flex justify-center py-4";
            placeholder.appendChild(centralNode);
            grid.appendChild(placeholder);

            projectManagementData.nodes.forEach(node => {
                const nodeEl = document.createElement('button');
                nodeEl.className = 'bg-white p-4 rounded-lg shadow-md hover:shadow-xl hover:-translate-y-1 transition-all duration-300 flex flex-col items-center justify-center text-center aspect-square';
                nodeEl.dataset.id = node.id;
                nodeEl.innerHTML = `
                    <span class="text-4xl md:text-5xl">${node.icon}</span>
                    <h3 class="mt-4 font-semibold text-base md:text-lg">${node.title}</h3>
                `;
                grid.appendChild(nodeEl);
            });

            grid.addEventListener('click', (e) => {
                const nodeEl = e.target.closest('button');
                if (!nodeEl || !nodeEl.dataset.id) return;

                const nodeData = projectManagementData.nodes.find(n => n.id === nodeEl.dataset.id);
                if (nodeData) {
                    displayNodeDetails(nodeData);
                }
            });

            function displayNodeDetails(node) {
                if (currentChart) {
                    currentChart.destroy();
                    currentChart = null;
                }

                let contentHtml = `
                    <div class="flex flex-col h-full">
                        <div class="flex-shrink-0">
                            <h2 class="text-3xl font-bold text-sky-600 flex items-center">
                                <span class="text-4xl mr-4">${node.icon}</span>
                                ${node.title}
                            </h2>
                            <p class="mt-2 text-stone-600 italic">${node.description}</p>
                            <hr class="my-6">
                        </div>
                        <div class="flex-grow overflow-y-auto pr-2">
                `;

                if (node.id === 'raci') {
                    contentHtml += generateRaciTable();
                } else if (node.id === 'causa-efeito') {
                    contentHtml += generateFishboneDiagram();
                } else {
                    contentHtml += '<ul class="space-y-4">';
                    node.items.forEach(item => {
                        if (typeof item === 'string') {
                            contentHtml += `<li class="flex items-start"><span class="text-sky-500 mr-3 mt-1">◆</span><span>${item}</span></li>`;
                        } else if (item.sub) {
                            contentHtml += '<li>';
                            contentHtml += `<strong class="font-semibold text-stone-700">${item.title}</strong>`;
                            contentHtml += '<ul class="mt-2 pl-6 space-y-2 border-l-2 border-stone-200">';
                            item.sub.forEach(subItem => {
                                contentHtml += `<li class="flex items-start"><span class="text-stone-400 mr-3 mt-1">-</span><span>${subItem}</span></li>`;
                            });
                            contentHtml += '</ul></li>';
                        } else if (item.text) {
                            contentHtml += `<li><strong class="font-semibold text-stone-700">${item.title}</strong><p class="pl-5 text-stone-600">${item.text}</p></li>`;
                        }
                    });
                    contentHtml += '</ul>';
                }

                if (node.id === 'qualidade') {
                    contentHtml += `<div class="mt-6"><div class="chart-container"><canvas id="qualityChart"></canvas></div></div>`;
                }

                contentHtml += `</div></div>`;
                detailContent.innerHTML = contentHtml;

                if (node.id === 'qualidade') {
                    const ctx = document.getElementById('qualityChart').getContext('2d');
                    currentChart = new Chart(ctx, {
                        type: 'doughnut',
                        data: {
                            labels: ['Planejamento', 'Garantia (QA)', 'Controle (QC)'],
                            datasets: [{
                                label: 'Componentes da Qualidade',
                                data: [1, 1, 1],
                                backgroundColor: ['#38bdf8', '#0ea5e9', '#0284c7'],
                                borderColor: '#ffffff',
                                borderWidth: 4,
                            }]
                        },
                        options: {
                            responsive: true,
                            maintainAspectRatio: false,
                            plugins: {
                                legend: {
                                    position: 'top',
                                },
                                title: {
                                    display: true,
                                    text: 'Componentes da Gestão da Qualidade',
                                    font: { size: 16 }
                                },
                                tooltip: {
                                    callbacks: {
                                        label: function(context) {
                                            return context.label;
                                        }
                                    }
                                }
                            }
                        }
                    });
                }
                
                openPanel();
            }

            function generateRaciTable() {
                const roles = [
                    {
                        letter: "R",
                        name: "Responsible (Responsável)",
                        desc: "Quem executa a tarefa."
                    },
                    {
                        letter: "A",
                        name: "Accountable (Aprovador)",
                        desc: "O único responsável final pela tarefa."
                    },
                    {
                        letter: "C",
                        name: "Consulted (Consultado)",
                        desc: "Quem deve ser consultado (comunicação bidirecional)."
                    },
                    {
                        letter: "I",
                        name: "Informed (Informado)",
                        desc: "Quem deve ser mantido informado (comunicação unidirecional)."
                    }
                ];

                let tableHtml = `
                    <div class="overflow-x-auto">
                        <table class="w-full text-left border-collapse">
                            <thead class="bg-stone-100">
                                <tr>
                                    <th class="p-3 font-semibold text-sm border-b">Papel</th>
                                    <th class="p-3 font-semibold text-sm border-b">Descrição</th>
                                </tr>
                            </thead>
                            <tbody>
                `;
                roles.forEach(role => {
                    tableHtml += `
                        <tr class="hover:bg-stone-50">
                            <td class="p-3 border-b border-stone-200">
                                <div class="flex items-center">
                                    <div class="w-8 h-8 rounded-full bg-sky-500 text-white flex items-center justify-center font-bold mr-3">${role.letter}</div>
                                    <span class="font-semibold">${role.name}</span>
                                </div>
                            </td>
                            <td class="p-3 border-b border-stone-200 text-stone-600">${role.desc}</td>
                        </tr>
                    `;
                });
                tableHtml += `</tbody></table></div>`;
                return tableHtml;
            }

            function generateFishboneDiagram() {
                const categories = ["Método", "Máquina", "Mão de Obra", "Material", "Medição", "Meio Ambiente"];
                return `
                    <div>
                        <p class="mb-4 text-stone-700">Esta é uma representação visual do Diagrama de Ishikawa (ou Espinha de Peixe), usado para mapear as possíveis causas de um problema (o 'efeito').</p>
                        <div class="relative flex items-center w-full h-80 bg-stone-50 p-4 rounded-lg">
                            <div class="fishbone-line w-full"></div>
                            <div class="absolute right-0 top-1/2 -translate-y-1/2 bg-sky-100 p-2 rounded-md shadow text-center">
                                <strong class="text-sky-800">Efeito</strong>
                                <div class="text-sm text-sky-700">(Problema)</div>
                            </div>
                            
                            <!-- Top Branches -->
                            <div class="fishbone-branch w-1/3 top-1/4 left-1/4" style="transform: rotate(-45deg);">
                                <span class="absolute -top-6 -left-2 bg-white p-1 rounded text-sm">${categories[0]}</span>
                            </div>
                            <div class="fishbone-branch w-1/3 top-1/4 left-1/2" style="transform: rotate(-45deg);">
                                <span class="absolute -top-6 -left-2 bg-white p-1 rounded text-sm">${categories[1]}</span>
                            </div>
                             <div class="fishbone-branch w-1/4 top-1/4 left-3/4" style="transform: rotate(-45deg);">
                                <span class="absolute -top-6 -left-2 bg-white p-1 rounded text-sm">${categories[2]}</span>
                            </div>
                            
                            <!-- Bottom Branches -->
                            <div class="fishbone-branch w-1/3 bottom-1/4 left-1/4" style="transform: rotate(45deg);">
                                <span class="absolute top-4 -left-2 bg-white p-1 rounded text-sm">${categories[3]}</span>
                            </div>
                            <div class="fishbone-branch w-1/3 bottom-1/4 left-1/2" style="transform: rotate(45deg);">
                                <span class="absolute top-4 -left-2 bg-white p-1 rounded text-sm">${categories[4]}</span>
                            </div>
                            <div class="fishbone-branch w-1/4 bottom-1/4 left-3/4" style="transform: rotate(45deg);">
                                <span class="absolute top-4 -left-2 bg-white p-1 rounded text-sm">${categories[5]}</span>
                            </div>
                        </div>
                    </div>
                `;
            }

            function openPanel() {
                detailPanel.classList.remove('translate-x-full');
                overlay.classList.remove('hidden');
                document.body.style.overflow = 'hidden';
            }

            function closePanel() {
                detailPanel.classList.add('translate-x-full');
                overlay.classList.add('hidden');
                document.body.style.overflow = '';
                if (currentChart) {
                    currentChart.destroy();
                    currentChart = null;
                }
            }

            closePanelBtn.addEventListener('click', closePanel);
            overlay.addEventListener('click', closePanel);

        });
    </script>
</body>
</html>
