# 🎓 Artstar — Educador Financeiro com IA

Agente conversacional de educação financeira personalizada, construído com Python, Streamlit e LLM local via Ollama.

## Sobre o Projeto

O Artstar é um chatbot que atua como educador financeiro amigável. Ele usa dados reais do cliente — transações, perfil de investidor e histórico de atendimentos — para contextualizar as explicações e tornar o aprendizado mais prático e personalizado.

O agente **não recomenda investimentos**. Ele explica como os produtos funcionam, ajuda o usuário a entender seus próprios gastos e responde perguntas de finanças pessoais de forma simples e direta.

## Funcionalidades

- Respostas contextualizadas com base no perfil e nas transações do cliente
- Explicações sobre produtos financeiros (Tesouro Selic, CDB, LCI/LCA, FIIs, Fundos de Ações)
- Análise de gastos por categoria a partir do histórico de transações
- Acompanhamento de metas financeiras (reserva de emergência, entrada do apartamento)
- Edge cases tratados: perguntas fora do escopo, tentativas de obter dados sensíveis e pedidos de recomendação direta

## Stack

- **Python** — lógica principal e integração com a LLM
- **Streamlit** — interface de chat
- **Ollama + LLaMA 3** — LLM local para geração de respostas
- **Pandas** — leitura e processamento dos dados do cliente

## Estrutura

```
.
├── app.py                        # Aplicação principal (Streamlit + Ollama)
├── README_PROMPTS_DO_AGENTE.md   # System prompt, few-shots e edge cases documentados
└── data/
    ├── perfil_investidor.json    # Perfil, metas e patrimônio do cliente
    ├── transacoes.csv            # Histórico de transações mensais
    ├── historico_atendimento.csv # Atendimentos anteriores
    └── produtos_financeiros.json # Catálogo de produtos disponíveis
```

## Como Rodar

**Pré-requisitos:** Python 3.10+, Ollama instalado e rodando com o modelo `llama3`.

```bash
# Clone o repositório
git clone https://github.com/artstar10/artstar.git
cd artstar

# Instale as dependências
pip install streamlit pandas requests

# Inicie o Ollama em outro terminal
ollama run llama3

# Rode a aplicação
streamlit run app.py
```

## Exemplo de Interação

> **Usuário:** Onde estou gastando mais?
>
> **Artstar:** Olhando suas transações de outubro, sua maior despesa é moradia (R$ 1.380), seguida de alimentação (R$ 570). Juntas, representam quase 80% dos seus gastos. Isso é bem comum! Quer que eu explique algumas estratégias de organização?

## Decisões de Projeto

O agente usa **few-shot prompting** para calibrar o tom e o comportamento. Os exemplos de perguntas e respostas estão documentados em `README_PROMPTS_DO_AGENTE.md`, junto com os edge cases testados e as observações sobre diferenças de comportamento entre modelos (ChatGPT, Copilot e Claude foram comparados com o mesmo system prompt).

## Licença

MIT
