# minecraft-bedrock
Como criar um servidor de Minecraft Bedrock (Mobile e VideoGame) para chamar de seu

## Motivo
A criançada estava querendo jogar Minecraft no Mobile e no Video Game mas queriam ter um ambiente único
para se conectar a qualquer momento e continuar jogando a qualquer momento.
Se eles se adicionarem como amigos nas contas M$ ou estiverem na mesma rede, eles conseguem se ver e
interagir entre o mundo que um crie ou que o outro crie.
O problema aqui é que se algum depes quiser continuar o jogo mas estava conectado no mundo do outro player
ele vai ter que esperar o amiguinho logar e abrir aquele mundo para consegui se conectar e jogar.
A outra opção é um servidor pago, o que poderia ser rateado entre os jogadores, mas ai tem que interagir
com os pais, alguém tem que pagar, muita possibilidade de dor de cabeça.
A terceira opção é, vamos montar um servidor de Minecraft, nesse caso da versão Bedrock usando a AWS
para usar os recurso do free-tier e vamos ver como se comporta.

## Limitações
Claro que como não sendo um servidor da própria M$, temos algumas limitações.
1. a administração é um pouco mais chata
2. tudo é com você
3. a conexão com os Video Games é mais chata, mas no servidor comprado tb é um saco.
4. a limitação dos recursos da EC2, já que vai ser de graça.

## Ingredientes
Para esse ambiente vamos precisar:
1. Uma conta AWS;
2. uma maquina EC2 no free tier;
3. tempo até acertar as configurações
4. o PufferPanel
5. os celulares, video games e tables
6. um celular adroid sobrando
7. um domínio (opcional)

## Modo de Preparo
Em uma conta AWS vamos criar uma maquina EC2 usando o Ubuntu.
Não sabe criar a conta na AWS? vai pesquisar...
Com a maquina configurada vamos instalar o PufferPanel
siga o manual no site:
https://docs.pufferpanel.com/en/3.x/installing.html
Por que usar o PufferPanel? a resposta simples é porque temos mais coisa pra fazer do que ficar sentado administrando
esse servidor de Minecraft, a garotada vai querer ficar entrando e saindo de criativo, dropar item, alterar configuração
e na configuração padrão tudo é feito na console do servidor, você vai querer passar suas credenciais e liberar o SSH
para todos eles?
Com o PufferPanel, por mais que ele não resolva todos os problemas, pelo menos tem uma interface gráfica web que ajuda,
você cria uns usuários e senhas e passa pra eles baterem cabeça.
Com tudo instalado e configurado agora você precisa liberar algumas portas TCP e UDP para chegar na EC2, vai lá no security
group e libera essas portas apenas para a sua EC2.

Com tudo instalado e configurado, agora é a parte de configurar os dispositivos.
Nos Minecrafts dos celulares e tablets, vá em um novo jogo e depois na guia servidores, desça a lista e você terá a opção
de adicionar um novo servidor, preencha com um nome qualquer e o nome do seu servidor, ou IP, aqui é a opção do domínio
caso você tenha um domínio hospedado em algum lugar pode criar uma entrada CNAME para o nome do host EC2 gerado pela AWS
para ficar mais fácil da criançada conseguir configurar.

Para administrar o servidor, lembra de liberar a porta do PufferPanel.

Agora para os consoles, eles não tem a opção de adicionar o servidor personalizado, para isso vamos usar esse celular
android que você tem sobrando ai, vai na PlayStore e baixa o aplicativo MC Server ASDASD
entra com o endereço do seu servidor de Minecraft e clica em Start Server, espera a propaganda e ele vai se conectar
no seu servidor, basicamente ele funciona como um roteamento de um jogo local para o servidor remoto.
No XBox, PS ou Switch, vai em novo jogo e em amigos você vai ver um novo amigo na rede, que é esse app.
Quando você se conectar nele ele vai fazer o NAT para o servidor removo e pronto para jogar.
Só não fecha o app no android e seja feliz, por isso do celular sobrando, você vai ter que acabar conectando ele em uma tomada.
Infelizmente esse processo vai ter que ser feito por todos os amigos que vão jogar usando Video Game, em cada uma das redes deles.

para uma lista de comandos do que pode ser feito no Minecraft BedRock acesse:
https://minecraftbedrock-archive.fandom.com/wiki/Commands/List_of_Commands
