# 🏥 Hospital Triage Simulation: Resilient Engine
> **Projeto de Automação de Triagem baseada no Protocolo de Manchester**[cite: 1]

## 📝 Sobre o Projeto
Este repositório contém a lógica de um motor de processamento para triagem hospitalar. O sistema foi projetado para converter a subjetividade clínica em regras binárias rígidas, garantindo que a priorização de pacientes seja feita de forma rápida, segura e à prova de falhas.

O projeto evoluiu de um fluxograma de decisão simples para um algoritmo resiliente que considera falhas de sensores e dados implausíveis, garantindo a continuidade do cuidado médico.

## 🚀 Funcionalidades Principais
- **Classificação Automática:** Processamento de sinais vitais (Temperatura, FC, Oxigenação) para definir o nível de urgência[cite: 1, 3].
- **Arquitetura de Resiliência (VAR):** Sistema preparado para lidar com três cenários distintos de entrada de dados.
- **Protocolo de Fallback (Plano B):** Mecanismo de segurança que aciona a intervenção humana imediata em caso de erro técnico.

## 🧠 Lógica de Processamento (Cenários VAR)
O algoritmo `Triagem_Emergencia_Resiliente_VAR` opera sob três camadas de verificação:

1. **Cenário C (Tratamento de Exceção):** 
   - Identifica falhas no status do sensor ou dados anatomicamente impossíveis (ex: Batimentos > 250).
   - **Ação:** Alerta de falha e encaminhamento imediato para triagem manual.
2. **Cenário B (Limite/Borda):** 
   - Monitora pacientes que atingem exatamente o limite crítico (ex: 90% de oxigenação ou 100 BPM).
   - **Ação:** Classificação Amarela (Monitoramento Urgente de Risco).
3. **Cenário A (Entrada Ideal):** 
   - Processamento padrão para emergências claras (Oxigenação < 90% ou FC > 120).
   - **Ação:** Classificação Vermelha (Emergência).

## 🛠 Desafios de Desenvolvimento & Logística
Durante a elaboração deste projeto, foram abordados dois desafios críticos do setor de tecnologia em saúde:
*   **Subjetividade vs. Binário:** O obstáculo de transformar a nuance do diagnóstico clínico em regras de "Sim/Não" para o computador.
*   **Redundância e Validação:** A implementação de validação de dados para evitar que sensores quebrados ou erros humanos comprometam a segurança do paciente.

## 🔧 Estrutura do Algoritmo
O sistema segue a seguinte ordem de execução:
1. **Coleta:** Nome, Idade, Sintomas e Sinais Vitais[cite: 1].
2. **Sanitização:** Verificação de plausibilidade dos valores recebidos.
3. **Decisão:** Cascata de condicionais (Emergência -> Urgência -> Leve).
4. **Fallback:** Verificação final de integridade do processo.

---
[Voltar ao início](https://github.com/dark60895-cpu/Portifolio-Guilherme-da-silva-ferreira-batista)
