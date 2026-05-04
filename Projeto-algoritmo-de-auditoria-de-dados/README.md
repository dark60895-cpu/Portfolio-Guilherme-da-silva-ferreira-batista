# 📊 Auditoria de Dados e Análise de Outliers

[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Field](https://img.shields.io/badge/campo-Auditoria%20Financeira-green.svg)](#)

Este projeto explora o impacto de discrepâncias de dados (outliers) na análise de médias e a importância da segurança lógica em sistemas de auditoria financeira.

---

## 🔍 1. Investigação e Descoberta

A fase inicial foca em conceitos estatísticos e regras de negócio essenciais para a fidedignidade dos dados.

*   **Discrepância de Dados (Outliers):** Valores significativamente fora da curva padrão que podem distorcer a média aritmética. Por exemplo, no conjunto $(100, 120, 110)$, a média é $110$; a inclusão de um valor extremo como $5000$ "puxa" a média para cima, deixando de representar a maioria dos dados.
*   **Normalização:** Técnica de ignorar valores extremos (máximos e mínimos) para obter um resultado que represente o comportamento "normal" do grupo, livre de interferências de casos fora do padrão.
*   **Margem de Tolerância (Distorção Tolerável):** Representa o limite máximo de erro ou irregularidade que um auditor aceita em uma transação antes que isso altere a opinião sobre a fidedignidade das demonstrações financeiras.

---

## 💻 2. Desenvolvimento em Python

Implementação de um algoritmo de validação de vendas com base em limites de segurança.
```python
# Configuração de Auditoria
limite_seguranca = 10000

# Entrada de Dados
num1 = float(input("Venda 01: "))
num2 = float(input("Venda 02: "))
num3 = float(input("Venda 03: "))

# Processamento da Média
media = (num1 + num2 + num3) / 3

# Validação Lógica
if media >= limite_seguranca:
    print("Limite de segurança atingido")
else:
    print("Sistema em quarentena")

# Relatório de Tipagem e Depuração
print("-" * 40)
print(f"Venda 01: {num1} | Tipo: {type(num1)}")
print(f"Média: {media:.2f} | Tipo: {type(media)}")
print(f"Limite: {limite_seguranca} | Tipo: {type(limite_seguranca)}")
print("-" * 40)
