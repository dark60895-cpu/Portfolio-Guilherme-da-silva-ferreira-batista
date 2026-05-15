Markdown
# 🚀 Soluções em Lógica de Programação e Engenharia de Processos

Este repositório reúne projetos focados em automação, arquitetura modular e tratamento de exceções, demonstrando a aplicação de lógica computacional em cenários reais de varejo e saúde.

---

## 🏥 1. Sistema de Triagem Hospitalar Resiliente

Algoritmo desenvolvido para automatizar a classificação de risco de pacientes, focado na robustez e no tratamento de falhas em sensores.

### 📋 Visão Geral
O sistema processa sinais vitais (Frequência Cardíaca, Oxigenação, Temperatura) e sintomas para categorizar o atendimento em três níveis principais, seguindo diretrizes de protocolos de emergência.

### ⚙️ Diferenciais Técnicos
* **Engenharia de Contexto:** Diferenciação entre caminhos comuns (Entrada Ideal) e cenários de limite/borda (Bordo crítico).
* **Resiliência e Fallback:** Sistema de detecção de falha em sensores. Caso um sensor retorne `Falso` ou dados implausíveis, o algoritmo aciona automaticamente um alerta para intervenção humana.
* **Lógica Binária vs. Subjetividade:** Tratamento do desafio de transformar nuances clínicas em regras rígidas de decisão.

### 🛠️ Fluxo de Decisão
1. **Emergência (Vermelho):** FC > 120, Falta de ar ou Convulsão.
2. **Urgência (Amarelo):** Temperatura >= 37.5°C ou Vômito/Dor Forte.
3. **Leve (Verde):** Sintomas estáveis, encaminhamento comum.

---

## 🛒 2. Gestão de Inventário e PDV (Ponto de Venda)

Sistema modular projetado para controle de estoque dinâmico e processamento financeiro de vendas.

### 🏗️ Arquitetura Modular
O projeto é dividido em módulos independentes para garantir manutenibilidade:
* **Módulo 1 (Validação):** Garante que o valor pago cobre a venda e verifica a disponibilidade física no estoque.
* **Módulo 2 (Processamento):** Realiza a baixa automática no estoque e executa o **Algoritmo de Troco Otimizado**.
* **Módulo 3 (Persistência):** Atualiza o banco de dados e emite o comprovante de venda.

### 🧮 Algoritmo de Troco
Implementação de lógica de divisão inteira (`//`) e módulo (`%`) para calcular a menor quantidade de cédulas (100, 50, 20, 10, 5, 2, 1) necessária para o troco.

### 📊 Exemplo de Fluxo
```python
# Entrada de mercadoria (Reposição)
entrada_estoque("All Star_38", 10) 

# Processamento de Venda
realizar_venda(item="Air Max_40", quantidade=1, valor_pago=1000)
🧠 Conceitos Demonstrados
Máquinas de Estado: Controle de fluxo desde o 'Início' até o 'Fim' com ramificações condicionais claras.

Tratamento de Exceções: Validação de dados de entrada para evitar erros de execução.

Modularização: Separação de responsabilidades (Entrada -> Processamento -> Saída).

Documentação de Processos: Uso de fluxogramas para planejamento antes da codificação.

✍️ Autor
Guilherme Silva Ferreira Batista Estudante de Análise e Desenvolvimento de Sistemas – UNICID

Projetos desenvolvidos para as disciplinas de Lógica de Programação e Engenharia de Sistemas.
