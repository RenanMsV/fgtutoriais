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
    - [Como colocar efeito reflexivo na fuselagem](#como-colocar-efeito-reflexivo-na-fuselagem)
  - ##### [Sons](#seção-sons)
  - ##### [Modelagem](#seção-modelagem)
    - [Como fazer modelos 3d para o FlightGear](#como-fazer-modelos-3d-para-o-flightgear)
  - ##### [Texturização](#seção-texturização)
    - [Como fazer texturas noturnas para modelos 3d](#como-fazer-texturas-noturnas-para-modelos-3d)

### Seção: Cenário

  - #### Como colocar objetos no cenário
    1 - Como são editados os cenários:
    Cenários são editados com o avião UFO, por meio de modelos 3D ( que são qualquer tipo de predio, estrutura, aéronave ) que vemos nos cenários e arquivos .stg.

    2 - O que é um arquivo .stg:
    Arquivos .stg contém informações que o simulador utiliza para colocar cada modelo em sua posição correta durante o carregamento de cenário. São arquivos de texto que dizem qual é o modelo 3D que deverá ser colocado no cenário, a posição que deverá ser colocado e sua rotação.

    3 - Como conseguir modelos 3D para meus cenários:
    O FlightGear já contém varios modelos 3D para cenários e você poderá usá-los. Mas também poderá criar seus proprios com um programa de modelagem 3D. AC3D é o programa padrão, mas muitos usuários preferem utilizar o Blender com plugin para modelar e exportar arquivos em formato .ac ( formato que o FlightGear utiliza em seus modelos ). Após terminado e exportado crie uma pasta em data/Models/NomeQueVcQuer e coloque seu modelo 3D nela. Coloque um nome unico, pois outras pessoas podem colocar o mesmo nome e entrar em conflito.

    4 - Usando UFO para editar o cenário:
    Vamos começar abrindo a launcher, selecionando o avião "UFO" e escolhendo o seu aeroporto que quer editar como ponto de partida.

    ![Tut](img/comocolocarobjetosnocenario/tut01.jpg?raw=true "Tut")

    Ele irá se mover como um avião normal, portanto aumente o throttle e se mova pelo cenário. Escolha uma posição boa.

    ![Tut](img/comocolocarobjetosnocenario/tut02.jpg?raw=true "Tut")

    De um clique com o botão esquerdo do mouse no local em que quer colocar um modelo. Perceba que irá aparecer um modelo padrão no local. Então aperte CTRL + Page UP para subir, e CTRL + Page Down para descer na lista de modelos. Vá clicando até encontrar algum que queira. Vou colocar uma aéronave.

    ![Tut](img/comocolocarobjetosnocenario/tut03.jpg?raw=true "Tut")

    Mas perceba que a aéronave está dentro do chão. Para mudar isto vamos apertar o botão "=" (igual) para abrir o menu de posicionamento e rotação dos modelos. Agora para termos certeza que vamos rotacionar e mover apenas o modelo que queremos temos que seleciona-lo. Aperte CTRL + Clique em cima do modelo. Se o modelo ficou piscando ele está selecionado com sucesso. Se ele não piscou mas outro modelo piscou tente denovo clicando em outro local do modelo. Com o modelo selecionado mova os controles no menu de posicionamento e rotação dos modelos e ele irá se mover e rotacionar. No meu caso vou usar o controle de altitude para move-lo para cima.

    ![Tut](img/comocolocarobjetosnocenario/tut04.jpg?raw=true "Tut")

    Para mover um objeto de lugar você também pode seleciona-lo e com ALT+Botão Esquerdo em cima do novo local onde quer coloca-lo.
    Para deletar um modelo selecione-o e clique em Backspace.

    Para colocar um novo modelo repita o processo, clique botão esquerdo no local em que quer colocar o novo modelo e vá apertando CTRL+PageUp para ir trocando até encontrar o que quer. Selecione este modelo com CTRL+Botão Esquerdo no modelo que quer selecionar e rotacione-o usando o menu de posicionamento e rotação que é aberto com o botão "=".
    A quantidade de opções de modelos que você terá para escolher irá depender de quantos modelos você tem instalado na pasta data/Models.

    Ao fim de todo seu trabalho aperte a tecla E para que seja salvo. Se o E não for apertado e você sair do simulador perderá tudo que fez.

    5 - Transformando sua edição em um arquivo .stg

    Tenha certeza que apertou a tecla E e feche o simulador. já com o simulador fechado aperte a tecla Windows+R. Digite %appdata% e clique em OK. Irá aparecer uma pasta cheia de pastas. Procure pela chamada flightgear.org e abra. Agora abra a pasta Export. Abra o arquivo "ufo-model-export.xml" que está la dentro. Ou vá direto a este diretorio : C:\Users\Usuario\AppData\Roaming\flightgear.org\Export\.
    O arquivo aberto conterá mais ou menos esta estrutura:

    ![Tut](img/comocolocarobjetosnocenario/tut05.jpg?raw=true "Tut")

    Tudo que utilizaremos é a localização do cenário que fica em stg-path e a linha de configuração do objeto que fica em object line.
    No nosso caso a localização é : "w050s30/w048s23/2166987.stg".
    Então criaremos um arquivo chamado "2166987.stg" em um editor de texto como notepad.
    No nosso caso a linha de configuração do objeto é: "OBJECT_SHARED Models/737-800.ac -47.10759645 -22.86117749 612.9396 0.0 0.0 -0.0".
    Isto significa que iremos colocar o objeto que fica em "Models/737-800.ac" nas posicoes "-47.10759645 -22.86117749 612.9396" e nas rotações "0.0 0.0 -0.0".
    Dentro do arquivo que criamos vamos então escrever essa linha, dar enter e escrever as proximas (caso voce tenha colocado varios objetos.)
    Um exemplo:

    ![Tut](img/comocolocarobjetosnocenario/tut06.jpg?raw=true "Tut")

    Salve o arquivo e coloque o no diretorio data\Scenery\Objects\w050s30\w048s23. Pois ali em cima diz que o diretorio é "w050s30/w048s23/2166987.stg". Então cada aeroporto que for editar terá um arquivo que deve ser colocado em um local diferente. Confira sempre o arquivo "ufo-model-export.xml".

    Pronto suas modificações já podem ser vistas ao entrar no jogo.

    ![Tut](img/comocolocarobjetosnocenario/tut07.jpg?raw=true "Tut")

    6 - Compartilhando seu trabalho com outras pessoas
    Para compartilhar seus trabalhos com outras pessoas você precisa passar pra elas o arquivo .stg e os modelos 3D que usou. Elas devem instalar os modelos na pasta data/Models dela e o arquivo .stg corretamente no diretorio correto. Por isso crie uma pasta e coloque o primeiro nome. ex "w050s30" e dentro outra pasta com o segundo nome. ex "w048s23" e dentro o arquivo .stg. Zipe tudo com um programa de compactação de arquivos e ficará facil para o outro instalar, já que a estrutura das pastas já foi feita por voce com o nome correto. Não esqueça de zipar junto os modelos que você usou.

  - #### Como criar ou editar aeroportos

    - ##### Primeiros passos
      FlightGear utiliza o mesmo sistema de arquivos de cenário que o XPlane. Com poucas mudanças.
      Este tutorial vai te dar uma ideia de como criar cenários, aeroportos para o FlightGear.

      O que você aprenderá aqui:

      Criar pistas, taxiways, patios.
      Criar posições de estacionamentos.

        Requisitos:
        Necessário +- 40GB de espaço em disco.
        Tutorial para Windows apenas.

      ======= Programas necessários: ========

      Download Completo : Arquivo zipado com todas ferramentas necessárias. Estão desatualizadas. Use-as caso as oficiais atualizadas não funcionem mais.
      Para baixar : EM BREVE

      Python 3 - Python 3 (nao Python 2) é necessário para rodar scripts .py.
      Para baixar : [https://www.python.org/downloads](https://www.python.org/downloads/)

      Java - Necessario para rodar programas em java. > ou MINECRAFT <
      Para baixar : [https://www.java.com/pt_BR/download/manual.jsp](https://www.java.com/pt_BR/download/manual.jsp)

      WED - World Editor : Ferramenta para Xplane e FlightGear que cria o layout de aeroportos. Taxiways, Pistas, Patios, Estacionamentos, etc são feitos por ele.
      Para baixar: [https://developer.x-plane.com/tools/worldeditor/](https://developer.x-plane.com/tools/worldeditor/) ou (provavelmente desatualizado) use o que veio no download completo.

      QGIS - Programa para edição e visualização de arquivos de Landclasses.
      Para baixar: [https://qgis.org/en/site/](https://qgis.org/en/site/)

      Airport Web Generator - É Opcional, um site permite que você compile seu aeroporto para teste. TESTE apenas, já que somente o aeroporto será gerado,
      E não as áreas próximas. Apenas abra o site e envie o arquivo .dat do aeroporto gerado pelo WED.
      Para acessar: [http://ns334561.ip-5-196-65.eu/tgweb/](http://ns334561.ip-5-196-65.eu/tgweb/)

      WedoMaker : É opcional, mas bastante recomendado. Permite usar fotos de satélite para auxiliar no posicionamento e tamanho correto do layout do aeroporto.
      Para baixar: [https://wedomaker.wordpress.com/](https://wedomaker.wordpress.com/) ou (provavelmente desatualizado) use o que veio no download completo.

      Dat2Gnet : Script .py que converte as posicoes de estacionamento das aeronaves de ICAO.dat para ICAO.groundnet.xml (utilizado pelo FlightGear).
      Para baixar: Vem no download completo.

      TerraGear : Ferramenta que gera os arquivos de cenário para o FlightGear.
      Para baixar : Vem no download completo.

      SRTM 3 :
      Arquivos de Altitude Global, permitem que o cenário contenha os relevos reais. Mais facil pois vem em tiles abrangendo áreas (Recomendado para quem está começando)
      Para baixar : É preciso saber exatamente a localidade do aeroporto requerido e baixar daqui o arquivo de relevo : [http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm](http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm)

      Outra fonte dos mesmos arquivos, porém nesse não vem em tiles, ele vem separado.
      Para baixar : É preciso saber exatamente a localidade do aeroporto requerido e baixar daqui o arquivo de relevo : [http://www.webgis.com/srtm3.html](http://www.webgis.com/srtm3.html)
      Clique no continente correto, ex: america do sul, e baixe o arquivo de acordo com a localizacao do aeroporto ex: S20W50.hgt.zip

      Outra fonte só que para QGIS - Resolução muito boa, pode ser aberto no programa QGIS.
      Para baixar : É preciso saber exatamente a localidade do aeroporto requerido e baixar daqui o arquivo de relevo : [http://srtm.csi.cgiar.org/SELECTION/inputCoord.asp](http://srtm.csi.cgiar.org/SELECTION/inputCoord.asp)

      Landclasses :

      Basicamente são arquivos que vão dizer quais texturas cada parte do cenário irá conter. Caso você saiba como fazer esses arquivos é possivel criar
      cenários com varias texturas diferentes e deixa-lo mais bonito a custo de mais processamento. Logo quando mais complexo e bonito o cenário mais pesado ele será.

      Globais - FlightGear TerraGit
      Você pode criar seu cenário só com alguns requeridos. v0_landmass (terreno), v0_lake (rios, lagos), v0_urban (cidades).
      Para baixar : [https://github.com/FGMEMBERS-TERRAGIT?utf8=%E2%9C%93&q=V0&type=&language=](https://github.com/FGMEMBERS-TERRAGIT?utf8=%E2%9C%93&q=V0&type=&language=) e baixe todos.

      Área - Basicamente o mesmo que o global mas apenas em uma área especifica. Diminue o tempo que demora para codificar e o espaço utilizado no HD.
      Não recomendado para quem está começando.
      Para baixar : [http://mapserver.mgras.net/shpdl/](http://mapserver.mgras.net/shpdl/)

      IBGE - Landclasses liberadas pelo Instituto Brasileiro de Geografia e Estatística (IBGE) e lógicamente só abrange áreas brasileiras.
      Para baixar : [ftp://geoftp.ibge.gov.br/cartas_e_mapas/bases_cartograficas_continuas/](ftp://geoftp.ibge.gov.br/cartas_e_mapas/bases_cartograficas_continuas/)

      Open Street Maps - Shapefiles Wiki. Contém vários sites para download de Landclasses.
      Para baixar : [https://wiki.openstreetmap.org/wiki/Shapefiles](https://wiki.openstreetmap.org/wiki/Shapefiles)

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

      BBox Finder - Muito util para encontrar coordenadas de uma área (min lat, max lat, min lon, max lon)
      Para baixar : [http://bboxfinder.com/](http://bboxfinder.com/)

    - ##### WED - WorldEditor
      Pessoas fazem aeroportos para Xplane ou Flightgear todos os dias, portanto provavelmente alguem já trabalhou no mesmo aeroporto que você quer fazer.
      Confira em [https://gateway.x-plane.com/airports/page](https://gateway.x-plane.com/airports/page) todos aeroportos já feitos. (não necessário).

      Caso esteja abrindo o programa pela primeira vez:
      Abra o WED, clique em Choose X-Plane Folder e selecione a pasta em que extraiu o WED.

      Criando o projeto:
      Abra o WED, clique em New Scenery Package, será criado um package chamado Untitled, clique nele e renomeie para o que quiser. Exemplo ICAO - Nome do aeroporto.

      Depois com ele selecionado clique em Open Scenery Package. Após aberto, clique em File > Import From Airport Scenery Gateway, aguarde carregar
      Vai aparecer uma lista com todos aeroportos já feitos, digite o ICAO do aerporto desejado, selecione-o na lista e clique em next (necessário conexao com internet).

      Vai aparecer uma lista com todas versões ja feitas desse aeroporto, escolha a em que está escrito Recommended. Selecione-a e clique em Import Pack (s).
      Caso de um erro "Illegal version line 2 .... " clique em ok e faça o seguinte procedimento: Feche o WED.

      Vá na pasta em que instalou o Wed, abra a pasta Custom Scenery, abra a pasta do projeto que criou (tem o nome que colocou no WED), abra o arquivo dat (ex: ICAO.dat) que está dentro dessa pasta no bloco de notas, procure onde está escrito:

          1100 Generated by WorldEditor  ...

      (pode estar 1000, 1100, 1150) e troque para:

          1050 Generated by WorldEditor  ...

      Abra o WED, dessa vez já selecione o projeto criado anteriormente e clique em Open Scenery Package, clique em File > Import apt.dat e selecione o arquivo dat que você editou.

      Selecione o aeroporto correto na lista que irá aparecer e clique em import. Pronto o aeroporto já deve ter aparecido para você.
      Agora você pode colocar a imagem de satélite.

      Para colocar imagem de satélite (opcional, recomendado):
      Clique em File > Save e feche o projeto no WED clicando em File > Close.

      Abra o WedoMaker. Aguarde-o iniciar. Ele irá abrir um site. Aperte SHIFT + F5 nesse site para prevenir possiveis erros.

      Copie o caminho do diretorio do WED ( ex : D:\Aviacao\WED ) e cole ao lado de onde está escrito " <- enter a valid X-Plane home directory here".

      Se tudo deu certo irá aparecer 2 opções. Na primeira selecione o projeto que você criou no WED e na segunda configure a qualidade da imagem de satelite. Recomendo 19 (melhor custo beneficio). Após selecionado deve aparecer no mapa o aeroporto que você quer.

      De zoom o maximo que der mantendo o aeroporto todo na tela. Clique no botão Make Visible in WED, aguarde carregar.
      Quando finalizado pode fechar o site, e clicar em Quit no WedoMaker.
      Você também pode colocar textos na pista, numeros de gates pelo WedoMaker utilizando a opção Insert text and symbols.

      Volte para o WED e abra o projeto novamente. Se tudo deu certo a imagem de satelite apareceu para você dentro do WED.

      Agora no canto superior direito do WED temos a hierarquia de objetos. Procure a nomeada Overlays-WOM, ela guarda todas imagens baixadas e posicionadas no seu projeto.
      Sim, essa imagem de satelite é a junção de 200 ou mais fotos corretamente posionadas. Portanto arraste a nomeada Overlays-WOM para a world.
      Assim separando elas do seu aeroporto. Permitindo que mova o aeroporto todo livremente.

      Agora crie / edite o layout do aeroporto no WED (veja tutoriais no youtube : como criar aeroportos para o Xplane). Não se esqueça de adicionar as posições
      de estacionamento. Quanto mais, melhor.

      Corrigindo problemas de compatibilidade:
      Provavelmente o cenário baixado irá conter certos objetos que são usados pelo X-Plane, mas o FlightGear não aceitará. Portanto para remove-los você
      deve na hierarquia de objetos apagar qualquer grupo nomeado Facades, Exclusion Zones, Objects...

      Exportando o projeto:
      Ao fim, clique em File > Save, clique em File > Validate e o programa validará para ver se não encontrou problemas (corrija-os).

      Clique em File > Export Target e selecione XPlane 10.50.

      Selecione na hierarchia de objetos o aeroporto que você fez. Clique em File > Export apt.dat,  salve em algum lugar como ICAO.dat, ja pode fechar o WED.

    - ##### Dat2Gnet

      Copie o arquivo ICAO.dat exportado e cole na pasta em que colocou o Dat2Gnet.py, abra o arquivo executar.bat com o bloco de notas.
      Neste arquivo bat temos que configurar 3 coisas. A primeira é o nome do script python a rodar, portanto Dat2Gnet.py.
      A segunda coisa é o arquivo .dat do aeroporto, portanto ICAO.dat, e a terceira o ICAO deste aeroporto
      (utilizado bastante quando o arquivo .dat contém varios aeroportos. sim você pode fazer varios aeroportos no no mesmo projeto do WED),
      portanto ICAO. EX: Faz de conta que estamos fazendo o aeroporto de São Paulo, então ficaria:

          Dat2Gnet.py SBGR.dat SBGR

      Após editado o arquivo bat, salve, feche e abra-o. Uma nova pasta deve ter aparecido com o as posições de estacionamento devidamente convertidas.
      Existem 2 maneiras de instalar posições de estacionamento. Uma é copiando a pasta Airports gerada para a pasta FlightGear/Scenery/ ou utilizando o sistema
      de Cenários Customizados do FlightGear (recomendado e que será utilizado por aqui). Copie a pasta Airports gerada para uma pasta
      dentro de Documents/FlightGear/CustomScenery/ICAO.

    - ##### QGIS

      Primeiramente você deve se perguntar

      "O que o terreno em volta do aéroporto irá conter? Ruas? Rios? Florestas? Ou apenas deserto?"

      Para cada uma dessas coisas uma Landclass é requerida. Landclasses vão dizer ao TerraGear onde fica a cidade, onde fica florestas, onde ficam ruas,
      onde ficam lagos, rios, pantanos, desertos, etc... para que o cenário seja criado o mais fielmente a realidade possível.

      Um cenário com somente floresta fica bom, mas não muito realista(exceto se você estiver fazendo um aéroporto cercado somente por florestas, sem ruas ou clareiras).

      Vá no site onde se encontram os arquivos de LandClass e baixe todos que deseja usar.
      Para visualizar ou editar você precisará utilizar o QGIS.
      Para importar uma landclass no QGIS basta arrastar o arquivo zipado para dentro do programa (os arquivos .shp, .shx.. devem estar dentro do arquivo zipado (sem pastas)).
      Ou extraia em alguma pasta e arraste o arquivo .shp direto para dentro do QGIS.
      Para editar procure um tutorial especifico na internet.

    - ##### Terragear

      Abra a pasta TerraGear/bin/ e abra o arquivo EXECUTAR_TERRAGEAR_GUI.bat . O TerraGear GUI será executado.

      Na aba Start terá que colocar 3 diretorios para que o programa salve dados em seu computador.

      Em Project Directory selecione a pasta TerraGear/bin/APT

      Em TerraGear Root selecione a pasta TerraGear

      Em FlightGear Root selecione a pasta Data de seu FlightGear. Ex: "C://Games/FlightGear2017/Data/"

      Na aba Elevation é onde controlamos os arquivos de elevação.

      Em HTG Files Directory selecione a pasta TerraGear/APT/data/SRTM-3/
      Em Resolution deixe o valor 3. Min. Nodes deixe 50, Max. Nodes deixe 1000 e Max. Error deixe 40.

      Baixando e processando arquivos de elevação:

      Este processo é muito importante, sem ele o seu cenário não conterá dados de elevação. Ficando todo o terreno com altitude 0ft (em relação ao mar).

      Vá no site onde se encontram os arquivos SRTM-3 e baixe o arquivo correspondente a area do aeroporto. Ou baixe varios caso seja de interesse. (pq não todos ?)?

      Será baixado um (ou varios) arquivo .hgt.zip, coloque o na pasta TerraGear/APT/data/SRTM-3

      Baixe arquivos de elevação aqui: [http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm](http://www.viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org3.htm)

      Ou faça o procedimento manual abaixo ...

      Para baixar todos arquivos de elevação de um continente inteiro:
      Abra a pasta WGet e abra o arquivo cmd.exe. Digite então:

          wget -r -l inf [link contendo os arquivos de elevação]

      Por exemplo:

          wget -r -l inf https://dds.cr.usgs.gov/srtm/version2_1/SRTM3/South_America/

      E tecle ENTER. Pronto o programa já deve ter começado a baixar. Agora só esperar algumas horas / DIAS.

      Por fim, copie todos arquivos zip baixados para a pasta TerraGear/APT/data/SRTM-3

      Dentro do TerraGear GUI vá na aba Elevation e clique em Convert Elevation Data e aguarde o programa converter(quanto mais arquivos .hgt.zip estiverem na pasta mais vai demorar).

      Quando terminar (barra azul completa e escrito 100%) vá na pasta TerraGear/APT/data/SRTM-3 e mova todos arquivos .hgt.zip para a pasta TerraGear/APT/data/backup.

      Ou apague-os, você não irá precisar deles. Caso você não os mova ou apague na proxima conversão de algum arquivo eles serão convertidos novamente inutilmente, já que você já os converteu anteriormente.

      Baixando e processando arquivos de LandClass:
      Este processo é muito importante, sem ele seu cenário não terá terreno.
      Após baixar e conferir todas Landclasses que você irá utilizar extraia todas para a pasta TerraGear/APT/data/.

      Devem ficar várias pastas como v0_lake, v0_landmass, v0_urban... e dentro de cada varios arquivos ex: v0_urban.shx, v0_urban.shp, v0_urban.prj, v0_urban.dbf
      Agora vá no TerraGearGUI e vá na aba Materials clique em Retrieve shapefiles e clique em Ok.

      Após ele irá mostrar uma tabela. A tabela contém o nome da shapefile, material, largura de linha (usado para ruas, estradas) e SQL.

      Você só precisa preencher a parte Material. Para isto clique na linha desejada por exemplo v0_landmass e logo abaixo no lado direito terá um dropbox e um simbolo de '+' do lado. Escolha no dropbox o nome do material no nosso caso o v0_landmass é sempre 'Default'. E clique no botão '+'. Ou apenas digite 'Default' na célula Material.

      Faça com todos, colocando os nomes corretos do material. Por exemplo, em v0_lake iremos utilizar o material 'Lake', em v0_urban iremos utilizar o material 'Urban'...

      É questão de logica. Mas nada impede de você utilizar o material 'Grass' no v0_urban porém todas as cidades irão ter uma textura de grama.

      Logo após preencher todos corretamente clique no botão escrito 'Decode Shapefiles and Apply Material'.

      Este processo levará horas ou minutos dependendo do poder de processamento do computador. Mas fique tranquilo isto só será necessário fazer a primeira vez.
      Como estes arquivos de LandClass disponibilizados pelo Terragit são globais e cobrem o mundo todo você só precisa decodificar uma vez. Exceto se você apagar os arquivos decodificados por algum motivo. Ai terá que refazer a decodificação.
      Caso você consiga encontrar arquivos de LandClass menores, cobrindo apenas a área do aéroporto em que você está trabalhando o processo de decodificação será muito mais rapido, sendo feito em poucos minutos ou segundos. Porém logicamente será necessário decodificar toda vez que estiver trabalhando em um novo aéroporto.

      Continuação em Breve......

    - ##### Finalizando

      Em breve...

### Seção: Aeronave

  - #### Como colocar efeito reflexivo na fuselagem

### Seção: Sons

  - Nada aqui ainda.

### Seção: Modelagem

  - #### Como fazer modelos 3d para o FlightGear
  Ferramentas uteis:
  - [Baixar Sketchup](https://www.sketchup.com/pt-BR)
  - [Baixar Blender](https://www.blender.org/features/releases/2-77/)
  - [Baixar AC3D Portable Gratis](https://goo.gl/tN5HEC)
  - [Baixar Plugin Exportação/Importação .AC para Blender](https://github.com/NikolaiVChr/Blender-AC3D)

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

  ![Tut](img/comofazermodelos3dparaoflightgear/tut01.jpg?raw=true "Tut")

### Seção: Texturização

  - #### Como fazer texturas noturnas para modelos 3d
  Ferramentas uteis:
  - [PaintNet - Windows](https://www.getpaint.net/download.html)
  - [PaintNet 300+ Plugins](http://paint.net.amihotornot.com.au/Download/PluginsPack/AttilaPro/) ou [PaintNet 300+ Plugins#2](downloads/PaintNet300Plugins.zip)

  - É necessário ter noções basicas de uso em cada um dos programas usados.
  - Abra a textura no paint.net
  - Duplique a camada (para backup) e desabilite uma.
  - Vá em Ajustes > Color Mixer. Selecione Brightness e coloque um valor geral de -95 ou o quanto preferir.
  - Crie uma nova camada, sete o tipo para Subexposição de Cor.
  - Selecione o Pincel, em dureza coloque 1, e em tamanho coloque o valor que quiser. Escolha uma cor e pinte as luzes. Separe cada cor de luz em uma nova camada.
  - Por fim junte todas as camadas (com cuidado para não bugar) e salve em PNG.
