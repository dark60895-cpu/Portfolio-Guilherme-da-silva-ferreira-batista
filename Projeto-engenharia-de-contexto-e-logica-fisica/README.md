# 🏠 Smart Home: Simulação de Microclima e Algoritmo de Evacuação

Este projeto explora a interseção entre o mapeamento físico de uma residência e a lógica de programação em Python. Ele está dividido em dois sistemas principais: um simulador de variáveis ambientais (microclima) e um protocolo inteligente de tomada de decisão para evacuação de emergência.

---

## 🛠️ Tecnologias e Conceitos
- **Linguagem:** Python 3
- **Estruturas:** Dicionários aninhados, listas de inventário e recursividade.
- **Lógica:** Tomada de decisão baseada em nós e estados de variáveis (energia, chaves, riscos).

---

## 📂 Estrutura do Projeto

### Parte 1: O Algoritmo do Microclima Local
O código simula como variáveis externas (temperatura e umidade) são processadas de forma distinta em cada cômodo, considerando características físicas:
*   **Sala/Cozinha:** Ambiente amplo que retém menos calor.
*   **Quarto 2:** Influência externa elevada devido à presença da varanda.

### Parte 2: Navegação e Evacuação Espacial
Um algoritmo de busca de caminho que avalia a segurança do agente durante uma saída de emergência.
*   **Layout da Casa:** Mapeado como um grafo de conexões entre Quarto 1, Quarto 2, Sala/Cozinha e Banheiro.
*   **Variáveis de Decisão:** 
    *   Presença de chaves no inventário.
    *   Nível de energia do agente para ações de alto risco (ex: pular da varanda em caso de urgência).
    *   Identificação de rotas bloqueadas vs. saídas principais.

---

## 🧠 Reflexão Crítica (O Pensamento Computacional)

### Do Espaço Físico aos Nós de Decisão
Durante o mapeamento físico da casa, percebi que o trajeto de evacuação depende de variáveis ambientais e recursos disponíveis. Obstáculos reais, como portas trancadas ou zonas de risco como a varanda, exigem uma tomada de decisão lógica que vai além do simples caminhar. Para traduzir isso, cada ponto da casa passou a ser tratado como um **nó de decisão**.

### O Desafio da Abstração
Sintetizar a complexidade física em regras binárias foi o maior desafio. Uma porta no mundo real possui múltiplos estados; para representar isso, utilizei **dicionários** que permitem checar simultaneamente a existência, a trava e o inventário necessário. A lógica da varanda no Quarto 2 exigiu uma condição que avalia o risco baseado na energia, mostrando que a "geografia" do código é, na verdade, uma hierarquia de prioridades e segurança.

### Programação como Lente Analítica
Aprender a programar ajuda a enxergar problemas cotidianos de forma estruturada. Situações comuns, como resolver imprevistos, funcionam como um algoritmo: é necessário decompor o desafio, avaliar recursos e decidir o melhor caminho. O raciocínio computacional treina a mente para ser mais analítica e buscar soluções lógicas antes mesmo que os problemas ocorram.

---

## 🔗 Links de Acesso
- [Acesse o código completo no Google Colab](https://colab.research.google.com/drive/1tbcFBWzeAJIxXB-Qn8XYxA5B38lzFp8Y?usp=sharing)

---
*Desenvolvido como parte de um estudo sobre algoritmos e simulação residencial.*
