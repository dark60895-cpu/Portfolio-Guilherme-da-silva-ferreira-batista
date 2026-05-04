# 🖼️ Gerenciamento de Playlist de Imagens e Manipulação de Pixels

Este módulo demonstra o uso de **métodos de listas** (`insert`, `pop`) e **iteração em coleções aninhadas** para gerenciar e editar uma galeria de imagens digitais representadas por matrizes de cores.

---

## 🛠️ Funcionalidades Técnicas

### 1. Processamento em Lote (Batch Processing)
O código percorre uma estrutura complexa de dicionários e listas para aplicar uma transformação em cada imagem da playlist:
*   **Iteração Profunda:** O algoritmo utiliza quatro níveis de repetição para alcançar o nível do pixel: `Chave` -> `Imagem` -> `Linha` -> `Pixel`.
*   **Transformação de Brilho:** Identifica a cor amarela `(255, 255, 0)` e aplica uma redução de luminosidade em 50% através da divisão inteira (`// 2`).

### 2. Gestão de Fluxo de Lista
Foram aplicados métodos fundamentais para manipulação dinâmica da playlist:
*   **`insert(0, ...)`**: Adiciona um novo elemento na primeira posição da lista (Index 0), deslocando os demais.
*   **`pop()`**: Remove o último elemento da lista, útil para manter o tamanho da coleção controlado ou remover itens descartados.

---

## 📂 Estrutura de Dados Utilizada
```python
playlist = {
    "nome": "Mix Emoji",
    "imagens": [
        {
            "titulo": "Sol",
            "pixels": [[(R, G, B), ...], [...]]
        },
        # ... mais imagens
    ]
}
