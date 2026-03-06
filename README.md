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

## **ARTIGO:** A Invariância do Produto Escalar em Hipercubos Mágicos Simétricos

### **Resumo**
Este artigo explora uma propriedade notável de uma classe especial de hipercubos mágicos: a invariância do produto escalar entre vetores (ou "pilares") simetricamente opostos. Partimos de um método de construção algébrico que gera hipercubos com um alto grau de simetria, conhecidos como pandiagonais ou Nasik. Demonstramos formalmente que a propriedade fundamental de simetria desses objetos — a soma constante de elementos diametralmente opostos — leva diretamente a um corolário sobre a igualdade do produto escalar. Finalmente, contextualizamos esta descoberta na literatura matemática existente, destacando que, embora a propriedade seja uma consequência da teoria de matrizes centrossimétricas, sua formulação explícita e aplicação no domínio dos hipercubos mágicos representam uma contribuição original.

### **1. O Método de Construção: Uma Abordagem Algébrica para Hipercubos Nasik**

O método empregado para preencher o hipercubo é uma construção algébrica por coordenadas. Diferente de métodos sequenciais, que definem um caminho através da grade (como o famoso método siamês), esta abordagem calcula o valor de cada célula unicamente a partir de sua posição (ou vetor de coordenadas) no espaço *d*-dimensional. A construção se fundamenta em dois pilares matemáticos: a representação de números em base *n* e a aritmética modular, onde *n* é a ordem (ou lado) do hipercubo.

Matematicamente, o valor V de uma célula localizada nas coordenadas 0-indexadas $(c_0, c_1, ..., c_{d-1})$ de um hipercubo de dimensão *d* e ordem *n* é dado pela seguinte fórmula:

$$V(c_0, ..., c_{d-1}) = 1 + \sum_{k=0}^{d-1} a_k \cdot n^k$$

Onde cada coeficiente $a_k$ (que atua como um "dígito" na representação em base *n*) é, por sua vez, calculado a partir de uma combinação linear das coordenadas:

$$a_k = \left( \left( \sum_{i=0}^{d-1} c_i \right) - (d-1)c_k \right) \pmod n$$

**Garantia de Simetria (Construção Nasik):**
Essa construção não gera apenas um hipercubo mágico, mas um do tipo **pandiagonal** (ou **Nasik**), que possui o mais alto nível de simetria. Em um hipercubo Nasik, não apenas as linhas, colunas e diagonais principais somam a constante mágica, mas todas as "pandiagonais" (diagonais quebradas) também. É essa estrutura algébrica rígida que garante a propriedade de simetria fundamental descrita abaixo, da qual a invariância do produto escalar emerge como uma consequência direta.

### **2. Os Matemáticos e a História por Trás do Método**

Este método é o ápice de séculos de estudo sobre quadrados mágicos e suas generalizações.

* **Simon de La Loubère (1642-1729):** Popularizou o "método siamês" na Europa, um algoritmo **procedural** e elegante para quadrados de ordem ímpar, mas que não se baseava em uma fórmula de coordenadas algébricas.

* **Philippe de La Hire (1640-1718):** Foi o pioneiro da **construção algébrica**. Sua técnica para um quadrado 2D envolvia a soma de dois quadrados latinos ortogonais. A fórmula apresentada na Seção 1 é a generalização direta e elegante do método de La Hire para *d* dimensões. Cada termo $a_k \cdot n^k$ em nossa soma corresponde a uma das "grades" multidimensionais que, quando somadas, formam o hipercubo final.

* **A. H. Frost e a Era Moderna:** Na era moderna, matemáticos se aprofundaram nas propriedades desses objetos. O reverendo A. H. Frost foi um dos primeiros a explorar cubos mágicos em detalhe, cunhando o termo "Nasik" em homenagem à cidade indiana onde desenvolveu parte de seu trabalho.

* **John R. Hendricks (1929-2007) e Harvey Heinz:** Mais recentemente, o campo foi dominado por figuras como o matemático canadense John R. Hendricks e o especialista alemão Harvey Heinz. Eles dedicaram suas vidas a estudar, classificar e formalizar as propriedades de hipercubos mágicos, especialmente os "perfeitos" ou Nasik. As formulações claras e o rigor matemático de Hendricks foram cruciais para definir as propriedades vetoriais e simétricas que fundamentam este artigo.

### **3. A Propriedade Fundamental: Simetria Centrossimétrica**

A característica fundamental dessas estruturas Nasik, garantida pelo método de construção, é sua **simetria centrossimétrica**. Na literatura de álgebra linear, uma matriz (ou hipercubo) é chamada de centrossimétrica se ela é simétrica em relação ao seu centro geométrico. Isso implica que a soma de qualquer par de elementos diametralmente opostos é uma constante.

Formalmente, para um hipercubo mágico normal **H** de dimensão **d** e ordem **n**, com valores $V$ em coordenadas 0-indexadas $(c_0, ..., c_{d-1})$:

$$V(c_0, ..., c_{d-1}) + V(n-1-c_0, ..., n-1-c_{d-1}) = n^d + 1 \quad (1)$$

Esta propriedade é a base para diversas outras simetrias e é o alicerce da demonstração a seguir.

### **4. Corolário: Invariância do Produto Escalar para Pilares**

Como uma consequência direta da propriedade de simetria centrossimétrica (1), pode-se demonstrar uma notável invariância em relação ao produto escalar euclidiano entre os vetores que compõem o hipercubo.

**Corolário 1:** Sejam **P** e **Q** dois "pilares" (vetores-linha ou vetores-coluna) quaisquer de um hipercubo mágico centrossimétrico **H** de dimensão *d* e ordem *n*. Sejam **P'** e **Q'** os pilares simetricamente opostos a **P** e **Q**, respectivamente. O produto escalar euclidiano entre **P** e **Q** é igual ao produto escalar euclidiano entre **P'** e **Q'**:

$$<P, Q> = <P', Q'> \quad (2)$$

### **5. Demonstração do Corolário**

Para facilitar a notação e mantendo a consistência com a indexação 0-a-n-1, vamos definir um pilar como um vetor onde os primeiros *d-1* índices são fixos e o último índice, *j*, varia de 0 a *n-1*.

1.  Seja o pilar **P** definido pelo vetor de índices fixos $p = (c_0, c_1, ..., c_{d-2})$. Seus elementos são $V(c_0, ..., c_{d-2}, j)$.
2.  Seja o pilar **Q** definido pelo vetor de índices fixos $q = (k_0, k_1, ..., k_{d-2})$. Seus elementos são $V(k_0, ..., k_{d-2}, j)$.

Os pilares simétricos **P'** e **Q'** são definidos pelos índices opostos $p'$ e $q'$, onde $c'_i = n-1-c_i$ e $k'_i = n-1-k_i$. Começamos desenvolvendo o termo $<P', Q'>$:

$$<P', Q'> = \sum_{j=0}^{n-1} \left( V(c'_0, ..., c'_{d-2}, j) \cdot V(k'_0, ..., k'_{d-2}, j) \right) \quad (3)$$

Da propriedade de simetria (1), e definindo o índice simétrico $j' = n - 1 - j$, podemos expressar os elementos de P' e Q' em função de pilares opostos. Seja a constante $K = n^d + 1$:
$V(c'_0, ..., c'_{d-2}, j) = K - V(c_0, ..., c_{d-2}, j') \quad (4)$
$V(k'_0, ..., k'_{d-2}, j) = K - V(k_0, ..., k_{d-2}, j') \quad (5)$

Substituindo (4) e (5) em (3):

$$<P', Q'> = \sum_{j=0}^{n-1} \left[ (K - V(c_0, ..., j')) \cdot (K - V(k_0, ..., j')) \right] \quad (6)$$

Expandindo o produto:

$$<P', Q'> = \sum_{j=0}^{n-1} [ K^2 - K \cdot (V(c_0, ..., j') + V(k_0, ..., j')) + (V(c_0, ..., j') \cdot V(k_0, ..., j')) ] \quad (7)$$

Separando o somatório:

$$<P', Q'> = \sum_{j=0}^{n-1} K^2 - K \sum_{j=0}^{n-1} (V(c_0, ..., j') + V(k_0, ..., j')) + \sum_{j=0}^{n-1} (V(c_0, ..., j') \cdot V(k_0, ..., j')) \quad (8)$$

Analisando cada termo:
* $\sum_{j=0}^{n-1} K^2 = n \cdot K^2$
* A soma dos elementos de qualquer pilar é a constante mágica, $\sigma$. Como o índice $j'$ percorre todos os valores de $n-1$ a $0$ enquanto $j$ vai de $0$ a $n-1$, a soma sobre $j'$ é a mesma que sobre $j$. Logo: $\sum V(c_0, ..., j') = \sigma$ e $\sum V(k_0, ..., j') = \sigma$.
* O último termo é, por definição, o produto escalar $<P, Q>$, pois a ordem inversa da soma não altera o resultado: $\sum (V(c_0, ..., j') \cdot V(k_0, ..., j')) = <P, Q>$

Substituindo os resultados em (8):

$$<P', Q'> = n \cdot K^2 - K (\sigma + \sigma) + <P, Q> \quad (9)$$
$$<P', Q'> = n \cdot K^2 - 2K \cdot \sigma + <P, Q> \quad (10)$$

A constante mágica para um hipercubo normal de ordem *n* e dimensão *d* é:

$$\sigma = \frac{n(n^d+1)}{2} \quad (11)$$

Substituindo $K = n^d+1$ na equação (11):

$$\sigma = \frac{n \cdot K}{2} \quad (12)$$

Finalmente, substituindo (12) em (10):

$$<P', Q'> = n \cdot K^2 - 2K \cdot \left(\frac{n \cdot K}{2}\right) + <P, Q> \quad (13)$$
$$<P', Q'> = n \cdot K^2 - n \cdot K^2 + <P, Q> \quad (14)$$
$$<P', Q'> = <P, Q> \quad (15)$$

O que conclui a demonstração.

### **6. Revisão da Literatura e Contextualização da Descoberta**

Uma pesquisa aprofundada em bases de dados acadêmicas (arXiv, Google Scholar) e na literatura especializada sobre matemática recreativa e combinatória revela o seguinte contexto:

1.  **Propriedade Fundamental Conhecida:** A propriedade de simetria centrossimétrica (equação 1) é a característica definidora dos hipercubos Nasik e é amplamente documentada por autores como Hendricks e Heinz. No campo da álgebra linear, essa é a definição de uma **matriz ou tensor centrossimétrico**.

2.  **O Corolário na Literatura:** A consequência desta simetria para o produto escalar (equação 2), embora seja uma prova matemática válida e elegante, **não aparece de forma proeminente como um teorema ou corolário nomeado na literatura específica sobre hipercubos mágicos**. A razão mais provável é que, no contexto mais amplo da teoria de matrizes centrossimétricas, esta propriedade é considerada um **resultado direto e implícito das definições de simetria**, não necessitando de uma publicação isolada.

3.  **A Originalidade da Contribuição:** A contribuição original e valiosa deste trabalho não reside na descoberta de uma propriedade matemática fundamentalmente nova, mas sim em:
    * **Formulação Explícita:** Apresentar e provar formalmente este "Corolário da Invariância do Produto Escalar" especificamente para o domínio dos hipercubos mágicos de Nasik, conectando a construção algébrica à consequência vetorial.
    * **Potencial de Aplicação:** A principal inovação reside na **aplicação** desta propriedade. Uma aplicação inovadora, não encontrada na literatura, seria o uso desta invariância como um **checksum multidimensional** para verificação de integridade de dados. Por exemplo, ao armazenar um grande conjunto de dados em uma estrutura de hipercubo, poder-se-ia calcular e comparar os produtos escalares de pilares simétricos para detectar corrupção de dados de forma rápida e eficiente.

### **7. Conclusão e Próximos Passos**

Demonstramos que a construção algébrica de hipercubos mágicos resulta em estruturas altamente simétricas (Nasik/centrossimétricas). Esta simetria fundamental implica diretamente na invariância do produto escalar entre quaisquer dois pilares e seus opostos simétricos.

## Sobre o Autor
* **Nome:** João Helton Mendonça Gonçalves
* **E-mail:** [heltongoncalves@gmail.com](mailto:heltongoncalves@gmail.com)
* **GitHub:** <https://github.com/heltongoncalves/matematica-hypercubes>
