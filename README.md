# 🤖 Automação de Triagem e Resposta de Feedbacks com IA

Este projeto foi desenvolvido como parte do meu portfólio e desenvolvimento. O objetivo é automatizar o atendimento ao cliente, analisando avaliações e gerando respostas humanizadas de forma rápida e escalável.

## 🎯 O Desafio
Em plataformas de delivery, milhares de avaliações chegam diariamente. Identificar clientes insatisfeitos (notas baixas) e responder de forma empática e rápida é um desafio operacional. Esta automação resolve esse problema usando lógica de programação e Inteligência Artificial.

## ⚙️ Como funciona o Fluxo (Workflow)

O projeto foi construído no **n8n** e dividido em 4 etapas principais:

1. **Trigger (Simulação de Entrada):** Recebe os dados da avaliação do cliente (Nome, Nota de 1 a 5 e Comentário).
2. **Análise de Dados com Python (Code Node):** 
   * O script em Python lê o comentário em busca de "palavras-chave de urgência" (ex: "fria", "demorou", "péssimo").
   * Define o nível de urgência (`ALTA` ou `BAIXA`).
   * Define a ação de negócio com base na nota (ex: Nota <= 3 -> "Entrar em contato para reembolso").
3. **Geração de Resposta com IA (AI Agent):** Utiliza IA Generativa para criar uma resposta empática e personalizada. O prompt da IA recebe as variáveis processadas pelo Python (nome do cliente, comentário, urgência e ação) e redige a mensagem final.
4. **Tratamento do Output (Edit Fields):** Extrai o texto final gerado pela IA, preparando o payload (JSON) que seria devolvido ao aplicativo do cliente.

## 🛠️ Tecnologias Utilizadas
*   **n8n:** Orquestração visual do fluxo de trabalho.
*   **Python:** Processamento de strings, lógica condicional e regras de negócio.
*   **Inteligência Artificial:** Geração de linguagem natural (IA nativa do n8n).
*   **JSON:** Estruturação e transporte de dados entre os nodes.

## 🚀 Como testar este projeto
1. Faça o download do arquivo `My workflow.json` neste repositório.
2. No seu n8n, clique em "Import from File" ou copie o JSON e cole na tela em branco.
3. Conecte suas próprias credenciais de IA (se necessário).
4. Clique em "Execute Workflow" e veja a mágica acontecer!

## 💡 Próximos Passos (Visão de Produção)
Para colocar em produção real no iFood, o node final (Edit Fields) seria substituído por uma requisição **HTTP Request** conectada à API do iFood, devolvendo a resposta gerada pela IA diretamente no chat do aplicativo do cliente.

---
*Desenvolvido por Livia Maria* 
