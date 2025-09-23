<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Portfolio | Mirwaise Khan</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/chartjs-adapter-date-fns/dist/chartjs-adapter-date-fns.bundle.min.js"></script>
    <!-- Chosen Palette: Tech Slate -->
    <!-- Application Structure Plan: A two-column layout featuring a sticky sidebar and a main scrollable content area. The left sidebar contains personal branding, contact info, and navigation, remaining constantly visible for easy access. The right column organizes the resume content (About, Experience, Skills, Education) into distinct, digestible cards. This structure separates navigation and identity from the detailed content, creating a focused and user-friendly experience that feels like a modern dashboard. Key interaction involves expanding project cards to reveal details, preventing visual clutter. -->
    <!-- Visualization & Content Choices: 
        - About Me -> Inform -> Text Block -> N/A -> Establishes a personal introduction at the top of the main content area. -> Vanilla HTML/Tailwind.
        - Experience -> Organize/Inform -> Interactive Cards -> Click to expand/collapse -> A modular and clean way to present distinct roles/projects. More modern than a simple timeline and very mobile-friendly. -> Vanilla JS & Tailwind CSS.
        - Skills -> Compare/Inform -> Horizontal Bar Chart -> Hover tooltips for proficiency scores -> Bar charts offer a more direct and clearer comparison of skill levels than a radar chart. Grouping by category adds useful structure. -> Chart.js.
        - Education -> Inform -> Static Card -> N/A -> A simple, clean presentation for academic credentials. -> Vanilla HTML/Tailwind.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap');
        body {
            font-family: 'Inter', sans-serif;
        }
        .details-panel {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-out, padding-top 0.5s ease-out, padding-bottom 0.5s ease-out;
            padding-top: 0;
            padding-bottom: 0;
        }
        .details-panel.open {
            max-height: 1000px; 
            padding-top: 1rem;
            padding-bottom: 1rem;
            transition: max-height 0.7s ease-in, padding-top 0.7s ease-in, padding-bottom 0.7s ease-in;
        }
        .nav-link.active {
            background-color: #38bdf8;
            color: white;
        }
    </style>
</head>
<body class="bg-slate-100">

    <div class="max-w-7xl mx-auto lg:grid lg:grid-cols-12 lg:gap-12 px-4 sm:px-6 lg:px-8">
        
        <header class="lg:col-span-4 lg:sticky lg:top-0 lg:h-screen lg:py-24 flex flex-col justify-between">
            <div>
                <h1 class="text-4xl font-bold text-slate-800">Mirwaise Khan</h1>
                <h2 class="mt-3 text-lg font-medium text-slate-600">Aspiring Blockchain & Smart Contract Developer</h2>
                <p class="mt-4 max-w-xs text-slate-500">I build decentralized solutions, turning complex concepts into secure and functional code.</p>
                
                <nav class="hidden lg:block mt-12">
                    <ul class="space-y-2">
                        <li><a href="#about" class="nav-link group flex items-center py-3 px-4 rounded-md text-slate-600 hover:bg-sky-100 hover:text-sky-800 transition-all duration-300">
                            <span class="w-2 h-0.5 bg-slate-500 group-hover:bg-sky-700 group-[.active]:bg-white transition-all duration-300 mr-4 group-hover:w-8 group-[.active]:w-8"></span>About
                        </a></li>
                        <li><a href="#experience" class="nav-link group flex items-center py-3 px-4 rounded-md text-slate-600 hover:bg-sky-100 hover:text-sky-800 transition-all duration-300">
                            <span class="w-2 h-0.5 bg-slate-500 group-hover:bg-sky-700 group-[.active]:bg-white transition-all duration-300 mr-4 group-hover:w-8 group-[.active]:w-8"></span>Experience
                        </a></li>
                        <li><a href="#skills" class="nav-link group flex items-center py-3 px-4 rounded-md text-slate-600 hover:bg-sky-100 hover:text-sky-800 transition-all duration-300">
                           <span class="w-2 h-0.5 bg-slate-500 group-hover:bg-sky-700 group-[.active]:bg-white transition-all duration-300 mr-4 group-hover:w-8 group-[.active]:w-8"></span>Skills
                        </a></li>
                    </ul>
                </nav>
            </div>
            
            <div class="mt-8 lg:mt-0 flex items-center space-x-4">
                <a href="https://linkedin.com/in/mirwaisekhan" target="_blank" rel="noopener noreferrer" class="text-slate-500 hover:text-sky-600">
                    <span class="text-2xl">●</span> 
                </a>
                 <a href="mailto:nifaskhan098@gmail.com" class="text-slate-500 hover:text-sky-600">
                    <span class="text-2xl">●</span>
                </a>
            </div>
        </header>

        <main class="lg:col-span-8 py-12 lg:py-24">
            
            <section id="about" class="mb-16 scroll-mt-24">
                <p class="text-slate-600 text-lg">Passionate about turning decentralized concepts into practical, functional code. I believe in learning by building, and I'm actively developing hands-on experience in the Web3 ecosystem. My internship and project work has involved developing smart contracts, integrating APIs for real-time data, and even creating educational content to demystify complex crypto topics. I am actively seeking roles where I can contribute to a forward-thinking team and continue to grow my skills in blockchain development.</p>
            </section>
            
            <section id="experience" class="scroll-mt-24">
                <h3 class="text-xl font-bold text-sky-800 mb-6">EXPERIENCE</h3>
                <div class="space-y-6">

                    <div class="bg-white/50 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 experience-card">
                        <div class="flex justify-between items-start">
                            <div>
                                <p class="text-xs font-semibold uppercase tracking-wider text-slate-500">Sep 2025 — Oct 2025</p>
                                <h4 class="text-lg font-bold text-slate-800 mt-1">Blockchain & Web3 Intern · Future Intern Inc.</h4>
                            </div>
                            <button class="expand-btn text-2xl text-sky-600 hover:text-sky-800 transition-transform duration-300">+</button>
                        </div>
                        <div class="details-panel">
                            <p class="text-slate-600">Gained a holistic understanding of the decentralized ecosystem by executing projects across smart contract development, API integration, and digital content creation.</p>
                            <ul class="mt-4 list-disc list-inside text-slate-600 space-y-1">
                                <li>Developed and deployed a custom ERC-20 token onto the Polygon Mumbai testnet.</li>
                                <li>Engineered a crypto portfolio tracker by integrating the CoinGecko API with Google Apps Script.</li>
                                <li>Designed engaging visual content to demystify complex crypto topics for a general audience.</li>
                                <li>Analyzed DeFi protocols and participated in a live airdrop to understand token distribution models.</li>
                            </ul>
                            <div class="mt-4 flex flex-wrap gap-2">
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">Solidity</span>
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">OpenZeppelin</span>
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">Polygon</span>
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">CoinGecko API</span>
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">React.js</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-white/50 p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300 experience-card">
                        <div class="flex justify-between items-start">
                            <div>
                                <p class="text-xs font-semibold uppercase tracking-wider text-slate-500">Project</p>
                                <h4 class="text-lg font-bold text-slate-800 mt-1">Decentralized Applications</h4>
                            </div>
                           <button class="expand-btn text-2xl text-sky-600 hover:text-sky-800 transition-transform duration-300">+</button>
                        </div>
                         <div class="details-panel">
                             <p class="text-slate-600">Developed and deployed smart contracts for a lottery and a crowdfunding platform, focusing on core logic, security, and functionality for handling user funds trustlessly on the blockchain.</p>
                             <div class="mt-4 flex flex-wrap gap-2">
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">Solidity</span>
                                <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">Foundry</span>
                                 <span class="bg-sky-100 text-sky-800 text-xs font-medium px-2.5 py-0.5 rounded-full">Remix IDE</span>
                            </div>
                        </div>
                    </div>

                </div>
            </section>

            <section id="skills" class="mt-16 scroll-mt-24">
                <h3 class="text-xl font-bold text-sky-800 mb-6">SKILLS</h3>
                 <p class="text-slate-600 mb-8">This chart illustrates my proficiency across key areas of blockchain development, programming languages, and essential tools. My ratings are based on direct, hands-on application in my projects and internship work, reflecting my practical capabilities.</p>
                <div class="bg-white/50 p-6 rounded-lg shadow-md">
                     <div class="chart-container relative w-full h-96 max-w-2xl mx-auto">
                        <canvas id="skillsBarChart"></canvas>
                    </div>
                </div>
            </section>
            
             <section id="education" class="mt-16">
                 <h3 class="text-xl font-bold text-sky-800 mb-6">EDUCATION</h3>
                 <div class="bg-white/50 p-6 rounded-lg shadow-md">
                     <p class="text-xs font-semibold uppercase tracking-wider text-slate-500">Expected 2026</p>
                     <h4 class="text-lg font-bold text-slate-800 mt-1">Bachelor of Technology</h4>
                     <p class="text-slate-600">Rajiv Gandhi Institute of Technology, Bangalore</p>
                 </div>
            </section>
        </main>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const experienceCards = document.querySelectorAll('.experience-card');
            experienceCards.forEach(card => {
                const button = card.querySelector('.expand-btn');
                const panel = card.querySelector('.details-panel');
                button.addEventListener('click', () => {
                    const isOpen = panel.classList.contains('open');
                    
                    document.querySelectorAll('.details-panel.open').forEach(openPanel => {
                       openPanel.classList.remove('open');
                       openPanel.closest('.experience-card').querySelector('.expand-btn').textContent = '+';
                       openPanel.closest('.experience-card').querySelector('.expand-btn').classList.remove('rotate-45');
                    });

                    if (!isOpen) {
                        panel.classList.add('open');
                        button.textContent = '−';
                        button.classList.add('rotate-45');
                    }
                });
            });

            const ctx = document.getElementById('skillsBarChart').getContext('2d');
            const skillsBarChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['Solidity', 'OpenZeppelin', 'Smart Contracts', 'Foundry', 'Python', 'React.js', 'DeFi'],
                    datasets: [{
                        label: 'Proficiency',
                        data: [9, 9, 8, 8, 7, 6, 8],
                        backgroundColor: 'rgba(56, 189, 248, 0.6)',
                        borderColor: 'rgba(2, 132, 199, 1)',
                        borderWidth: 1
                    }]
                },
                options: {
                    indexAxis: 'y',
                    maintainAspectRatio: false,
                    responsive: true,
                    scales: {
                        x: {
                            beginAtZero: true,
                            max: 10,
                            grid: {
                                display: false
                            },
                             ticks: {
                                color: '#64748b'
                            }
                        },
                        y: {
                             grid: {
                                color: '#e2e8f0'
                            },
                            ticks: {
                                color: '#334155',
                                font: {
                                    weight: '500'
                                }
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            display: false
                        },
                        tooltip: {
                            backgroundColor: '#0f172a',
                            titleFont: {
                                size: 14,
                                weight: 'bold'
                            },
                            bodyFont: {
                                size: 12
                            },
                            callbacks: {
                                label: function(context) {
                                    return `Proficiency: ${context.raw} / 10`;
                                }
                            }
                        }
                    }
                }
            });

            const sections = document.querySelectorAll('section[id]');
            const navLinks = document.querySelectorAll('.nav-link');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.remove('active');
                            if (link.getAttribute('href').substring(1) === entry.target.id) {
                                link.classList.add('active');
                            }
                        });
                    }
                });
            }, { rootMargin: "-50% 0px -50% 0px" });

            sections.forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
# mirwaise-RESUME
