  Water Intake Tracker body { font-family: Arial, sans-serif; background-color: #f9f9f9; padding: 20px; } .header { display: flex; justify-content: center; align-items: center; margin-bottom: 20px; } .header h1 { margin: 0; color: #333; } .tracker { display: flex; flex-direction: column; align-items: center; } .months { display: grid; grid-template-columns: repeat(12, 1fr); justify-content: space-between; width: 90%; font-size: 14px; color: #555; text-align: center; margin-bottom: 10px; } .grid-container { display: flex; } .days-of-week { display: flex; flex-direction: column; justify-content: space-between; margin-right: 10px; font-size: 12px; color: #555; text-align: right; height: 120px; /\* Alinhado com os quadrados \*/ } .grid { display: grid; grid-template-columns: repeat(52, 12px); /\* 52 semanas \*/ grid-gap: 2px; } .square { width: 12px; height: 12px; border-radius: 2px; background-color: #e0e0e0; /\* Começa com cinza claro \*/ cursor: pointer; transition: background-color 0.2s ease; } .square\[data-level="0"\] { background-color: #e0e0e0; /\* Nenhum progresso \*/ } .square\[data-level="1"\] { background-color: #b3d9ff; /\* 25% \*/ } .square\[data-level="2"\] { background-color: #66b3ff; /\* 50% \*/ } .square\[data-level="3"\] { background-color: #1a8cff; /\* 75% \*/ } .square\[data-level="4"\] { background-color: #0056b3; /\* 100% \*/ } .legend { margin-top: 20px; font-size: 14px; text-align: center; } .legend span { display: inline-block; width: 12px; height: 12px; margin: 0 5px; border-radius: 2px; } .level-0 { background-color: #e0e0e0; } .level-1 { background-color: #b3d9ff; } .level-2 { background-color: #66b3ff; } .level-3 { background-color: #1a8cff; } .level-4 { background-color: #0056b3; }

Water Intake Tracker
====================

Jan

Feb

Mar

Apr

May

Jun

Jul

Aug

Sep

Oct

Nov

Dec

Mon

Wed

Fri

Legenda:

Nenhum 25% 50% 75% 100% (Meta Atingida)

const grid = document.getElementById("grid"); const totalDays = 365; // Adiciona quadrados para cada dia do ano for (let i = 0; i < totalDays; i++) { const square = document.createElement("div"); square.classList.add("square"); square.setAttribute("data-level", "0"); // Nível inicial square.addEventListener("click", () => toggleLevel(square)); grid.appendChild(square); } // Alternar níveis de progresso function toggleLevel(square) { let currentLevel = parseInt(square.getAttribute("data-level"), 10); let nextLevel = (currentLevel + 1) % 5; // Alterna entre 0 e 4 square.setAttribute("data-level", nextLevel); }