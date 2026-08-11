# Classificação de Gatos vs Cachorros com Transfer Learning

> Projeto desenvolvido como parte dos meus estudos em Deep Learning e Visão Computacional.

---

##  Sobre o Projeto

Este projeto tem como objetivo construir um classificador de imagens capaz de distinguir entre **gatos e cachorros**, utilizando a técnica de **Transfer Learning** com redes neurais convolucionais (CNNs) pré-treinadas.

Em vez de treinar uma rede do zero onde exige muito mais dados e poder computacional, aproveitei modelos já treinados em grandes datasets (como o ImageNet) e os adaptei para classificação binária.

---

##  Tecnologias e Bibliotecas Utilizadas

- **Python 3**
- **TensorFlow / Keras** — construção e treinamento do modelo
- **Transfer Learning** — aproveitamento de modelos pré-treinados
- **NumPy** — manipulação de arrays e dados numéricos
- **Matplotlib** — visualização de imagens e curvas de aprendizado
- **Jupyter Notebook** — ambiente de desenvolvimento 

---

##  Pipeline do Projeto

1. **Carregamento e exploração do dataset**
   - Organização das imagens em classes (gatos e cachorros)
   - Verificação da distribuição e qualidade dos dados

2. **Pré-processamento das imagens**
   - Redimensionamento para o formato esperado pelo modelo base
   - Normalização dos pixels
   - Aplicação de Data Augmentation para aumentar a variabilidade dos dados de treino

3. **Construção do modelo com Transfer Learning**
   - Carregamento de uma rede pré-treinada (base convolucional)
   - Congelamento das camadas base (`freeze`)
   - Adição de camadas densas customizadas para a classificação binária

4. **Treinamento e validação**
   - Compilação com otimizador e função de perda adequados
   - Monitoramento das métricas de acurácia e perda em treino e validação

5. **Avaliação dos resultados**
   - Análise das curvas de aprendizado
   - Testes com imagens novas

---

##  O que Aprendi

- Modelos poderosos já existem e podem ser adaptados de forma eficiente para novos problemas.

- Dedicar tempo ao tratamento das imagens (redimensionamento, normalização, augmentation) impacta diretamente no desempenho do modelo.

- Quando o dataset é relativamente pequeno, técnicas como flip horizontal, zoom e rotação ajudam o modelo a generalizar melhor e evitar overfitting.

- A interpretar os gráficos de `loss` e `accuracy` para identificar se o modelo está sofrendo de overfitting, underfitting ou se está aprendendo de forma saudável.

---

##  Dificuldades Encontradas

- O modelo aprendia muito bem no treino, mas ia mal na validação. Resolver isso com Data Augmentation e Dropout me fez entender na prática por que essas técnicas existem.

- Carregar todas as imagens de uma vez gerava problemas de memória. Aprender a usar geradores de dados (`ImageDataGenerator` ou `tf.data`) foi importante.

---

##  Resultados

O modelo treinado com Transfer Learning alcançou uma **acurácia satisfatória na validação**, demonstrando que a técnica é extremamente eficaz mesmo com datasets de tamanho moderado. A comparação entre treinar do zero e usar um modelo pré-treinado deixou claro o ganho em performance e tempo de treinamento.

---

##  Skills Desenvolvidas

| Área | Habilidades |
|------|-------------|
| Deep Learning | Transfer Learning, Fine-tuning, CNNs |
| Visão Computacional | Pré-processamento de imagens, Data Augmentation |
| TensorFlow/Keras | API funcional, camadas, compilação e treinamento de modelos |
| Análise de Resultados | Interpretação de curvas de aprendizado, diagnóstico de overfitting |
| Boas Práticas | Organização de código em notebooks, reprodutibilidade |

---

##  Referências

- [TensorFlow — Transfer Learning Guide](https://www.tensorflow.org/tutorials/images/transfer_learning)
- [Keras Applications — Modelos pré-treinados](https://keras.io/api/applications/)
- [Deep Learning with Python — François Chollet](https://www.manning.com/books/deep-learning-with-python)

---

*Projeto desenvolvido para fins educacionais e de aprendizado pessoal.* 
