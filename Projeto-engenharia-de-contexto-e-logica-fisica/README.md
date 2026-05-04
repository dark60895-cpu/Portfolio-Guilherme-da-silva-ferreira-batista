# 🚀 Portfólio de Lógica de Programação & Auditoria de Sistemas

[![Python Version](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Este repositório reúne uma série de desafios práticos que conectam a lógica de programação com situações reais, abrangendo desde a gestão financeira até protocolos de segurança residencial.

---

## 📂 Projetos e Exercícios

### 1. Sistema de Gestão de Inventário e PDV
Desenvolvimento de um sistema modular para controle de stock e automação de vendas.
*   **Módulo 1:** Validação de transações e disponibilidade de produtos.
*   **Módulo 2:** Processamento de baixa e algoritmo de troco otimizado utilizando divisão inteira (`//`) e módulo (`%`).
*   **Módulo 3:** Atualização de banco de dados (dicionários) e emissão de comprovativos.

### 2. Algoritmo de Auditoria de Dados (Outliers)
Investigação sobre como valores extremos podem distorcer análises e ocultar fraudes.
*   **Conceitos:** Normalização de dados e Margem de Tolerância (Distorção Tolerável).
*   **Segurança:** Análise dos perigos de variáveis globais em sistemas bancários e a importância da proteção de dados críticos.

### 3. Modelagem de Microclima e Evacuação Lógica
Mapeamento físico de uma residência convertido em uma estrutura de dados para navegação em emergências.
*   **Simulação de Microclima:** Algoritmo que ajusta temperatura e humidade com base na arquitetura de cada cómodo (ex: retenção de calor na Sala vs. exposição na Varanda).
*   **Nós de Decisão:** Implementação de lógica recursiva para evacuação, considerando inventário (chaves) e níveis de energia para ações de alto risco.

---

## 💻 Exemplos de Implementação

### Algoritmo de Cálculo de Troco (PDV)
```python
def calcular_troco(valor_troco):
    cedulas = [100, 50, 20, 10, 5, 2, 1]
    resultado = {}
    for nota in cedulas:
        quantidade = valor_troco // nota
        if quantidade > 0:
            resultado[nota] = quantidade
            valor_troco %= nota
    return resultado
