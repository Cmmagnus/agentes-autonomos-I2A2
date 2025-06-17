# 🤖 FiscalBot Gemini – Consulta Inteligente de Notas Fiscais em CSV

Projeto desenvolvido como atividade obrigatória do curso **Agentes Autônomos com IA Generativa**.  
O objetivo é utilizar **LangChain**, integrado ao modelo **Google Gemini**, para responder automaticamente a perguntas formuladas em linguagem natural, com base nos dados contidos em arquivos CSV de notas fiscais.

---

## 📁 Estrutura dos Dados

- `202401_NFs_Cabecalho.csv`: informações gerais das notas (data de emissão, valor total, fornecedor).
- `202401_NFs_Itens.csv`: itens detalhados de cada nota (descrição, quantidade, valor unitário).

---

## ⚙️ Tecnologias Utilizadas

- `pandas`: análise e transformação de dados estruturados em CSV
- `langchain`: framework para aplicações com modelos de linguagem
- `langchain-google-genai`: conector oficial para uso do modelo Gemini
- `LLMChain + PromptTemplate`: estrutura de cadeia personalizada para consultas baseadas em contexto
- `rich`: biblioteca de visualização para terminais com feedback estilizado

---

## 🚀 Como Executar

1. Clone este repositório:
```bash
git clone https://github.com/seuusuario/fiscalbot-gemini.git
```

2. Crie um arquivo `.env` com sua chave da API Gemini:
```env
GEMINI_API_KEY=sua_chave_aqui
```

3. Instale as dependências do projeto:
```bash
pip install -r requirements.txt
```

4. Execute o notebook `fiscalbot_gemini.ipynb` no VS Code com Jupyter ou outro ambiente compatível.

---

## ❓ Exemplos de Perguntas Respondidas

- Qual item teve maior quantidade entregue?
- Qual fornecedor recebeu o maior valor total?
- Quantas notas foram emitidas no dia 2024-01-10?
- Qual a média do valor total das notas fiscais?

---

## 📂 Estrutura do Projeto

```
fiscalbot-gemini/
├── data/
│   └── 202401_NFs/
├── fiscalbot_gemini.ipynb
├── .env.example
├── README.md
└── docs/
    ├── manual_execucao.md
    └── validacao_requisitos.md
```

---

## 🔐 Segurança

A chave de API da Gemini é mantida em um arquivo `.env` (não versionado).  
Use o arquivo `.env.example` como modelo para configuração local segura.

---
