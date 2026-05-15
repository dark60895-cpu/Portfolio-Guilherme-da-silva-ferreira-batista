# 🏙️ Urban Intelligence: Microclima, Conforto e Evacuação

Este projeto em Python integra análise de dados ambientais em tempo real com simuladores de tomada de decisão. O foco principal é a convergência entre conceitos de **Smart Cities** (Cidades Inteligentes), segurança residencial e bem-estar urbano.

---

## 🛠️ Tecnologias e Técnicas Utilizadas

* **Linguagem:** Python 3.10+
* **Lógica Avançada:** Implementação de estrutura `match-case` para classificações de saúde e estados de risco.
* **Modelagem Matemática:** Fórmulas ponderadas para cálculo de Índice de Conforto Urbano (ICU).
* **Simulação de Agente:** Lógica de navegação baseada em estados (inventário, energia e condições ambientais).

---

## 📂 Estrutura do Sistema

### 1. Analisador de Microclima Urbano
O script processa dados reais de pontos específicos de São Paulo (ex: Rua Dr. Assis Ribeiro), avaliando a qualidade do ar (IQA) conforme os padrões da **CETESB**.

* **Classificação Dinâmica:** Avalia se o ar está *Bom*, *Moderado*, *Ruim* ou *Péssimo*.
* **Índice de Conforto Urbano (ICU):** Um algoritmo original que pondera diferentes variáveis ambientais:
    * **Temperatura (35%):** Penaliza desvios da faixa ideal (18°C - 26°C).
    * **Umidade (25%):** Foco no conforto máximo entre 50% e 70%.
    * **Qualidade do Ar (40%):** Escala invertida baseada no índice IQA.

### 2. Simulador de Evacuação Inteligente
Um motor de simulação baseado em turnos que modela a saída de uma residência em situação de urgência extrema.

* **Máquina de Estados:** Cada cômodo (Quarto, Sala, Banheiro) possui atributos dinâmicos como `trancado`, `presença de chave` e `saída de emergência`.
* **Gestão de Recursos:** O agente deve gerenciar seu nível de **Energia** e seu **Inventário** para garantir a sobrevivência.
* **Lógica de Risco:** Implementação de caminhos alternativos. No "Quarto 2", o sistema avalia se o agente possui energia suficiente para uma saída via varanda ou se deve prosseguir pelo caminho padrão sob condições de risco.

---

## 📊 Exemplo de Processamento (Output)

```text
📍 Rua Dr. Assis Ribeiro, 2575 — 23:26
--------------------------------------------------
  Temp (°C): 17
  Umidade (%): 91
  IQA: 44
  Qualidade do Ar: Moderada
  Risco: Risco para grupos sensíveis.
  Nota de Conforto Urbano: 7.21/10 — Bom
⚙️ Funcionalidades Técnicas
Processamento de Strings: Formatação dinâmica de endereços e timestamps para relatórios.

Tratamento de Dados Condicionais: Uso de lógica booleana complexa para decidir o próximo estado do simulador de evacuação.

Escalabilidade: O motor de análise pode ser facilmente adaptado para outras metrópoles ou integrado a sensores IoT (Internet of Things).

🚀 Como Executar
Clone o repositório:

Bash
git clone [https://github.com/seu-usuario/urban-intelligence.git](https://github.com/seu-usuario/urban-intelligence.git)
Execute o script principal:

Bash
python urban_analysis.py
🧠 Conceitos de Engenharia de Contexto
O projeto demonstra como o contexto físico (clima e arquitetura) pode influenciar a lógica de software. O simulador não apenas segue um caminho, mas "sente" o ambiente através dos dados de energia e risco, alterando o fluxo de execução em tempo real.

✍️ Autor
Guilherme Silva Ferreira Batista
Estudante de Análise e Desenvolvimento de Sistemas – UNICID

Desenvolvido como parte dos estudos de Engenharia de Contexto e Lógica Física Aplicada.
