# Projeto desenhando emojis com dados

# 🎨 Python Matrix Suite: Processamento de Imagem e Dados Musicais

Este repositório reúne uma série de algoritmos em Python focados na manipulação de **estruturas de dados comp# 🎨 Python Matrix Suite: Emojis com Dados & Processamento de Matrizes

Este repositório reúne uma série de algoritmos em Python focados na manipulação de **estruturas de dados complexas**, matrizes multidimensionais e processamento de **Pixel Art**. O projeto utiliza bibliotecas de visualização científica para transformar matrizes numéricas em representações visuais.

---

## 🛠️ Tecnologias e Bibliotecas

* **Linguagem:** Python 3.x
* **Visualização:** `matplotlib` (utilizado para renderização de matrizes RGB e exibição de Pixel Art).
* **Estruturas de Dados:** Dicionários aninhados, listas multidimensionais e tuplas imutáveis para representação de canais de cor.

---

## 📂 Módulos do Projeto

### 1. Processamento de Imagem (Pixel Art RGB)
O projeto utiliza matrizes para representar emojis e ícones em formatos compactos (5x5 e 2x2).
* **Filtro de Luminosidade:** Implementação de um algoritmo que percorre a matriz e reduz o brilho de pixels específicos (ex: converte Amarelo Vibrante em Oliva) através de divisão inteira nos canais R, G e B.
* **Renderização Científica:** Conversão de arrays numéricos em imagens coloridas via `plt.imshow()`.

### 2. Gestão Dinâmica de Galeria
Demonstração de métodos avançados de manipulação de listas para gerenciar coleções de imagens digitais:
* **Navegação Profunda:** Acesso a dados em quatro níveis de aninhamento (`Dicionário > Lista > Dicionário > Lista`).
* **Manipulação de Pilha:** * Uso de `insert(0, ...)` para priorizar novos elementos no topo da galeria.
    * Uso de `pop()` para remoção controlada e edição *in-place* para otimização de memória.

### 3. Transposição de Matrizes Musicais
Algoritmo focado na reestruturação de frequências sonoras:
* **Lógica de Transposição:** Inversão de eixos em matrizes de frequências (Canais vs. Tempo/Frame).
* **Update Dinâmico:** Uso do método `.update()` para substituição atômica de dados processados.

---

## 💻 Exemplo de Lógica Aplicada

### Transformação de Cor em Matriz
O trecho abaixo exemplifica a lógica de identificação e processamento de pixels:

```python
# Exemplo de processamento de pixel individual
pixel = (255, 255, 0) # Amarelo Brilhante

if pixel == (255, 255, 0): 
    r, g, b = pixel
    # Aplica redução de 50% de luminosidade via divisão inteira
    novo_pixel = (r // 2, g // 2, b // 2) 
Estrutura de Dados da Galeria
O sistema organiza os emojis de forma hierárquica para facilitar a recursão:

Python
galeria_emojis = {
    "categoria": "Mix de Emojis",
    "itens": [
        {
            "titulo": "Emoji Sol",
            "resolucao": "5x5",
            "pixels": [
                [(255, 255, 0), (255, 255, 0), ...], # Linha 1
                [(255, 255, 0), (255, 255, 0), ...]  # Linha 2
            ]
        }
    ]
}
🚀 Como Visualizar os Emojis
Pré-requisitos
Certifique-se de ter o matplotlib instalado em seu ambiente:

Bash
pip install matplotlib
Execução
Para gerar as visualizações das matrizes, execute:

Bash
python desenha_emojis.py
O sistema abrirá uma janela de visualização mostrando a matriz de dados convertida em imagem.

🧠 Conceitos Demonstrados
Matrizes Coloridas: Representação e manipulação de cores no espaço RGB.

Algoritmos de Busca: Localização de padrões e filtros em listas aninhadas.

Modularização: Separação clara entre a lógica de processamento de dados e a camada de visualização.

✍️ Autor
Guilherme Silva Ferreira Batista Estudante de Análise e Desenvolvimento de Sistemas – UNICID

Projeto desenvolvido para exploração de algoritmos de transposição de matrizes e lógica de Pixel Art com Python.lexas**, matrizes multidimensionais e processamento de **Pixel Art** utilizando bibliotecas de visualização científica.

---

## 🛠️ Tecnologias e Bibliotecas
*   **Linguagem:** Python 3.x
*   **Visualização:** `matplotlib` (para renderização de matrizes RGB).
*   **Estruturas:** Dicionários aninhados, listas multidimensionais e tuplas.

---

## 📂 Módulos do Projeto

### 1. Processamento de Imagem (Pixel Art RGB)
O projeto utiliza matrizes para representar emojis em formato 5x5 e 2x2.
*   **Filtro de Luminosidade:** Implementação de um algoritmo que percorre a matriz e reduz o brilho de pixels específicos (amarelo) pela metade, utilizando divisão inteira nos canais R, G e B.
*   **Renderização:** Uso de `plt.imshow()` para converter dados numéricos em representações visuais coloridas.

### 2. Gestão Dinâmica de Playlists
Demonstração de métodos avançados de manipulação de listas para gerenciar uma galeria de imagens:
*   **Navegação Profunda:** Acesso a dados em quatro níveis de aninhamento (`Dicionário > Lista > Dicionário > Lista`).
*   **Métodos de Lista:** 
    *   `insert(0, ...)` para adicionar novos elementos no topo da pilha.
    *   `pop()` para remoção controlada de elementos.
    *   Edição *in-place* de pixels para otimização de memória.

### 3. Transposição de Matrizes Musicais
Algoritmo focado na reestruturação de frequências sonoras dentro de dicionários:
*   **Lógica de Transposição:** Converte uma matriz de frequências organizada por "canais" para um formato organizado por "tempo/frame".
*   **Update Dinâmico:** Uso do método `.update()` para substituir matrizes originais por suas versões processadas.

---

## 💻 Exemplo de Lógica Aplicada

### Transformação de Pixel:
```python
if pixel == (255, 255, 0): # Identifica o Amarelo Brilhante
    r, g, b = pixel
    novo_pixel = (r // 2, g // 2, b // 2) # Transforma em Oliva (Escuro)

    playlist = {
    "nome": "Mix Emoji",
    "imagens": [
        {"titulo": "Sol", "pixels": [[(R, G, B), ...]]}
    ]
}
