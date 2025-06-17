# ⚠️ Justificativa Técnica – Não Utilização do Arquivo `fiscalbot_teste.ipynb`

Este notebook (`fiscalbot_teste.ipynb`) foi mantido no projeto como parte do processo iterativo de desenvolvimento, porém **não foi utilizado como solução final** por motivos técnicos detalhados a seguir.

---

## 🧪 Contexto do Notebook

O notebook `fiscalbot_teste.ipynb` foi inicialmente criado com a proposta de utilizar o agente `create_pandas_dataframe_agent` do framework **LangChain**, com o modelo **Gemini** via `langchain-google-genai`.

A intenção era integrar diretamente os DataFrames carregados a um agente que interpretasse perguntas em linguagem natural e executasse queries automáticas sobre os dados fiscais.

---

## ❌ Motivos Técnicos para Não Utilização

### 1. Incompatibilidade entre `create_pandas_dataframe_agent` e Gemini API

A estrutura interna de `create_pandas_dataframe_agent` utiliza atributos como `intermediate_steps`, `thought`, `action`, e `tool_call`, os quais são **suportados apenas por modelos como OpenAI GPT-3.5/GPT-4**, mas **não são aceitos pelos modelos da API Gemini**, resultando em:

```text
Unknown field for Part: thought
```

Essa falha decorre da ausência de suporte a mensagens intermediárias complexas no endpoint Gemini `v1` e `v1beta`, que rejeita campos fora do padrão da estrutura de prompt contínuo (como o chat da Gemini AI Studio).

---

### 2. Restrições do LangChain AgentExecutor com Gemini

Mesmo com tentativas de adaptação via `allow_dangerous_code=True`, os agentes tradicionais do LangChain **não conseguem executar fluxos baseados em raciocínio passo a passo** (chain-of-thought) com Gemini.

Além disso, chamadas assíncronas e `toolkits` de execução dinâmica são incompatíveis com o `GoogleGenerativeAI`, limitando as abordagens tradicionais de agente.

---

### 3. Decisão Estratégica: Uso de `LLMChain` com Prompt Customizado

A solução adotada neste projeto foi construir uma cadeia leve (`LLMChain`) com `PromptTemplate`, enviando resumos gerados com `pandas` como contexto para o modelo responder de forma natural.

Essa abordagem:

- ✅ Garante compatibilidade completa com Gemini
- ✅ Evita uso de campos rejeitados pela API
- ✅ Permite controle total sobre o prompt e os dados enviados
- ✅ Atende ao requisito da atividade (resposta baseada em CSV de forma autônoma)

---

## 🗂️ Por que manter este notebook no repositório?

O arquivo `fiscalbot_teste.ipynb` foi mantido por motivos de **rastreabilidade de desenvolvimento e experimentação técnica**. Ele serve como:

- Registro da tentativa de implementação com agentes tradicionais
- Documentação de erros enfrentados com Gemini + LangChain
- Material de consulta para ajustes futuros com OpenAI ou agentes compatíveis

---

## ✅ Conclusão

A decisão de **não utilizar `fiscalbot_teste.ipynb` na entrega final** foi puramente técnica, visando garantir a compatibilidade com o modelo Google Gemini e cumprir todos os requisitos da atividade com estabilidade, segurança e clareza operacional.

