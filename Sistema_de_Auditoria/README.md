# Auditoria de Orçamentos Corporativos

**Disciplina:** Python Avançado  
**Conceitos aplicados:** Recursão, Decorators, *args, **kwargs  

---

## Código Completo

```python
import time

# =============================================================================
# 1. DECORATOR @auditor
# =============================================================================

def auditor(funcao):
    """
    Decorator responsável por:
    - Exibir cabeçalho de auditoria antes da execução
    - Registrar os argumentos recebidos
    - Medir e exibir o tempo total de execução
    """
    def wrapper(*args, **kwargs):
        print("=" * 60)
        print("       SISTEMA DE AUDITORIA - INÍCIO DO CÁLCULO")
        print("=" * 60)

        if args:
            estrutura = args[0]
            ignorados = args[1:]
            print(f"  Estrutura recebida: {type(estrutura).__name__}")
            if ignorados:
                print(f"  Departamentos ignorados: {ignorados}")
            else:
                print("  Departamentos ignorados: nenhum")

        if kwargs:
            print(f"  Parâmetros de conversão: {kwargs}")
        else:
            print("  Conversão de moeda: não aplicada")

        print("-" * 60)

        inicio = time.time()
        resultado = funcao(*args, **kwargs)
        fim = time.time()

        tempo_total = fim - inicio

        print("-" * 60)
        print(f"  Tempo de processamento: {tempo_total:.6f} segundos")
        print("=" * 60)

        return resultado

    return wrapper


# =============================================================================
# 2. ESTRUTURA DE DADOS
# =============================================================================

empresa = {
    "Matriz": {
        "TI": {
            "Infraestrutura": 150_000,
            "Desenvolvimento": {
                "Backend": 200_000,
                "Frontend": 180_000,
                "QA": 90_000
            },
            "Segurança": 120_000
        },
        "RH": {
            "Recrutamento": 80_000,
            "Treinamento": 60_000,
            "Benefícios": 110_000
        },
        "Financeiro": {
            "Contabilidade": 95_000,
            "Controladoria": 130_000,
            "Tesouraria": 75_000
        }
    },
    "Filial_SP": {
        "Vendas": {
            "Comercial": 220_000,
            "Marketing": 160_000,
            "CRM": 50_000
        },
        "Operações": {
            "Logística": 140_000,
            "Estoque": 85_000
        }
    },
    "Filial_RJ": {
        "Vendas": {
            "Comercial": 190_000,
            "Marketing": 130_000
        },
        "Suporte": 70_000
    }
}


# =============================================================================
# 3. FUNÇÃO RECURSIVA
# =============================================================================

@auditor
def calcular_orcamento(estrutura, *args, **kwargs):

    def _somar_recursivo(no, ignorados):
        total = 0

        if isinstance(no, (int, float)):
            return no

        if isinstance(no, dict):
            for chave, valor in no.items():

                if chave in ignorados:
                    print(f"  [IGNORADO] Departamento '{chave}' foi excluído.")
                    continue

                total += _somar_recursivo(valor, ignorados)

        return total

    departamentos_ignorados = set(args)

    total_base = _somar_recursivo(estrutura, departamentos_ignorados)

    taxa = kwargs.get("taxa_cambio", 1.0)
    moeda = kwargs.get("moeda_destino", "USD")

    total_convertido = total_base * taxa

    print(f"\n  Orçamento base (USD): $ {total_base:,.2f}")
    print(f"  Taxa de câmbio ({moeda}): {taxa}")
    print(f"  Total convertido ({moeda}): R$ {total_convertido:,.2f}")

    return total_convertido


# =============================================================================
# 4. EXECUÇÃO
# =============================================================================

if __name__ == "__main__":

    print("\n>>> CÁLCULO 1: Completo em BRL\n")
    total_1 = calcular_orcamento(
        empresa,
        moeda_destino="BRL",
        taxa_cambio=5.20
    )
    print(f"\nRESULTADO: R$ {total_1:,.2f}\n")


    print("\n>>> CÁLCULO 2: Ignorando Vendas e RH\n")
    total_2 = calcular_orcamento(
        empresa,
        "Vendas",
        "RH",
        moeda_destino="BRL",
        taxa_cambio=5.20
    )
    print(f"\nRESULTADO: R$ {total_2:,.2f}\n")


    print("\n>>> CÁLCULO 3: Apenas TI e Financeiro\n")
    total_3 = calcular_orcamento(
        empresa,
        "Vendas",
        "RH",
        "Operações",
        "Suporte",
        "Filial_RJ"
    )
    print(f"\nRESULTADO: $ {total_3:,.2f}\n")

## 🧠 Lógica e Estrutura do Código
O código foi organizado separando claramente as responsabilidades. A lógica principal de cálculo foi construída com uma função recursiva interna (_somar_recursivo), responsável por percorrer toda a estrutura hierárquica da empresa (dicionário aninhado). A cada nível, ela verifica se o valor é numérico (caso base) ou outro dicionário (caso recursivo), somando os valores enquanto respeita os departamentos que devem ser ignorados. Essa separação permite que a recursão fique isolada, simples e focada apenas no processamento dos dados.
## 👤 Autor [Guilherme da silva ferreira batista]** * LinkedIn: [https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white]*[ E-mail: dark60895@gmail.com]
Já o decorator @auditor foi acoplado de forma externa à função principal (calcular_orcamento), sem interferir na lógica da recursão. Ele atua como uma camada adicional responsável por auditoria: exibindo informações de entrada (*args e *kwargs), controlando o tempo de execução e padronizando a saída. Dessa forma, o código fica modular, reutilizável e mais organizado, seguindo o princípio de separação de responsabilidades.
