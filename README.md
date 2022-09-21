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

De acordo com Ferrari & Silva (2017) [2], em problemas de classificação binária, predições podem ter quatro possíveis classes

- **Verdadeiro positivo (VP):** quando o método diz que a **classe é positiva** e, ao verificar a resposta, vê-se que **a classe era **realmente**positiva**;
- **Verdadeiro negativo (VN):** quando o método diz que a **classe é negativa** e, ao verificar a resposta, vê-se que **a classe era **realmente**negativa**;
- **Falso positivo (FP):** quando o método diz que a **classe é positiva**, mas ao verificar a resposta, vê-se que **a classe era negativa**;
- **Falso negativo (FN):** quando o método diz que a **classe é negativa**, mas ao verificar a resposta, vê-se que **a classe era positiva**;





