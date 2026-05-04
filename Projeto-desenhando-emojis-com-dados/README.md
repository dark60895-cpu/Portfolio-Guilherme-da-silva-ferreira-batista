# Projeto desenhando emojis com dados

# 🎨 Python Matrix Suite: Processamento de Imagem e Dados Musicais

Este repositório reúne uma série de algoritmos em Python focados na manipulação de **estruturas de dados complexas**, matrizes multidimensionais e processamento de **Pixel Art** utilizando bibliotecas de visualização científica.

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
