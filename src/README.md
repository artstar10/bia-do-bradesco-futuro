# Passo a passo de execução

## Setup do Ollama

```bash
# 1. Instalar Ollama (ollama.com)
# 2. Baixar um modelo leve
ollama pull gpt-oss

# 3. Testar se funciona
ollama run llama3 "Olá!"
```
## Código completo

```
Todo o código fonte está no arquivo app.py
```
## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run src/app.py
```
