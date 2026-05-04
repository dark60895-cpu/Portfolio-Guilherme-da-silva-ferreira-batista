# Projeto algoritmo de auditoria de dados
# 📊 Algoritmo de Auditoria de Dados (EX1)

[![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Este projeto foi desenvolvido para explorar os conceitos de **Análise de Dados**, **Segurança Financeira** e **Tratamento de Exceções** utilizando Python. O foco principal foi entender como valores atípicos (*outliers*) impactam médias e como garantir a integridade de sistemas críticos.

---

## 📖 Parte 1: Investigação e Descoberta

Antes da codificação, foram analisados conceitos fundamentais de auditoria:

*   **Discrepância de Dados (Outliers):** Valores que fogem significativamente do padrão do grupo. Um único valor extremamente alto ou baixo pode distorcer a média, fazendo com que ela não represente a maioria dos dados.
*   **Normalização:** Técnica de ignorar valores extremos (máximos e mínimos) para obter um resultado que represente o comportamento "normal" do grupo sem interferências externas.
*   **Margem de Tolerância (Distorção Tolerável):** Em auditoria, é o limite máximo de erro ou irregularidade aceitável em uma transação sem que isso comprometa a fidedignidade das demonstrações financeiras.

---

## 💻 Parte 2: Desenvolvimento em Python

O algoritmo abaixo simula uma auditoria básica de vendas, comparando a média de transações com um limite de segurança.
```python
# Configuração do limite
limite_seguranca = 10000

# Entrada de dados
num1 = float(input("Venda 01: "))
num2 = float(input("Venda 02: "))
num3 = float(input("Venda 03: "))

# Cálculo da média
media = (num1 + num2 + num3) / 3

# Lógica de Auditoria
if media >= limite_seguranca:
    print("Limite de segurança atingido")
else:
    print("Sistema em quarentena")

# Relatório de Diagnóstico
print("-" * 40)
print(f"Venda 01: {num1} | Tipo: {type(num1)}")
print(f"Venda 02: {num2} | Tipo: {type(num2)}")
print(f"Venda 03: {num3} | Tipo: {type(num3)}")
print(f"Média: {media:.2f} | Tipo: {type(media)}")
print(f"Limite: {limite_seguranca} | Tipo: {type(limite_seguranca)}")
print("-" * 40)
