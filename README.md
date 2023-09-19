
# Projeto my-image-processing

Projeto da Formação Python Developer no módulo "Descomplicando a criação de pacotes de processamento de imagens em Python" ministrado por [Karina Kato](https://github.com/tiemi) através da plataforma [Digital Innovation One](https://web.dio.me) - DIO.

O objetivo aqui é aprender como criar pacotes em Python e publicá-los no repositório oficial da linguagem o [Pypi](https://pypi.org). Com isso em mente, o projeto utilizado para subir para Pypi é de total autoria de Karina Kato e está disponível em https://github.com/tiemi/image-processing-package.

## Passo a passo para criar distribuições e publicar pacote

Com o projeto pronto e o arquivo setup.py devidamente configurado, no terminal acesse a raiz do projeto e depois digite os comandos:

Para upgrade do pip
```bash
python -m pip install --upgrade pip
```
Para instalar o Twine
```bash
python -m pip install --user twine
```
Para instalar setuptools wheel
```bash
python -m pip install --user setuptools wheel
```
Para criar as distribuições
```bash
python setup.py sdist bdist_wheel
```

Após rodar o comando acima, se tudo deu certo irá aparecer na pasta raiz do projeto as pastas abaixo :
- build
- dist
- my_image_processing.egg-info

Com isso e após criação da sua conta no **Pypi** o projeto está pronto para subir.

 Antes porém, como boa prática, fomos orientados pela Karina Kato a subir primeiro no [Test Pypi](https://test.pypi.org/), então é preciso criar uma conta lá também( sugerido criar com mesmos dados, usuário e senha do Pypi).

Para subir o pacote para o Test Pypi:
 ```bash
 python -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*
 ```
 Ao rodar o comando acima, será solicitado usuário e senha que foram cadastrados na criação da conta em Test Pypi. Feito isso, o projeto estará hospedado e pronto para uso.

 Para instalar o pacote :
 ```bash
 pip install –-index-url https://test.pypi.org/simple/ image-processing
 ```

**Publicando no Pypi**

Processo muito similar ao anterior, onde após rodar o comando abaixo será solicitado o usuário e senha da conta Pypi e se não ocorrer nenhum erro seu pacote estará	publicado e pronto para ser usado por toda a comunidade de desenvolvedores Python. Digite:
```
python -m twine upload --repository-url https://upload.pypi.org/legacy/ dist/*
```
Para instalar o pacote:
```bash
python -m pip install my_image_processing
```

Exemplos de como utilizar:
```python
from my_image_processing.processing import combination, transformation
```

# Autor

[karina Kato](https://github.com/tiemi), [Miguel Mendes Serrano](https://github.com/miguelmendesSerrano)

# License

[MIT](https://choosealicense.com/licenses/mit)