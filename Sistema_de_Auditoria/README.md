Auditoria de Orçamentos Corporativos
Disciplina: Python Avançado  

Conceitos Aplicados: Recursão, Decorators, *args, kwargs

  

1. Visão Geral do Projeto
Este sistema simula uma auditoria financeira automatizada para uma estrutura organizacional complexa. O script é capaz de processar dicionários aninhados que representam departamentos e sub-departamentos, permitindo:  

Cálculo Recursivo: Soma de valores em qualquer nível de profundidade da estrutura.  

Filtragem Dinâmica: Exclusão de setores específicos via argumentos variáveis (*args).  

Conversão de Moedas: Aplicação de taxas de câmbio flexíveis via parâmetros nomeados (kwargs).  

Monitoramento: Auditoria de tempo de execução e inspeção de dados através de decoradores.  

2. Código-Fonte Completo
Python

import time

# =============================================================================
# 1. DECORATOR @auditor
# =============================================================================

def auditor(funcao):
    """
    Decorator responsável por monitorar a execução da função de cálculo.
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
# 2. ESTRUTURA DE DADOS (Dicionários Aninhados)
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
# 3. LÓGICA DE PROCESSAMENTO (Recursão e Args/Kwargs)
# =============================================================================

@auditor
def calcular_orcamento(estrutura, *args, **kwargs):

    def _somar_recursivo(no, ignorados):
        total = 0

        # Caso base: valor numérico
        if isinstance(no, (int, float)):
            return no

        # Caso recursivo: dicionário
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
# 4. EXEMPLOS DE EXECUÇÃO
# =============================================================================

if __name__ == "__main__":

    # Cálculo 1: Empresa inteira com conversão
    total_1 = calcular_orcamento(
        empresa,
        moeda_destino="BRL",
        taxa_cambio=5.20
    )

    # Cálculo 2: Filtrando departamentos específicos
    total_2 = calcular_orcamento(
        empresa,
        "Vendas",
        "RH",
        moeda_destino="BRL",
        taxa_cambio=5.20
    )
3. Explicação Técnica
*args: Captura todos os nomes de departamentos que devem ser ignorados durante a soma, transformando-os em um conjunto (set) para otimizar a busca.  

kwargs: Permite definir parâmetros de conversão de moeda de forma opcional, garantindo que o código funcione tanto para orçamentos locais quanto globais.  

Recursão: A função _somar_recursivo mergulha nos dicionários aninhados, tratando cada nível como uma nova estrutura até alcançar os valores numéricos finais.
