# 📊 Data Audit & Sales Management System

[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Este repositório contém o desenvolvimento de um sistema modular para **Gestão de Inventário** e um **Algoritmo de Auditoria de Dados**. O projeto foca em integridade transacional, detecção de discrepâncias (outliers) e segurança em sistemas financeiros.

---

## 📋 Conteúdo do Projeto

O projeto está dividido em duas frentes principais:
1. **Sistema de PDV (Ponto de Venda):** Gestão de entrada/saída de stock e cálculo automatizado de troco.
2. **Algoritmo de Auditoria:** Ferramenta para análise de médias de vendas e identificação de comportamentos atípicos.

---

## 🏗️ Arquitetura do Sistema de Vendas

O sistema foi desenhado seguindo uma estrutura modular para garantir escalabilidade:

### Módulo 1: Validação e Disponibilidade
* **Conferência de Entrada:** Valida novos itens no inventário.
* **Check de Inventário:** Bloqueia vendas caso não existam unidades disponíveis.
* **Validação Financeira:** Garante que o valor pago cobre o custo da venda.

### Módulo 2: Processamento Lógico
* **Baixa de Stock:** Atualiza as quantidades no dicionário de dados de forma atómica.
* **Algoritmo de Troco:** Utiliza divisões inteiras e o operador de módulo (`%`) para calcular a menor quantidade de notas (100, 50, 20, 10, 5, 2, 1).

### Módulo 3: Persistência e Saída
* **Update de Banco de Dados:** Regista o novo estado do stock.
* **Emissão de Recibo:** Gera o comprovativo detalhado da transação.



---

## 🔍 Auditoria e Análise de Dados (Outliers)

Como parte da inteligência do sistema, implementamos um módulo de auditoria para identificar **Discrepâncias de Dados**.

*   **O problema dos Outliers:** Um único valor extremo (ex: uma venda de 5000 num grupo de 100) pode distorcer a média aritmética, "mentindo" sobre o comportamento real do grupo.
*   **Normalização:** O sistema foi projetado para entender que ignorar extremos pode levar a resultados mais fiéis à realidade.
*   **Margem de Tolerância:** Implementação do conceito de "Distorção Tolerável", essencial em auditorias bancárias para validar a fidedignidade das operações.

### Teste de Estresse do Algoritmo
Ao testar o sistema com valores como `100`, `200` e `5000`:
*   A média resultante é `1766.67`.
*   O sistema identifica que, embora o valor `5000` seja suspeito, a média ainda não atingiu o limite crítico de segurança (`10000`), mantendo o estado de quarentena para análise humana.

---

## 💻 Exemplo de Implementação (Python)

### Estrutura do Inventário
```python
estoque = {
    "Air Max_40": 5,
    "All Star_38": 2
}
