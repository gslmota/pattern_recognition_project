
# Comparação entre redes GNN e MLP para classificação de características

O repositório é um projeto de comparação entre  GNN - Graph Neural Networks e  MLP - Multilayer Perceptrons para a tarefa de classificação de padrões. O projeto é implementado utilizando as bibliotecas PyTorch e TensorFlow.

## Equipe
- Gabriel Sávio
- Rodrigo Jeremias

## Informações de Treinamento
### Ambiente
Todos os modelos foram treinados utilizando o Google Colab. A maioria das bibliotecas estão pré-instaladas dentro do colab. Algumas será necessário a instalação, porém já estão incluídas no notebook, necessário apenas a execução. Certifique-se de que essas bibliotecas estejam instaladas em seu ambiente, caso queira repetir o treinamento no Google Colab.

##### Parâmetros do Modelo GNN

- **Tarefa (Task):** Classificação
- **Modo (Mode):** Treinamento
- **Modelo (Model):** GNN
- **Épocas (Epochs):** 500.
- **Paciência (Patience):** 50.
- **Tamanho do Lote (Batch):** auto.


##### Parâmetros do Modelo MLP

- **Tarefa (Task):** Classificação
- **Modo (Mode):** Treinamento
- **Modelo (Model):** MLP
- **Épocas (Epochs):** 500.
- **Paciência (Patience):** 15.
- **Tamanho do Lote (Batch):** auto.

## Como Executar o Projeto Localmente

1. **Clone este repositório:**

   ```shell
   
   git clone https://github.com/gslmota/pattern_recognition_project.git
   ```

2. **Instale o Anaconda:**

   Se você ainda não tem o Anaconda instalado, você pode baixá-lo [aqui](https://www.anaconda.com/products/distribution) e seguir as instruções de instalação apropriadas para o seu sistema operacional.

3. **Crie um Ambiente Conda:**

   No terminal ou Anaconda Prompt, navegue até o diretório e crie um ambiente. Instale nesse ambiente as bibliotecas usadas dentro do notebook para que a execução funcione.

4. **Ative o Ambiente Conda:**

   ```shell
   conda activate 'nome-do-seu-ambiente'
   ```

6. **Execute o Jupyter Notebook:**

   ```shell
   jupyter-notebook
   ```

7. **Abra o Arquivo "Projeto.ipynb":**

   Dentro do Jupyter Notebook, abra o arquivo "Projeto.ipynb" para visualizar e executar o projeto.
   
   **Observação:** Certifique-se de que o ambiente conda "nome-do-seu-ambiente" está ativado enquanto você executa o Jupyter Notebook.

   Modifique a variável `dataset_path` para o caminho do seu dataset local.
   
   Isso deve permitir que você execute o projeto em seu ambiente local. Certifique-se de ter todas as dependências instaladas.

## Como Executar o Projeto Google Colab
   Para executar dentro do Colab, basta abrir o notebook e modificar a variável `dataset_path` para o caminho do seu dataset no drive.

   Isso deve permitir que você execute o projeto em seu ambiente Google Colab. Certifique-se de ter todas as dependências instaladas.



