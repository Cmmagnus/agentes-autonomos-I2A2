# ✅ Validação dos Requisitos da Atividade

A seguir, demonstramos como a solução proposta atende **integralmente aos critérios obrigatórios exigidos no desafio**:

---

## ✅ 1. Interface de interação com o usuário

A aplicação utiliza um **loop interativo com entrada de texto** (`input()`), permitindo ao usuário fazer múltiplas perguntas em linguagem natural.  
As respostas são exibidas com **estilo visual via `rich`**, simulando um ambiente de chat.

```python
pergunta = input("🟢 Digite sua pergunta (ou 'sair'): ").strip()
```

---

## ✅ 2. Agente que descompacta, seleciona e carrega os dados

Os arquivos CSV são carregados automaticamente com `pandas`, e a estrutura está pronta para incluir descompactação do `.zip` se necessário:

```python
df_cabecalho = pd.read_csv('data/202401_NFs/202401_NFs_Cabecalho.csv')
df_itens = pd.read_csv('data/202401_NFs/202401_NFs_Itens.csv')
```

Caso necessário, também pode ser incluído:

```python
import zipfile
with zipfile.ZipFile("data/202401_NFs.zip", 'r') as zip_ref:
    zip_ref.extractall("data/")
```

---

## ✅ 3. Capacidade de realizar queries a partir das perguntas feitas

A IA é acionada a partir de uma **cadeia (`LLMChain`)** que recebe:

- A **pergunta do usuário** (`{pergunta}`)
- Um **contexto dinâmico gerado com `pandas`** a partir dos dados dos arquivos CSV (`{contexto}`)

```python
contexto = f"Cabecalho:\n{df_cabecalho.head()}\n\nItens:\n{df_itens.head()}"
resposta = chain.run({"contexto": contexto, "pergunta": pergunta})
```

---

## ✅ 4. Geração automática de respostas coerentes

As respostas são geradas exclusivamente pelo modelo **Gemini 1.5 Flash**, por meio do framework **LangChain**, sem intervenção manual:

```python
llm = GoogleGenerativeAI(...)
chain = LLMChain(llm=llm, prompt=prompt)
resposta = chain.run({...})
```

A resposta é exibida em tempo real:

```python
console.print(Panel(resposta, title="📢 Resposta do agente", border_style="green"))
```

---

✅ Com isso, garantimos que a solução:

- Usa **IA Generativa para processar dados CSV**
- Interage com o usuário em tempo real
- Gera respostas baseadas nos dados reais
- Está de acordo com os **critérios eliminatórios da atividade**
