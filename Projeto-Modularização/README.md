# Projeto-Modularização 
# 🛒 Sistema de Gestão de Inventário e PDV (Ponto de Venda)

> Solução modular para controlo de stock e automação de vendas, focada na integridade de dados e otimização do checkout.

---

## 📋 Visão Geral

Este projeto simula o ciclo de vida de produtos num ambiente de retalho. O sistema gere desde a entrada de mercadoria até à finalização da venda com cálculo automático de troco e atualização de inventário em tempo real. 

A arquitetura foi desenhada seguindo o princípio da **Modularização**, dividindo as responsabilidades para garantir um código limpo, escalável e de fácil manutenção.

---

## 🏗️ Arquitetura do Sistema

O sistema opera em três camadas lógicas fundamentais, garantindo que cada etapa do processo seja validada antes da próxima:

### 1. Módulo de Validação e Disponibilidade
* **Entrada:** Receção e conferência de itens.
* **Check de Inventário:** Bloqueia a transação caso não existam unidades disponíveis (Prevenção de stock negativo).
* **Validação Financeira:** Garante que o valor fornecido pelo cliente é suficiente para cobrir o custo total.

### 2. Módulo de Processamento Lógico
* **Movimentação de Stock:** Atualiza as quantidades no dicionário global de forma atómica.
* **Algoritmo de Troco Otimizado:** Utiliza lógica de divisão inteira e resto (`//` e `%`) para calcular a menor quantidade de notas necessária, utilizando cédulas de: 100, 50, 20, 10, 5, 2 e 1.

### 3. Módulo de Persistência e Saída
* **Update de Estado:** Regista o estado final do inventário após a transação.
* **Comprovativo de Venda:** Gera um resumo detalhado (Talão) com itens comprados, total pago e detalhamento do troco.

---

## 📉 Fluxograma do Processo

O fluxo de venda segue a seguinte hierarquia:

1.  **Início:** Receção do pedido.
2.  **Módulo 1:** Verificação de saldo.
    * *Se Insuficiente:* Notificação de erro e interrupção do processo.
    * *Se Disponível:* Avança para o processamento.
3.  **Módulo 2:** Baixa no stock e cálculo de troco.
4.  **Módulo 3:** Emissão de comprovativo e atualização de base de dados.

---

## 💻 Demonstração de Implementação

### Estrutura de Dados (Exemplo)
O sistema utiliza dicionários para uma busca rápida ($O(1)$) de produtos e tamanhos:

```python
estoque = {
    "Air Max_40": 5,
    "All Star_38": 2,
    "Tesla Coil_42": 10
}
