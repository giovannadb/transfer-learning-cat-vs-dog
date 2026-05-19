# Classificação de Gatos vs Cachorros com Transfer Learning

> Projeto desenvolvido como parte dos meus estudos em Deep Learning e Visão Computacional.

---

##  Sobre o Projeto

Este projeto tem como objetivo construir um classificador de imagens capaz de distinguir entre **gatos e cachorros**, utilizando a técnica de **Transfer Learning** com redes neurais convolucionais (CNNs) pré-treinadas.

Em vez de treinar uma rede do zero — o que exigiria muito mais dados e poder computacional — aproveitei modelos já treinados em grandes datasets (como o ImageNet) e os adaptei para a nossa tarefa específica de classificação binária. Esse é um dos principais truques do Deep Learning moderno: reutilizar o conhecimento que uma rede já adquiriu!

---

##  Estrutura do Repositório

```
transfer-learning-cat-vs-dog/
│
├── cat_vs_dogs.ipynb       # Notebook principal com todo o pipeline
└── pet-Images/             # Dataset de imagens de gatos e cachorros
```

---

##  Tecnologias e Bibliotecas Utilizadas

- **Python 3**
- **TensorFlow / Keras** — construção e treinamento do modelo
- **Transfer Learning** — aproveitamento de modelos pré-treinados
- **NumPy** — manipulação de arrays e dados numéricos
- **Matplotlib** — visualização de imagens e curvas de aprendizado
- **Jupyter Notebook** — ambiente de desenvolvimento interativo

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

Algumas das principais lições que levo:

- **Transfer Learning não é só uma técnica.** Aprendi que não precisamos reinventar a roda o tempo todo — modelos poderosos já existem e podemos adaptá-los de forma eficiente para novos problemas.

- **A importância do pré-processamento.** Percebi que dedicar tempo ao tratamento das imagens (redimensionamento, normalização, augmentation) impacta diretamente no desempenho do modelo.

- **Data Augmentation resolve muita coisa.** Quando o dataset é relativamente pequeno, técnicas como flip horizontal, zoom e rotação ajudam o modelo a generalizar melhor e evitar overfitting.

- **Congelar e descongelar camadas.** Entendi a diferença entre usar o modelo base apenas como extrator de features (camadas congeladas) versus fazer um *fine-tuning* parcial para adaptar os pesos ao novo domínio.

- **Leitura de curvas de aprendizado.** Aprendi a interpretar os gráficos de `loss` e `accuracy` para identificar se o modelo está sofrendo de overfitting, underfitting ou se está aprendendo de forma saudável.

---

##  Dificuldades Encontradas

Nem tudo foi fácil! Algumas pedras no caminho que me fizeram crescer muito:

- **Entender o fluxo do Transfer Learning no Keras** foi confuso no início. A diferença entre `include_top=False`, o papel do `GlobalAveragePooling2D` e quando usar `trainable = False` não ficou óbvio de imediato — precisei ler bastante documentação e experimentar.

- **Overfitting nos primeiros experimentos.** O modelo aprendia muito bem no treino, mas ia mal na validação. Resolver isso com Data Augmentation e Dropout me fez entender na prática por que essas técnicas existem.

- **Gerenciamento de memória com imagens.** Carregar todas as imagens de uma vez gerava problemas de memória. Aprender a usar geradores de dados (`ImageDataGenerator` ou `tf.data`) foi um passo importante.

- **Escolher os hiperparâmetros certos.** Learning rate, número de epochs, tamanho do batch... cada um desses parâmetros afeta o resultado de forma diferente, e encontrar uma combinação razoável exigiu bastante experimentação e paciência!.

- **Interpretar os resultados.** No começo, eu olhava para a acurácia final e achava que era tudo. Com o tempo, aprendi a olhar para as curvas completas, testar com imagens novas e questionar o modelo além dos números do relatório.

---

##  Resultados

O modelo treinado com Transfer Learning alcançou uma **acurácia satisfatória na validação**, demonstrando que a técnica é extremamente eficaz mesmo com datasets de tamanho moderado. A comparação entre treinar do zero versus usar um modelo pré-treinado deixou claro o ganho em performance e tempo de treinamento.

---

##  Como Executar

```bash
# Clone o repositório
git clone https://github.com/giovannadb/transfer-learning-cat-vs-dog.git
cd transfer-learning-cat-vs-dog

# Instale as dependências
pip install tensorflow numpy matplotlib jupyter

# Abra o notebook
jupyter notebook cat_vs_dogs.ipynb
```

> **Requisito:** Python 3.8+ e TensorFlow 2.x

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

##  Autora

**Giovanna** — Estudante de Ciência de Dados apaixonada por tecnologia.

[![GitHub](https://img.shields.io/badge/GitHub-giovannadb-181717?style=flat&logo=github)](https://github.com/giovannadb)

---

*Projeto desenvolvido para fins educacionais e de aprendizado pessoal.* 
