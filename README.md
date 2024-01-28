
# Comparação entre redes GNN e MLP para classificação de características

O projeto tem como objetivo o desenvolvimento de protótipo para automatizar o processo de leitura e correção de provas e simulados aplicando técnicas de visão computacional. Foram aplicadas técnicas de Classificação, Detecção, etc.


### Resumo:
- O projeto começa com a classificação da imagem como "Prova" ou "Simulado" usando o `YOLOv8m-cls`.
- Se for uma prova, é aplicado o `YOLOv8m` para detectar a questão marcada.
- Se for um simulado, é feita uma nova classificação para determinar o tipo de simulado usando outro modelo `YOLOv8m-cls`.
- Em seguida, um segundo modelo `YOLOv8m` é utilizado para detectar as questões marcadas no simulado.


## Informações de Treinamento
### Ambiente
Todos os modelos foram treinados utilizando o Google Colab. O arquivo [`requirements.txt`](envs/requirements.txt) contém a lista de todas as bibliotecas e suas versões necessárias para este projeto. Certifique-se de que essas bibliotecas estejam instaladas em seu ambiente, caso queira repetir o treinamento.

### Modelos de Classificação

#### Modelo Provas ou Simulado

##### Parâmetros do Modelo

- **Tarefa (Task):** Classificação
- **Modo (Mode):** Treinamento
- **Modelo (Model):** YOLOv8m-cls.pt `pre-trained` 
- **Dados (Data):** Diretório "/content/gdrive/MyDrive/simulados" contendo as imagens de treinamento.
- **Épocas (Epochs):** 300.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** 16.
- **Tamanho da Imagem (Imgsz):** 224 pixels.
- **Aumento de Dados(Data Augmentation):** rotation: 5 and 10 degrees.

##### Resultados do Modelo de Prova ou Simulado

<div style="display: flex; justify-content: space-between;">
  <a target="_blank" align="center">
    <img height="400" width="400" src="https://github.com/Daniel227a/desafio/blob/dev/images/results_ProvaGabarito.png" alt="Resultados da Prova">
  </a>
  <a target="_blank" align="center">
    <img height="400" width="400" src="https://github.com/Daniel227a/desafio/blob/dev/images/confusion_matrix_normalized_ProvaGabarito.png" alt="Matriz de Confusão - Modelo Verde">
  </a>
</div>

#### Modelo dos Simulados

##### Parâmetros do Modelo

- **Tarefa (Task):** Classificação
- **Modo (Mode):** Treinamento
- **Modelo (Model):** YOLOv8m-cls.pt `pre-trained`
- **Dados (Data):** Diretório "/content/gdrive/MyDrive/simulados" contendo as imagens de treinamento.
- **Épocas (Epochs):** 300.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** 16.
- **Tamanho da Imagem (Imgsz):** 224 pixels.
- **Aumento de Dados(Data Augmentation):** rotation: 5 and 10 degrees.
##### Resultados do Modelo de Prova ou Simulado

<div style="display: flex; justify-content: space-between;">
  <a target="_blank" align="center">
    <img height="400" width="400" src="https://github.com/Daniel227a/desafio/blob/dev/images/results_Simulados.png" alt="Resultados da Prova">
  </a>
  <a target="_blank" align="center">
    <img height="400" width="400" src="https://github.com/Daniel227a/desafio/blob/dev/images/confusion_matrix_normalized_Simulados.png" alt="Matriz de Confusão - Modelo Verde">
  </a>
</div>

### Modelos de Detecção

#### Parâmetros do Modelo de Provas
- **Tarefa (Task):** detecção 
- **Modo (Mode):** Treinamento
- **Modelo (Model):** yolov8m.pt `pre-trained`
- **Dados (Data):** Diretório "/content/gdrive/MyDrive/simulados" contendo as imagens de treinamento.
- **Épocas (Epochs):** 300.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** 16.
- **Tamanho da Imagem (Imgsz):** 640 pixels.

#### Resultados do Modelo de Provas
<div style="display: flex; justify-content: space-between;">
  <a target="_blank" align="center">
    <img height="270" width="410" src="https://github.com/Daniel227a/desafio/blob/dev/images/resultsProva.png" alt="Resultados da Prova">
  </a>
  <a target="_blank" align="center">
    <img height="270" width="410" src="https://github.com/Daniel227a/desafio/blob/dev/images/matrixProvas.png" alt="Matriz de Confusão - Modelo Verde">
  </a>
</div>

#### Parâmetros do Modelo para o Tipo verde
- **Tarefa (Task):** detecção 
- **Modo (Mode):** Treinamento
- **Modelo (Model):** yolov8m.pt `pre-trained`
- **Dados (Data):** Diretório "/content/gdrive/MyDrive/simulados" contendo as imagens de treinamento.
- **Épocas (Epochs):** 300.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** 16.
- **Tamanho da Imagem (Imgsz):** 640 pixels.
- **Aumento de Dados(Data Augmentation):** rotation: 5 and 10 degrees.

#### Resultados do Modelo para o Tipo verde

<div style="display: flex; justify-content: space-between;">
  <a target="_blank" align="center">
    <img height="270" width="410" src="https://github.com/Daniel227a/desafio/blob/dev/images/results_verde.png" alt="Resultados da Prova">
  </a>
  <a target="_blank" align="center">
    <img height="270" width="410" src="https://github.com/Daniel227a/desafio/blob/dev/images/confusion_matrix_verde_normalized.png" alt="Matriz de Confusão - Modelo Verde">
  </a>
</div>

#### Parâmetros do Modelo para o Tipo Azul
- **Tarefa (Task):** detecção 
- **Modo (Mode):** Treinamento
- **Modelo (Model):** yolov8m.pt `pre-trained`
- **Épocas (Epochs):** 300.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** 16.
- **Tamanho da Imagem (Imgsz):** 640 pixels.
- **Aumento de Dados(Data Augmentation):** rotation: 5 and 10 degrees.
  
#### Resultados do Modelo para o Tipo Azul

<div style="display: flex; justify-content: space-between;">
  <a target="_blank" align="center">
    <img height="270" width="410" src="https://github.com/Daniel227a/desafio/blob/dev/images/results_blue_.png" alt="Resultados da Prova">
  </a>
  <a target="_blank" align="center">
    <img height="270" width="410" src="https://github.com/Daniel227a/desafio/blob/dev/images/confusion_blue_matrix_normalized.png" alt="Matriz de Confusão - Modelo Verde">
  </a>
</div>

#### Parâmetros do Modelo para o Tipo Diversos
- **Tarefa (Task):** detecção 
- **Modo (Mode):** Treinamento
- **Modelo (Model):** yolov8m.pt `pre-trained`
- **Épocas (Epochs):** 150.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** 16.
- **Tamanho da Imagem (Imgsz):** 640 pixels.
- **Aumento de Dados(Data Augmentation):** rotation: 5 and 10 degrees.

	
## Como Executar o Projeto Localmente

1. **Clone este repositório:**

   ```shell
   git clone https://github.com/Daniel227a/desafio.git
   ```

2. **Baixe os modelos treinados e insira no diretório "modelos":**

   - [Google Drive - Modelos Treinados](https://drive.google.com/drive/folders/150vCXrseNIn_qCshArFYYRjI4ODhuXoW?usp=sharing)

3. **Instale o Anaconda:**

   Se você ainda não tem o Anaconda instalado, você pode baixá-lo [aqui](https://www.anaconda.com/products/distribution) e seguir as instruções de instalação apropriadas para o seu sistema operacional.

4. **Crie um Ambiente Conda:**

   No terminal ou Anaconda Prompt, navegue até o diretório do projeto e execute:

   ```shell
   conda env create -f environment.yml
   ```

   Isso criará um ambiente conda chamado "hackaton-env" com as dependências necessárias.

5. **Ative o Ambiente Conda:**

   ```shell
   conda activate hackaton-env
   ```

6. **Execute o Jupyter Notebook:**

   ```shell
   jupyter-notebook
   ```

7. **Abra o Arquivo "Hackaton.ipynb":**

   Dentro do Jupyter Notebook, abra o arquivo "Hackaton.ipynb" para visualizar e executar o projeto.
   
   **Observação:** Certifique-se de que o ambiente conda "hackaton-env" está ativado enquanto você executa o Jupyter Notebook.
   
   Isso deve permitir que você execute o projeto em seu ambiente local. Certifique-se de ter todas as dependências instaladas e os modelos treinados disponíveis no diretório apropriado.





