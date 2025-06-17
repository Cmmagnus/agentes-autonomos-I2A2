# 📘 Manual de Execução – FiscalBot Gemini

## 🧰 Requisitos

- Python 3.8 ou superior
- Conexão com a internet
- Conta no [Google AI Studio](https://makersuite.google.com/) para gerar a chave da API Gemini

---

## 🛠️ Etapas para execução

1. Instale as dependências do projeto:
```bash
pip install -r requirements.txt
```

2. Extraia os arquivos CSV e coloque-os na pasta:
```
data/202401_NFs/
```

3. Crie um arquivo `.env` com o seguinte conteúdo:
```env
GEMINI_API_KEY=sua_chave_gerada_no_google
```

4. Abra o notebook `fiscalbot_gemini.ipynb` no VS Code (com Jupyter extension) ou no ambiente Jupyter de sua preferência.

5. Execute as células sequencialmente.  
   Ao final, interaja com o agente utilizando linguagem natural. Exemplos:
   - "Qual o item com maior quantidade entregue?"
   - "Qual fornecedor recebeu o maior valor em janeiro?"
   - "Quantas notas fiscais foram emitidas no dia 2024-01-10?"
   - "Qual a média do valor total das notas?"

---

## 📌 Observações

- O modelo utilizado foi `gemini-1.5-flash`, gratuito e compatível com contas Google padrão.
- A aplicação utiliza o framework `LangChain`, integrando `LLMChain` e `PromptTemplate` para gerar respostas contextuais baseadas nos dados do CSV.
- Não utilizamos agentes tradicionais (`create_pandas_dataframe_agent`) para evitar incompatibilidades com o Gemini.

---
