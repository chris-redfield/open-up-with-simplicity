Exemplo prático de visualização de dados
===========================================================

## Apresentação ##

Esse experimento é fruto do [Curso sobre datos abiertos para entidades públicas de América Latina y el Caribe](http://www.od4d.org/2013/05/28/curso-sobre-datos-abiertos-para-entidades-publicas-de-america-latina-y-el-caribe/). O exemplo tem o objetivo de demonstrar como pode ser fácil(ou difícil) criar visualizações úteis à partir da utilização de dados bem formatados e com as ferramentas certas.

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

Agora, poderíamos buscar uma solução simples, converter o ShapeFile para CSV e visualizar no [Google Maps Engine](https://mapsengine.google.com), mas temos duas questões:
1. Seria fácil demais, somos guerreiros e vamos tomar o caminho mais difícil buscando o aprendizado!
2. Na verdade o google maps engine só aceita 100 pontos por arvquivo csv, e nós queremos volume! O arquivo possui 40 mil paradas de ônibus e queremos visualizar todas.

Sabemos que existem outras soluções que permitiriam fazer coisas como essa, mas as que conhecemos são proprietárias, então vamos propor utilizar soluções livres e gratuitas, ao alcance de todos!

### Preparando os arquivos para utilização ###

Abra o QuantumGis(QGis), arraste e solte o v_uptu_paradas.shp para o meio do programa.

![QGis](https://dl.dropboxusercontent.com/u/18364240/drag-and-drop.png)

Você obterá um resultado como esse:

![Paradas no QGis](https://dl.dropboxusercontent.com/u/18364240/bus-stops-QGis.jpg)

Ahá!!! já dá pra ter noção do resultado final, agora só precisamos de um mapinha onde pintar os pontos.

Clique com o Botão direito na única camada disponível: v_uptu_paradas, e selecione a opção Abrir tabela de atributos conforme abaixo.

![Abrir tabela de atributos](https://dl.dropboxusercontent.com/u/18364240/open-atribute-table.png)

Essa tabela de atributos carrega os dados do .dbf, que contém os atributos dos pontos, informações como código da localidade, nome da rua, código da rua etc.

![atributes table](https://dl.dropboxusercontent.com/u/18364240/tabela-de-atributos.jpg)

Como estamos fazendo um exercícío, vamos excluir esses dados para reduzir o tamanho do arquivo final que vamos transformar.
OBSERVAÇÃO IMPORTANTE: lembramos que esses atributos são muito importantes para um desenvolvedor que queira gerar um serviço de qualidade em cima desses dados, como nosso objetivo é didático, vamos reduzir o tamanho do arquivo para facilitar nossa visualização.
OBSERVAÇÃO IMPORTANTE2: Algumas vezes o QGis não permite deletar essas colunas, nesse caso você vai abrir o .dbf com o Libre Office Calc e apagar as colunas manualmente (tem que ser libre office 4, se seu Sistema Operacional for Linux, você também devera instalar o [Libre Office Base](http://pt-br.libreoffice.org/libreoffice/base/)). Ainda não sabemos se é possível simplesmente apagar o arquivo .dbf :)

Clique no botão circulado em vermelho na imagem acima, para excluir os campos. 

Selecione cada uma das colunas e clique no botão ok.

![columns for deletion](https://dl.dropboxusercontent.com/u/18364240/delete-atributes.png)

Agora clique novamente na camada v_uptu_paradas e selecione a opção "salvar como...". Daqui há várias coisas que precisam ser feitas:

1. Selecione o formato GeoJSON
2. Selecione a mesma pasta onde você baixou o HTML do curso 
3. Dê esse nome ao arquivo paradas-montevideo.geojson
3. Selecione o formato WGS84 (o que está escrito somente WGS84, não é o WGS84 / UTM zone 21S)
4. Pressione "ok" para salvar!

![save layer as](https://dl.dropboxusercontent.com/u/18364240/save-layer-as.jpg)

### Visualizando os dados ###

Como falamos acima, nosso objetivo é criar algumas reflexões sobre a facilidade(ou dificuldade) na visualização de dados disponíveis. Não queremos formar desenvolvedores, tampouco especialistas em uma ou outra ferramenta.
Portanto, criamos um arquivo HTML simples, baseado em diversos exemplos na web, que recebe o arquivo GeoJSON e pinta os pontos em um mapa.

Para visualizar as paradas de ônibus, selecionamos:

1. O [Open Street Map](http://www.openstreetmap.org/), uma solução de mapas livre, e não proprietária.

![Open Street Map](http://www.openstreetmap.org/assets/osm_logo-0c85efbce2a8dac886d90b6b3609c55d.png)

2. O Leaflet, uma biblioteca que facilita o trabalho de "pintar" os pontos no mapa.

![Leaflet](http://leafletjs.com/docs/images/logo.png)

Para os mais vorazes, que gostam de olhar por baixo do capô, mostramos o código do HTML com algumas considerações:

	<!DOCTYPE html>
	<html>
	<head>
		<title>Ejemplo de utilizacción de datos abiertos geograficos</title>
		<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.5/leaflet.css" />
	 <!--[if lte IE 8]>
		<link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.5/leaflet.ie.css" />
	 <![endif]-->
		<script src="http://cdn.leafletjs.com/leaflet-0.5/leaflet.js"></script>
		<script src="http://code.jquery.com/jquery-2.0.0.min.js"></script>
	</head>
	<body>
		<div id="map" style="width:800px; height:480px;"></div>
		<script type="text/javascript">
			var map = L.map('map').setView([-34.906417,-56.199238], 14);
			L.tileLayer('http://{s}.tile.cloudmade.com/91e81d26d1c949c7aeb49b86f8381ad3/997/256/{z}/{x}/{y}.png', {
				attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://cloudmade.com">CloudMade</a>',
				maxZoom: 18
			}).addTo(map);
			$.getJSON("paradas-montevideo.geojson").done(function(pontos){
				L.geoJson(pontos, {
					pointToLayer: function (feature, latlng) {
						return L.circleMarker(latlng, {
								radius: 2,
								fillColor: "#ff7800",
								color: "#000",
								weight: 1,
								opacity: 1,
								fillOpacity: 0.8
							   });
					}
				}).addTo(map);
			});
		</script>
	</body>
	</html>

1. Na linha 13 definimos a área onde o mapa será pintado e seu tamanho
2. Na linha 15 definimos as coordenadas onde o mapa será aberto e o zoom inicial
3. Na linha 16 definimos o serviço do qual retiramos as "telhas" (imagens do mapa) e a devida atribuição a essas fontes (o seriviço utilizado para pegar as telhas do Open Street Map foi o [CLoudMade](http://cloudmade.com/)
4. Na linha 20 carregamos o arquivo GeoJSON e definimos as características do ponto (cor, tamanho etc)

Por fim resta abrir o HTML com o FireFox (o Google Chrome não permite a abertura de arquivos json localmente, não testamos outros navegadores) e visualizar o resultado!

![Mapa final 1](https://dl.dropboxusercontent.com/u/18364240/mapa1.png)


![Mapa final 2](https://dl.dropboxusercontent.com/u/18364240/mapa2.png)

Sim, vai ficar bem pesado, pois são 40 mil paradas de ônibus desenhadas em um mapa.
No mesmo local onde está o html (<https://github.com/chris-redfield/open-up-with-simplicity>), há um arquivo chamado "metade-paradas-montevideo.zip" dentro da pasta ejemplos. Retiramos algumas paradas para gerar uma visualização mais leve.

