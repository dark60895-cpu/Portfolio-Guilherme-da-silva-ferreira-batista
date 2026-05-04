# 🎬 Sistema de Recomendação de Filmes

## 📝 Descrição do Projeto
Este projeto consiste em um motor de recomendação inteligente que utiliza técnicas de filtragem colaborativa e baseada em conteúdo. O objetivo principal é mitigar a "paralisia de escolha", oferecendo aos usuários sugestões personalizadas com base em seu histórico de visualização e preferências de gênero.

Desenvolvido como parte da disciplina de **Inteligência Artificial (2024.1)**, o sistema processa grandes volumes de dados (datasets de filmes e avaliações) para identificar padrões de comportamento e similaridades entre títulos, utilizando algoritmos de aprendizado de máquina para prever a nota que um usuário daria a um filme ainda não assistido.

![Dashboard do Sistema](http://googleusercontent.com/image_generation_content/0)
*Figura 1: Dashboard principal do sistema exibindo recomendações personalizadas.*

## 🚀 Tecnologias Utilizadas
* **Linguagem:** Python 3.10
* **Bibliotecas:** Pandas, Scikit-learn, Matplotlib
* **Ferramentas:** Jupyter Notebook, Google Colab

## 🧠 Reflexões Técnicas e Aprendizados
A implementação deste projeto envolveu a tradução de conceitos de lógica de programação para a sintaxe específica do Python, conforme documentado no arquivo `Projeto-traduzindo-logica-para-python.ipynb`:

### 1. Manipulação de Tipagem e Entrada de Dados
* **Comportamento do `input()`**: Em Python, a função `input()` sempre retorna dados como uma `String`.
* **Necessidade de Conversão**: Para realizar cálculos matemáticos com as avaliações e metadados, é essencial o uso de `int()` ou `float()`, caso contrário, o operador `+` apenas concatena os textos (ex: "5" + "5" vira "55").
* **Tratamento de Erros**: A ausência de conversão correta pode resultar em erros de execução do tipo `TypeError` em operações de divisão ou subtração.

### 2. Estruturas de Repetição e a Função `range()`
* **Limite Superior Exclusivo**: Ao contrário do pseudocódigo tradicional, o limite final da função `range()` no Python é exclusivo.
* **Lógica de Iteração**: Para incluir o último número em uma contagem (como o total de meses processados), deve-se utilizar a sintaxe `range(1, total_meses + 1)`.
* **Design do Python**: O uso de índice zero e o foco na "distância" entre os números (onde o número de repetições é o fim menos o início) facilita a manipulação de listas de dados no sistema.

## 📊 Resultados do Modelo
O projeto alcançou resultados sólidos em ambiente de teste, demonstrando a eficácia do modelo híbrido:
* **Acurácia de 92%**: O modelo atingiu alta precisão nos testes de validação.
* **Redução de Ruído**: Aplicação de técnicas de limpeza e normalização de dados para otimizar a performance dos algoritmos.
* **Visualização de Clusters**: Implementação de gráficos que demonstram o agrupamento de filmes por afinidade de gênero e comportamento.

## 🔧 Como Executar
# 1. Clone o repositório
[git clone](https://github.com/dark60895-cpu/Portifolio-Guilherme-da-silva-ferreira-batista)

# 2. Acesse a pasta do projeto
cd Portifolio-Guilherme-da-silva-ferreira-batista

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Inicie o Jupyter Notebook
jupyter notebook
