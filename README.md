# AI-Assisted Requirements Engineering

Projeto prático de aprendizagem ativa utilizando **Gemini Notebook** para estudar Engenharia de Requisitos, testar estratégias de prompt engineering e analisar criticamente os limites do uso de Inteligência Artificial na definição de requisitos de software.

O projeto foi desenvolvido como parte de um desafio da **DIO**, com foco em curadoria de fontes, organização do conhecimento, pensamento crítico e documentação do processo de aprendizagem.

---

## 🎯 Objetivo

O objetivo deste projeto foi utilizar IA como ferramenta de apoio ao estudo de **Engenharia de Requisitos**, explorando principalmente:

- fundamentos da Engenharia de Requisitos;
- elicitação, análise, especificação, validação e gerenciamento;
- requisitos funcionais e não funcionais;
- stakeholders;
- User Stories;
- critérios INVEST;
- modelo dos 3Cs;
- critérios de aceitação;
- rastreabilidade;
- gerenciamento de mudanças;
- riscos de assumir informações não validadas.

Além do conteúdo técnico, o projeto buscou avaliar uma questão específica:

> **Até que ponto uma IA consegue apoiar a construção de requisitos sem transformar inferências em fatos?**

---

## 🧠 Ferramenta utilizada

Foi utilizado o **Gemini Notebook** como ambiente de estudo e experimentação.

As fontes foram adicionadas ao notebook e utilizadas como base para:

- síntese de conceitos;
- geração de material de estudo;
- aplicação em estudo de caso;
- revisão crítica de respostas;
- comparação entre evidências, inferências e suposições;
- geração de perguntas de elicitação.

---

## 📚 Curadoria de Fontes

A seleção de fontes priorizou materiais relacionados a Engenharia de Requisitos, Business Analysis e práticas ágeis.

Entre as principais referências utilizadas no notebook estão:

### SWEBOK — Software Requirements

Referência utilizada para fundamentos de Engenharia de Requisitos, incluindo:

- elicitação;
- análise;
- especificação;
- validação;
- gerenciamento;
- requisitos funcionais e não funcionais;
- rastreabilidade.

**Fonte:**  
https://swebokwiki.org/Chapter_1%3A_Software_Requirements

---

### Carnegie Mellon University / Software Engineering Institute

Material utilizado para aprofundar o estudo de **Requirements Elicitation** e técnicas de descoberta de requisitos junto aos stakeholders.

**Fonte:**  
https://www.sei.cmu.edu/library/lecture-notes-on-requirements-elicitation/

---

### Agile Business Consortium — User Stories

Utilizado para estudo de:

- User Stories;
- modelo dos 3Cs;
- INVEST;
- colaboração com stakeholders;
- refinamento iterativo de requisitos.

**Fonte:**  
https://www.agilebusiness.org/resource/what-are-user-stories/

---

### Scrum Alliance — Agile Glossary

Utilizado como apoio para conceitos relacionados a práticas ágeis, incluindo critérios de aceitação e terminologia associada ao desenvolvimento iterativo.

**Fonte:**  
https://www.scrumalliance.org/glossary

---

## 🔬 Metodologia do Experimento

O estudo foi dividido em três etapas.

### 1. Exploração conceitual

O primeiro prompt foi deliberadamente simples:

> Explique o que é Engenharia de Requisitos e quais são seus principais conceitos.

A resposta foi tecnicamente boa e bem estruturada, mas predominantemente descritiva.

Isso mostrou que uma explicação conceitual não era suficiente para avaliar a capacidade da IA de aplicar o conhecimento.

---

### 2. Aplicação em um cenário prático

Foi apresentado o seguinte cenário:

> Uma pequena loja de varejo atualmente controla parte de seu estoque e de suas vendas manualmente e deseja desenvolver um sistema para digitalizar esse processo.

A IA recebeu a tarefa de:

- identificar stakeholders;
- criar 5 requisitos funcionais;
- criar 5 requisitos não funcionais;
- explicar as necessidades atendidas;
- sinalizar lacunas em vez de inventar informações.

Apesar dessa instrução, a resposta introduziu diversos detalhes não presentes no cenário.

Entre eles:

- tempo de resposta de **2 segundos**;
- disponibilidade de **99%**;
- backup às **23h59**;
- RTO de **4 horas**;
- RPO de **1 dia**;
- máximo de **5 interações**;
- conclusão de uma venda com 3 itens em até **1 minuto**;
- exportação de relatórios em PDF ou CSV.

Esses elementos pareciam tecnicamente precisos, mas não haviam sido validados com stakeholders.

---

### 3. Auditoria crítica

Foi então criado um novo prompt pedindo que a própria IA auditasse sua resposta anterior e classificasse cada informação como:

- **Fundamentado**
- **Inferência razoável**
- **Suposição não fundamentada**

A auditoria reconheceu que vários parâmetros haviam sido introduzidos sem evidência suficiente.

Além disso, as suposições foram transformadas em **perguntas de elicitação**, como:

> Qual é o tempo de atendimento aceitável no caixa?

> Qual é o impacto para a operação se o sistema ficar indisponível?

> Quanto tempo a empresa pode permanecer sem acesso ao sistema em caso de falha?

> Como os responsáveis pretendem visualizar os dados de vendas?

Essa etapa mostrou que a IA se tornou mais útil quando utilizada para **identificar perguntas a serem feitas**, em vez de decidir sozinha quais deveriam ser os requisitos.

---

## 🩹 Cicatriz do Processo

O principal problema encontrado foi a geração de **especificidade artificial**.

Um requisito como:

```text
O sistema deve ser rápido.
```

é inadequado por ser vago.

Porém, transformá-lo automaticamente em:

```text
O sistema deve responder em até 2 segundos.
```

também pode ser incorreto quando esse valor não foi levantado com stakeholders.

O aprendizado central foi:

> **Precisão textual não é evidência.**

Uma resposta pode parecer objetiva, profissional e tecnicamente convincente e ainda assim estar baseada em uma premissa não validada.

---

## 📘 Miniguia de Estudo

O projeto também gerou um miniguia consolidado sobre Engenharia de Requisitos.

O material inclui:

- fundamentos de ER;
- elicitação;
- análise;
- especificação;
- validação;
- gerenciamento;
- RFs e RNFs;
- stakeholders;
- User Stories;
- 3Cs;
- INVEST;
- critérios de aceitação;
- rastreabilidade;
- gerenciamento de mudanças;
- riscos comuns;
- glossário;
- perguntas de revisão;
- prompts reutilizáveis.

📎 [Acessar o Miniguia de Engenharia de Requisitos](./docs/miniguia-engenharia-requisitos.md)

---

## 🧪 Engenharia de Prompts

O histórico completo dos testes, ajustes, troubleshooting e aprendizados está documentado separadamente.

📎 [Ver Engenharia de Prompts e Cicatrizes](./docs/prompt-engineering.md)

---

## 💡 Principais Aprendizados

Este projeto reforçou alguns pontos importantes sobre o uso de IA em Engenharia de Software:

- uma resposta plausível não é necessariamente verdadeira;
- requisitos específicos ainda precisam de evidência;
- métricas não devem ser inventadas apenas para tornar um RNF mensurável;
- lacunas devem gerar perguntas de elicitação;
- stakeholders continuam sendo a principal fonte de validação;
- IA pode apoiar análise, revisão e organização do conhecimento;
- supervisão humana continua essencial.

A IA se mostrou especialmente útil como ferramenta para:

- levantar possibilidades;
- encontrar ambiguidades;
- organizar conhecimento;
- revisar requisitos;
- gerar perguntas de elicitação;
- apoiar estudos e revisões.

---

## 🔁 Prompts Reutilizáveis

Algumas estruturas de prompt que se mostraram úteis durante o projeto:

### Auditoria de requisitos

> Compare cada requisito com as informações disponíveis no cenário. Classifique cada elemento como Fundamentado, Inferência Razoável ou Suposição Não Fundamentada. Para cada inferência ou suposição, formule uma pergunta de elicitação.

### Investigação de RNFs

> Identifique categorias de requisitos não funcionais que deveriam ser investigadas. Não invente métricas. Para cada informação ausente, formule uma pergunta que permita obter o dado necessário com stakeholders.

### Revisão de User Stories

> Analise as User Stories utilizando os critérios INVEST. Identifique problemas, explique sua avaliação e proponha melhorias sem introduzir necessidades de negócio que não estejam presentes no cenário.

Mais exemplos estão disponíveis no [miniguia](./docs/miniguia-engenharia-requisitos.md).

---

## 📂 Estrutura do Repositório

```text
ai-assisted-requirements-engineering/
│
├── README.md
│
└── docs/
    ├── miniguia-engenharia-requisitos.md
    └── prompt-engineering.md
```

---

## 🚀 Conclusão

O uso de Inteligência Artificial pode acelerar significativamente atividades de estudo, síntese e exploração em Engenharia de Software.

Entretanto, no contexto de Engenharia de Requisitos, existe uma diferença fundamental entre:

- algo ser possível;
- algo parecer razoável;
- algo ter sido realmente validado.

O experimento demonstrou que a IA pode apoiar a descoberta de requisitos e principalmente a identificação de lacunas, mas não substitui a participação ativa dos stakeholders.

A Engenharia de Requisitos continua sendo um processo de **investigação, comunicação, negociação e validação**.

---

## 👩‍💻 Autora

**Franciele Avibar**  
Estudante de Engenharia de Software

GitHub: [@franavibar](https://github.com/franavibar)

---

> Projeto desenvolvido para fins educacionais como parte de um desafio prático da DIO.
