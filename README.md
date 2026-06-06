# Nexvisual - Trilha de Visão Computacional e Realidade Aumentada

O projeto **Nexvisual** integra o projeto **Residência em TIC 43 − Visão Computacional e Realidade Aumentada**, uma iniciativa apoiada pelo Ministério da Ciência, Tecnologia e Inovação (MCTI), com recursos da Lei nº 8.248/1991, coordenada pela **Softex** no âmbito do **Programa MCTI Futuro**.

* **Publicado em:** 29/04/2025

## 🛠️ Resumo dos Desafios Resolvidos

Todos os desafios da trilha de Visão Computacional foram resolvidos com sucesso. A seguir está o detalhamento de cada um deles:

### [Desafio 1: Desfocagem de Fundo (Blur)](file:///c:/Users/joaor/Documents/GitArrumar/TrilhaVisaoComputacional/Desafios/desafio_1_blur/desafio_1_blur/VC_Desafio_1.ipynb)
* **Objetivo:** Borrar o fundo de uma imagem preservando a nitidez da face detectada (similar ao efeito de fundo desfocado em videoconferências).
* **Solução Implementada:**
  1. Leitura e conversão da imagem de entrada (`desafio_1.jpeg`) de BGR para RGB e tons de cinza.
  2. Detecção facial utilizando o classificador clássico **Haar Cascade** (`haarcascade_frontalface_default.xml`).
  3. Recorte da região da face adicionando uma margem (*padding*) de 100 pixels para melhor enquadramento.
  4. Aplicação do filtro **GaussianBlur** na imagem inteira.
  5. Restauração da área da face original e nítida por cima da imagem borrada.
* **Notebook:** [VC_Desafio_1.ipynb]

### [Desafio 2: Reconhecimento Facial (Face Recognition)]
* **Objetivo:** Implementar um pipeline de detecção e reconhecimento facial usando Deep Learning e SVM (Support Vector Machine).
* **Solução Implementada:**
  1. Pré-processamento e extração de características (*embeddings*) da base de dados (`dataset/`) usando o detector facial **Res10 SSD** e o extrator de características **OpenFace**.
  2. Codificação das classes utilizando `LabelEncoder` e treinamento de um classificador SVM (`SVC`) linear com probabilidades habilitadas.
  3. Salvamento dos pesos e labels gerados em arquivos binários pickle.
  4. Validação do modelo com uma imagem de teste (`test/modelo_2_1.jpeg`), exibindo bounding box, nome da pessoa reconhecida e porcentagem de confiança.
* **Notebook:** [VC_Desafio_2.ipynb]

### [Desafio 3: Rastreamento de Objetos (Object Tracking)]
* **Objetivo:** Realizar o rastreamento em vídeo utilizando a arquitetura YOLO.
* **Solução Implementada:**
  1. Carregamento do modelo YOLO pré-treinado (`yolo11n.pt`).
  2. Configuração de execução dinâmica em hardware (GPU/CUDA caso disponível, ou CPU).
  3. Execução da rotina de rastreamento (`model.track`) sobre o vídeo fonte com limiar de confiança de 0.1 e IoU de 0.7.
  4. Salvamento do vídeo final com as marcações de rastreamento (`output.avi`) utilizando o codec XVID e a biblioteca OpenCV.
* **Notebook:** [VC_Desafio_3.ipynb]

### [Desafio 4: Estimação de Poses Humanas (Pose Estimation)]
* **Objetivo:** Detectar a pose e os pontos de articulação chave (*keypoints*) do corpo humano a partir de uma imagem estática.
* **Solução Implementada:**
  1. Inicialização do modelo YOLO focado em pose (`yolo11n-pose.pt`).
  2. Mapeamento de hardware para inferência eficiente.
  3. Processamento e inferência na imagem de teste (`desafio_4.jpeg`).
  4. Extração do array com as anotações visuais de esqueleto e conversão de BGR para RGB para correta renderização com `matplotlib`.
* **Notebook:** [VC_Desafio_4.ipynb]

---

## 📦 Como Executar os Desafios

### Requisitos Prévios
Certifique-se de possuir o Python instalado em seu sistema e crie um ambiente virtual para instalação dos pacotes necessários:

```bash
# Criar ambiente virtual
python -m venv .venv

# Ativar ambiente virtual (Windows)
.venv\Scripts\activate

# Instalar dependências gerais dos desafios
pip install opencv-python matplotlib imutils tqdm ultralytics torch scikit-learn pillow
```

### Execução dos Notebooks
Com o ambiente ativado, abra seu ambiente de preferência (Jupyter Notebook, JupyterLab ou VS Code) e execute as células de cada notebook individualmente para ver os resultados práticos e visuais.
