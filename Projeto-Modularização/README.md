# 👟 Sneaker Control System

## 📝 Descrição do Projeto
O **Sneaker Control** é um sistema modular de gestão de inventário e ponto de venda (PDV) desenvolvido para otimizar o fluxo de entrada e saída de mercadorias em lojas de calçados. O projeto foi concebido através de um mapeamento lógico detalhado, garantindo que cada transação, desde o recebimento de mercadoria até o cálculo de troco, siga regras de negócio rigorosas.

O sistema resolve problemas comuns de varejo, como a "venda fantasma" (venda de itens sem stock) e a automação do cálculo de cédulas para troco.

---

## 🏗️ Arquitetura do Sistema
O software foi desenhado seguindo uma arquitetura modular dividida em três etapas principais:

### 📥 Módulo 1: Entrada e Validação
- **Recebimento:** Registo de novos lotes de mercadoria.
- **Conferência:** Validação de modelos e quantidades antes da atualização do banco de dados.
- **Verificação de Disponibilidade:** Verificação em tempo real se o stock comporta um pedido de venda.

### ⚙️ Módulo 2: Processamento
- **Atualização de Saldo:** Incremento (entrada) ou decremento (saída) automatizado de itens.
- **Registo de Transação:** Log detalhado de cada movimentação realizada no sistema.

### 📄 Módulo 3: Finalização e Financeiro
- **Emissão de Comprovante:** Geração de recibos de venda.
- **Lógica de Troco:** Algoritmo de otimização de cédulas que calcula a menor quantidade de notas necessária para o troco do cliente.

---

## 📊 Fluxogramas do Processo
A lógica do sistema foi validada através de diagramas de blocos que garantem a integridade do fluxo de dados:

1. **Fluxo de Entrada:** Início -> Recebimento -> Conferência -> Atualização de Banco de Dados -> Fim.
2. **Fluxo de Saída:** Início -> Pedido -> Verificação de Stock (Sim/Não) -> Processamento -> Emissão de Comprovante -> Fim.

---

## 🚀 Tecnologias Utilizadas
* **Linguagem:** Python 3.x
* **Paradigma:** Programação Estruturada e Modular
* **Estruturas de Dados:** Dicionários (para mapeamento de stock) e Listas (para gestão de cédulas).

---

## 💻 Exemplos de Implementação

### Gestão de Stock
O sistema utiliza identificadores únicos (SKUs) para cada modelo:
```python
# Exemplo de processamento de venda
def venda_tenis(modelo, quantidade):
    saldo_atual = estoque.get(modelo, 0)
    if saldo_atual >= quantidade:
        estoque[modelo] -= quantidade
        print(f"Venda confirmada: {quantidade} {modelo}(s).")
    else:
        print(f"Erro: Stock insuficiente de {modelo}.")
