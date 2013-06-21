Exemplo prático de visualização de dados
===========================================================

## Apresentação ##

Esse experimento é fruto do [Curso sobre datos abiertos para entidades públicas de América Latina y el Caribe](http://www.od4d.org/2013/05/28/curso-sobre-datos-abiertos-para-entidades-publicas-de-america-latina-y-el-caribe/). O exemplo tem o objetivo de demonstrar como pode ser fácil criar visualizações úteis à partir da utilização de dados bem formatados e com as ferramentas certas.

Em homenagem ao país anfitrião do curso, optamos por utilizar dados de transporte público da cidade de Montevidéu, disponíveis no [datos.gub.uy](http://datos.gub.uy/). 

### Sobre a apresentação ###

A visualização será muito simples, vamos pintar em um mapa as paradas de ônibus da cidade, provando que seria fácil criar, por exemplo, um aplicativo que localiza a parada de ônibus mais próxima onde passa a linha desejada. 
OBSERVAÇÃO IMPORTANTE: Esse exemplo não fará isso!!! Nosso objetivo é mostrar que isso é altamente factível em menos de uma hora. Não pesquisamos se já existem aplicativos que fazem isso na cidade, mas lembramos novamente que o objetivo do exemplo não é criar um aplicativo que faça isso, e sim demonstrar a facilidade para tal.

## Pré requisitos ###

Para essa atividade vamos precisar de:

1. Esses dados: <https://catalogodatos.gub.uy/dataset/transporte-colectivo-paradas-lineas-puntos-de-control>
2. QuantumGis: <http://hub.qgis.org/projects/quantum-gis/wiki/Download>
3. Esse html, pré criado pelos professores: <https://github.com/chris-redfield/open-up-with-simplicity/blob/master/ejemplos/paradas-montevideo.html>
4. Libre Office 4: <http://www.libreoffice.org/download>
5. Navegador Firefox: <http://www.mozilla.org/en-US/products/download.html?product=firefox-21.0&os=win&lang=en-US>
6. Paciência e motivação!


## Mãos à obra! ##

### baixando os arquivos ###

Na página do dataset no datos.gub.uy, vamos fazer o download das localidades das paradas de ônibus. Escolha o dataset apontado na foto, clique no botao azul e selecione a opção de descarregar. O arquivo v_uptu_paradas.zip será baixado para sua máquina.

![datos.gub.uy](https://dl.dropboxusercontent.com/u/18364240/datos.gub.uy.png)

Embora não tenhamos encontrado informações sobre a licença "Uruguay Open Data Licence", acreditamos que a licença autorize a utilização dos dados para esse curso.

Descompacte o zip em uma pasta de sua escolha, você obterá esses arquivos:
* v_uptu_paradas.dbf
* v_uptu_paradas.prj
* v_uptu_paradas.shp
* v_uptu_paradas.shx

Esses arquivos fazem parte de um ShapeFile, que é um arquivo de especificação aberta para dados geoespaciais. Mais informações sobre shapefiles [aqui](https://en.wikipedia.org/wiki/Shapefile).

### Preparando os arquivos para utilização ###

Abra o QuantumGis(QGis), arraste e solte o v_uptu_paradas.shp para o meio do programa.

![QGis](https://dl.dropboxusercontent.com/u/18364240/drag-and-drop.png)

Você obterá um resultado como esse:

![Paradas no QGis](https://dl.dropboxusercontent.com/u/18364240/bus-stops-QGis.jpg)

Clique com o Botão direito na única camada disponível: v_uptu_paradas, e selecione a opção Abrir tabela de atributos conforme abaixo.

![Abrir tabela de atributos](https://dl.dropboxusercontent.com/u/18364240/open-atribute-table.png)













