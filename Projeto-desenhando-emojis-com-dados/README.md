# 🏠 Simulação de Microclima e Evacuação Residencial (EX6)

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Acessar-Google%20Colab-orange?logo=googlecolab)](https://colab.research.google.com/drive/1tbcFBWzeAJIxXB-Qn8XYxA5B38lzFp8Y?usp=sharing)

Este projeto aplica conceitos de **Pensamento Computacional** e **Estruturas de Dados** para modelar o ambiente físico de uma residência, simulando variáveis climáticas e protocolos de segurança para evacuação.

---

## 🌡️ Parte 1: O Algoritmo do Microclima Local

Estudo da variação de temperatura e umidade em diferentes pontos da casa, tratando cada cômodo como um ambiente com variáveis únicas.

*   **Objetivo:** Pesquisar e codificar a influência do microclima em ambientes fechados.
*   **Acesso ao código:** [Google Colab - Notebook](https://colab.research.google.com/drive/1tbcFBWzeAJIxXB-Qn8XYxA5B38lzFp8Y?usp=sharing)

---

## 🚶 Parte 2: Navegação e Evacuação Espacial

Modelagem lógica da planta residencial para tomada de decisão em situações de emergência. A casa foi decomposta em 4 cômodos principais com regras de acessibilidade específicas:

### Mapeamento dos Cômodos
1.  **Quarto 1:** Porta acessível (chave sempre disponível); sem saída de emergência.
2.  **Quarto 2:** Acesso à **Varanda**. A varanda não é uma saída oficial, mas serve como última opção de socorro (envolvendo risco de acidente/queda).
3.  **Sala/Cozinha:** Ambiente amplo integrado com a **única porta de entrada/saída principal**.
4.  **Banheiro:** Porta acessível; sem saídas alternativas.

---

## 🧠 Parte 3: Reflexão Crítica

### A Casa como um Grafo de Decisão
Durante o mapeamento físico, percebi que um trajeto de evacuação é muito mais que um caminho; é um sistema dependente de variáveis ambientais e recursos. Obstáculos reais como portas trancadas ou zonas de risco exigem que cada ponto da casa seja tratado como um **nó de decisão**.

### Da Complexidade Física à Lógica Binária
O maior desafio foi sintetizar a complexidade física em regras de código. Enquanto uma porta no mundo real tem estados variados, no código precisei usar **dicionários** para checar simultaneamente:
*   Existência da porta;
*   Estado (trancada/aberta);
*   Inventário (posse da chave).
A lógica da varanda no Quarto 2 foi o ponto mais crítico, exigindo uma condição que avalia o risco baseado na "energia" do agente.

### Programação na Vida Real
Esta experiência mostrou que o raciocínio computacional vai além das telas. Planejar tarefas ou resolver imprevistos funciona como um algoritmo: decompor desafios, avaliar recursos (tempo/esforço) e decidir o caminho mais seguro. A programação treina a mente para ser analítica e prever falhas antes que elas ocorram na rotina.

---

## 🛠️ Tecnologias e Conceitos
*   **Linguagem:** Python
*   **Estruturas:** Dicionários, Condicionais Aninhadas, Operadores Lógicos.
*   **Conceitos:** Abstração, Decomposição de Problemas e Algoritmos de Busca.

---
*Projeto desenvolvido como parte dos estudos de Lógica de Programação.*
