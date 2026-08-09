# 🧠 Engenharia de Prompts e Cicatrizes do Processo

Este documento registra os testes de prompts realizados no Gemini Notebook durante o estudo de **Engenharia de Requisitos**.

O objetivo não foi apenas obter respostas corretas, mas observar como pequenas alterações na formulação das instruções afetavam a qualidade, a aplicabilidade e a confiabilidade das respostas produzidas pela IA.

O experimento seguiu três etapas principais:

1. exploração conceitual;
2. aplicação em um cenário prático;
3. auditoria crítica das respostas produzidas.

---

# 1. Prompt inicial — Exploração conceitual

## Prompt

> Explique o que é Engenharia de Requisitos e quais são seus principais conceitos.

## Objetivo

Avaliar como o Gemini Notebook sintetizaria o conteúdo das fontes sem fornecer instruções adicionais sobre:

- nível de profundidade;
- público-alvo;
- formato;
- aplicação prática;
- estrutura da resposta.

## Resultado observado

A resposta apresentou uma visão ampla e organizada sobre Engenharia de Requisitos, incluindo:

- elicitação;
- análise;
- especificação;
- validação;
- gerenciamento;
- requisitos funcionais;
- requisitos não funcionais;
- User Stories;
- critérios de aceitação;
- práticas ágeis.

## O que funcionou

Mesmo com um prompt bastante simples, a IA conseguiu:

- consolidar conceitos de múltiplas fontes;
- organizar o conteúdo hierarquicamente;
- estabelecer relações entre Engenharia de Requisitos tradicional e abordagens ágeis;
- produzir uma explicação tecnicamente útil para revisão.

## Limitação encontrada

A resposta ficou predominantemente **descritiva**.

Ela explicou os conceitos, mas não demonstrou como aplicá-los em uma situação real.

Isso revelou uma primeira limitação do prompt:

> pedir uma explicação conceitual não é suficiente para avaliar se o conhecimento pode ser aplicado corretamente a um problema.

Essa observação motivou o segundo experimento.

---

# 2. Prompt de aplicação — Construção de requisitos

## Cenário utilizado

> Uma pequena loja de varejo atualmente controla parte de seu estoque e de suas vendas manualmente e deseja desenvolver um sistema para digitalizar esse processo.

## Prompt

> Considere o seguinte cenário: uma pequena loja de varejo atualmente controla parte de seu estoque e de suas vendas manualmente e deseja desenvolver um sistema para digitalizar esse processo.
>
> Com base exclusivamente nas fontes fornecidas, identifique os principais stakeholders e elabore 5 requisitos funcionais e 5 requisitos não funcionais para esse sistema.
>
> Para cada requisito, explique brevemente qual necessidade ele atende. Os requisitos devem ser claros, específicos e verificáveis. Quando alguma informação necessária não estiver disponível no cenário ou nas fontes, sinalize a lacuna em vez de presumir uma resposta.

## Objetivo

Forçar a IA a sair de uma explicação teórica e aplicar os conceitos de Engenharia de Requisitos em um cenário de negócio.

Além disso, o prompt incluiu explicitamente a instrução:

> "Quando alguma informação necessária não estiver disponível, sinalize a lacuna em vez de presumir uma resposta."

A intenção era reduzir a introdução de informações não fundamentadas.

---

# 3. A cicatriz mais importante do experimento

Apesar da instrução explícita para não presumir informações ausentes, a IA introduziu diversos detalhes específicos que não estavam presentes no cenário.

Entre eles:

- tempo máximo de resposta de **2 segundos**;
- disponibilidade mínima de **99%**;
- backup automático às **23h59**;
- RTO de **4 horas**;
- RPO de **1 dia**;
- conclusão de uma venda com 3 itens em até **1 minuto**;
- limite de **5 interações**;
- exportação de relatórios em **PDF ou CSV**;
- definição de perfis específicos de acesso;
- existência de um limite mínimo configurável para estoque.

Essas especificações pareciam profissionais porque eram objetivas e mensuráveis.

Entretanto, não existiam dados suficientes no cenário para justificá-las.

## Problema identificado

O experimento revelou uma distinção importante:

> **um requisito pode parecer tecnicamente preciso e ainda assim não possuir evidência suficiente.**

Por exemplo:

```text
"O sistema deve ser rápido."
```

é um requisito ruim porque é vago.

Mas transformar essa frase automaticamente em:

```text
"O sistema deve responder em até 2 segundos."
```

também é problemático se ninguém validou que **2 segundos** representam a necessidade real do negócio.

O segundo requisito possui maior precisão textual, mas não necessariamente maior validade.

---

# 4. Prompt de auditoria

Para investigar o problema, foi utilizado um terceiro prompt no mesmo contexto.

## Prompt

> Audite criticamente os requisitos que você acabou de elaborar.
>
> Compare cada requisito com o cenário original e com as fontes fornecidas. Identifique todas as informações, regras de negócio, valores numéricos, limites, permissões, formatos, horários ou decisões de implementação que foram introduzidos sem evidência explícita no cenário.
>
> Classifique cada item como:
>
> - **Fundamentado**: diretamente sustentado pelo cenário ou pelas fontes;
> - **Inferência razoável**: plausível, mas precisa ser validada com stakeholders;
> - **Suposição não fundamentada**: informação específica criada sem evidência suficiente.
>
> Não tente corrigir os requisitos ainda. Para cada inferência ou suposição, formule uma pergunta de elicitação que deveria ser feita ao stakeholder antes de transformar aquela informação em requisito.
>
> Cite as fontes utilizadas para justificar sua avaliação.

---

# 5. Resultado da auditoria

A auditoria identificou que grande parte das informações específicas da resposta anterior deveria ser classificada como **inferência** ou **suposição não fundamentada**.

## Alguns exemplos

| Elemento | Resultado da auditoria |
|---|---|
| Tempo de resposta de 2 segundos | Suposição não fundamentada |
| Disponibilidade de 99% | Suposição não fundamentada |
| Backup às 23h59 | Suposição não fundamentada |
| RTO de 4 horas | Suposição não fundamentada |
| RPO de 1 dia | Suposição não fundamentada |
| Venda de 3 itens em 1 minuto | Suposição não fundamentada |
| Máximo de 5 interações | Suposição não fundamentada |
| Exportação em PDF/CSV | Decisão não fundamentada |
| Controle de acesso | Necessidade plausível, mas detalhes precisam de validação |
| Cadastro de produtos | Inferência razoável, mas campos e permissões precisam de elicitação |

A própria IA reconheceu que a minimalidade do cenário fazia com que muitos papéis, métricas e regras anteriormente apresentados fossem inferências ou suposições. 

---

# 6. Transformando suposições em perguntas de elicitação

Um dos resultados mais úteis da auditoria foi transformar informações inventadas em **perguntas que deveriam ser feitas aos stakeholders**.

### Desempenho

Em vez de assumir:

> O sistema deve responder em até 2 segundos.

A pergunta adequada seria:

> Qual é o tempo de atendimento aceitável no caixa para que o sistema não provoque gargalos na operação?

---

### Disponibilidade

Em vez de assumir:

> O sistema deverá possuir 99% de disponibilidade.

A pergunta seria:

> Qual é o impacto para a operação se o sistema ficar indisponível durante o expediente?

---

### Backup

Em vez de determinar automaticamente frequência, RTO e RPO:

> Quanto tempo a empresa pode permanecer sem acesso ao sistema em caso de falha?

> Qual quantidade máxima de dados recentes poderia ser perdida sem causar impacto inaceitável ao negócio?

---

### Relatórios

Em vez de decidir antecipadamente que o sistema deve exportar PDF ou CSV:

> Como os responsáveis pela loja pretendem consultar os dados de vendas?

> Eles precisam de telas, relatórios impressos, planilhas ou outro formato?

---

### Estoque

Em vez de assumir automaticamente um alerta de estoque mínimo:

> Como a empresa controla hoje o momento de realizar o reabastecimento?

> Um alerta automático realmente agrega valor ao processo?

---

# 7. Evolução dos prompts

O experimento pode ser resumido da seguinte forma:

```text
PROMPT 1
Explique o conceito.
        ↓
Boa síntese teórica
        ↓
Limitação: pouca aplicação prática


PROMPT 2
Aplique os conceitos em um cenário.
        ↓
Resposta aparentemente muito precisa
        ↓
Problema: introdução de informações não validadas


PROMPT 3
Audite evidências, inferências e suposições.
        ↓
Identificação das premissas
        ↓
Transformação das lacunas em perguntas de elicitação
```

Cada prompt não apenas buscou uma resposta melhor.

Ele foi utilizado para investigar uma limitação encontrada na etapa anterior.

---

# 8. Troubleshooting

## Problema 1 — Prompt amplo demais

### Sintoma

A primeira resposta era correta e organizada, mas muito descritiva.

### Ajuste

Introdução de um cenário prático.

### Resultado

A IA passou a aplicar os conceitos, permitindo avaliar sua capacidade de raciocínio sobre requisitos.

---

## Problema 2 — Especificidade artificial

### Sintoma

Ao solicitar requisitos "claros, específicos e verificáveis", a IA criou valores concretos mesmo quando o cenário não oferecia evidência suficiente.

### Ajuste

Criação de um prompt de auditoria com três categorias:

- Fundamentado;
- Inferência razoável;
- Suposição não fundamentada.

### Resultado

A IA conseguiu revisar criticamente a própria resposta e identificar diversas decisões prematuras.

---

## Problema 3 — Confundir possibilidade com requisito

### Sintoma

Algumas funcionalidades plausíveis foram apresentadas como se fossem necessidades já confirmadas do negócio.

Exemplos:

- relatórios;
- alertas de estoque;
- estrutura de permissões;
- formatos de exportação.

### Ajuste

Transformar essas possibilidades em perguntas de elicitação.

### Resultado

A IA passou a funcionar melhor como **apoio à descoberta de perguntas** do que como fonte definitiva de requisitos.

---

# 9. Aprendizados sobre Engenharia de Prompt

O experimento mostrou que aumentar o nível de detalhe de um prompt não garante automaticamente uma resposta mais confiável.

Algumas práticas se mostraram especialmente úteis.

## Delimitar a fonte de conhecimento

Instruções como:

> "Com base exclusivamente nas fontes fornecidas"

ajudam a reduzir o uso indiscriminado de informações externas.

---

## Solicitar identificação explícita de lacunas

Em vez de permitir que a IA complete silenciosamente informações ausentes:

> "Quando não houver informação suficiente, sinalize a lacuna."

---

## Separar evidência de inferência

Uma das técnicas mais eficazes foi solicitar uma classificação explícita:

```text
Fundamentado
Inferência razoável
Suposição não fundamentada
```

Isso tornou muito mais fácil avaliar a confiabilidade das afirmações.

---

## Pedir perguntas, não respostas inventadas

Em Engenharia de Requisitos, uma lacuna muitas vezes não deve ser preenchida pela IA.

Ela deve produzir uma pergunta.

Exemplo:

```text
❌ Qual será o RTO?
→ A IA escolhe 4 horas.

✅ Qual será o RTO?
→ A IA formula perguntas para que o stakeholder determine
   quanto tempo de indisponibilidade é aceitável.
```

---

# 10. O papel da supervisão humana

O estudo reforçou que ferramentas de IA podem apoiar atividades como:

- organização de conhecimento;
- geração de hipóteses;
- identificação de possíveis stakeholders;
- revisão de requisitos;
- criação de perguntas de elicitação;
- identificação de ambiguidades;
- revisão para estudo.

Entretanto, essas ferramentas não possuem acesso automático às necessidades reais dos stakeholders.

Por isso:

> **IA pode apoiar a Engenharia de Requisitos, mas não substitui elicitação e validação.**

A participação humana continua essencial para verificar se:

- uma necessidade realmente existe;
- uma métrica possui justificativa;
- uma prioridade representa o negócio;
- uma regra está correta;
- uma decisão técnica é apropriada.

---

# 11. Principal cicatriz

O principal aprendizado deste experimento pode ser resumido em uma frase:

> **Precisão textual não é evidência.**

Uma resposta estruturada, detalhada e convincente pode conter premissas incorretas.

O papel do usuário não é apenas melhorar o prompt até obter uma resposta mais bonita.

Também é necessário:

1. questionar de onde cada informação veio;
2. verificar quais dados possuem evidência;
3. identificar inferências;
4. expor suposições;
5. validar decisões com as pessoas que conhecem o problema real.

Essa mudança de perspectiva transformou o uso da IA neste projeto de uma simples ferramenta de geração de texto em uma ferramenta de **aprendizagem ativa e análise crítica**.

---

## 🔗 Conteúdo relacionado

O resumo dos principais conceitos estudados está disponível em:

[`miniguia-engenharia-requisitos.md`](./miniguia-engenharia-requisitos.md)

O README principal do repositório apresenta a visão geral do projeto, objetivos, fontes utilizadas e principais conclusões.
