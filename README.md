# 📄 `README.md` — Desafio do DBA

```markdown
# 🗄️ Desafio do DBA — Semana #6

![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-brightgreen)
![Licença](https://img.shields.io/badge/licen%C3%A7a-acad%C3%AAmico-blue)
![Dependências](https://img.shields.io/badge/depend%C3%AAncias-0-success)

> **Jogo educativo interativo** sobre **Administração de bancos de dados e Estimativa de crescimento**.
> Criado a partir do material da **Semana #6 — Universidade Jala** (uso estritamente acadêmico).

---

## 📋 Sobre o Projeto

O **Desafio do DBA** é um jogo de navegador que transforma o conteúdo teórico da aula
em uma experiência gamificada. O jogador assume o papel de um **DBA em treinamento**
e precisa completar 5 níveis para conquistar o título de **DBA Master** 🏆.

Todo o conteúdo das perguntas foi extraído diretamente dos slides do material:
espelhamento, particionamento, os 3 Vs de dados, técnicas de estimativa de crescimento
e o caso de estudo com ERP.

---

## 🎮 Como Jogar

### Pré-requisitos
- Apenas um navegador moderno (Chrome, Firefox, Edge ou Safari).
- **Sem internet, sem instalação, sem build.**

### Passo a passo
1. Copie o código-fonte e salve como `desafio-dba.html`;
2. Dê **duplo clique** no arquivo para abrir no navegador;
3. Digite seu nome e clique em **▶ Iniciar Jogo**;
4. Complete os níveis na ordem — cada conclusão desbloqueia o próximo;
5. Veja seu ranking final no botão **📊 Ver Resultado Final**.

> 💡 **Atalhos de teclado no quiz:** teclas `1` a `4` respondem; `Enter` avança.

---

## 🧩 Níveis e Conteúdo

| Nível | Ícone | Tema (material de origem) | Mecânica | Desafio |
|:---:|:---:|---|---|:---:|
| 1 | 🪞 | Database Mirroring (slides 5–9) | Quiz | 5 perguntas |
| 2 | ✂️ | Database Splitting (slides 10–13) | Quiz | 5 perguntas |
| 3 | 🧩 | Os 3 Vs: Volume, Velocity, Variety (slides 16–19) | Ligar Pares | 6 pares |
| 4 | 📈 | Estimativa de Crescimento (slides 15, 20–21) | Quiz | 5 perguntas |
| 5 | 🏭 | Caso de Estudo ERP + projeção 1/2/5 anos (slides 27–29, 33) | Quiz | 6 perguntas |

---

## ✨ Funcionalidades

- ✅ **5 níveis progressivos** com desbloqueio por conclusão
- ⭐ **Sistema de estrelas** por desempenho (1–3 estrelas por nível)
- 🔥 **Sequência (streak)** de respostas certas consecutivas
- 🎁 **Bônus "Perfeito!"** (+5 pontos) ao acertar tudo em um nível
- 💾 **Progresso salvo** automaticamente no navegador (`localStorage`)
- 📘 **Botão "Dica da teoria"** com resumo dos slides antes de cada nível
- 🔊 **Efeitos sonoros** via Web Audio API (com botão de mudo)
- 🎊 **Confetes** em níveis perfeitos e no resultado final
- 🏆 **Ranking final** com títulos por aproveitamento
- 📱 **Design responsivo** (desktop e mobile)
- 🌐 **100% offline** — um único arquivo HTML

---

## 🏆 Sistema de Pontuação

| Ação | Pontos |
|---|:---:|
| Resposta certa no quiz | 10 |
| Par ligado à primeira tentativa | 10 |
| Par ligado em tentativas seguintes | 5 |
| Bônus "Perfeito!" (100% do nível) | +5 |
| **Pontuação máxima possível** | **280** |

### Ranking final
| Aproveitamento | Título |
|:---:|---|
| ≥ 90% | 🏆 DBA Master |
| ≥ 75% | 🥇 Administrador Sênior |
| ≥ 60% | 🥈 Administrador Pleno |
| ≥ 40% | 🥉 Administrador Júnior |
| < 40% | 🌱 Estagiário de BD |

---

## 🛠️ Tecnologias

- **HTML5** — estrutura e telas
- **CSS3** — design responsivo, animações e tema
- **JavaScript (Vanilla ES6+)** — lógica do jogo, pontuação e persistência
- **Web Audio API** — efeitos sonoros
- **localStorage** — salvamento do progresso

> Zero dependências, zero frameworks, zero build. 🎯

---

## 📂 Estrutura do Projeto

```
desafio-dba/
├── desafio-dba.html   # Jogo completo (HTML + CSS + JS em um arquivo)
└── README.md          # Este arquivo
```

---

## ⚙️ Personalização (para professores/tutores)

Todo o conteúdo pedagógico está centralizado no array `LEVELS`, no início do `<script>`:

```javascript
const LEVELS = [
  {
    id: 1,
    icon: "🪞",
    title: "Mirroring (Espelhamento)",
    kind: "quiz",              // "quiz" ou "match"
    tip: "Resumo teórico exibido no botão Dica...",
    questions: [
      { q: "Pergunta...", o: ["A", "B", "C", "D"], a: 0, e: "Explicação..." }
    ]
  },
  // ...
];
```

- `kind: "quiz"` → campo `questions` (`o` = opções, `a` = índice da correta, `e` = explicação);
- `kind: "match"` → campo `pairs` (`[conceito, definição]`);
- Para criar um **novo nível**, basta adicionar um objeto ao array — a interface se ajusta sozinha.

---

## 🗺️ Roadmap

- [x] Jogo base com 5 níveis
- [x] Persistência de progresso
- [ ] Modo contrarrelógio (cronômetro por pergunta)
- [ ] Modo multiplayer local (2 jogadores)
- [ ] Exportar pontuação em CSV para o tutor
- [ ] Versão em inglês

---

## 📄 Licença & Aviso Acadêmico

> ⚠️ **Este material é apenas para uso acadêmico.**
> É proibido distribuí-lo ou publicá-lo sem autorização prévia por escrito.
> © 2026 Universidade Jala — Todos os direitos são reservados.

---

## 📚 Referências

- Material da aula: *Semana #6 — Administração de bancos de dados e Estimativa de crescimento* (Universidade Jala);
- Estimativa de tamanho de tabelas: [dwbi1.wordpress.com — Estimating the size of dimension and fact tables](https://dwbi1.wordpress.com/2015/02/13/estimating-the-size-of-dimension-and-fact-tables/);
- Monitoramento: SolarWinds Database Performance Analyzer (exibido em aula).

---


*Contate-me ou ao seu Tutor se precisar de algum esclarecimento.*
```

✅ **Pronto!** Basta salvar este conteúdo como `README.md` na mesma pasta do `desafio-dba.html`.
