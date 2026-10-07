# Análise de Dados de Conversas do WhatsApp

Aplicação em Python (Jupyter Notebook) que lê uma conversa de grupo exportada do WhatsApp e carrega os dados em um DataFrame do Pandas com as colunas **data**, **hora**, **remetente** e **mensagem**.

## Funcionalidades

| # | Análise | Descrição |
|---|---------|-----------|
| – | Tabela completa | Exibe o DataFrame com data, hora, remetente e mensagem |
| 1 | Resumo das conversas | Total de mensagens por remetente, do maior para o menor |
| 2 | Histórico do remetente | Filtra as mensagens de um remetente (com data e hora) |
| 3 | Gráfico do histórico do remetente | Histograma da quantidade de mensagens por dia de cada remetente |
| 4 | Gráfico de pizza | Percentual de mensagens de cada remetente |
| 5 | Gráfico de linhas | Mensagens ao longo do tempo, uma linha (cor) por remetente |

Ao final do notebook há um menu interativo que executa qualquer uma das análises.

Suporta exportações de **Android** (`dd/mm/aaaa hh:mm - Nome: mensagem`) e **iPhone** (`[dd/mm/aaaa, hh:mm:ss] Nome: mensagem`), em `.txt` ou no `.zip` gerado pelo WhatsApp.

## 1. Exportar a conversa

**Android:** abra o grupo > ⋮ (três pontos) > Mais > Exportar conversa > **Sem mídia**.
**iPhone:** abra o grupo > toque no nome do grupo > Exportar conversa > **Sem mídia**.

Envie o arquivo para você mesmo (e-mail, Drive etc.) e baixe no computador.

## 2. Executar

### Opção A — Google Colab (sem instalar nada)

1. Acesse [colab.research.google.com](https://colab.research.google.com) > **Arquivo > Fazer upload de notebook** e selecione `analise_whatsapp.ipynb`.
2. No menu lateral esquerdo, clique no ícone de **pasta** e arraste o arquivo exportado (`.zip` ou `.txt`).
3. Na célula **Configuração**, ajuste o nome do arquivo:
   ```python
   ARQUIVO = "Conversa do WhatsApp com Meu Grupo.zip"
   ```
4. **Ambiente de execução > Executar tudo** (Ctrl+F9).

### Opção B — Localmente

Requisitos: Python 3.9+.

```bash
git clone https://github.com/Mrcidele/analise-whatsapp.git
cd analise-whatsapp
pip install -r requirements.txt
jupyter notebook analise_whatsapp.ipynb
```

1. Copie o arquivo exportado para a pasta do projeto.
2. Ajuste a variável `ARQUIVO` na célula **Configuração**.
3. **Run > Run All Cells**.

> No VS Code: instale a extensão **Jupyter**, abra o `.ipynb` e clique em **Run All**.

## Estrutura

```
analise_whatsapp.ipynb   # aplicação
requirements.txt         # dependências (pandas, matplotlib, ipywidgets, notebook)
README.md
```

> Os arquivos de conversa (`.txt`/`.zip`) estão no `.gitignore` para não publicar mensagens e números de telefone.
