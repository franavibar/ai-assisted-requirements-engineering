# 📘 Miniguia de Estudo — Engenharia de Requisitos

Este miniguia foi desenvolvido como parte de um experimento de **aprendizagem assistida por Inteligência Artificial**, utilizando o Gemini Notebook para estudar e consolidar conceitos fundamentais de Engenharia de Requisitos.

O conteúdo foi produzido a partir das fontes selecionadas para o projeto e posteriormente revisado criticamente, buscando transformar a IA em uma ferramenta de apoio ao aprendizado — e não apenas em um gerador de respostas.

---

## 📑 Sumário

1. [O que é Engenharia de Requisitos?](#1-o-que-é-engenharia-de-requisitos)
2. [Processo de Engenharia de Requisitos](#2-processo-de-engenharia-de-requisitos)
3. [Requisitos Funcionais e Não Funcionais](#3-requisitos-funcionais-e-não-funcionais)
4. [Stakeholders](#4-stakeholders)
5. [User Stories, 3Cs e INVEST](#5-user-stories-3cs-e-invest)
6. [Critérios de Aceitação](#6-critérios-de-aceitação)
7. [Rastreabilidade e Gerenciamento de Mudanças](#7-rastreabilidade-e-gerenciamento-de-mudanças)
8. [Principais Erros e Riscos](#8-principais-erros-e-riscos)
9. [Glossário](#9-glossário)
10. [Perguntas de Revisão](#10-perguntas-de-revisão)
11. [Prompts Reutilizáveis](#11-prompts-reutilizáveis)

---

# 1. O que é Engenharia de Requisitos?

Segundo o **SWEBOK (Software Engineering Body of Knowledge)**, requisitos de software expressam necessidades e restrições impostas a um produto de software para contribuir com a solução de um problema do mundo real.

A **Engenharia de Requisitos (ER)** é a área da Engenharia de Software responsável pelas atividades de:

- elicitação;
- análise;
- especificação;
- validação;
- gerenciamento de requisitos.

Essas atividades acompanham o ciclo de vida do produto e ajudam a estabelecer um entendimento compartilhado entre stakeholders e equipe técnica.

## Por que ela é importante?

Problemas relacionados aos requisitos podem resultar em:

- retrabalho;
- atrasos;
- aumento de custos;
- escopo inadequado;
- sistemas que não atendem às necessidades dos usuários;
- defeitos descobertos apenas em fases avançadas do desenvolvimento.

Um software tecnicamente bem construído ainda pode fracassar caso resolva o problema errado.

### Abordagem tradicional x abordagem ágil

Em abordagens tradicionais, é comum tentar definir e documentar grande parte dos requisitos antes do desenvolvimento.

Em abordagens ágeis, os requisitos podem evoluir de maneira **iterativa e incremental**, conforme aumenta o conhecimento sobre o produto, o negócio e os usuários.

Uma ideia importante nesse contexto é:

> **Just Enough, Just in Time**

Ou seja: detalhar o necessário no momento em que aquele conhecimento realmente passa a ser necessário.

---

# 2. Processo de Engenharia de Requisitos

Embora possam ser apresentadas separadamente para fins de estudo, as atividades da Engenharia de Requisitos possuem forte relação entre si e podem ocorrer de maneira iterativa.

```text
Elicitação
    ↓
Análise
    ↓
Especificação
    ↓
Validação
    ↓
Gerenciamento e evolução
```

## 2.1 Elicitação

A **elicitação de requisitos** busca descobrir necessidades, objetivos, restrições e regras do domínio junto aos stakeholders e outras fontes relevantes.

Algumas técnicas utilizadas incluem:

- entrevistas;
- questionários;
- workshops;
- observação;
- cenários;
- prototipagem;
- histórias de usuário.

### Conhecimento tácito

Um dos grandes desafios da elicitação é o **conhecimento tácito**.

Trata-se de informações que os stakeholders possuem, mas não necessariamente verbalizam, seja porque consideram determinado processo óbvio, seja porque têm dificuldade de descrevê-lo.

Por isso, perguntar apenas:

> "O que o sistema precisa fazer?"

raramente é suficiente.

O profissional responsável pela elicitação precisa investigar processos, exceções, problemas atuais, objetivos e necessidades que podem não aparecer espontaneamente durante uma conversa.

---

## 2.2 Análise

A análise examina os requisitos coletados para verificar aspectos como:

- consistência;
- viabilidade;
- ausência de ambiguidades;
- conflitos;
- prioridades;
- testabilidade;
- limites do sistema.

Também pode envolver modelagem e negociação entre diferentes stakeholders.

---

## 2.3 Especificação

A especificação transforma necessidades analisadas em representações estruturadas e compreensíveis.

Dependendo do contexto, podem existir diferentes níveis de documentação, como:

- especificações orientadas ao usuário;
- especificações de requisitos de software;
- especificações mais amplas de sistema.

Uma **Software Requirements Specification (SRS)** documenta os comportamentos esperados do software e suas restrições relevantes.

---

## 2.4 Validação

A validação procura responder:

> **Estamos especificando o sistema que os stakeholders realmente precisam?**

Algumas formas de validação incluem:

- revisões;
- inspeções;
- protótipos;
- simulações;
- testes de aceitação;
- demonstrações incrementais aos usuários.

Validar requisitos antes ou durante o desenvolvimento reduz o risco de descobrir tarde que uma funcionalidade foi construída a partir de uma interpretação incorreta.

---

## 2.5 Gerenciamento

Requisitos mudam.

Por isso, a Engenharia de Requisitos também envolve:

- controle de mudanças;
- versionamento;
- priorização;
- rastreabilidade;
- análise de impacto;
- manutenção das informações associadas aos requisitos.

O objetivo não é impedir mudanças, mas compreender e administrar seus efeitos.

---

# 3. Requisitos Funcionais e Não Funcionais

## Requisitos Funcionais — RF

Os **Requisitos Funcionais** descrevem **o que o sistema deve fazer**.

Podem representar:

- operações;
- cálculos;
- processamento de dados;
- interações com usuários;
- fluxos de negócio;
- respostas do sistema a determinadas entradas.

Uma forma simples de visualizá-los é:

```text
Entrada → Comportamento do sistema → Saída
```

### Exemplo

> O sistema deve permitir que um usuário autorizado registre uma nova venda.

A funcionalidade esperada está explicitamente descrita.

---

## Requisitos Não Funcionais — RNF

Os **Requisitos Não Funcionais** descrevem atributos de qualidade, níveis de serviço e restrições relevantes para o funcionamento da solução.

Podem envolver:

- desempenho;
- segurança;
- disponibilidade;
- confiabilidade;
- usabilidade;
- escalabilidade;
- portabilidade;
- integridade de dados.

### Exemplo ruim

> O sistema deve ser rápido.

O requisito é subjetivo e não oferece uma condição clara de validação.

### Exemplo mensurável

> A consulta deverá apresentar o resultado dentro do limite de tempo definido e validado com os stakeholders para o contexto operacional.

O valor concreto dessa métrica deve ser definido com base nas necessidades reais do projeto.

> **Importante:** tornar um requisito mensurável não significa inventar uma métrica. O valor precisa possuir justificativa e ser validado com os stakeholders.

Esse ponto se tornou especialmente importante durante o experimento deste projeto: a IA conseguiu produzir RNFs aparentemente precisos ao introduzir métricas que não estavam presentes no cenário original.

---

# 4. Stakeholders

Um **stakeholder** é uma pessoa, grupo ou organização que pode afetar ou ser afetada pelas decisões, atividades ou resultados de um projeto.

Dependendo do contexto, podem existir stakeholders relacionados a:

- negócio;
- gestão;
- operação;
- desenvolvimento;
- testes;
- usuários finais;
- especialistas de domínio;
- conformidade ou regulamentação.

Nenhum stakeholder isoladamente representa necessariamente todas as formas de uso do sistema.

## Análise de stakeholders

Algumas ferramentas podem auxiliar nesse processo.

### Power/Interest Grid

Classifica stakeholders de acordo com:

- poder de influência;
- interesse no projeto.

Isso ajuda a planejar como cada grupo deve ser envolvido e comunicado.

### RACI / RASCI

Pode ser utilizada para explicitar responsabilidades:

- **R — Responsible**
- **A — Accountable**
- **S — Support**
- **C — Consulted**
- **I — Informed**

A identificação correta dos stakeholders é fundamental para uma boa elicitação de requisitos.

---

# 5. User Stories, 3Cs e INVEST

## User Stories

Uma **User Story** é uma descrição curta de uma necessidade apresentada sob a perspectiva de quem receberá valor com determinada funcionalidade.

Um formato bastante utilizado é:

> **Como um** [papel],  
> **eu quero** [funcionalidade],  
> **para que** [benefício/valor].

### Exemplo

> Como gerente da loja, quero consultar os produtos com estoque baixo para que possa planejar o reabastecimento.

A User Story não deve funcionar como um contrato rígido ou substituir todas as conversas sobre o requisito.

Ela serve como ponto de partida para colaboração e refinamento.

---

## Modelo dos 3Cs

O modelo dos **3Cs** descreve três componentes importantes de uma User Story.

### Card

O registro curto da necessidade.

### Conversation

As conversas realizadas entre stakeholders e equipe para compreender e refinar o requisito.

### Confirmation

As condições que permitem confirmar se a necessidade foi atendida, normalmente expressas por meio de critérios de aceitação.

```text
CARD
  ↓
CONVERSATION
  ↓
CONFIRMATION
```

A história escrita é apenas uma parte do processo. A compreensão do requisito emerge principalmente das conversas e da validação.

---

## INVEST

O acrônimo **INVEST** ajuda a avaliar a qualidade de uma User Story:

| Letra | Critério | Significado |
|---|---|---|
| I | Independent | Independente |
| N | Negotiable | Negociável |
| V | Valuable | Valiosa |
| E | Estimable | Estimável |
| S | Small | Pequena |
| T | Testable | Testável |

Uma história que não consegue ser testada, estimada ou associada a algum valor pode precisar de refinamento.

---

# 6. Critérios de Aceitação

Os **Critérios de Aceitação** estabelecem condições claras e testáveis para determinar se determinada funcionalidade atende às expectativas estabelecidas.

Eles devem descrever **o que precisa ser verdadeiro para a funcionalidade ser aceita**, e não obrigatoriamente como ela deverá ser implementada.

### Exemplo subjetivo

> A busca deve ser rápida.

### Exemplo testável

> Dado que o usuário realizou uma consulta, quando o sistema processar a solicitação, então o resultado deverá respeitar o limite de desempenho previamente acordado para esse fluxo.

A métrica utilizada deve ser validada no contexto real.

---

## Acceptance Criteria x Definition of Done

Embora relacionados à qualidade da entrega, os conceitos possuem propósitos diferentes.

| | Acceptance Criteria | Definition of Done |
|---|---|---|
| **Escopo** | Funcionalidade ou história específica | Aplicável aos itens entregues pelo time |
| **Foco** | Comportamento e necessidade de negócio | Qualidade e práticas técnicas |
| **Pergunta** | Esta funcionalidade atende ao esperado? | Este trabalho atende ao padrão de conclusão do time? |

Um critério de aceitação pode determinar o comportamento necessário para uma funcionalidade específica.

A **Definition of Done (DoD)** pode envolver práticas técnicas acordadas pelo time, como testes, revisão de código e outros critérios de qualidade.

---

# 7. Rastreabilidade e Gerenciamento de Mudanças

## Rastreabilidade

A **rastreabilidade de requisitos** permite acompanhar a origem e a evolução de um requisito ao longo do ciclo de vida.

### Backward Traceability

Permite voltar à origem do requisito.

Exemplo:

```text
Requisito → Necessidade de negócio → Stakeholder
```

### Forward Traceability

Permite acompanhar o requisito em direção à implementação e validação.

Exemplo:

```text
Requisito → Design → Código → Testes
```

Essa relação ajuda em atividades como:

- análise de impacto;
- cobertura de testes;
- gerenciamento de mudanças;
- investigação de origem de funcionalidades.

---

## Gerenciamento de mudanças

Mudanças nos requisitos são esperadas à medida que o conhecimento sobre o produto e o negócio evolui.

Antes de implementar uma alteração, é importante avaliar:

1. Qual requisito será alterado?
2. Qual necessidade originou esse requisito?
3. Quais outros requisitos dependem dele?
4. Quais componentes podem ser impactados?
5. Quais testes precisarão ser atualizados?
6. Quem precisa aprovar ou ser informado sobre a mudança?

O objetivo é evitar que uma alteração aparentemente pequena produza consequências inesperadas em outras partes da solução.

---

# 8. Principais Erros e Riscos

## 8.1 Negligenciar requisitos não funcionais

Concentrar-se somente nas funcionalidades visíveis pode fazer com que aspectos como segurança, desempenho ou escalabilidade sejam descobertos tarde demais.

Dependendo da solução, RNFs podem influenciar decisões arquiteturais importantes.

---

## 8.2 Criar requisitos vagos

Exemplos:

> "O sistema deve ser intuitivo."

> "O sistema precisa ser rápido."

> "A aplicação deve ser segura."

Essas declarações não possuem critérios objetivos de validação.

O caminho adequado é investigar o que **intuitivo**, **rápido** ou **seguro** significa naquele contexto específico.

---

## 8.3 Criar precisão sem evidência

O problema inverso também existe.

Transformar:

> "O sistema deve ser rápido."

em:

> "O sistema deve responder em exatamente 2 segundos."

não resolve o problema caso ninguém tenha determinado que **2 segundos** é a necessidade real.

Uma especificação pode parecer tecnicamente melhor por possuir números e ainda assim estar baseada em uma premissa falsa.

---

## 8.4 Especificar detalhes cedo demais

Tentar definir antecipadamente todos os detalhes de uma solução pode:

- aumentar documentação desnecessária;
- gerar requisitos obsoletos;
- limitar alternativas de implementação;
- criar retrabalho quando o negócio mudar.

---

## 8.5 Ignorar conhecimento tácito

Stakeholders nem sempre mencionam espontaneamente exceções, regras ou processos que fazem parte de sua rotina.

Uma elicitação superficial pode produzir requisitos incompletos.

---

## 8.6 User Stories sem valor ou confirmação

Uma User Story não deve ser apenas uma tarefa técnica.

Exemplo problemático:

> Criar tabela de usuários no banco de dados.

Essa frase descreve uma atividade técnica, mas não explica quem recebe valor ou qual necessidade está sendo atendida.

Além disso, histórias sem critérios de aceitação dificultam determinar quando a necessidade foi realmente satisfeita.

---

# 9. Glossário

| Termo | Definição |
|---|---|
| **Acceptance Criteria** | Condições claras e testáveis utilizadas para avaliar se uma funcionalidade atende ao comportamento esperado. |
| **Business Analyst (BA)** | Profissional que facilita a comunicação entre necessidades de negócio e solução, apoiando atividades como elicitação e análise de requisitos. |
| **Card** | Registro curto de uma User Story que funciona como lembrete da necessidade. |
| **Confirmation** | Condições utilizadas para confirmar que a necessidade representada pela User Story foi atendida. |
| **Conversation** | Discussão colaborativa utilizada para compreender e refinar uma User Story. |
| **Definition of Done (DoD)** | Conjunto compartilhado de critérios que estabelece o padrão de conclusão do trabalho. |
| **Elicitação** | Processo de descoberta e obtenção de necessidades, objetivos, restrições e informações relevantes para os requisitos. |
| **INVEST** | Critérios utilizados para avaliar User Stories: Independent, Negotiable, Valuable, Estimable, Small e Testable. |
| **Product Backlog** | Lista dinâmica e ordenada de itens necessários para evolução de um produto. |
| **Requisito Funcional** | Descreve uma função ou comportamento que o sistema deve executar. |
| **Requisito Não Funcional** | Descreve atributo de qualidade, nível de serviço ou restrição relevante para o sistema. |
| **SRS** | Software Requirements Specification; documento estruturado de especificação de requisitos de software. |
| **Stakeholder** | Pessoa, grupo ou organização que pode afetar ou ser afetada pelo projeto. |
| **Tacit Knowledge** | Conhecimento existente no domínio ou entre stakeholders que não é necessariamente verbalizado de maneira espontânea. |
| **Traceability** | Capacidade de acompanhar a origem, relações e evolução de um requisito ao longo do ciclo de vida. |
| **User Story** | Representação curta de uma necessidade sob a perspectiva de quem recebe valor. |

---

# 10. Perguntas de Revisão

### 1. O que é Engenharia de Requisitos?

É a área da Engenharia de Software relacionada à elicitação, análise, especificação, validação e gerenciamento de requisitos durante o ciclo de vida do software.

### 2. Qual é a diferença básica entre RF e RNF?

Um requisito funcional descreve **o que o sistema deve fazer**, enquanto um requisito não funcional estabelece atributos de qualidade, níveis de serviço ou restrições relevantes.

### 3. O que é conhecimento tácito?

É o conhecimento que stakeholders possuem sobre determinado domínio ou processo, mas que não necessariamente verbalizam espontaneamente durante a elicitação.

### 4. O que representam os 3Cs?

**Card, Conversation e Confirmation.**

O cartão registra a necessidade, a conversa permite seu refinamento e a confirmação estabelece como verificar que ela foi atendida.

### 5. O que significa INVEST?

- Independent
- Negotiable
- Valuable
- Estimable
- Small
- Testable

### 6. Qual é a diferença entre Acceptance Criteria e Definition of Done?

Os critérios de aceitação são relacionados ao comportamento esperado de uma funcionalidade específica. A Definition of Done representa padrões compartilhados de conclusão e qualidade aplicáveis ao trabalho do time.

### 7. Para que serve a rastreabilidade?

Para relacionar requisitos às suas origens e acompanhar sua evolução até elementos posteriores, como design, implementação e testes.

### 8. Por que requisitos vagos são problemáticos?

Porque dificultam a validação objetiva e podem gerar interpretações diferentes entre stakeholders e equipe.

### 9. Por que simplesmente adicionar números a um RNF não garante sua qualidade?

Porque a métrica precisa representar uma necessidade ou restrição real. Um número arbitrário cria apenas uma falsa sensação de precisão.

### 10. Por que os requisitos mudam?

Porque o conhecimento sobre usuários, negócio, tecnologia e solução evolui ao longo do projeto. O gerenciamento de requisitos deve permitir compreender e controlar os impactos dessas mudanças.

---

# 11. Prompts Reutilizáveis

Os prompts abaixo podem ser reutilizados em futuras sessões de estudo com ferramentas de IA.

## Prompt 1 — Avaliação com INVEST

> Considere que sou estudante de Engenharia de Software. Analise as User Stories abaixo utilizando os critérios INVEST (Independent, Negotiable, Valuable, Estimable, Small e Testable). Identifique problemas, explique sua avaliação e proponha melhorias sem introduzir necessidades de negócio que não estejam presentes no cenário.

---

## Prompt 2 — Requisitos Não Funcionais

> Analise o cenário apresentado e identifique possíveis categorias de requisitos não funcionais que deveriam ser investigadas. Não invente métricas ou limites. Para cada informação ausente, formule uma pergunta de elicitação que permita obter o dado necessário junto aos stakeholders.

---

## Prompt 3 — Simulação de Elicitação

> Atue como um stakeholder especialista no domínio de [DOMÍNIO]. Eu serei responsável pela elicitação de requisitos. Responda somente às informações que minhas perguntas forem capazes de descobrir e mantenha conhecimentos tácitos até que eu formule perguntas adequadas. Ao final, avalie quais perguntas foram mais eficazes.

---

## Prompt 4 — Critérios de Aceitação

> Com base exclusivamente no cenário e na User Story fornecidos, proponha critérios de aceitação claros e testáveis. Diferencie os critérios específicos da funcionalidade dos itens que deveriam pertencer à Definition of Done do time. Sinalize qualquer informação ausente que precise ser validada antes de criar um critério objetivo.

---

## Prompt 5 — Auditoria de Suposições

> Audite os requisitos apresentados e compare cada afirmação com as informações disponíveis no cenário. Classifique cada elemento como Fundamentado, Inferência Razoável ou Suposição Não Fundamentada. Para cada inferência ou suposição, formule uma pergunta de elicitação que deveria ser respondida antes de transformar aquela informação em requisito.

---

# 💡 Principal aprendizado

A utilização de IA pode acelerar atividades de estudo, síntese, exploração e análise de requisitos. Entretanto, respostas bem estruturadas e tecnicamente plausíveis não devem ser confundidas com requisitos validados.

Durante o experimento deste projeto, a IA foi capaz de gerar requisitos não funcionais aparentemente precisos, incluindo métricas de desempenho, disponibilidade, backup e usabilidade, mesmo quando esses valores não estavam presentes no cenário fornecido.

Ao ser submetida a uma etapa posterior de auditoria, a própria ferramenta identificou diversas dessas informações como **inferências ou suposições não fundamentadas**.

O experimento reforçou uma distinção importante:

> **Precisão textual não é evidência.**

A IA pode ajudar a identificar possibilidades, organizar conhecimento e até revelar perguntas que ainda precisam ser feitas. A definição de requisitos, entretanto, continua dependendo de **contexto, elicitação, validação e participação dos stakeholders**.

---

## 📚 Sobre este material

Este miniguia integra o projeto **AI-Assisted Requirements Engineering**, desenvolvido como atividade prática de aprendizagem ativa sobre Engenharia de Requisitos e uso crítico de Inteligência Artificial.

O processo completo de engenharia de prompts, incluindo os testes, limitações encontradas e refinamentos realizados durante o experimento, está documentado separadamente no repositório.
