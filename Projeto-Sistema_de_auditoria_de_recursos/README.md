# 🏢 Sistema de Cálculo de Orçamento Corporativo

Sistema desenvolvido em Python puro que simula a estrutura financeira hierárquica de uma multinacional. O script percorre recursivamente um dicionário aninhado de profundidade desconhecida, calculando orçamentos com suporte a filtros por departamento, conversão de moeda e auditoria automática de execução.

<br>

## 🚀 Funcionalidades

- 🌳 **Recursão** — navega por toda a árvore hierárquica, independente da profundidade
- 🚫 **Departamentos Ignorados** — exclui setores e todos os seus sub-departamentos via `*args`
- 💱 **Conversão de Moeda** — aplica taxa de câmbio ao total via `**kwargs`
- 🔍 **Auditoria Automática** — decorator `@auditor` registra argumentos e tempo de execução

<br>

## 🛠️ Tecnologias

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Lib](https://img.shields.io/badge/Biblioteca-time%20(stdlib)-grey?style=for-the-badge)

> Nenhuma dependência externa. Apenas Python 3.10+ instalado é suficiente.

<br>

## 📂 Estrutura do Projeto

```
📦 orcamento-corporativo
 ┣ 📄 orcamento_empresa.py   # Script principal
 ┗ 📄 README.md              # Documentação
```

<br>

## ▶️ Como Executar

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/seu-repositorio.git

# 2. Acesse a pasta
cd seu-repositorio

# 3. Execute
python orcamento_empresa.py
```

<br>

## 🧠 Conceitos Aplicados

### 🔁 Recursão
A função auxiliar interna `_somar()` chama a si mesma sempre que encontra um sub-dicionário, descendo quantos níveis forem necessários até atingir os valores numéricos (nós folha).

```python
def _somar(no, ignorados):
    for chave, valor in no.items():
        if isinstance(valor, dict):
            total += _somar(valor, ignorados)   # ← chamada recursiva
        elif isinstance(valor, (int, float)):
            total += valor
```

---

### 📦 `*args` — Departamentos Ignorados
Permite passar zero ou mais nomes de departamentos que serão excluídos da soma. Toda a subárvore do departamento ignorado também é descartada.

```python
# Ignora Marketing e Juridico (e todos os seus filhos)
calcular_orcamento(empresa, "Marketing", "Juridico")
```

---

### 🔑 `**kwargs` — Conversão de Moeda
Aceita `moeda_destino` e `taxa_cambio` como parâmetros nomeados opcionais. O valor final é multiplicado pela taxa antes de ser retornado. Se omitidos, o retorno é em BRL sem alteração.

```python
# Converte o total para USD
calcular_orcamento(empresa, moeda_destino="USD", taxa_cambio=0.19)
```

---

### 🎯 Decorator `@auditor`
Envolve `calcular_orcamento` de forma transparente. A função interna `wrapper(*args, **kwargs)` garante compatibilidade com qualquer assinatura de função.

**O que o decorator registra:**

| Campo | Descrição |
|---|---|
| Função auditada | Nome da função decorada |
| `*args` recebidos | Departamentos marcados para ignorar |
| `**kwargs` recebidos | Parâmetros de conversão de moeda |
| Tempo de execução | Medido com `time.perf_counter()` |

<br>

## 🖥️ Saída do Terminal

<details>
<summary><strong>Cenário 1</strong> — Orçamento total, sem filtros</summary>

```
============================================================
          SISTEMA DE AUDITORIA — INÍCIO DO CÁLCULO
============================================================
  Função auditada  : calcular_orcamento
  Departamentos ignorados (*args) : Nenhum
  Parâmetros de conversão (**kwargs): Nenhum
------------------------------------------------------------

  Orçamento bruto (BRL)     : R$    3,640,000.00

------------------------------------------------------------
  Tempo de processamento : 0.000323 segundos
============================================================
          SISTEMA DE AUDITORIA — CÁLCULO ENCERRADO
============================================================
  Resultado final: R$ 3,640,000.00
```
</details>

<details>
<summary><strong>Cenário 2</strong> — Ignorando Marketing e Juridico</summary>

```
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
  Tempo de processamento : 0.000054 segundos
============================================================
          SISTEMA DE AUDITORIA — CÁLCULO ENCERRADO
============================================================
  Resultado final: R$ 3,090,000.00
```
</details>

<details>
<summary><strong>Cenário 3</strong> — Convertendo para USD, ignorando Filial_RJ</summary>

```
============================================================
          SISTEMA DE AUDITORIA — INÍCIO DO CÁLCULO
============================================================
  Função auditada  : calcular_orcamento
  Departamentos ignorados (*args) : ('Filial_RJ',)
  Parâmetros de conversão (**kwargs): {'moeda_destino': 'USD', 'taxa_cambio': 0.19}
------------------------------------------------------------
  [IGNORADO] Departamento 'Filial_RJ' excluído da soma.

  Orçamento bruto (BRL)     : R$    2,920,000.00
  Taxa de câmbio aplicada   :             0.1900
  Orçamento convertido (USD): USD     554,800.00

------------------------------------------------------------
  Tempo de processamento : 0.000027 segundos
============================================================
          SISTEMA DE AUDITORIA — CÁLCULO ENCERRADO
============================================================
  Resultado final: USD 554,800.00
```
</details>


## 🧠 Lógica e Estrutura do Código
O código foi organizado separando claramente as responsabilidades. A lógica principal de cálculo foi construída com uma função recursiva interna (_somar_recursivo), responsável por percorrer toda a estrutura hierárquica da empresa (dicionário aninhado). A cada nível, ela verifica se o valor é numérico (caso base) ou outro dicionário (caso recursivo), somando os valores enquanto respeita os departamentos que devem ser ignorados. Essa separação permite que a recursão fique isolada, simples e focada apenas no processamento dos dados.
 
## 👤 Autor [Guilherme da silva ferreira batista]
  ** * LinkedIn: [https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white]*      ﻿[ E-mail: dark60895@gmail.com]
 
  Já o decorator @auditor foi acoplado de forma externa à função principal (calcular_orcamento), sem interferir na lógica da recursão. Ele atua como uma camada adicional responsável por auditoria: exibindo informações de entrada (*args e *kwargs), controlando o tempo de execução e padronizando a saída. Dessa forma, o código fica modular, reutilizável e mais organizado, seguindo o princípio de separação de responsabilidades.
 
 

<

