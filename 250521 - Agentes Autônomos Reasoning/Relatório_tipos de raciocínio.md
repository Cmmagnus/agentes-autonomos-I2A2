# Agentes Autônomos – Reasoning

## 1. Nome do Grupo

> GRUPO_5

## 2. Participantes

| Nome Completo          | Telefone          | E-mail                         | Contribuiu com a Atividade? |
| ---------------------- | ----------------- | ------------------------------ | --------------------------- |
| Carlos Magno Marcelino | +55 11 98949-8106 | cmmarcelinus@gmail.com         | ✅ Sim                      |
| Ewerton                | +55 22 98870-9994 | bomsensoink@gmail.com          | ✅ Sim                      |
| Luis Antônio           | +55 69 99260-4163 | luisantoniocostaneto@gmail.com | ✅ Sim                      |
| Vivian                 | +55 11 98488-2650 | vivian.ruiz74@gmail.com        | ✅ Sim                      |
| Ivan                   | +55 63 98121-0234 |                                | ⬜ Não                      |
| Lucas L                | +55 12 98163-1975 |                                | ⬜ Não                      |
| Márcio Ferreira        | +55 66 99910-4231 |                                | ⬜ Não                      |
| Martins                | +244 932 964 743  |                                | ⬜ Não                      |

---

## 3. Métodos de Raciocínio Estudados

### 3.1 Raciocínio Dedutivo

- **Descrição:** Aplica uma regra geral a um caso específico para chegar a uma conclusão lógica.
- **Aplicação Fiscal:** Ideal para agentes que validam regras tributárias fixas, como a correspondência entre CFOP e tipo de operação.
- **Exemplo Testado:** "Se toda venda interna deve usar CFOP começando com 5, e a nota apresenta CFOP 6.101, essa operação está correta?"

---

### 3.2 Raciocínio Indutivo

- **Descrição:** Baseia-se em várias observações para formular uma regra geral.
- **Aplicação Fiscal:** Útil para aprender padrões de comportamento fiscal com base no histórico de documentos (ex: uso repetido de CFOP).
- **Exemplo Testado:** "Todas as notas anteriores com CFOP 5.102 foram de venda dentro do estado. Podemos considerar que esse CFOP representa esse tipo de operação?"

---

### 3.3 Raciocínio Abdutivo

- **Descrição:** Parte de um fato observado (efeito) e sugere hipóteses para sua causa.
- **Aplicação Fiscal:** Ajuda o agente a diagnosticar possíveis falhas, como erros de CST, CFOP ou cálculos incorretos.
- **Exemplo Testado:** "O valor do ICMS está abaixo do esperado em uma nota. Quais podem ser as causas prováveis?"

---

### 3.4 Raciocínio Baseado em Casos (CBR)

- **Descrição:** Usa situações anteriores resolvidas para lidar com novos casos semelhantes.
- **Aplicação Fiscal:** Permite ao agente aprender com o histórico de erros e aplicar correções automaticamente.
- **Exemplo Testado:** "Notas de devolução anteriores apresentaram erro ao usar CFOP 5.102 ao invés de 5.202. Se uma nova nota repete esse CFOP, como agir com base no histórico?"

---

## 4. Testes Realizados

### 4.1 Cenário Geral

> As perguntas foram realizadas utilizando modelos de linguagem generativa (LLMs) como **ChatGPT (GPT-4o)**, **Grok (XAI)** e **Gemini Flash 2.0 (Google)**.  
> O objetivo foi testar a capacidade desses agentes em aplicar diferentes tipos de raciocínio (dedutivo, indutivo, abdutivo e baseado em casos) em situações reais de análise de documentos fiscais eletrônicos.  
> Os testes simulam erros e padrões típicos de CFOP, ICMS e devoluções em notas fiscais eletrônicas (NF-e), avaliando como os agentes poderiam contribuir com automação e inteligência contábil.

---

### 4.2 Testes e Resultados

#### 🔹 Raciocínio Dedutivo

- **Pergunta utilizada:**  
  _"Sabemos que, segundo a legislação vigente, toda nota fiscal de venda para consumidor final dentro do mesmo estado deve ter CFOP iniciado por 5. Se uma nota fiscal de venda tem CFOP 6.101, essa operação está correta? Justifique com base na regra."_

- **Modelos utilizados e análise:**

  - **ChatGPT (GPT-4o):** Aplicou corretamente a lógica dedutiva, identificando o uso incorreto do CFOP 6.101. Fundamentou com base no Manual do Contribuinte e sugeriu automatização.
  - **Grok:** Reforçou as premissas fiscais com clareza, explicando a diferença entre operações interestaduais e internas.
  - **Gemini Flash 2.0:** Aplicou as premissas dedutivas corretamente e ainda relacionou com a Emenda Constitucional 87/2015 (DIFAL), mostrando bom domínio fiscal.

- **Conclusão:**  
  Todos os modelos demonstraram **boa capacidade de aplicar regras fixas**, sendo eficazes para sistemas automatizados de validação fiscal.

---

#### 🔹 Raciocínio Indutivo

- **Pergunta utilizada:**  
  _"Observe os seguintes CFOPs em notas anteriores: 5.102, 5.102, 5.102, 5.102, 5.102. Todas são operações de venda de mercadoria dentro do estado. Podemos dizer que o CFOP 5.102, em geral, se refere a esse tipo de operação? Por quê?"_

- **Modelos utilizados e análise:**

  - **ChatGPT (GPT-4o):** Inferiu corretamente que o CFOP 5.102 costuma representar venda de mercadoria adquirida de terceiros, com ressalvas quanto à indução.
  - **Grok:** Fez uma inferência bem estruturada e sustentada pela tabela de CFOPs do CONFAZ.
  - **Gemini Flash 2.0:** Construiu uma generalização lógica e explicou os limites do raciocínio indutivo no contexto fiscal.

- **Conclusão:**  
  As LLMs foram eficazes na generalização com base em padrões, mas **reconheceram limitações da indução**. Esse raciocínio pode ser útil para detectar tendências de uso incorreto de códigos.

---

#### 🔹 Raciocínio Abdutivo

- **Pergunta utilizada:**  
  _"Uma nota fiscal apresenta um valor de ICMS muito abaixo do esperado, considerando o total dos produtos e a alíquota. Quais poderiam ser as causas prováveis desse erro? Liste hipóteses possíveis e explique."_

- **Modelos utilizados e análise:**

  - **ChatGPT (GPT-4o):** Listou múltiplas hipóteses plausíveis como erro no CST, base de cálculo, aplicação de isenção, ou erro sistêmico. Resposta bem estruturada.
  - **Grok:** Apresentou hipóteses bem detalhadas com exemplos práticos e explicações técnicas.
  - **Gemini Flash 2.0:** Organizou as hipóteses por tipo de erro, com forte embasamento fiscal e sugestões de investigação.

- **Conclusão:**  
  O raciocínio abdutivo foi **muito bem representado pelas LLMs**, que se mostraram capazes de atuar como “diagnosticadores” de falhas fiscais e sugerir causas prováveis com base em evidências.

---

#### 🔹 Raciocínio Baseado em Casos (CBR)

- **Pergunta utilizada:**  
  _"Em uma situação passada, identificamos que um erro comum nas notas fiscais de devolução era o uso incorreto do CFOP, utilizando 5.102 no lugar de 5.202. Se encontrarmos hoje uma nova nota de devolução com CFOP 5.102, o que podemos concluir com base nesse histórico? Como o sistema pode agir automaticamente nesse caso?"_

- **Modelos utilizados e análise:**

  - **ChatGPT (GPT-4o):** Aplicou com precisão a lógica CBR, sugerindo alertas automáticos, bloqueios e registros de reincidência.
  - **Grok:** Reproduziu fielmente o padrão do erro anterior e propôs ações automatizadas, reforçando o uso de workflows e auditoria interna.
  - **Gemini Flash 2.0:** Estruturou o raciocínio em etapas (recuperação, comparação, conclusão e ação), com recomendações detalhadas de prevenção e validação automatizada.

- **Conclusão:**  
  Todos os modelos demonstraram **capacidade avançada de aprender com casos anteriores**, sendo aplicáveis a sistemas de automação com memória de histórico e aprendizado contínuo.

---

### 4.3 Comparativo entre LLMs Utilizadas

A seguir, apresentamos uma análise comparativa entre os modelos de linguagem utilizados no experimento (ChatGPT, Grok e Gemini), considerando aspectos como clareza da resposta, profundidade técnica, aplicabilidade prática e capacidade de generalização ou raciocínio adaptativo.

---

#### 🧠 ChatGPT (GPT-4o)

**Pontos Fortes:**

- Excelente estrutura de resposta, com organização lógica clara (premissas → análise → conclusão).
- Linguagem acessível e técnica ao mesmo tempo.
- Respostas complementadas com sugestões de automação, regras de RPA ou códigos simples.
- Capacidade de contextualizar a legislação fiscal com fluidez.

**Pontos Fracos:**

- Em alguns casos, a resposta foi mais voltada para **clareza didática** do que para **profundidade tributária**.
- Depende do nível de contexto fornecido: respostas podem variar em completude se o prompt não for bem estruturado.

---

#### 🧠 Grok (XAI)

**Pontos Fortes:**

- Respostas **altamente técnicas e completas**, especialmente nos raciocínios abdutivo e baseado em casos.
- Fundamentação consistente em legislação fiscal brasileira e boas práticas contábeis.
- Oferece detalhamento com **justificativas e fluxos automatizáveis** em linguagem empresarial.

**Pontos Fracos:**

- Linguagem ligeiramente mais densa, exigindo mais atenção para leitura.
- Em alguns testes, foi mais expositivo do que interativo (menos sugestões proativas de automação).
- Pode repetir explicações já óbvias, tornando a resposta extensa.

---

#### 🧠 Gemini Flash 2.0

**Pontos Fortes:**

- Respostas **objetivas, bem estruturadas e juridicamente fundamentadas**.
- Ótima capacidade de **simular o raciocínio jurídico-fiscal**, com foco em CFOP, CST e ICMS.
- Fez boa distinção entre cenários (ex: diferenciar venda x devolução) e sugeriu validações automatizadas.

**Pontos Fracos:**

- Algumas respostas foram mais conservadoras, sem extrapolar sugestões práticas como automação via código ou ferramentas.
- Apesar de corretas, nem todas as conclusões trouxeram diferencial criativo (ex: modelo de ação ou script).

---

### 🏁 Considerações Finais da Comparação

| Critério                        | ChatGPT (GPT-4o) | Grok       | Gemini Flash 2.0 |
| ------------------------------- | ---------------- | ---------- | ---------------- |
| Clareza e didática              | ⭐⭐⭐⭐⭐       | ⭐⭐⭐⭐   | ⭐⭐⭐⭐         |
| Profundidade técnica            | ⭐⭐⭐⭐         | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐         |
| Sugestões práticas de automação | ⭐⭐⭐⭐⭐       | ⭐⭐⭐⭐   | ⭐⭐⭐           |
| Capacidade de diagnóstico       | ⭐⭐⭐⭐         | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐         |
| Adaptação a casos reais         | ⭐⭐⭐⭐         | ⭐⭐⭐⭐   | ⭐⭐⭐⭐         |
| Linguagem acessível             | ⭐⭐⭐⭐⭐       | ⭐⭐⭐     | ⭐⭐⭐⭐         |

> **Conclusão do comparativo:**  
> Todos os modelos se mostraram eficazes nos testes. O ChatGPT se destacou pela **clareza e aplicabilidade imediata**, Grok pela **robustez técnica e precisão**, e Gemini pela **fundamentação legal objetiva e confiável**. A combinação dos três oferece uma perspectiva rica para a construção de agentes fiscais inteligentes e auditáveis.

---

## 5. Conclusão

O experimento realizado com diferentes LLMs (ChatGPT, Grok e Gemini) permitiu avaliar como modelos de linguagem podem aplicar diferentes formas de raciocínio — dedutivo, indutivo, abdutivo e baseado em casos — para analisar documentos fiscais eletrônicos de forma inteligente e automatizada.

### Principais conclusões:

- **Raciocínio Dedutivo** foi o mais consistente entre os modelos, sendo ideal para **validações de regras fiscais fixas** (como CFOPs e CSTs obrigatórios). Todos os modelos conseguiram aplicar essa lógica com clareza e correção.

- **Raciocínio Indutivo** mostrou-se útil para detectar **padrões recorrentes** em documentos fiscais, mas com ressalvas, pois a indução depende fortemente de histórico suficiente para evitar generalizações incorretas.

- **Raciocínio Abdutivo** foi extremamente eficaz para **diagnosticar anomalias fiscais**, como valores de ICMS incorretos. Os modelos listaram hipóteses variadas e técnicas, mostrando grande potencial para uso em sistemas de auditoria automática.

- **Raciocínio Baseado em Casos (CBR)** demonstrou ser uma abordagem valiosa para **aprendizado contínuo de erros passados**, com possibilidade de aplicar correções automáticas em sistemas integrados com histórico.

A análise comparativa entre os modelos revelou que:

- O **ChatGPT (GPT-4o)** é forte em clareza, organização e sugestão de automação.
- O **Grok** oferece um nível técnico elevado, ideal para aplicações em auditoria e compliance.
- O **Gemini Flash 2.0** se destacou pela fundamentação legal e foco na conformidade.

### Implicações para o projeto final:

Este estudo validou o uso de LLMs como **motores de raciocínio fiscal autônomo**, demonstrando que é viável construir agentes inteligentes que reduzem erros, otimizam tempo e aumentam a conformidade tributária. Os aprendizados aqui servirão de base para o desenvolvimento das próximas fases do projeto, que incluirá automações práticas e integração com documentos reais ou simulados.

---

## 6. Referências Bibliográficas

- Slides da aula de 15/05/2025 – Curso de Inteligência Artificial e Agentes Autônomos
- Manual de Orientação do Contribuinte – NF-e
- Tabela de CFOP – CONFAZ
- Emenda Constitucional nº 87/2015 (DIFAL)
- ChatGPT (GPT-4o) – https://chat.openai.com
- Gemini Flash 2.0 – https://gemini.google.com
- Grok (XAI/Elon Musk) – https://grok.com/
- Documentação fiscal da SEFAZ/SP
- Ajuste SINIEF 01/2024
