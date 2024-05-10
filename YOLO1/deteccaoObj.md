### Configurando a GPU para utilização com YOLO

```python
import tensorflow as tf
device_name = tf.test.gpu_device_name()
print(device_name)
```

### Download da ferramenta DARKNET
Clone do repositório do Alexey que é uma das pessoas responsáveis pela construção do YOLO

```
git clone https://github.com/AlexeyAB/darknet
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando git clone.


Mudar para o diretório Darknet
```
cd darknet
```

#### Compilar a biblioteca com base na pasta que está sendo acessada para construir o framework para utilização
```
sed -i 's/OPNECV=0/OPENCV=1/g' Makefile
sed -i 's/GPU=0/GPU=1/g' Makefile
sed -i 's/CUDNN=0/CUDNN=1/g' Makefile
make
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando sed.


Agora vamos baixar o modelo pré treinado (por causa do CNN)
```
wget https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights
````

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando wget.

Testando o detector
```
./darknet detect cfg/yolov4.cfg yolov4.weights data/dog.jpg
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do ponto .


### Visualização de resultados
```python
import cv2
import matplotlib.pyplot as plt

def mostrar (frame):
  imagem = cv2.imread(frame)
  fig = plt.gcf() #Função que chama uma figura
  fig.set_size_inches(18, 10) #Tamanho da saída
  plt.axis('off') #Retira o formato padrão da matplotlib
  plt.imshow(cv2.cvtColor(imagem, cv2.COLOR_BGR2RGB)) #Convertendo BGR para RGB
  plt.show
```

```python
mostrar('predictions.jpg')
```


