# Invariância do Produto Escalar em Hipercubos Nasik

Este projeto é uma aplicação web interativa para a geração, visualização e análise de Hipercubos Mágicos Invariantes (também conhecidos como Hipercubos de Nasik) de ordem ímpar e dimensão *n*. A ferramenta permite que os usuários explorem visualmente as propriedades desses objetos matemáticos fascinantes, com um foco especial na demonstração da propriedade de invariância do produto escalar entre seus vetores de linha e coluna.

A aplicação serve como uma implementação prática e visual dos conceitos explorados na dissertação de mestrado de João Helton Mendonça Gonçalves.

## Funcionalidades Principais

A interface da aplicação é dividida em seções colapsáveis que permitem uma exploração clara e organizada das propriedades dos hipercubos gerados.

### 1. Geração do Hipercubo
O usuário pode definir dois parâmetros principais:
* **Dimensão (`d`):** O número de dimensões do hipercubo, variando de 3 (Cubo) a 9 (Ennerato).
* **Ordem (`n`):** O tamanho da aresta do hipercubo. Apenas ordens ímpares (3, 5, 7, ...) são permitidas, pois o algoritmo de geração é específico para esta condição.

### 2. Verificação de Propriedades
Para cada hipercubo gerado, a aplicação realiza e exibe os resultados de várias verificações fundamentais:
* **Constante Mágica:** Calcula e exibe a constante mágica esperada, que é a soma dos elementos de qualquer linha, coluna ou diagonal principal.
* **Normalidade:** Confirma se o hipercubo contém todos os inteiros de 1 a nᵈ, sem repetições.
* **Simetria (Invariância):** Verifica a propriedade central dos hipercubos Nasik, onde a soma de quaisquer dois elementos diametralmente opostos ao centro é constante e igual a `nᵈ + 1`.
* **Somas de Eixos e Diagonais:** Valida se as somas de todos os eixos e das diagonais principais e secundárias correspondem à constante mágica.

### 3. Validação de Produto Escalar (Funcionalidade Chave)
Esta é a principal característica do projeto, demonstrando a tese central da dissertação de mestrado. A aplicação permite que o usuário:
* Selecione dois "pilares" (linhas ou colunas) do hipercubo.
* Calcule interativamente o **produto escalar euclidiano** entre eles.
* Verifique a propriedade de invariância: o produto escalar entre dois vetores-linha (ou coluna) `p` e `q` é igual ao produto escalar de seus vetores simétricos `p'` e `q'`, onde `p' = n - p + 1` e `q' = n - q + 1`.

### 4. Visualização 3D e Matrizes
* **Visualizador 3D Interativo:** Renderiza uma fatia 3D do hipercubo gerado. Para dimensões maiores que 3 (como o Tesserato), sliders dinâmicos permitem ao usuário "fatiar" o hipercubo em eixos superiores (W, V, etc.) para visualizar o cubo 3D resultante. O visualizador permite rotação, panorâmica e zoom.
* **Visualização de Matrizes:** Exibe as matrizes 2D que compõem a fatia 3D atualmente visualizada, facilitando a compreensão da estrutura interna do hipercubo.

## Base Matemática
O projeto é fundamentado nos estudos sobre Quadrados e Cubos Mágicos Invariantes. A propriedade central do produto escalar é uma generalização de observações feitas por matemáticos e foi formalmente demonstrada na dissertação de mestrado que deu origem a esta ferramenta.

Um **Hipercubo Mágico Invariante** (ou Nasik) é uma matriz n-dimensional onde não apenas as linhas, colunas e diagonais principais somam a mesma constante mágica, mas também apresenta uma simetria mais profunda: a soma de quaisquer dois elementos opostos em relação ao centro geométrico da matriz é constante.

Essa propriedade de invariância é a chave para a demonstração da igualdade dos produtos escalares, um dos principais resultados explorados por esta aplicação.

### Referências
* **Dissertação de Mestrado:** A base teórica completa, incluindo as demonstrações formais das propriedades, pode ser encontrada na dissertação:
    * Gonçalves, J. H. M. (2015). *A Igualdade do Produto Escalar Euclidiano entre Linhas e Colunas dos Quadrados Mágicos Invariantes*. (Dissertação de Mestrado, Universidade Estadual do Ceará). Acesso em: <https://siduece.uece.br/siduece/trabalhoAcademicoPublico.jsf?id=88958>

## Sobre o Autor
* **Nome:** João Helton Mendonça Gonçalves
* **E-mail:** [heltongoncalves@gmail.com](mailto:heltongoncalves@gmail.com)
* **GitHub:** <https://github.com/heltongoncalves/matematica-hypercubes>
