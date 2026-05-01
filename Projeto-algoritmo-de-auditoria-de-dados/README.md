# 🛡️ Algoritmo de Auditoria de Dados
 
## 📝 Descrição do Projeto
Este projeto consiste em um sistema de **auditoria de dados financeiros** desenvolvido para identificar discrepâncias (outliers) e monitorar limites de segurança em transações de vendas. O objetivo principal é garantir a fidedignidade das demonstrações financeiras, mitigando o impacto de valores extremos que podem distorcer a média real de um grupo de dados[cite: 3].
 
Desenvolvido como parte de um exercício prático de **Lógica de Programação com Python**, o algoritmo aplica conceitos de **Distorção Tolerável** (Margem de Tolerância) e normalização de dados para validar se o comportamento de um conjunto de vendas está dentro dos parâmetros de segurança estabelecidos[cite: 3].
 
> **Nota de Auditoria:** O sistema utiliza o conceito de "quarentena" para fluxos que não atingem o limite de segurança, sinalizando a necessidade de análise humana para identificar possíveis fraudes ou erros críticos[cite: 3].
 
## 🚀 Tecnologias Utilizadas
* **Linguagem:** Python 3.x[cite: 3].
* **Conceitos Aplicados:** Conversão de tipos (`float`), f-strings para formatação, estruturas condicionais e tratamento de discrepâncias[cite: 3].
* **Ambiente:** Google Colab / Jupyter Notebook[cite: 3].
 
## 📊 Resultados e Aprendizados
O desenvolvimento deste algoritmo permitiu a compreensão prática de como dados mal geridos podem afetar decisões corporativas.
 
* **Identificação de Outliers:** Compreensão de como um único valor discrepante pode "puxar" a média e invalidar uma análise estatística[cite: 3].
* **Segurança da Informação:** Análise do perigo de utilizar variáveis globais em sistemas bancários reais, o que poderia gerar brechas de segurança e prejuízos financeiros[cite: 3].
* **Distorção Tolerável:** Implementação da lógica de limite máximo de erro aceitável antes que a integridade dos dados seja comprometida[cite: 3].
* **Tratamento de Erros:** Experiência prática na resolução de erros de sintaxe e lógica de indentação durante o desenvolvimento[cite: 3].
 
## 🔧 Como Executar
1. Certifique-se de ter o **Python 3** instalado em sua máquina.
2. Clone este repositório ou baixe o arquivo `.py`.
3. Execute o script via terminal:
   ```bash
   python auditoria_vendas.py
