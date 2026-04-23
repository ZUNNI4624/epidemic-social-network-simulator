# 🦠 Epidemiological Social Network Simulator

[![GitHub Pages](https://img.shields.io/badge/demo-github%20pages-blue)](https://zunni4624.github.io/epidemic-social-network-simulator/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

A sophisticated **SIR epidemic simulator** built on a **bipartite social network** model.  
The simulation uses stochastic transmission algorithms, age‑dependent risk factors, and a force‑directed D3.js visualization to illustrate how diseases spread through a population.

> **Live demo**: [https://zunni4624.github.io/epidemic-social-network-simulator/](https://zunni4624.github.io/epidemic-social-network-simulator/)

![Landing Page](screenshots/landing.png)
*Parameter configuration page*

![Simulation Running](screenshots/simulation.png)
*Real‑time network animation and SIR curves*

---

## ✨ Features

- **Bipartite graph model** – People connect only to buildings (home + activity). Transmission occurs when susceptible and infected individuals share a building.
- **SIR disease dynamics** – Susceptible → Infected → Recovered with stochastic recovery.
- **Age‑dependent risk** – Children (higher contact rate) and elderly (higher susceptibility) have modified transmission probabilities.
- **Lockdown intervention** – Four levels (0‑3) reduce visits to activity buildings and contact probability inside buildings.
- **Force‑directed visualization** – Powered by D3.js with distinct shapes for building types (hexagon = home, circle = college, square = mall, cross = hospital). Person nodes are coloured by disease state, sized by age, and stroked by gender.
- **Real‑time charts** – Epidemic curve (canvas), age distribution, and gender distribution (D3 bar charts).
- **Infection path tracking** – Recent transmissions are shown as animated dashed arrows.
- **Tooltips on nodes** – Hover over any person to see their age, gender, status, home, and activity building.
- **Performance optimised** – Infection queue, occupant sampling in large buildings, and tuned force simulation for populations up to 5000.

---

## 🗂️ Project Structure
├── index.html # Landing page with parameter sliders
├── simulation.html # Main simulation page (visualisation + controls)
├── css/
│ └── styles.css # Global styles, dark theme, glassmorphism
└── js/
├── constants.js # Enums, age factors, colours, building ratios
├── dataStructures.js # AdjacencyList, InfectionQueue, InfectionPathTracker
├── networkGenerator.js # Creates bipartite graph (people ↔ buildings)
├── simulationEngine.js # SIR tick logic, lockdown, age‑based risk
├── visualization.js # D3 force layout, custom shapes, updates
└── charts.js # Epicurve (Canvas) + bar charts (D3)

## 🚀 How to Run Locally
1. Clone the repository
   	git clone https://github.com/ZUNNI4624/epidemic-social-	network-simulator.git
   	cd epidemic-social-network-simulator
2. Serve the files with a local web server
	Because the simulation uses D3.js and dynamic SVG rendering, you must use a web server (not just file://).
		>Python 3
			python -m http.server 8000
		>Node.js (npx)
			npx http-server -p 8000
		>VS Code Live Server – right‑click index.html → Open with Live Server
3. Open your browser at http://localhost:8000
4. Adjust parameters (population, buildings, transmission rate, lockdown level) and click Start Simulation.

## 🧠 DSA Concepts Demonstrated
>Graph (Adjacency List)
>Queue (Infection Queue)
>Bipartite Graph
>Stochastic Simulation
>Force‑Directed Layout

## 🛠️ Tech Stack
>HTML5 / CSS3 – Structure, dark glassmorphic UI
>JavaScript (ES6) – Core logic, modules (no build step required)
>D3.js (v7) – Force‑directed graph, bar charts
>Canvas API – High‑performance epidemic curve rendering