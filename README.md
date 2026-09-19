# FIAPOS — FioBot

## 1. PROJETO
O **FioBot** é um chatbot desenvolvido para a plataforma fictícia **FIAPOS**, uma plataforma digital voltada para a comercialização de produtos artesanais, encomendas personalizadas, serviços de reparo e venda de moldes e receitas. Os produtos são voltados para peças produzidas por meio de técnicas como crochê, tricô, costura, bordado, ponto-cruz, entre outras.
O objetivo do projeto é desenvolver um assistente capaz de responder dúvidas de clientes e artesãos utilizando um conhecimento interno específico da FIAPOS. O chatbot foi configurado para seguir as regras e informações presentes nesse contexto, evitando inventar informações que não estejam disponíveis no conhecimento fornecido.
O sistema utiliza a **Gemini API** para geração das respostas e foi desenvolvido e executado no **Google Colab**. O conhecimento interno da FIAPOS é mantido em um arquivo separado presente no repositório (conhecimento_interno.txt), enquanto o código da aplicação está no notebook `fiapos_fiobot.ipynb`.
A aplicação permite a realização de **três perguntas por conversa**. Ao final da terceira pergunta, o sistema gera um resumo da interação.

---

## 2. ESTRUTURA

### Arquivos

**`conhecimento_interno.txt`**
Contém o conhecimento interno utilizado pelo FioBot, incluindo regras, serviços, funcionamento da plataforma, encomendas, devoluções, reparos, cadastro de artesãos e demais informações da FIAPOS.

**`fiapos_fiobot.ipynb`**
Contém todo o código desenvolvido para o chatbot. O notebook é executado no Google Colab e reúne as etapas de configuração, carregamento do contexto, autenticação, comunicação com a Gemini API, gerenciamento do histórico e execução da conversa.

**`requirements.txt`**
Contém as bibliotecas necessárias para executar o projeto.

**`.env.example`**
Apresenta os nomes das variáveis utilizadas para configuração da aplicação, sem armazenar valores de credenciais. No caso do uso do Colab, deve ser configurado na aba de Secrets. O arquivo `.env.example` serve apenas como referência para as variáveis de configuração utilizadas pelo projeto.

**`.gitignore`**
Evita o envio de arquivos que não devem ser armazenados no repositório, necessário se o código não fosse executado no Colab.

---

## 3. CONFIGURAÇÃO DA API

A chave de acesso à Gemini API foi gerada no Google AI Studio.

---

## 4. PASSO A PASSO

### 4.1. Abrir o projeto

Acesse o repositório do projeto no GitHub e abra o arquivo:

```text
FIAPOS_Bot_Colab.ipynb
```
Abra o notebook utilizando o Google Colab.

---

### 4.2. Configurar o Secret

No Google Colab, abra o painel de Secrets e crie uma variável chamada:

```text
GEMINI_API_KEY
```
Informe como valor a chave da Gemini API obtida no Google AI Studio.
Não é necessário adicionar a chave diretamente ao código.

---

### 4.3. Instalar a biblioteca

Execute a célula responsável pela instalação das dependências:

```python
%pip install -q -U google-genai
```
A instalação ocorre no ambiente temporário do Google Colab.

---

### 4.4. Executar a configuração

Execute as células iniciais do notebook para:

* importar as bibliotecas;
* carregar a chave armazenada no Secret;
* configurar o modelo utilizado;
* criar o cliente da Gemini API.

---

### 4.5. Carregar o conhecimento da FIAPOS

O arquivo:

```text
FIAPOS_contexto_final.txt
```
deve estar disponível neste repositório GitHub.
Durante a execução, o notebook acessa esse arquivo e carrega seu conteúdo para a variável `KNOWLEDGE`.
Esse conteúdo é utilizado como conhecimento interno do FioBot.

---

### 4.6. Executar o chatbot

Execute as células do notebook em ordem até chegar à interface do FioBot.
O sistema apresentará uma área para digitar a pergunta e um botão para enviá-la.
O usuário pode realizar até três perguntas durante a conversa.
O histórico também é armazenado durante a execução para permitir a continuidade da conversa e a geração do resumo final.

---
 
