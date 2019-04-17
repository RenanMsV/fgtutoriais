## Bem vindo ao índice de tutoriais do simulador de voo FlightGear.

#### Índice:
  - ##### [Cenário](#seção-cenário)
    - [Como colocar objetos no cenário](#como-colocar-objetos-no-cenário)
	- [Como criar ou editar aeroportos](#como-criar-ou-editar-aeroportos)
  - ##### [Aeronave](#seção-aeronave)
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

### Seção: Aeronave

  - ####

### Seção: Sons

  - Nada aqui ainda.

### Seção: Modelagem

  - #### Como fazer modelos 3d para o FlightGear

### Seção: Texturização

  - #### Como fazer texturas noturnas para modelos 3d
  	Ferramentas uteis:
	- [PaintNet - Windows](https://www.getpaint.net/download.html)
	- [PaintNet 300+ Plugins](http://paint.net.amihotornot.com.au/Download/PluginsPack/AttilaPro/)

	- É necessário ter noções basicas de uso em cada um dos programas usados.
	- Abra a textura no paint.net
	- Duplique a camada (para backup) e desabilite uma.
	- Vá em Ajustes > Color Mixer. Selecione Brightness e coloque um valor geral de -95 ou o quanto preferir.
	- Crie uma nova camada, sete o tipo para Subexposição de Cor.
	- Selecione o Pincel, em dureza coloque 1, e em tamanho coloque o valor que quiser. Escolha uma cor e pinte as luzes. Separe cada cor de luz em uma nova camada.
	- Por fim junte todas as camadas (com cuidado para não bugar) e salve em PNG.
