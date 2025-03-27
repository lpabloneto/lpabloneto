<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simulado - Farmacologia 1 (IDOMED)</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      line-height: 1.6;
      background-color: #f9f9f9;
    }
    .question {
      margin-bottom: 30px;
      padding: 15px;
      border: 1px solid #ccc;
      border-radius: 8px;
      background: white;
    }
    .option {
      margin: 8px 0;
      padding: 10px;
      border: 1px solid #ddd;
      background-color: #eee;
      cursor: pointer;
    }
    .correct {
      background-color: #d4edda;
      color: #155724;
      border-color: #c3e6cb;
    }
    .incorrect {
      background-color: #f8d7da;
      color: #721c24;
      border-color: #f5c6cb;
    }
  </style>
</head>
<body>
  <h1>Simulado Interativo – Farmacologia 1 (IDOMED)</h1>
  <p>Clique em uma alternativa para saber se está correta e ver a explicação.</p>

  <div id="quiz"></div>

  <script>
    const questions = [
      {
        text: "1. Um paciente idoso com vômitos não responde à metoclopramida oral. O médico opta por via intramuscular. Por quê?",
        options: {
          A: "A biodisponibilidade oral da metoclopramida é maior.",
          B: "A absorção oral é mais rápida em casos de náusea.",
          C: "A via parenteral evita o efeito de primeira passagem hepática.",
          D: "A metoclopramida não pode ser administrada por outras vias além da oral.",
          E: "A via parenteral é usada porque retarda o início da ação."
        },
        correct: "C",
        explanations: {
          A: "Incorreto. A biodisponibilidade oral é afetada pelo efeito de primeira passagem.",
          B: "Incorreto. A absorção oral é prejudicada em casos de náusea/vômito.",
          C: "Correto. A via parenteral evita o efeito de primeira passagem hepática.",
          D: "Incorreto. A metoclopramida tem diversas vias de administração.",
          E: "Incorreto. A via parenteral costuma ter início mais rápido."
        }
      },
      {
        text: "2. Uma paciente com hipoalbuminemia usa fenitoína. Qual risco ela apresenta?",
        options: {
          A: "Redução da biodisponibilidade da fenitoína.",
          B: "Aumento da ligação da droga às proteínas plasmáticas.",
          C: "Redução da fração livre e ativa da droga.",
          D: "Aumento da fração livre, aumentando o risco de toxicidade.",
          E: "Aumento da meia-vida de eliminação da droga."
        },
        correct: "D",
        explanations: {
          A: "Incorreto. A biodisponibilidade não depende da albumina.",
          B: "Incorreto. Menos albumina = menos ligação.",
          C: "Incorreto. O efeito é o contrário: aumenta a fração livre.",
          D: "Correto. Menos ligação = mais droga livre = mais toxicidade.",
          E: "Incorreto. A meia-vida pode não ser afetada diretamente."
        }
      }
      // Adicione mais perguntas aqui se quiser
    ];

    const quizContainer = document.getElementById('quiz');

    questions.forEach((q, index) => {
      const questionDiv = document.createElement('div');
      questionDiv.classList.add('question');
      questionDiv.innerHTML = `<strong>${q.text}</strong>`;

      Object.entries(q.options).forEach(([letter, text]) => {
        const option = document.createElement('div');
        option.classList.add('option');
        option.textContent = `${letter}) ${text}`;
        option.addEventListener('click', () => {
          option.classList.add(letter === q.correct ? 'correct' : 'incorrect');
          option.innerHTML += `<br><em>${q.explanations[letter]}</em>`;
          Array.from(option.parentNode.children).forEach(btn => btn.style.pointerEvents = "none");
        });
        questionDiv.appendChild(option);
      });

      quizContainer.appendChild(questionDiv);
    });
  </script>
</body>
</html>