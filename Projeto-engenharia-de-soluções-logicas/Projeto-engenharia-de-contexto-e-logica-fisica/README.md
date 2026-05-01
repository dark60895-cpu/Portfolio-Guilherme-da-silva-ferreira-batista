# 🎬 Sistema de Recomendação de Filmes

## 📝 Descrição do Projeto
Este projeto consiste em um motor de recomendação inteligente que utiliza técnicas de filtragem colaborativa e baseada em conteúdo. O objetivo principal é mitigar a **"paralisia de escolha"**, oferecendo aos usuários sugestões personalizadas com base em seu histórico de visualização e preferências de gênero.

Desenvolvido como parte da disciplina de **Inteligência Artificial (2024.1)**, o sistema processa grandes volumes de dados (datasets de filmes e avaliações) para identificar padrões de comportamento e similaridades entre títulos, utilizando algoritmos de aprendizado de máquina para prever a nota que um usuário daria a um filme ainda não assistido.

## 🚀 Tecnologias Utilizadas
* **Linguagem:** Python 3.10
* **Bibliotecas:** Pandas, Scikit-learn, Matplotlib
* **Ferramentas:** Jupyter Notebook, Google Colab

## 🧠 Reflexões Técnicas e Aprendizados (Tradução de Lógica)
Durante a implementação, foram consolidados conhecimentos fundamentais sobre a transição da lógica de programação para a sintaxe Python, essenciais para a integridade dos dados do sistema:

### 1. Tipagem e Manipulação de Entradas (input)
* **Comportamento Padrão:** Em Python, a função `input()` sempre retorna o dado como uma **String** (texto), mesmo para entradas numéricas.
* **Consequências:** A ausência de conversão (casting) via `int()` ou `float()` impede cálculos matemáticos. O operador `+` realiza apenas a concatenação (ex: "5" + "5" = "55"), enquanto operações de subtração ou divisão geram erros de tipo (`TypeError`).

### 2. Estruturas de Repetição e range()
* **Limite Superior Exclusivo:** Diferente do pseudocódigo tradicional, o limite superior do `range()` é exclusivo — o número final não entra na contagem.
* **Inclusão do Último Valor:** Para iterar corretamente de 1 até o total desejado, utiliza-se a sintaxe `range(1, total + 1)`.
* **Raciocínio de Design:** Esta estrutura facilita a manipulação de listas (índice zero) e permite prever o número de repetições pela diferença entre o fim e o início.

## 🏗️ Engenharia de Contexto e Lógica Física
O projeto também integra conceitos de **Engenharia de Contexto** aplicados a simulações de evacuação residencial, onde o ambiente físico é traduzido em variáveis lógicas:
* **Mapeamento de Ambientes:** Divisão da residência em nós de decisão (Quarto 1, Quarto 2 com varanda de risco, Sala/Cozinha integrada e Banheiro).
* **Variáveis de Decisão:** Uso de dicionários para checar simultaneamente o estado das portas (abertas/trancadas), disponibilidade de chaves e energia do agente para escolhas críticas.

## 📊 Resultados Alcançados
* **Acurácia:** O modelo atingiu **92% de acurácia** nos testes de validação.
* **Redução de Ruído:** Aplicação de técnicas de limpeza e normalização de dados para melhorar a performance dos algoritmos.
* **Visualização de Clusters:** Implementação de gráficos que agrupam filmes por afinidade semântica.

## 🔧 Como Executar
1. Clone o repositório.
2. Instale as dependências: `pip install -r requirements.txt`.
3. Execute o comando: `python main.py`.

---
*Este projeto demonstra como o raciocínio computacional ajuda a decompor desafios complexos em partes menores, seja na recomendação de mídia ou no planejamento de segurança.*
