## **Cálculo de Métricas deAvaliação de Aprendizado**

 

Neste projeto, vamos calcularas principais métricas para avaliação de modelos de classificação de dados, como **acurácia, sensibilidade (recall), especificidade, precisão e F-score**. Para que seja possível implementar estas funções, você deve utilizar os métodos e suas fórmulas correspondentes (Tabela 1).

Para a leitura dos valores de VP, VN, FP e FN, será necessário escolher uma matriz de confusão para a base dos cálculos. Essa matriz você pode escolher de forma arbitraria, pois nosso objetivo é entender como funciona cada métrica. 

| Método         | Fórmula           |
| -------------- | ----------------- |
| Sensibilidade  | VP / (VP+FN)      |
| Especificidade | VN / (FP+VN)      |
| Acurácia       | (VP+VN) / N       |
| Precisão       | VP / (VP+FP)      |
| F-score        | 2 x (PxS) / (P+S) |

**Tabela 1**: Visão geral das métricas usadas para avaliar métodos de classificação. VP: verdadeiros positivos; FN: falsos negativos; FP: falsos positivos; VN: verdadeiros negativos; P: precisão; S: sensibilidade; N: total
de elementos.



### Introdução

Um modelo de classificação de dados visa realizar uma previsão com base em ocorrências passadas. Para isso, o modelo utiliza um conjunto de dados com entradas (indivíduos) e atributos (propriedades). Além disso, é necessário conhecer o resultado esperado para esse conjunto de dados (rótulos). Todas essas informações serão usadas para treinar um modelo que será utilizado para predizer resultados esperados para novos dados que surgirem no futuro. Ao treinar esse modelo deve-se utilizar um conjunto de dados (não usados no treinamento) para testar o quanto o modelo acerta. Entretanto, não basta apenas contar a quantidade de acertos que seu modelo teve para dizer se ele é bom ou não. Dependendo do problema estudado, métricas diferentes devem ser utilizadas para essa avaliação. Entretanto, antes de apresentarmos essas métricas, precisamos entender alguns conceitos para classificação binárias: as classes que os dados preditos poderão receber.



### Classes de dados preditos: VP, VN, FP e FN

De acordo com Ferrari & Silva (2017), em problemas de classificação binária, predições podem ter quatro possíveis classes

- **Verdadeiro positivo (VP):** quando o método diz que a **classe é positiva** e, ao verificar a resposta, vê-se que **a classe era **realmente **positiva**;
- **Verdadeiro negativo (VN):** quando o método diz que a **classe é negativa** e, ao verificar a resposta, vê-se que **a classe era **realmente **negativa**;
- **Falso positivo (FP):** quando o método diz que a **classe é positiva**, mas ao verificar a resposta, vê-se que **a classe era negativa**;
- **Falso negativo (FN):** quando o método diz que a **classe é negativa**, mas ao verificar a resposta, vê-se que **a classe era positiva**;




### Matriz de confusão

Uma maneira simples de se representar os resultados de um método de classificação de dados é através da chamada matriz de confusão (Tabela 2).![img](https://bioinfo.com.br/wp-content/uploads/2021/07/tabela2-1024x219.png)

Tabela 2. Matriz de confusão. Muitos autores costumam utilizar as siglas TP e TN (do inglês *true positive* e *true negative*) como sinônimos para VP e VN, respectivamente. Fonte: adaptado de Ferrari & Silva (2017).



A matriz de confusão indica a quantidade de ocorrências que o programa teve para cada uma das quatro categorias.



### Acurácia

A **acurácia** (*accuracy* ou ACC) é considerada uma das métricas mais simples e importantes. Ela avalia simplesmente o percentual de acertos, ou seja, ela pode ser obtida pela razão entre a quantidade de acertos e o total de entradas:

![img](https://bioinfo.com.br/wp-content/uploads/2021/07/image.png)



Utilizando como base a matriz de confusão, podemos obter a acurácia pela fórmula:

![img](https://bioinfo.com.br/wp-content/uploads/2021/07/image-1.png)



### Sensibilidade

Outra métrica que pode ser utilizada é a **sensibilidade** (também conhecida como* recall* ou revocação). Essa métrica avalia a capacidade do método de detectar com sucesso resultados classificados como positivos. Ela pode ser obtida pela equação:

![img](https://bioinfo.com.br/wp-content/uploads/2021/07/image-2.png)



## Especificidade

Por outro lado, a **especificidade** avalia a capacidade do método de detectar resultados negativos. Podemos calculá-la usando a equação:

![img](https://bioinfo.com.br/wp-content/uploads/2021/07/image-3.png)



### Precisão

A **precisão** é uma métrica que avalia a quantidade de verdadeiros positivos sobre a soma de todos os valores positivos:

![img](https://bioinfo.com.br/wp-content/uploads/2021/07/image-4.png)



### F-score

*F*–*measure*, F-*score* ou *score* F1 é uma média harmônica calculada com base na precisão e na revocação. Ela pode ser obtida com base na equação:

![img](https://bioinfo.com.br/wp-content/uploads/2021/07/image-5.png)



### Quando usar cada uma das métricas

Ao usar **machine learning** para solução de problemas reais, obviamente desejamos construir classificadores perfeitos, que sempre acerta, mas no mundo real quase nunca isso é possível. Assim, ao construir um preditor, devemos visar o melhor resultado possível. Uma maneira simples de observar o quão bom é um modelo de classificação é usando a acurácia. A acurácia pode ser considerada uma métrica que nos dá uma visão geral do resultado, uma vez que ela mede o total de acertos considerando o total de observações. Entretanto, outras métricas podem ser importantes dependendo de como o problema foi modelado.

O uso de cada métrica depende do objetivo do modelo que se deseja criar. Por exemplo, suponha que desejamos criar um sistema que faça a detecção automática de spam. Nesse caso, um falso positivo pode ser considerado um problema mais crítico (uma mensagem importante ser considerada spam pode causar prejuízos ao usuário do sistema). Logo, a melhor métrica para comparação entre diferentes sistemas de detecção de spam seria a precisão.

Agora imagine um sistema que detecta falhas em um avião. Imagine que uma peça apresenta problemas, mas o sistema indica que não há nada errado. Isso poderia colocar vidas em perigo. Logo, para este exemplo um falso negativo seria um problema crítico. Portanto, um sistema construído para esse propósito deve levar em consideração uma taxa de falsos negativos próxima a zero. Uma métrica que poderia ser utilizada para comparar sistemas diferentes seria a sensibilidade. Valores altos de sensibilidade indicam altos valores de verdadeiros positivos mesmo quando se leva em conta o total de falsos negativos.