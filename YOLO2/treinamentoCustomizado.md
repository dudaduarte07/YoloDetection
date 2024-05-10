## Coleta e catalogação das imagens dos objetos para treinamento

### Etapa1 - Clonando o repositório da ferraemnta
```
git clone https://github.com/EscVM/OIDv4_ToolKit.git
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando git clone.

### Etapa2 - Acessando o diretório da ferramenta
```
ls
```

```
cd OIDv4_ToolKit/
```

```
ls
```

### Etapa3 - Instalação das bibliotecas necessárias
```
pip3 install -r requirements.txt
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando pip.

### Etapa4 - Fazendo o download das imagens

#### Imagens de treinamento
```
python main.py downloader --classes Bird Butterfly Flower --type_csv train --limit 500 --multiclasses 1 #o ultimo parametro é o numero de pastas para colocar as imagens
```

> [!IMPORTANT]
> Aqui você define quais imagens quer treinar (Pássaro, borboleta e flor).
> Você define quantas imagens quer treinar (500)

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando python.

> [!NOTE]
> Esse processo vai demorar.

#### Imagens de validação
```
python main.py downloader --classes Bird Butterfly Flower --type_csv test --limit 100 --multiclasses 1
```

> [!IMPORTANT]
> Você precisa de 20% da quantidade das imagens de treino para validação (100)

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando python.

> [!NOTE]
> Esse processo vai demorar.


### Etapa5 - Convertendo os arquivos de anotação
Colocar as classes no arquivo classes.txt
```
cat classes.txt #Mostra as classes salvas no tx
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando cat.

```
echo -e 'Bird\nButterfly\nFlower' > classes.txt #Configurar o nome das classes no txt
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando echo.

Clonando o repositório da ferramenta
```
git clone -n https://github.com/Hemilibeatriz/TreinamentoCustomizadoYOLO.git
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando git clone.

```
cd TreinamentoCustomizadoYOLO/
```
```
git checkout HEAD converter_anotacoes.py #Download apenas da pasta necessaria
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando git.

```
mv converter_anotacoes.py /content/OIDv4_ToolKit/ #mover para a pasta raiz
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando mv.

```
cd ..
```

#### Executar  o arquivo de conversão
```
python converter_anotacoes.py
```

> [!WARNING]
> Caso esteja usando o GoogleColab não se esqueça de colocar ! antes do comando python.
