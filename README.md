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
* [.csv](http://en.wikipedia.org/wiki/Comma-separated_values)
* [.tsv](http://en.wikipedia.org/wiki/Tab-separated_values)
* .txt (com tsv ou csv dentro)
* [.ods](http://en.wikipedia.org/wiki/OpenDocument)
* [.xls](http://en.wikipedia.org/wiki/Microsoft_Excel#Binary)
* [.xlsx](http://en.wikipedia.org/wiki/Office_Open_XML)

Como estamos falando de dados abertos, aconselhamos fortemente a publicação em formatos abertos (formatos que não impõe restrição tecnológica - [mais informações](http://opendefinition.org/)) :
* todos com exceção do .xls e do .xlsx!

Por fim, se queremos publicar dados em formatos simples e tamanhos pequenos, façamos como o <http://datos.gub.uy/> : csv compactado!

### Onde e porque ###

Como é de conhecimento de todos, o canal mais democrático e de maior permeabilidade da atualidade é a web! É na web lá que qualquer pessoa do mundo pode ter acesso aos dados que disponibilizamos com qualquer navegador.

![Tim Berners Lee](http://www.scientificamerican.com/media/inline/the-mind-behind-the-web_1.jpg)
&nbsp;
![WEB](http://www.pr-vantage.com/wp-content/uploads/2010/12/Web-Connection-300x232.jpg)

Considerando que queremos facilitar o trabalho dos nossos consumidores e que para isso selecionamos a web, é fundamental seguir [a sua arquitetura](http://www.w3.org/TR/webarch/) e algumas considerações do seu criador ([Sir Tim Berners Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee)) e de pesquisadores como [Roy Fielding](https://en.wikipedia.org/wiki/Roy_Fielding), que defendem sua utilização de forma simples e direta:
* Disponibilizá-lo em uma URL fixa, para que qualquer pessoa possa encontrá-lo e compartilhá-lo com terceiros;
* Não utilizar abstrações adicionais de outros protocolos, permitindo que qualquer aplicação possa chegar ao arquivo sem maiores complicações.

Atualmente qualquer web service que siga o [estilo arquitetural REST](https://en.wikipedia.org/wiki/Representational_State_Transfer) ou ferramenta pronta de catalogação permite que se compartilhe dados em URLs fixas, ou persistentes.

Por último, pode ser vantajoso padronizar URLs de acesso aos arquivos de dados: essa abordagem facilita o trabalho de crawlers, desenvolvedores, de mecanismos de busca e de muitas outras pessoas quando procurando nossos dados.

Um grande exemplo de organização da informação nas URLs é o caso do governo do Reino Unido:

1. Página inicial do governo eletrônico do Reio Unido: <https://www.gov.uk/>
2. Página inicial para serviços de direção, transporte e viagens: <https://www.gov.uk/browse/driving>
3. Página inicial para serviços de trabalho e pensão: <https://www.gov.uk/browse/working>
4. Página inicial da parceria Reino Unido e Brasil: <https://www.gov.uk/government/world/brazil>

Esse exemplo não demonstra a organização nas URLs de conjuntos de dados, mas mostra que nas páginas do governo britânico existe na nomenclatura das páginas de serviços, uma padronização. Ainda mostra, além dessa padronização, a tentativa de agregar significado às URLs, para que elas sejam intuitivas para quem for utilizar.

## Catálogos de dados abertos e o CKAN ##

Para facilitar o processo de busca dos dados publicados em formatos abertos, utilizamos catálogos de dados abertos. 

A única descrição encontrada sobre o que é um catálogo de dados está aqui: <http://www.w3.org/TR/vocab-dcat/#class-catalog>

> "A data catalog is a curated collection of metadata about datasets."
> W3C

Considerando que essa foi a única definição encontrada, vou inventar a minha:

Um catálogo de dados abertos é um mecanismo, ferramenta ou serviço que faz a gestão e publicação na web de metadados relativos a dados abertos.

A funcionalidade básica de um catálogo de dados é então permitir: a busca, inclusão, alteração e exclusão desses metadados. 
As soluções de catálogo mais conhecidas, no entanto, têm incorporado cada vez mais funcionalidades:
* Integração com [sistemas de gestão de conteúdo](http://en.wikipedia.org/wiki/Content_management_system) (CMS como [wordpress](http://en.wikipedia.org/wiki/WordPress), [joomla](http://en.wikipedia.org/wiki/Joomla), [drupal](http://en.wikipedia.org/wiki/Drupal), [plone](http://en.wikipedia.org/wiki/Plone_(software)), etc.) ou ter seus próprios sistemas de gestão de conteúdo
* Possibilidade de visualização dos dados catalogados
* Controle de acesso a partes dos conjuntos de dados disponibilizados (acesso)
* Controle de acesso descentralizado para inclusão e edição de metadados, permitindo delegação por organizações e usuários
* Hospedagem de arquivos
* Transformação de arquivos
* APIs de acesso automatizado

### Soluções conhecidas: ###

* Socrata (Socrata)
* Junar Open Data Platform (Junar)
* CKAN (OKFN)

__Observações:__ 
* Essas são as soluções de mercado de maior destaque atualmente. Na verdade, devo esclarecer que são as únicas que conheço. Caso haja alguma outra que seja importante e eu não tenha colocado, por favor me avise!
* Não tive a oportunidade de testar as soluções Socrata e Junar como publicador, só como usuário.

### Socrata ###

![Socrata Home Page](https://photos-3.dropbox.com/t/0/AABQm3gFtyqC_n4b0ItX6PsjnJyMd4xvgjw5kUVaN_wFPQ/12/18364240/jpeg/32x32/3/_/1/2/Socrata.jpg/EzWsMsnxRmWMvrnTfhzXD2fGj-Xla1oQL9rpQ9-TbGs?size=1024x768)

#### Principais características ####
* Sotware como serviço
* API para acesso automático
* Pré visualização de dados tabulares
* Construção de visualizações mais elaboradas (formatação condicional, gráficos e mapas)


#### Quem usa? ###
* [Kenya](https://opendata.go.ke/)
* [Programa de Desenvolvimento das Nações Unidas](http://www.undp.org/content/undp/en/home.html) <https://data.undp.org/>
* [Banco Mundial](https://finances.worldbank.org/)
* [Estados Unidos (até 2013)](http://www.data.gov/)
* [Dezenas de cidades e estados nos Estados Unidos e no Mundo](http://www.socrata.com/customer-spotlight/)

### Junar Open Data Platform ###

![Junar Home Page](https://photos-4.dropbox.com/t/0/AAD48ncEMfORhlltWE0fqrBgQMbK54mev3gF30gXqihWxQ/12/18364240/jpeg/32x32/3/_/1/2/junar.jpg/--5i3Cu53p3w4OtSY-uFZhUP0dT--67C7GqiPDpQOr0?size=1024x768)

#### Principais características ####
* Software como serviço
* API para acesso automático
* Pré visualização de dados tabulares
* Visualização de dashboards pré elaborados

#### Quem usa? ###
* [Chile](http://datos.gob.cl/)
* [Costa Rica](http://datosabiertos.gob.go.cr/)
* [6 municípios nos Estados Unidos e no Mundo](http://www.junar.com/plans)
* [La nación (Jornal da Argentina)](http://data.lanacion.com.ar/)

### CKAN ###

![CKAN Home Page](https://photos-6.dropbox.com/t/0/AABEWPFfd_5ML1NYOCqQR0JroGtLRr5X5fztfRICwBq9wQ/12/18364240/jpeg/32x32/3/_/1/2/ckan.jpg/knz_ahNH1kXW0wU4EC2W267_aw_pczSlevS9wbwyOr0?size=1024x768)

#### Principais características ####
* Sotware Open Source - <https://github.com/okfn/ckan>
* Software como serviço
* API para acesso automático
* Pré visualização de dados tabulares
* Construção de visualizações (gráficos e mapas)
* Busca de datasets geolocalizada

#### Quem usa? ###
* [Reino Unido](http://data.gov.uk/)
* [Estados Unidos](http://www.data.gov/)
* [Alemanha](https://www.govdata.de/)
* [public.data.eu](http://publicdata.eu/)
* [Brasil](http://dados.gov.br/)
* [Dezenas de países, estados e cidades no mundo](http://ckan.org/instances/)


## APIs - por que e como? ##

O que é uma API ?

API quer dizer Application Programming Interface (Interface de Programação de Aplicação).
> "Generally speaking, an application programming interface specifies how some software components should interact with each other."
> [Wikipedia](https://en.wikipedia.org/wiki/Application_programming_interface)

Ou seja, é um componente de interoperabilidade. Na prática uma API é uma biblioteca, em alguma linguagem de programação, que encapsula ou abstrai a uma rotina que pode ou não ser de comunicação com outros componentes.

O que chamamos de APIs quando falamos de dados abertos, na verdade, são Web APIs.



### Protocolo de interoperabilidade de catálogo de dados ###


Data Catalog Interoperability Protocol
![OKFN's DCIP](https://photos-4.dropbox.com/t/0/AAANtsg7lmKJfZtd5Y0Z0JiR07oQVJ4huCRxrqvLivNS2Q/12/18364240/jpeg/32x32/3/_/1/2/DCIP.jpg/6XHdLEkNdUi5KZ0-07i5v4l7dlMQXx6J1CEWK8qbVTI?size=1024x768)

## Exercício práctico ##

## Referências ##
