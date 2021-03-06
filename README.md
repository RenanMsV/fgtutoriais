## Bem vindo ao índice de tutoriais do simulador de voo FlightGear.

#### Índice:
  - ##### [Cenário](#seção-cenário)
    - [Como colocar objetos no cenário](#como-colocar-objetos-no-cenário)
  - [Como criar ou editar aeroportos](#como-criar-ou-editar-aeroportos)
    - [Primeiros passos](#primeiros-passos)
    - [WED - World Editor](#wed---worldeditor)
    - [Dat2Gnet](#dat2gnet)
    - [QGIS](#qgis)
    - [Terragear](#terragear)
    - [Finalizando](#finalizando)
  - ##### [Aeronave](#seção-aeronave)
    - [Como aplicar reflexo e relevo na fuselagem](#como-aplicar-reflexo-e-relevo-na-fuselagem)
  - ##### [Sons](#seção-sons)
  - ##### [Modelagem](#seção-modelagem)
    - [Como fazer modelos 3d para o FlightGear](#como-fazer-modelos-3d-para-o-flightgear)
  - ##### [Animação](#seção-animação)
    - [Conhecendo os AXIS e suas relações](#conhecendo-os-axis-e-suas-relações)
  - ##### [Texturização](#seção-texturização)
    - [Como fazer texturas noturnas para modelos 3d](#como-fazer-texturas-noturnas-para-modelos-3d)

### Seção: Cenário

  - #### Como colocar objetos no cenário

    1 - Como são editados os cenários:

    Cenários são editados com o avião UFO, por meio de modelos 3D ( que são qualquer tipo de prédio, estrutura, aeronave ) que vemos nos cenários e arquivos .stg.

    2 - O que é um arquivo .stg:

    Arquivos .stg contém informações que o simulador utiliza para colocar cada modelo em sua posição correta durante o carregamento de cenário. São arquivos de texto que dizem qual é o modelo 3D que deverá ser colocado no cenário, a posição que deverá ser colocado e sua rotação.

    3 - Como conseguir modelos 3D para meus cenários:

    O FlightGear já contém vários modelos 3D para cenários e você poderá usá-los. Mas também poderá criar seus próprios com um programa de modelagem 3D.

    AC3D é o programa padrão, mas muitos usuários preferem utilizar o Blender com plugin para modelar e exportar arquivos em formato .ac ( formato que o FlightGear utiliza em seus modelos ).

    Após terminado e exportado crie uma pasta em data/Models/NomeQueVcQuer e coloque seu modelo 3D nela. Coloque um nome único, pois outras pessoas podem colocar o mesmo nome e entrar em conflito.

    4 - Usando UFO para editar o cenário:

    Vamos começar abrindo a launcher, selecionando o avião "UFO" e escolhendo o seu aeroporto que quer editar como ponto de partida.

    ![Tut](assets/img/comocolocarobjetosnocenario/tut01.jpg?raw=true "Tut")

    Ele irá se mover como um avião normal, portanto aumente o throttle e se mova pelo cenário. Escolha uma posição boa.

    ![Tut](assets/img/comocolocarobjetosnocenario/tut02.jpg?raw=true "Tut")

    De um clique com o botão esquerdo do mouse no local em que quer colocar um modelo. Perceba que irá aparecer um modelo padrão no local.

    Então aperte CTRL + Page UP para subir, e CTRL + Page Down para descer na lista de modelos. Vá clicando até encontrar algum que queira. Vou colocar uma aeronave.

    ![Tut](assets/img/comocolocarobjetosnocenario/tut03.jpg?raw=true "Tut")

    Mas perceba que a aeronave está dentro do chão. Para mudar isto vamos apertar o botão "=" (igual) para abrir o menu de posicionamento e rotação dos modelos.

    Agora para termos certeza que vamos rotacionar e mover apenas o modelo que queremos temos que seleciona-lo. Aperte CTRL + Clique em cima do modelo.

    Se o modelo ficou piscando ele está selecionado com sucesso. Se ele não piscou mas outro modelo piscou tente de novo clicando em outro local do modelo.

    Com o modelo selecionado mova os controles no menu de posicionamento e rotação dos modelos e ele irá se mover e rotacionar.

    No meu caso vou usar o controle de altitude para move-lo para cima.

    ![Tut](assets/img/comocolocarobjetosnocenario/tut04.jpg?raw=true "Tut")

    Para mover um objeto de lugar você também pode seleciona-lo e com ALT+Botão Esquerdo em cima do novo local onde quer coloca-lo.

    Para deletar um modelo selecione-o e clique em Backspace.

    Para colocar um novo modelo repita o processo, clique botão esquerdo no local em que quer colocar o novo modelo e vá apertando CTRL+PageUp para ir trocando até encontrar o que quer. Selecione este modelo com CTRL+Botão Esquerdo no modelo que quer selecionar e rotacione-o usando o menu de posicionamento e rotação que é aberto com o botão "=".

    A quantidade de opções de modelos que você terá para escolher irá depender de quantos modelos você tem instalado na pasta data/Models.

    Ao fim de todo seu trabalho aperte a tecla E para que seja salvo. Se o E não for apertado e você sair do simulador perderá tudo que fez.

    5 - Transformando sua edição em um arquivo .stg

    Tenha certeza que apertou a tecla E e feche o simulador.

    Já com o simulador fechado aperte a tecla Windows+R. Digite %appdata% e clique em OK. Irá aparecer uma pasta cheia de pastas. Procure pela chamada flightgear.org e abra. Agora abra a pasta Export. Abra o arquivo "ufo-model-export.xml" que está lá dentro.

    Ou vá direto a este diretório:

        C:\Users\Usuario\AppData\Roaming\flightgear.org\Export\.

    O arquivo aberto conterá mais ou menos esta estrutura:

    ![Tut](assets/img/comocolocarobjetosnocenario/tut05.jpg?raw=true "Tut")

    Tudo que utilizaremos é a localização do cenário que fica em stg-path e a linha de configuração do objeto que fica em object line.

    No nosso caso a localização é :

        w050s30/w048s23/2166987.stg

    Então criaremos um arquivo chamado "2166987.stg" em um editor de texto como notepad.
    No nosso caso a linha de configuração do objeto é:

        OBJECT_SHARED Models/737-800.ac -47.10759645 -22.86117749 612.9396 0.0 0.0 -0.0

    Isto significa que iremos colocar o objeto que fica em "Models/737-800.ac" nas posições:

        -47.10759645 -22.86117749 612.9396" e nas rotações "0.0 0.0 -0.0

    Dentro do arquivo que criamos vamos então escrever essa linha, dar enter e escrever as próximas (caso você tenha colocado vários objetos.)
    Um exemplo:

    ![Tut](assets/img/comocolocarobjetosnocenario/tut06.jpg?raw=true "Tut")

    Salve o arquivo e coloque o no diretório data\Scenery\Objects\w050s30\w048s23. Pois ali em cima diz que o diretório é "w050s30/w048s23/2166987.stg".

    Lembre-se que cada aeroporto que for editar terá um arquivo que deve ser colocado em um local diferente. Confira sempre o arquivo "ufo-model-export.xml".

    Pronto suas modificações já podem ser vistas ao entrar no jogo.

    ![Tut](assets/img/comocolocarobjetosnocenario/tut07.jpg?raw=true "Tut")

    6 - Compartilhando seu trabalho com outras pessoas

    Para compartilhar seus trabalhos com outras pessoas você precisa passar pra elas o arquivo .stg e os modelos 3D que usou.

    Elas devem instalar os modelos na pasta data/Models dela e o arquivo .stg corretamente no diretório correto. Por isso crie uma pasta e coloque o primeiro nome. ex "w050s30" e dentro outra pasta com o segundo nome. ex "w048s23" e dentro o arquivo .stg.

    Zipe tudo com um programa de compactação de arquivos e ficará fácil para o outro instalar, já que a estrutura das pastas já foi feita por você com o nome correto. Não esqueça de zipar junto os modelos que você usou.

  - #### Como criar ou editar aeroportos

    - ##### Primeiros passos
      FlightGear utiliza o mesmo sistema de arquivos de cenário que o XPlane. Com poucas mudanças.
      Este tutorial vai te dar uma ideia de como criar cenários, aeroportos para o FlightGear.

      O que você aprenderá aqui:

      - Criar pistas, taxiways, pátios.
      - Criar posições de estacionamentos.
      - Compilar o cenário.

            Requisitos:
            Necessário +- 40GB de espaço em disco.
            Tutorial para Windows apenas.

      Programas necessários:

      Download Completo : Arquivo zipado com todas ferramentas necessárias. Estão desatualizadas. Use-as caso as oficiais atualizadas não funcionem mais.
      Para baixar : [Download Completo](assets/downloads/FlightGearSceneryDevelopmentPack.7z)

      Python 3 - Python 3 (não Python 2) é necessário para rodar scripts .py.
      Para baixar : [https://www.python.org/downloads](https://www.python.org/downloads/)

      Java - Necessário para rodar programas em java. > ou MINECRAFT <
      Para baixar : [https://www.java.com/pt_BR/download/manual.jsp](https://www.java.com/pt_BR/download/manual.jsp)

      WED - World Editor : Ferramenta para Xplane e FlightGear que cria o layout de aeroportos. Taxiways, Pistas, Pátios, Estacionamentos, etc são feitos por ele.
      Para baixar: [https://developer.x-plane.com/tools/worldeditor/](https://developer.x-plane.com/tools/worldeditor/) ou (provavelmente desatualizado) use o que veio no download completo.

      QGIS - Programa para edição e visualização de arquivos de Landclasses.
      Para baixar: [https://qgis.org/en/site/](https://qgis.org/en/site/)

      Airport Web Generator - É Opcional, um site permite que você compile seu aeroporto para teste. TESTE apenas, já que somente o aeroporto será gerado,
      E não as áreas próximas. Apenas abra o site e envie o arquivo .dat do aeroporto gerado pelo WED.
      Para acessar: [http://ns334561.ip-5-196-65.eu/tgweb/](http://ns334561.ip-5-196-65.eu/tgweb/)

      WedoMaker : É opcional, mas bastante recomendado. Permite usar fotos de satélite para auxiliar no posicionamento e tamanho correto do layout do aeroporto.
      Para baixar: [https://wedomaker.wordpress.com/](https://wedomaker.wordpress.com/) ou (provavelmente desatualizado) use o que veio no download completo.

      Dat2Gnet : Script .py que converte as posições de estacionamento das aeronaves de ICAO.dat para ICAO.groundnet.xml (utilizado pelo FlightGear).
      Para baixar: Vem no download completo.

      TerraGear : Ferramenta que gera os arquivos de cenário para o FlightGear.
      Para baixar : Vem no download completo.

      SRTM 3 :
      Arquivos de Altitude Global, permitem que o cenário contenha os relevos reais. Mais fácil pois vem em tiles abrangendo áreas (Recomendado para quem está começando)
      Para baixar : É preciso saber exatamente a localidade do aeroporto requerido e baixar daqui o arquivo de relevo : [http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm](http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm)

      Outra fonte dos mesmos arquivos, porém nesse não vem em tiles, ele vem separado.
      Para baixar : É preciso saber exatamente a localidade do aeroporto requerido e baixar daqui o arquivo de relevo : [http://www.webgis.com/srtm3.html](http://www.webgis.com/srtm3.html)
      Clique no continente correto, ex: américa do sul, e baixe o arquivo de acordo com a localização do aeroporto ex: S20W50.hgt.zip

      Outra fonte só que para QGIS - Resolução muito boa, pode ser aberto no programa QGIS.
      Para baixar : É preciso saber exatamente a localidade do aeroporto requerido e baixar daqui o arquivo de relevo : [http://srtm.csi.cgiar.org/SELECTION/inputCoord.asp](http://srtm.csi.cgiar.org/SELECTION/inputCoord.asp)

      Landclasses :

      Basicamente são arquivos que vão dizer quais texturas cada parte do cenário irá conter. Caso você saiba como fazer esses arquivos é possível criar
      cenários com varias texturas diferentes e deixa-lo mais bonito a custo de mais processamento. Logo quando mais complexo e bonito o cenário mais pesado ele será.

      Globais - FlightGear TerraGit
      Você pode criar seu cenário só com alguns requeridos. v0_landmass (terreno), v0_lake (rios, lagos), v0_urban (cidades).
      Para baixar : [https://github.com/FGMEMBERS-TERRAGIT?utf8=%E2%9C%93&q=V0&type=&language=](https://github.com/FGMEMBERS-TERRAGIT?utf8=%E2%9C%93&q=V0&type=&language=) e baixe todos.

      Área - Basicamente o mesmo que o global mas apenas em uma área especifica. Diminui o tempo que demora para codificar e o espaço utilizado no HD.
      Não recomendado para quem está começando.
      Para baixar : [http://mapserver.mgras.net/shpdl/](http://mapserver.mgras.net/shpdl/)

      IBGE - Landclasses liberadas pelo Instituto Brasileiro de Geografia e Estatística (IBGE) e logicamente só abrange áreas brasileiras.
      Para baixar : [ftp://geoftp.ibge.gov.br/cartas_e_mapas/bases_cartograficas_continuas/](ftp://geoftp.ibge.gov.br/cartas_e_mapas/bases_cartograficas_continuas/)

      Open Street Maps - Shapefiles Wiki. Contém vários sites para download de Landclasses.
      Para baixar : [https://wiki.openstreetmap.org/wiki/Shapefiles](https://wiki.openstreetmap.org/wiki/Shapefiles)
      
      Open Stree Maps - Land Polygons. Contém o mundo todo extraido apenas com uma textura. Util para fazer regiões costeiras ou ilhas.
      Para baixar : [https://osmdata.openstreetmap.de/data/land-polygons.html](https://osmdata.openstreetmap.de/data/land-polygons.html)

      GeoFabrik - Região Brasileira
      Para baixar : [http://download.geofabrik.de/south-america/brazil.html](http://download.geofabrik.de/south-america/brazil.html)

      BBBike - Principais cidades do Mundo
      Contém : buildings, landuse, vegetation, places, points, railways, roads, waterways
      Para baixar : [https://download.bbbike.org/osm/bbbike/](https://download.bbbike.org/osm/bbbike/)

      BBBike Extrator - Extrai landclasses por áreas. Comunitário, necessário aguardar outras pessoas que estejam na fila. Cerca de 10 minutos de espera.
      Contém : buildings, landuse, vegetation, places, points, railways, roads, waterways
      Para baixar : [https://extract.bbbike.org/](https://extract.bbbike.org/)

      Osm2Shp - Continental
      Para baixar : [http://osm2shp.ru/](http://osm2shp.ru/)

      WGet - Programa que possibilita downloads completos de sites. Com esta ferramenta poderemos baixar todos arquivos de elevação de uma só vez.
      Para baixar : Vem no download completo.

      BBox Finder - Muito útil para encontrar coordenadas de uma área (min lat, max lat, min lon, max lon)
      Para baixar : [http://bboxfinder.com/](http://bboxfinder.com/)

    - ##### WED - WorldEditor
      Pessoas fazem aeroportos para Xplane ou Flightgear todos os dias, portanto provavelmente alguém já trabalhou no mesmo aeroporto que você quer fazer.
      Confira em [https://gateway.x-plane.com/airports/page](https://gateway.x-plane.com/airports/page) todos aeroportos já feitos. (não necessário).

      FlightGear Wiki - [WED](http://wiki.flightgear.org/WorldEditor).

      Antes de abrir o WED pela primeira vez:

      O X-Plane em si não precisa ser instalado antes de usar o WED. No entanto, o WED exigirá que você escolha a pasta do X-Plane antes de permitir que você faça qualquer coisa. Vamos então fingir que estamos com X-Plane instalado.

      Crie um diretório de trabalho com a seguinte estrutura antes de iniciar o WED pela primeira vez.
      ```
      diretorio de trabalho <-- Escolha um nome
         |--Custom Scenery
         |--Global Scenery
         |--Resources
         |--WED.exe
      ```
      Exemplo:
      ![Tut](assets/img/comocriaroueditaraeroportos/tut01.jpg?raw=true "Tut")
      ###### AVISO: O WED procura por essa estrutura de diretórios específica e nomes de diretórios específicos!

      Abra o WED, clique em Choose X-Plane Folder e selecione a pasta em que extraiu o WED.

      Criando o projeto:

      Abra o WED, clique em New Scenery Package, será criado um package chamado Untitled, clique nele e renomeie para o que quiser. Exemplo ICAO - Nome do aeroporto.

      Depois com ele selecionado clique em Open Scenery Package. Após aberto, clique em File > Import From Airport Scenery Gateway, aguarde carregar

      Vai aparecer uma lista com todos aeroportos já feitos, digite o ICAO do aeroporto desejado, selecione-o na lista e clique em next (necessário conexão com internet).

      Vai aparecer uma lista com todas versões ja feitas desse aeroporto, escolha a em que está escrito Recommended. Selecione-a e clique em Import Pack (s).

      <iframe width="560" src="https://www.youtube.com/embed/VSV7_4VDRIA" frameborder="0" allowfullscreen="" height="315"></iframe>

      Caso de um erro "Illegal version line 2 .... " clique em ok e faça o seguinte procedimento:

      Feche o WED.

      Vá na pasta em que instalou o Wed, abra a pasta Custom Scenery, abra a pasta do projeto que criou (tem o nome que colocou no WED), abra o arquivo dat (ex: ICAO.dat) que está dentro dessa pasta no bloco de notas, procure onde está escrito:

          1100 Generated by WorldEditor  ...

      (pode estar 1000, 1100, 1150) e troque para:

          1050 Generated by WorldEditor  ...

      <iframe width="560" src="https://www.youtube.com/embed/tDed9zqdKZ0" frameborder="0" allowfullscreen="" height="315"></iframe>

      Abra o WED, dessa vez já selecione o projeto criado anteriormente e clique em Open Scenery Package, clique em File > Import apt.dat e selecione o arquivo dat que você editou.

      Selecione o aeroporto correto na lista que irá aparecer e clique em import.

      <iframe width="560" src="https://www.youtube.com/embed/vsg70Y4DraE" frameborder="0" allowfullscreen="" height="315"></iframe>

      Pronto o aeroporto já deve ter aparecido para você.
      Agora você pode colocar a imagem de satélite.

      Para colocar imagem de satélite (opcional, recomendado):

      Clique em File > Save e feche o projeto no WED clicando em File > Close.

      Abra o WedoMaker. Aguarde-o iniciar. Ele irá abrir um site. Aperte SHIFT + F5 nesse site para prevenir possíveis erros.

      Copie o caminho do diretório do WED ( ex : D:\Aviacao\WED ) e cole ao lado de onde está escrito " <- enter a valid X-Plane home directory here".

      Se tudo deu certo irá aparecer 2 opções.

      Na primeira selecione o projeto que você criou no WED e na segunda configure a qualidade da imagem de satélite. Recomendo 19 (melhor custo beneficio).

      Após selecionado deve aparecer no mapa o aeroporto que você quer.

      De zoom o máximo que der mantendo o aeroporto todo na tela. Clique no botão Make Visible in WED, aguarde carregar.

      Quando finalizado pode fechar o site, e clicar em Quit no WedoMaker.

      Você também pode colocar textos na pista, números de gates pelo WedoMaker utilizando a opção Insert text and symbols.

      Volte para o WED e abra o projeto novamente. Se tudo deu certo a imagem de satélite apareceu para você dentro do WED.

      Agora no canto superior direito do WED temos a hierarquia de objetos. Procure a nomeada Overlays-WOM, ela guarda todas imagens baixadas e posicionadas no seu projeto.

      Sim, essa imagem de satélite é a junção de 200 ou mais fotos corretamente posicionadas. Portanto arraste a nomeada Overlays-WOM para a world.
      Assim separando elas do seu aeroporto. Permitindo que mova o aeroporto todo livremente.

      Agora crie / edite o layout do aeroporto no WED (veja tutoriais no youtube : como criar aeroportos para o Xplane). Não se esqueça de adicionar as posições
      de estacionamento. Quanto mais, melhor.

      Corrigindo problemas de compatibilidade:

      Provavelmente o cenário baixado irá conter certos objetos que são usados pelo X-Plane, mas o FlightGear não aceitará.

      Portanto para remove-los você deve na hierarquia de objetos apagar qualquer grupo nomeado Facades, Exclusion Zones, Objects...

      Exportando o projeto:
      Ao fim, clique em File > Save, clique em File > Validate e o programa validará para ver se não encontrou problemas (corrija-os).

      Clique em File > Export Target e selecione XPlane 10.50.

      Selecione na hierarquia de objetos o aeroporto que você fez. Clique em File > Export apt.dat,  salve em algum lugar como ICAO.dat, já pode fechar o WED.

      <iframe width="560" src="https://www.youtube.com/embed/JIr9PlDdgQQ" frameborder="0" allowfullscreen="" height="315"></iframe>

      Tutoriais avançados em Inglês:

      - [Airport Creation - Xplane-wiki](http://wiki.x-plane.com/Airport_Creation)
      - [WED tutorial parte 1 (Xsimreviews blog)](https://web.archive.org/web/20131024102137/http://xsimreviews.com/2012/12/16/x-plane-scenery-design-tutorial-4-wed-pt1/)
      - [WED tutorial parte 2 (Xsimreviews blog)](https://web.archive.org/web/20140403230901/http://xsimreviews.com/2013/02/03/x-plane-scenery-design-tutorial-5-wed-part-ii/)
      - [Manual Online WED](https://developer.x-plane.com/manuals/wed/)
      - [WED Tutoriais no Youtube](https://www.youtube.com/playlist?list=PLGRsg_6rB1D4vm0UHvHm6J-rvIyUBGN_K)

    - ##### Dat2Gnet

      Copie o arquivo ICAO.dat exportado e cole na pasta em que colocou o Dat2Gnet.py, abra o arquivo executar.bat com o bloco de notas.

      Neste arquivo bat temos que configurar 3 coisas. A primeira é o nome do script python a rodar, portanto Dat2Gnet.py.

      A segunda coisa é o arquivo .dat do aeroporto, portanto ICAO.dat, e a terceira o ICAO deste aeroporto (utilizado bastante quando o arquivo .dat contém vários aeroportos. sim você pode fazer vários aeroportos no mesmo projeto do WED),
      portanto ICAO. EX: Faz de conta que estamos fazendo o aeroporto de São Paulo, então ficaria:

          Dat2Gnet.py SBGR.dat SBGR

      Após editado o arquivo bat, salve, feche e abra-o. Uma nova pasta deve ter aparecido com o as posições de estacionamento devidamente convertidas.

      Existem 2 maneiras de instalar posições de estacionamento.

      Uma é copiando a pasta Airports gerada para a pasta FlightGear/Scenery/

      Ou utilizando o sistema de Cenários Customizados do FlightGear (recomendado e que será utilizado por aqui). Copie a pasta Airports gerada para uma pasta
      dentro de Documents/FlightGear/CustomScenery/ICAO.

      <iframe width="560" src="https://www.youtube.com/embed/GWkmivVUPS8" frameborder="0" allowfullscreen="" height="315"></iframe>

    - ##### QGIS

      Primeiramente você deve se perguntar

      "O que o terreno em volta do aeroporto irá conter? Ruas? Rios? Florestas? Ou apenas deserto?"

      Para cada uma dessas coisas uma Landclass é requerida. Landclasses vão dizer ao TerraGear onde fica a cidade, onde fica florestas, onde ficam ruas,
      onde ficam lagos, rios, pântanos, desertos, etc... para que o cenário seja criado o mais fielmente a realidade possível.

      Um cenário com somente floresta fica bom, mas não muito realista(exceto se você estiver fazendo um aeroporto cercado somente por florestas, sem ruas ou clareiras).

      Vá no site onde se encontram os arquivos de LandClass e baixe todos que deseja usar.

      Para visualizar ou editar você precisará utilizar o QGIS.

      Para importar uma landclass no QGIS basta arrastar o arquivo zipado para dentro do programa (os arquivos .shp, .shx.. devem estar dentro do arquivo zipado (sem pastas)).

      Ou extraia em alguma pasta e arraste o arquivo .shp direto para dentro do QGIS.
      Para editar procure um tutorial especifico na internet.

      <iframe width="560" src="https://www.youtube.com/embed/9qcPrqE5_Bc" frameborder="0" allowfullscreen="" height="315"></iframe>

    - ##### Terragear

      Extraindo o Terragear:

      <iframe width="560" src="https://www.youtube.com/embed/jKgTxxRE2cY" frameborder="0" allowfullscreen="" height="315"></iframe>

      Abra a pasta TerraGear/bin/ e abra o arquivo EXECUTAR_TERRAGEAR_GUI.bat . O TerraGear GUI será executado.

      Na aba Start terá que colocar 3 diretórios para que o programa salve dados em seu computador.

      Em Project Directory selecione a pasta TerraGear/bin/APT

      Em TerraGear Root selecione a pasta TerraGear

      Em FlightGear Root selecione a pasta Data de seu FlightGear. Ex: "C://Games/FlightGear2017/Data/"

      <iframe width="560" src="https://www.youtube.com/embed/hH0V3HHIaXQ" frameborder="0" allowfullscreen="" height="315"></iframe>

      Na aba Elevation é onde controlamos os arquivos de elevação.

      Em HTG Files Directory selecione a pasta TerraGear/APT/data/SRTM-3/
      - Em Resolution deixe o valor 3
      - Em Min. Nodes deixe 50
      - Em Max. Nodes deixe 1000
      - E em Max. Error deixe 40

      <iframe width="560" src="https://www.youtube.com/embed/5TH92J7urlc" frameborder="0" allowfullscreen="" height="315"></iframe>

      Baixando e processando arquivos de elevação:

      Este processo é muito importante, sem ele o seu cenário não conterá dados de elevação. Ficando todo o terreno com altitude 0ft (em relação ao mar).

      Vá no site onde se encontram os arquivos SRTM-3 e baixe o arquivo correspondente a área do aeroporto. Ou baixe vários caso seja de interesse. (por que não todos?)

      Será baixado um (ou vários) arquivo zip com arquivos .hgt dentro.

      Baixe arquivos de elevação aqui: [http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm](http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm)

      Baixando arquivos de elevação:

      <iframe width="560" src="https://www.youtube.com/embed/9o-IOv30mhY" frameborder="0" allowfullscreen="" height="315"></iframe>

      Por fim, extraia todos arquivos .hgt baixados para a pasta TerraGear/APT/data/SRTM-3

      <iframe width="560" src="https://www.youtube.com/embed/pFr50I1qavI" frameborder="0" allowfullscreen="" height="315"></iframe>

      Dentro do TerraGear GUI vá na aba Elevation e clique em Convert Elevation Data e aguarde o programa converter(quanto mais arquivos .hgt.zip estiverem na pasta mais vai demorar).

      <iframe width="560" src="https://www.youtube.com/embed/6dPpJSwrogE" frameborder="0" allowfullscreen="" height="315"></iframe>

      Quando terminar (barra azul completa e escrito 100%) vá na pasta TerraGear/APT/data/SRTM-3 e mova todos arquivos .hgt.zip para a pasta TerraGear/APT/data/backup.

      Ou apague-os, você não irá precisar deles. Caso você não os mova ou apague na próxima conversão de algum arquivo eles serão convertidos novamente inutilmente, já que você já os converteu anteriormente.

      <iframe width="560" src="https://www.youtube.com/embed/cq7518_47oY" frameborder="0" allowfullscreen="" height="315"></iframe>

      Baixando e processando arquivos de LandClass:

      Este processo é muito importante, sem ele seu cenário não terá terreno.
      Após baixar e conferir todas Landclasses que você irá utilizar extraia todas para a pasta TerraGear/APT/data/.

      Baixando:

      <iframe width="560" src="https://www.youtube.com/embed/_40BLOLFT_E" frameborder="0" allowfullscreen="" height="315"></iframe>

      Extraindo:

      <iframe width="560" src="https://www.youtube.com/embed/RWkd00g37Bc" frameborder="0" allowfullscreen="" height="315"></iframe>

      Devem ficar várias pastas como:
      - v0_lake
      - v0_landmass
      - v0_urban
      - ...

      e dentro de cada vários arquivos, exemplo dentro de v0_urban contém os arquivos:
      - v0_urban.shx
      - v0_urban.shp
      - v0_urban.prj
      - v0_urban.dbf
      - ...

      <iframe width="560" src="https://www.youtube.com/embed/2CrxQDKjGmM" frameborder="0" allowfullscreen="" height="315"></iframe>

      Agora vá no TerraGearGUI, vá na aba Materials, clique em Retrieve shapefiles e clique em Ok.

      Após ele irá mostrar uma tabela. A tabela contém o nome da shapefile, material, largura de linha (usado para ruas, estradas) e SQL.

      Você só precisa preencher a parte Material. Para isto clique na linha desejada por exemplo v0_landmass e logo abaixo no lado direito terá um dropbox e um símbolo de '+' do lado.

      Escolha no dropbox o nome do material no nosso caso o v0_landmass é sempre 'Default'. E clique no botão '+'. Ou apenas digite 'Default' na célula Material.

      Faça com todos, colocando os nomes corretos do material. Por exemplo, em v0_lake iremos utilizar o material 'Lake', em v0_urban iremos utilizar o material 'Urban'...

      É questão de logica. Mas nada impede de você utilizar o material 'Grass' no v0_urban porém todas as cidades irão ter uma textura de grama.

      <iframe width="560" src="https://www.youtube.com/embed/7huW9TRDSF0" frameborder="0" allowfullscreen="" height="315"></iframe>

      ###### Detalhe, alguns nomes de materiais não estão corretamente colocados no programa, por exemplo, DryCropPastureCover deveria ser somente DryCrop, e GrassLand deveria ser Grassland com L minúsculo. Colocar o nome errado não deixa que o programa decodifique. Para colocar o nome certo basta editar o nome manualmente na aba de materiais. Para saber os nomes corretos basta abrir o arquivo "Terragear/share/Terragear/default_priorities.txt"  

      Logo após preencher todos corretamente clique no botão escrito 'Decode Shapefiles and Apply Material'.

      <iframe width="560" src="https://www.youtube.com/embed/hAdNKx6opSI" frameborder="0" allowfullscreen="" height="315"></iframe>

      Este processo levará horas ou minutos dependendo do poder de processamento do computador. Mas fique tranquilo isto só será necessário fazer a primeira vez.

      As vezes pode bugar e não começar a decodificar, ou nunca avisar que acabou e você ficar esperando atoa. Para verificar se está decodificando basta olhar se o processo ogr-decode está rodando no gerenciador de tarefas.

      <iframe width="560" src="https://www.youtube.com/embed/Z6lRss7mHYo" frameborder="0" allowfullscreen="" height="315"></iframe>

      Como estes arquivos de LandClass disponibilizados pelo Terragit são globais e cobrem o mundo todo você só precisa decodificar uma vez. Exceto se você apagar os arquivos decodificados por algum motivo. Ai terá que refazer a decodificação.

      Caso você consiga encontrar arquivos de LandClass menores, cobrindo apenas a área do aeroporto em que você está trabalhando o processo de decodificação será muito mais rápido, sendo feito em poucos minutos ou segundos. Porém logicamente será necessário decodificar toda vez que estiver trabalhando em um novo aeroporto.

      No final os arquivos decodificados devem ficar assim:

      <iframe width="560" src="https://www.youtube.com/embed/3G7TpJuDQcQ" frameborder="0" allowfullscreen="" height="315"></iframe>

      Cortando arquivos de LandClass:

      <iframe width="560" src="https://www.youtube.com/embed/vwuj5FFSfG4" frameborder="0" allowfullscreen="" height="315"></iframe>

      Processando arquivos .dat de aeroportos:

      Pegue o arquivo .dat exportado pelo WED e coloque na pasta "Terragear/bin/APT/data/airports"

      Depois, vá na aba airpors, selecione o arquivo .dat, selecione All airports in .dat file e clique em Generate Airports.

      <iframe width="560" src="https://www.youtube.com/embed/9HGiJG_shQs" frameborder="0" allowfullscreen="" height="315"></iframe>

      Pode demorar um pouco caso o aeroporto seja muito grande e tenha muitos nodes, taxiways ou pistas.

      Para verificar se tudo foi exportado corretamente abra a pasta "Terragear/bin/APT/work/" e verifique que foi criada as pasta AirportObj e AirportArea.

      <iframe width="560" src="https://www.youtube.com/embed/Il9OofowfDE" frameborder="0" allowfullscreen="" height="315"></iframe>

    - ##### Finalizando

      Para gerar o cenário é necessário que você já tenha feito:

      - Decodificado arquivos de elevação SRTM
      - Decodificado arquivos de LandClass
      - Decodificado arquivo .dat do aeroporto

      Va na aba Construct.

      Agora para gerar o cenário temos 2 opções.
      Gerar o cenário em uma área demarcada em um mapa, ou, gerar o cenário de somente um quadrado (chamado tile) inserindo seu ID manualmente.

      Caso for por demarcar em um mapa é preciso ir na aba Download e marcar a área selecionada.

      <iframe width="560" src="https://www.youtube.com/embed/XJjWlWv0WYM" frameborder="0" allowfullscreen="" height="315"></iframe>

      Caso for por ID de tile apenas escreva o ID no campo Tile ID.

      Agora clique em Update list.
      Deixe todos selecionados em Terrain Types e clique Generate Scenery.

      <iframe width="560" src="https://www.youtube.com/embed/thCz6MDlF0w" frameborder="0" allowfullscreen="" height="315"></iframe>

      Caso ele de um erro e não gere o cenário desmarque um por um (menos o Default) da lista de Terrain Types, para encontrar o que está causando o problema.

      Pode demorar bastante, dependendo do tamanho da área e da complexidade das LandClasses que você utilizou.

      Por fim para pegar os arquivos gerados e colocar num cenário customizado basta ir em "Terragear/bin/APT/output" e copiar a pasta Terrain para sua pasta de cenario.

      <iframe width="560" src="https://www.youtube.com/embed/DUqdq0INPDE" frameborder="0" allowfullscreen="" height="315"></iframe>

      Pronto agora só entrar no simulador, escolher este aeroporto e voar? Sim! Mas agora seria uma boa hora para você colocar objetos no cenário. Ou melhorar ainda mais editando as LandClasses utilizadas.

      <iframe width="560" src="https://www.youtube.com/embed/hRXfMb6W" frameborder="0" allowfullscreen="" height="315"></iframe>

      No meu caso a falta de LandClasses detalhadas deixou tudo com uma textura só de Floresta.
      Além de que pelo terreno não ser plano o aeroporto tem algumas partes suspensas e é bem elevado. Da pra editar o arquivo .dat no WED para tentar amenizar.

      E aqui fica as imagens do aeroporto depois de editar as LandClasses.

      ![Tut](assets/img/comocriaroueditaraeroportos/tut02.jpg?raw=true "Tut")

      ![Tut](assets/img/comocriaroueditaraeroportos/tut03.jpg?raw=true "Tut")

### Seção: Aeronave

  - #### Como aplicar reflexo e relevo na fuselagem

    - ##### Informações importantes
      Este efeito permite deixar um reflexo na aeronave e as marcas de relevo na mesma.

      Alguns exemplos abaixo:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut02.jpg?raw=true "Tut")
      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut01.jpg?raw=true "Tut")

      - Este efeito só é visível caso o usuário esteja com as seguintes configurações:

        - Configurações de renderização de shader de modelo deve estar ativada.

          ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut05.jpg?raw=true "Tut")

      - Este efeito requer cuidados ao aplicar:
        - Se aplicado em objetos ou superfícies sem [mapeamento UV](https://pt.wikipedia.org/wiki/Mapeamento_UV) fará o jogo travar e fechar. Sempre confira se o objeto possuí mapeamento.
        - Este efeito só deve ser aplicado em superfícies visíveis e de preferencia somente em superfícies que façam parte da [livery](http://wiki.flightgear.org/Howto:Edit_a_livery) da aeronave.
        - Este efeito irá reduzir desempenho do jogo. Principalmente se aplicado em muitos objetos. Use com moderação.

    - ##### Preparações:

      Pegue o arquivo .png ou .jpg da livery da aeronave que você quer aplicar. É recomendável que não possua nomes / números / identificações, ou seja, deve possuir apenas as linhas que compõem a estrutura da fuselagem da aeronave. Já que essa vai servir para dar o efeito de relevo.

      Vamos utilizar essa aqui de um AT-29 como exemplo:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut03.png?raw=true "Tut")

      Precisamos gerar um [normal map](http://wiki.flightgear.org/Howto:Use_the_normal_map_effect_in_aircraft).

      Vamos utilizar este site [Normal Map Online](http://cpetry.github.io/NormalMap-Online/)

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut06.jpg?raw=true "Tut")

      Arraste a imagem para dentro do site onde está escrito "click or drag % drop".

      Então configure as variáveis para:

        - Em Strength coloque 1.0
        - Em Level coloque 10.0
        - Em Blur/Sharp deixe 0
        - Em Filter deixe Sobel
        - Em Invert deixe R, G e Height desmarcados

        ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut07.jpg?raw=true "Tut")

      Então clique em Download para baixar o seu normal map.

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut08.jpg?raw=true "Tut")

      Normal map gerado:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut03n.png?raw=true "Tut")

      Salve este código abaixo como fuse_bumpreflect.eff

      ```xml
      <?xml version="1.0" encoding="utf-8"?>
      <PropertyList>
        <name>$MY_AIRCRAFT$_bumpspecreflect</name>
        <inherits-from>Effects/model-combined-deferred</inherits-from>
        <parameters>
          <rain-enabled type="int">2</rain-enabled>
          <normalmap-enabled type="int">1</normalmap-enabled>
          <normalmap-dds type="int">0</normalmap-dds>
          <texture n="2">
            <image>Aircraft/$MY_AIRCRAFT$/Models/Effects/fuse_reflection_effect/$MY_AIRCRAFT$-normal.png</image>
            <filter>linear-mipmap-linear</filter>
            <wrap-s>repeat</wrap-s>
            <wrap-t>repeat</wrap-t>
            <internal-format>normalized</internal-format>
          </texture>
          <lightmap_enabled type="int">0</lightmap_enabled>
          <reflection-enabled type="int">1</reflection-enabled>
          <reflect-map-enabled type="int">1</reflect-map-enabled>
          <reflection-correction type="float"><use>/sim/rendering/$MY_AIRCRAFT$/refl_correction</use></reflection-correction>
          <reflection-fresnel-factor type="float"><use>/sim/rendering/$MY_AIRCRAFT$/fresnel-factor</use></reflection-fresnel-factor>
          <reflection-type type="int"><use>/sim/rendering/$MY_AIRCRAFT$/refl-type</use></reflection-type>
          <reflection-dynamic type="int">1</reflection-dynamic>
          <texture n="4">
            <image>Aircraft/$MY_AIRCRAFT$/Models/Effects/fuse_reflection_effect/grey.png</image>
            <filter>linear-mipmap-linear</filter>
            <wrap-s>clamp</wrap-s>
            <wrap-t>clamp</wrap-t>
            <internal-format>normalized</internal-format>
          </texture>
          <texture n="5">
            <type>cubemap</type>
            <images>
              <positive-x>Aircraft/Generic/Effects/fgfs-sky2/1.png</positive-x>
              <negative-x>Aircraft/Generic/Effects/fgfs-sky2/4.png</negative-x>
              <positive-y>Aircraft/Generic/Effects/fgfs-sky2/2.png</positive-y>
              <negative-y>Aircraft/Generic/Effects/fgfs-sky2/3.png</negative-y>
              <positive-z>Aircraft/Generic/Effects/fgfs-sky2/6.png</positive-z>
              <negative-z>Aircraft/Generic/Effects/fgfs-sky2/5.png</negative-z>
            </images>
          </texture>
          <texture n="6">
            <image>Aircraft/$MY_AIRCRAFT$/Models/Effects/fuse_reflection_effect/alpha.png</image>
            <type>2d</type>
            <filter>linear-mipmap-linear</filter>
            <wrap-s>repeat</wrap-s>
            <wrap-t>repeat</wrap-t>
            <internal-format>normalized</internal-format>
          </texture>
          <reflection-fresnel type="float">0.00</reflection-fresnel>
          <reflection-rainbow type="float">0.00</reflection-rainbow>
          <reflection-noise type="float">0.00</reflection-noise>
          <ambient-correction type="float">0.0</ambient-correction>
          <dirt-enabled type="int">0</dirt-enabled>
          <dirt-color type="vec3d">1.0 1.0 1.0</dirt-color>
          <dirt-factor type="float">0.5</dirt-factor>
        </parameters>
      <!-- ####################
      ### NORMALMAP INCLUDE ###
      ######################### -->
      <generate>
        <tangent type="int">6</tangent>
        <binormal type="int">7</binormal>
      </generate>

      <technique n="4">
        <pass>
          <program>
            <attribute>
              <name>tangent</name>
              <index>6</index>
            </attribute>
            <attribute>
              <name>binormal</name>
              <index>7</index>
            </attribute>
          </program>
        </pass>
      </technique>

      <technique n="7">
        <pass>
          <program>
            <attribute>
              <name>tangent</name>
              <index>6</index>
            </attribute>
            <attribute>
              <name>binormal</name>
              <index>7</index>
            </attribute>
          </program>
        </pass>
      </technique>
      <technique n="9">
        <pass>
          <program>
            <attribute>
              <name>tangent</name>
              <index>6</index>
            </attribute>
            <attribute>
              <name>binormal</name>
              <index>7</index>
            </attribute>
          </program>
        </pass>
      </technique>
      <!-- ########################
      ### END NORMALMAP INCLUDE ###
      ############################# -->
      </PropertyList>
      ```

      O local em que o arquivo deve ser salvo em sua aeronave é na pasta Models/Effects/fuse_reflection_effect por exemplo:

          $FGDATA$/Aircraft/Airbus320/Models/Effects/fuse_reflection_effect/

      Agora substitua no código onde está escrito $MY_AIRCRAFT$ pelo nome de sua aeronave (não utilize espaços ou caracteres especiais). Use a ferramenta replace de seu editor de texto preferido caso queira substituir tudo mais rapidamente.

      Por exemplo se estivermos fazendo um Airbus320 utilizando o editor Atom:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut09.jpg?raw=true "Tut")

      Agora copie a imagem de normal map que você gerou antes para a pasta e troque o nome para NOME_DA_AERONAVE-normal.png. Por exemplo:

          $FGDATA$/Aircraft/Airbus320/Models/Effects/fuse_reflection_effect/Airbus320-normal.png

      Agora coloque baixe essas [2 fotos](assets/downloads/fuselagereflectalphagrey.zip) e coloque na pasta também.

      A pasta deve ficar assim:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut10.jpg?raw=true "Tut")

      Agora vá no arquivo de modelo [XML](http://wiki.flightgear.org/FlightGear_configuration_via_XML) de sua aeronave.

      No meu caso AT-29\Models\AT-29.xml, e procure aonde está a parte que coloca a livery. Exemplo:

      ```xml
      <animation>
        <type>material</type>
        <object-name>GroupFuselage</object-name>
        <property-base>sim/model/livery</property-base>
        <texture-prop>fuselage</texture-prop>
        <texture>Liveries/USA/fuselage.png</texture>
      </animation>
      ```

      - Detalhe que neste caso só aparece um objeto nomeado GroupFuselage pois no FlightGear podemos agrupar objetos para uso posterior. Se procurarmos no arquivo iremos encontrar onde este grupo foi criado:

        ```xml
        <animation>
          <name>GroupFuselage</name>
          <object-name>fuselage</object-name>
          <object-name>entradadear</object-name>
          <object-name>VentralFin</object-name>
          <object-name>Spinner</object-name>
          <object-name>Speedbrake</object-name>
          <object-name>Rudder</object-name>
          <object-name>NoseWellCover</object-name>
        </animation>
        ```
        Portanto esse grupo chamado GroupFuselage contém os objetos fuselage, entradadear, VentralFin, Spinner, SpeedBrake, Rudder e NoseWellCover. Todos terão suas texturas substituídas dependendo da livery escolhida. Iremos também aplicar o efeito de reflexo nesses objetos.

      Aqui está um exemplo de código para aplicar o efeito:

      ```xml
      <effect>
        <inherits-from>Aircraft/$MY_AIRCRAFT$/Models/Effects/fuse_reflection_effect/fuse_bumpreflect</inherits-from>
        <object-name>objeto_exemplo</object-name>
      </effect>
      ```

      No caso para o AT-29 pegamos a lista de objetos que compõem a fuselagem e aplicamos o efeito, o código fica assim:

      ```xml
      <effect>
        <inherits-from>Aircraft/AT-29/Models/Effects/fuse_reflection_effect/fuse_bumpreflect</inherits-from>
        <object-name>fuselage</object-name>
        <object-name>entradadear</object-name>
        <object-name>VentralFin</object-name>
        <object-name>Spinner</object-name>
        <object-name>Speedbrake</object-name>
        <object-name>Rudder</object-name>
        <object-name>NoseWellCover</object-name>
      </effect>
      ```

      Verifique se não existem outros efeitos sendo aplicados para o mesmo objeto pois no FlightGear cada objeto pode conter apenas um efeito. Novos efeitos adicionados no arquivo irão substituir o efeito antigo.

      Resultado:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut11.jpg?raw=true "Tut")

      Mas perceba que parece que a aeronave não tem livery, e é feita de lata. Para corrigir isso precisamos alterar algumas propriedades do efeito usando a ferramenta Property Browser. No meu caso elas ficam no node /sim/rendering/AT-29.

      - Altere o valor de fresnel-factor para 0
      - Altere o valor de refl-type para 2 ( 1 para normal, 2 para suporte ALS incluso)
      - Altere o valor de refl_correction para um valor em torno de -1 e 1. Dependendo do valor ele fica com mais reflexão ou menos. Ajuste do modo que preferir.

      Ficando assim:

      ![Tut](assets/img/comoaplicarreflexoerelevonafuselagem/tut12.jpg?raw=true "Tut")

      Mas ter que alterar esses valores toda vez nas propriedades não é bom, para corrigir isso vamos definir esses valores no arquivo -set de definição da aeronave. No meu caso Aircraft/AT-29/AT-29-set.xml

      Abra o arquivo e procure por 'rendering'.
      No meu caso encontrei:

      ```xml
      <rendering>
        <redout>
          <parameters>
            <blackout-onset-g>4.0</blackout-onset-g>
            <blackout-complete-g>8.0</blackout-complete-g>
          </parameters>
        </redout>
      </rendering>
      ```

      Basta então adicionar o node AT-29 (ou o nome de sua aeronave) com as propriedades do efeito.

      ```xml
       <rendering>
        <redout>
          <parameters>
            <blackout-onset-g>4.0</blackout-onset-g>
            <blackout-complete-g>8.0</blackout-complete-g>
          </parameters>
        </redout>
        <AT-29>
          <refl_correction>-0.5</refl_correction>
          <refl-type>2</refl-type>
          <fresnel-factor>0</fresnel-factor>
        </AT-29>
      </rendering>
      ```

      Os valores podem variar de aeronave para aeronave, portanto teste valores diferentes para saber o melhor para a sua aeronave.

### Seção: Sons

  - Nada aqui ainda.

### Seção: Modelagem

  - #### Como fazer modelos 3d para o FlightGear
    Ferramentas uteis:
    - [Baixar Sketchup](https://www.sketchup.com/pt-BR)
    - [Baixar Blender](https://www.blender.org/features/releases/2-77/)
    - [Baixar AC3D Portable Gratis](https://goo.gl/tN5HEC)
    - [Baixar Plugin Exportação/Importação .AC para Blender](https://github.com/NikolaiVChr/Blender-AC3D)

    Tutorial:
    - É necessário ter noções básicas de uso em cada um dos programas usados.
    - Pegar medidas do que for modelar.
    - Modelar principais partes ( sem detalhes )
    - Coloque a textura.
    - Arrume a posição da textura. Nunca rotacione a textura pelo sketchup... use um editor externo para isso.
    - Modele o resto e vá texturizando.
    - Exporte para .3ds ( com as opções da imagem abaixo )
    - Importe no Blender
    - Reduza a escala do modelo ( exportar em 3ds não mantém a escala do Sketchup... reduza para 0.1f como um começo, ajuste se precisar )
    - Cuidado, modelos AC não suportam 2 texturas na mesma face. Portanto de uma olhada e se precisar ajuste.
    - Exporte para .ac.
    - Importe no AC3D.
    - Mova o objeto para o centro. ( x = 0, y = deixe como está, z = 0 )
    - Salve o modelo. Isso fará com que o arquivo tenha um tamanho reduzido. ( A conversão para .ac pelo blender não é muito otimizada )

    ![Tut](assets/img/comofazermodelos3dparaoflightgear/tut01.jpg?raw=true "Tut")

### Seção: Texturização

  - #### Como fazer texturas noturnas para modelos 3d
    Ferramentas uteis:
    - [PaintNet - Windows](https://www.getpaint.net/download.html)
    - [PaintNet 300+ Plugins](http://paint.net.amihotornot.com.au/Download/PluginsPack/AttilaPro/) ou [PaintNet 300+ Plugins#2](assets/downloads/PaintNet300Plugins.zip)

    Tutorial:
    - É necessário ter noções básicas de uso em cada um dos programas usados.
    - Abra a textura no paint.net
    - Duplique a camada (para backup) e desabilite uma.
    - Vá em Ajustes > Color Mixer. Selecione Brightness e coloque um valor geral de -95 ou o quanto preferir.
    - Crie uma nova camada, sete o tipo para Subexposição de Cor.
    - Selecione o Pincel, em dureza coloque 1, e em tamanho coloque o valor que quiser. Escolha uma cor e pinte as luzes. Separe cada cor de luz em uma nova camada.
    - Por fim junte todas as camadas (com cuidado para não bugar) e salve em PNG.

### Seção: Animação
  - #### Conhecendo os AXIS e suas relações
    - AC3D X é FGFS X
    - AC3D Y é FGFS Z
    - AC3D Z é FGFS -Y

    - Blender X é FGFS Z
    - Blender Y é FGFS X
    - Blender Z é FGFS Y

    - AC3D X é Blender X
    - AC3D Y é Blender Z
    - AC3D Z é Blender -Y

    - FGFS X é frente/tras (positivo é tras)
    - FGFS Y é direita/esquerda (positivo é direita)
    - FGFS Z é cima/baixo (positivo é cima)

    - Na simulação CFD da mesh voce inverte o eixo Z, voce precisa fazer o mesmo com JSBsim
