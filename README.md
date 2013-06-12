Introdução a ferramentas - desmistificando os dados abertos
===========================================================

> "A simplicidade é o último grau de sofisticação."
> Leonardo da Vinci

   Antes de mergulhar nas ferramentas e metodologias mais aclamadas para a publicação de dados abertos, é importante voltarmos aos objetivos desse modelo de publicação: por que publicar dados abertos?
  
   Publicar dados abertos é, antes de tudo, um esforço para tornar os dados mais fáceis de se utilizar e cruzar possível por desenvolvedores. Nós não sabemos quem vai utilizar e com quais outros dados os nossos serão cruzados, isso exige que os tornemos simples e bem documentados.
   
   Nessa parte do curso o aluno será orientado a buscar a simplicidade para agilizar a publicação de dados e conhecer ferramentas que facilitam esse trabalho.

## Das Planilhas locais para dados na web ##

### Formatos ###

![Brinquedo de formas de crianças](http://4.bp.blogspot.com/-QmNc--UT8NM/UJGHobnbzDI/AAAAAAAAAXY/6_lVMxtrx-c/s1600/wooden_toy_shape_sorter_block_box.jpg)

Dentre as formas de se publicar dados abertos, a que consideramos mais simples é utilizar formatos de planilha:
* .csv
* .tsv
* .txt (com tsv ou csv dentro)
* .ods
* .xls
* .xlsx -> isso é aberto mesmo ? aparentemente sim  @_@ -> [Standard ECMA-376 - Office Open XML File Formats](http://www.ecma-international.org/publications/standards/Ecma-376.htm)

Como estamos falando de dados abertos, aconselhamos fortemente a publicação em formatos abertos (formatos que não impõe restrição tecnológica - [mais informações](http://opendefinition.org/)) :
* todos com exceção do .xls !

Por fim, se queremos publicar dados em formatos simples e tamanhos pequenos, façamos como o <http://datos.gub.uy/> : csv compactado!

### Onde e porque ###

Como é de conhecimento de todos, o canal mais democrático e de maior permeabilidade da atualidade é a web! É na web lá que qualquer pessoa do mundo pode ter acesso aos dados que disponibilizamos com qualquer navegador.

![Tim Berners Lee](http://www.scientificamerican.com/media/inline/the-mind-behind-the-web_1.jpg)
&nbsp;
![WEB](http://www.pr-vantage.com/wp-content/uploads/2010/12/Web-Connection-300x232.jpg)

Considerando que queremos facilitar o trabalho dos nossos consumidores e que para isso selecionamos a web, é fundamental seguir algumas considerações do seu criador (Sir Tim Berners Lee) e de pesquisadores como Roy Fielding, que defendem sua utilização de forma simples e direta:
* Disponibilizá-lo em uma URL fixa, para que qualquer pessoa possa encontrá-lo e compartilhá-lo com terceiros;
* Não utilizar abstrações adicionais de outros protocolos, permitindo que qualquer aplicação possa chegar ao arquivo sem muitas complicações;

Hoje qualquer web service ou ferramenta pronta de catalogação permite que se compartilhe dados em URLs fixas, ou persistentes

Por último, pode ser vantajoso padronizar URLs de acesso aos arquivos de dados: essa abordagem facilita o trabalho de crawlers, desenvolvedores, da google do yahoo e de muitas outras pessoas quando buscando pelos nossos dados (TODO -- BUSCAR EXEMPLOS E REFERENCIAS)

## Catálogos de dados e o CKAN ##

Ideias de conteúdo para essa seção:

Falar rapidamente sobre serviços e prestadores de serviços de dados abertos:
* SOCRATA
* JUNAR
* CKAN

On a tight budget ? go for open source software!

## APIs - por que e como? ##

## Exercício práctico ##

## Referências ##
