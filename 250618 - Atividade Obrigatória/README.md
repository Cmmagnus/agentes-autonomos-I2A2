
# 🧠 FiscalBot Gemini – Consultor Inteligente de Dados Fiscais

Projeto desenvolvido como parte do curso **Agentes Autônomos com Redes Generativas** (I2A2, Meta & MetadataH).

---

## 📌 Sobre o Projeto

O **FiscalBot Gemini** é um agente autônomo de IA criado para responder perguntas em linguagem natural sobre arquivos fiscais no formato CSV. Utilizando o framework **LangChain** com o modelo **Google Gemini 1.5 Flash**, o sistema permite interações inteligentes com dados estruturados, sem intervenção manual.

---

## ⚙️ Tecnologias Utilizadas

- **LangChain** com `LLMChain` e `PromptTemplate`
- **Google Gemini 1.5 Flash** (`langchain-google-genai`)
- **Pandas** – Análise e tratamento de dados CSV
- **dotenv** – Gerenciamento seguro de chaves de API
- **Rich** – Saída estilizada no terminal

---

## 🧱 Estrutura da Solução

1. Instalação das bibliotecas essenciais
2. Descompactação automática dos arquivos `.zip`
3. Leitura e tratamento dos arquivos:
   - `202401_NFs_Cabecalho.csv`
   - `202401_NFs_Itens.csv`
4. Construção de prompts dinâmicos
5. Execução de perguntas com base nos dados
6. Geração automática de respostas usando IA generativa

---

## ❓ Exemplos de Perguntas Respondidas

| Pergunta                                         | Resumo da Resposta Gerada                     |
|--------------------------------------------------|-----------------------------------------------|
| Qual fornecedor recebeu mais?                   | Companhia Brasileira de Educ. – R$ 522,50     |
| Qual item teve mais peças entregues?            | CINEMATICO RODO-AR – 4 unidades               |
| Quantas notas foram emitidas em 2024-01-10?     | Nenhuma nota foi emitida                      |
| Qual é a média do valor das notas emitidas?     | R$ 453,50 (baseado em três registros)         |

📷 *Print das respostas reais:*  
![respostas_geradas](fiscalbot-csv/assets/respostas.png)

---

## 📁 Estrutura do Repositório

```plaintext
📦 FiscalBot
├── fiscalbot_gemini.ipynb       # Código principal do agente
├── .env.example                 # Modelo para variáveis de ambiente
├── data/
│   └── 202401_NFs/              # Arquivos CSV originais
├── assets/
│   └── respostas.png            # Print das respostas do agente
└── docs/
    ├── manual_execucao.md      # Guia de execução
    └── validacao_requisitos.md # Checklist do desafio
```

---

## 🔒 Segurança e Conformidade

- ✅ Sem exposição de chaves sensíveis
- ✅ Uso de `.env` para configurações seguras
- ✅ Utilização de modelo gratuito e compatível com os critérios do curso

---

## 🧠 Potencial de Expansão

- Integração com interfaces como **Streamlit**
- Suporte a múltiplos tipos de documentos fiscais
- Implementação de **RAG** e consultas multimodais

---

## 👤 Informações do Autor

**Carlos M. Marcelino**  
🎓 Curso: Agentes Autônomos com Redes Generativas  
📅 Data: 15/06/2025  

📫 Contato:
- Email: [carmmarcelino86@gmail.com](mailto:carmmarcelino86@gmail.com)
- LinkedIn: [Carlos Magno](https://www.linkedin.com/in/carlos-magno-marcelino-619ab9186/)
- GitHub: [@Cmmagnus](https://github.com/Cmmagnus)

---

## 📎 Envio Oficial

**Grupo:** CMagnus_86  
**Envio:** `challenges@i2a2.academy`  
**Repositório do Projeto:**  
🔗 [github.com/Cmmagnus/agentes-autonomos-I2A2](https://github.com/Cmmagnus/agentes-autonomos-I2A2/tree/main/250618-atividade-obrigatoria)

---
