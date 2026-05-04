# 🏙️ Urban Intelligence: Microclima, Conforto e Evacuação

Este projeto em Python integra análise de dados ambientais em tempo real com simuladores de tomada de decisão, focando em conceitos de cidades inteligentes e segurança residencial.

---

## 🛠️ Tecnologias e Técnicas Utilizadas
- **Linguagem:** Python 3.10+
- **Lógica Avançada:** Estrutura `match-case` para classificações de saúde.
- **Modelagem Matemática:** Fórmulas ponderadas para cálculo de Índice de Conforto Urbano.
- **Simulação de Agente:** Lógica de navegação em estados (inventário, energia e riscos).

---

## 📂 Estrutura do Sistema

### 1. Analisador de Microclima Urbano
O script processa dados reais de pontos específicos de São Paulo, avaliando a qualidade do ar (IQA) conforme os padrões da CETESB.
- **Classificação Dinâmica:** Avalia se o ar está *Bom*, *Moderado*, *Ruim* ou *Péssimo*.
- **Índice de Conforto Urbano:** Um cálculo original que pondera:
    - **Temperatura (35%):** Penaliza desvios da faixa ideal (18°C - 26°C).
    - **Umidade (25%):** Conforto máximo entre 50% e 70%.
    - **Qualidade do Ar (40%):** Escala invertida baseada no IQA.

### 2. Simulador de Evacuação Inteligente
Um motor de jogo baseado em turnos que simula a saída de uma residência em situação de urgência.
- **Máquina de Estados:** Cada cômodo (Quarto, Sala, Banheiro) possui estados específicos como `trancada`, `porta` e `chave`.
- **Gestão de Recursos:** O agente precisa gerenciar seu nível de **Energia** e seu **Inventário** para sobreviver.
- **Lógica de Risco:** No Quarto 2, o sistema avalia se o agente tem energia suficiente para uma saída de emergência via varanda ou se deve seguir o caminho padrão.

---

## 📊 Exemplo de Saída (Análise Urbana)
```text
📍 Rua Dr. Assis Ribeiro, 2575 — 23:26
--------------------------------------------------
  Temp (°C): 17
  Umidade (%): 91
  IQA: 44
  Qualidade do Ar: Moderada
  Risco: Risco para grupos sensíveis.
  Nota de Conforto Urbano: 7.21/10 — Bom
