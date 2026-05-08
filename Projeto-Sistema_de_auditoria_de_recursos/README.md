markdown
# 📊 Sistema de Orçamento Corporativo com Auditoria

Sistema robusto para cálculo de orçamento em estruturas hierárquicas de empresas multinacionais, com suporte a:

- ✅ Navegação recursiva em dicionários aninhados
- ✅ Filtro seletivo de departamentos (ignorar setores inteiros)
- ✅ Conversão de moeda com taxa de câmbio personalizada
- ✅ Sistema de auditoria automática com medição de tempo
- ✅ Registro detalhado de todas as operações

## 🏗️ Estrutura da Empresa

| Departamento | Subdepartamentos | Orçamento (R$) |
|-------------|------------------|----------------|
| **Matriz - TI** | Infraestrutura, Desenvolvimento | 760.000 |
| **Matriz - RH** | Recrutamento, Treinamento, Benefícios | 185.000 |
| **Matriz - Financeiro** | Contabilidade, Auditoria, Tesouraria | 335.000 |
| **Matriz - Marketing** | Mídias Pagas, Conteúdo, Branding | 390.000 |
| **Filial_SP - Operações** | Logística, Estoque | 265.000 |
| **Filial_SP - Vendas** | Varejo, Atacado, E-commerce | 930.000 |
| **Filial_SP - Suporte** | - | 55.000 |
| **Filial_RJ - Operações** | Logística, Estoque | 210.000 |
| **Filial_RJ - Vendas** | Varejo, Atacado | 350.000 |
| **Filial_RJ - Jurídico** | Contratos, Compliance | 160.000 |
| **TOTAL** | | **R$ 3.640.000,00** |

text

**Orçamento total bruto:** R$ 3.640.000,00

## 🎯 Funcionalidades Principais

### 1. Cálculo Recursivo Inteligente
Percorre automaticamente toda a árvore hierárquica, somando valores numéricos em qualquer nível de profundidade.

### 2. Filtro por Departamentos
Ignore departamentos específicos (e todos os seus subdepartamentos) usando `*args`:

```python
# Ignorar Marketing e Jurídico
calcular_orcamento(empresa, "Marketing", "Juridico")
3. Conversão de Moeda
Converta o resultado final para qualquer moeda usando **kwargs:

python
# Converter para USD com taxa 0.19
calcular_orcamento(
    empresa, 
    moeda_destino="USD", 
    taxa_cambio=0.19
)
4. Sistema de Auditoria Automático
O decorator @auditor registra automaticamente:

📋 Função auditada

🚫 Departamentos ignorados

💱 Parâmetros de conversão

⏱️ Tempo de processamento

📊 Resumo financeiro

📈 Exemplos de Uso
Cenário 1: Orçamento Total
python
total = calcular_orcamento(empresa)
# Resultado: R$ 3.640.000,00
Cenário 2: Com Filtros
python
total = calcular_orcamento(empresa, "Marketing", "Juridico")
# Resultado: R$ 3.090.000,00
# (Exclui Marketing da Matriz e Jurídico da Filial_RJ)
Cenário 3: Conversão Cambial
python
total = calcular_orcamento(
    empresa,
    "Filial_RJ",
    moeda_destino="USD",
    taxa_cambio=0.19
)
# Resultado: USD 554.800,00
📝 Saída do Sistema de Auditoria
text
============================================================
          SISTEMA DE AUDITORIA — INÍCIO DO CÁLCULO
============================================================
  Função auditada  : calcular_orcamento
  Departamentos ignorados (*args) : ('Marketing', 'Juridico')
  Parâmetros de conversão (**kwargs): Nenhum
------------------------------------------------------------
  [IGNORADO] Departamento 'Marketing' excluído da soma.
  [IGNORADO] Departamento 'Juridico' excluído da soma.

  Orçamento bruto (BRL)     : R$    3,090,000.00

------------------------------------------------------------
  Tempo de processamento : 0.000029 segundos
============================================================
          SISTEMA DE AUDITORIA — CÁLCULO ENCERRADO
============================================================
🛠️ API da Função Principal
calcular_orcamento(estrutura, *args, **kwargs)
Parâmetros:

estrutura (dict): Dicionário aninhado com os orçamentos

*args (str): Nomes dos departamentos a ignorar

**kwargs:

moeda_destino (str): Símbolo da moeda (ex: "USD", "EUR")

taxa_cambio (float): Fator de conversão (padrão: 1.0)

Retorno:

float: Total do orçamento (convertido se taxa fornecida)

🔧 Requisitos
Python 3.7+

Módulo time (biblioteca padrão)

🚀 Como Executar
bash
python orcamento_empresa.py
O sistema executará automaticamente três cenários de demonstração com diferentes combinações de filtros e conversões cambiais.

📊 Estatísticas de Performance
⚡ Processamento em microssegundos

🔄 Navegação recursiva otimizada

📦 Suporta estruturas de qualquer profundidade

Desenvolvido com Python 🐍 | Sistema de Auditoria Integrado ✅

text

Este README fornece uma documentação completa e profissional do seu sistema, destacando todas as funcionalidades, exemplos de uso e a saída esperada do sistema de auditoria.
