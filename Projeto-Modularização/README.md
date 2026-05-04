# 🛒 Sistema de Gestão de Inventário e PDV (Ponto de Venda)

[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Este repositório contém o planeamento lógico e a implementação de um sistema modular para controlo de stock e automação de vendas. O projeto foca-se na integridade de dados e na otimização da experiência de checkout (PDV).

---

## 📋 Visão Geral

O sistema está desenhado para gerir o ciclo de vida de produtos num ambiente de retalho, desde a **entrada de mercadoria** até à **emissão de talão com cálculo de troco**. A arquitetura é dividida em módulos independentes para facilitar a manutenção e escalabilidade.

---

## 🏗️ Arquitetura do Sistema

O sistema opera em três camadas lógicas fundamentais:

### Módulo 1: Validação e Disponibilidade
* **Entrada:** Recebe e confere novos itens no sistema.
* **Validação Financeira:** Garante que o valor pago é suficiente para cobrir o custo da venda.
* **Check de Inventário:** Bloqueia vendas caso não existam unidades disponíveis.

### Módulo 2: Processamento Lógico
* **Movimentação de Stock:** Atualiza as quantidades no dicionário global de forma atómica.
* **Algoritmo de Troco Otimizado:** Calcula a menor quantidade de notas necessária para o troco utilizando as cédulas: `100, 50, 20, 10, 5, 2, 1`.

### Módulo 3: Persistência e Saída
* **Update do Banco de Dados:** Regista o estado final do inventário após a transação.
* **Comprovativo de Venda:** Gera um resumo detalhado para o cliente.

---

## 📉 Fluxogramas de Processo



### Fluxo de Venda (Saída)
1. **Início:** Receção do pedido de venda.
2. **Módulo 1:** Verificação de disponibilidade e saldo atual.
   - *Se Negativo:* Notificação de "Estoque Insuficiente" -> Fim.
   - *Se Positivo:* Avança para o Módulo 2.
3. **Módulo 2:** Processamento de baixa e cálculo de troco (Divisão Inteira/Módulo).
4. **Módulo 3:** Atualização do estado final e emissão de talão.

---

## 💻 Exemplo de Implementação (Python)

### Estrutura de Dados (In-Memory)
```python
estoque = {
    "Air Max_40": 5,
    "All Star_38": 2
}
