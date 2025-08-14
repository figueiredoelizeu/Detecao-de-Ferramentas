# Detecao-de-Ferramentas
Monitoramento de Inventário de Ferramentas com Visão Computacional e YOLOv8
Este projeto utiliza Visão Computacional para automatizar a verificação de inventários de ferramentas em tempo real. Através de uma câmera, o sistema detecta as ferramentas presentes em um quadro e as compara com uma lista de referência, identificando e relatando aquelas que estão ausentes. Os resultados são exportados para um arquivo Excel, facilitando o gerenciamento e a auditoria do inventário.

Tecnologias Utilizadas
Python: Linguagem principal do projeto.

Ultralytics YOLOv8: Framework de Inteligência Artificial para a detecção de objetos, fornecendo o modelo de machine learning pré-treinado.

OpenCV (cv2): Biblioteca de Visão Computacional utilizada para o acesso e processamento do feed de vídeo da câmera.

Pandas: Biblioteca para manipulação de dados, usada para criar e gerenciar o relatório de ferramentas ausentes em formato Excel.

Google Colab / Ambiente Local: Ambiente de desenvolvimento e execução do código.

Como o Projeto Funciona
A lógica do projeto é dividida em três etapas principais:

Detecção de Objetos (Visão Computacional): A cada frame do feed de vídeo da câmera, o modelo YOLOv8 é executado para identificar e localizar as ferramentas no quadro. Ele retorna o nome de cada ferramenta detectada e sua caixa delimitadora (bounding box).

Lógica de Inventário: A cada X segundos (intervalo configurável), o sistema compara a lista de ferramentas detectadas com uma lista de referência pré-definida. A diferença entre essas duas listas resulta na identificação das ferramentas ausentes.

Relatório e Exportação: As informações sobre as ferramentas ausentes, juntamente com um registro de data e hora (timestamp), são organizadas e salvas em um arquivo Excel. Isso cria um relatório contínuo que pode ser usado para auditorias ou alertas em tempo real.

Instruções de Como Rodar
Para executar este projeto, siga os passos abaixo no seu ambiente local (computador).

Pré-requisitos
Python 3.6 ou superior instalado.

Acesso a uma câmera (webcam).

Seu modelo YOLOv8 treinado (best.pt).

1. Instalação das Bibliotecas
Abra o terminal (ou Anaconda Prompt) e execute o seguinte comando para instalar todas as bibliotecas necessárias:

Bash

pip install ultralytics opencv-python pandas
2. Preparação dos Arquivos
Certifique-se de que o arquivo do seu modelo treinado (best.pt) e o script Python do projeto estão na mesma pasta.

(Opcional) Crie o arquivo relatorio_ferramentas_ausentes.xlsx vazio, ou ele será criado automaticamente na primeira execução.

3. Execução do Código
Execute o script Python a partir do seu terminal:

Bash

python seu_script_de_monitoramento.py
Uma janela será aberta, mostrando a visualização da sua câmera com as detecções em tempo real.

As informações sobre as ferramentas ausentes serão impressas no terminal a cada intervalo de tempo.

O relatório em Excel será atualizado automaticamente a cada verificação.

Para encerrar a execução, clique na janela de visualização e pressione a tecla q
