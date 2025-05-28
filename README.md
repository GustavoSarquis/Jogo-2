Descrição Geral: 
Você é um caçador de recompensas contratado pelo chefe de uma vila para recuperar um amuleto sagrado e um tesouro roubado por um monstro em uma masmorra perigosa. A jornada é dividida em mapas progressivos 
com desafios diferentes, NPCs interativos e obstáculos mortais. Seu objetivo é sobreviver, coletar os itens e voltar à vila em segurança. O jogo é composto por 4 mapas, sendo 3 fases de progressão, e uma vila, a qual começamos o jogo e terminamos. O jogador possuí 3 vidas, ao zerar as vidas, o usuário volta para o menu. No desenvolvimento do jogo foi utilizado 6 bibliotecas:
- <stdio.h>
- <stdlib.h>
- <time.h>
- <windows.h>
- <conio.h>
- <locale.h>

Menu: 
Para o desenvolvimento do menu foi utilizado switch case, assim oferecendo três opções:
1 – Jogar: Inicia o jogo a partir da vila e segue por 3 mapas até o retorno para a vila.
2 – Créditos: Exibe os nomes dos desenvolvedores.
3 – Sair: Encerra o jogo.

Mapas:
Acerca do desenvolvimento dos mapas, para as suas criações foram utilizadas matrizes, para a vila e para o mapa 1 10x10, para o mapa 2 matriz 20x20 e para o mapa 3 40x40 , dividindo os elementos do mapa por numeros da matriz, quando as variaveis da matriz forem iguais a :
1: Será uma parede, representada pelo caráter "*". 
2: Será um espinho que causa dano ao jogador, representado pelo caráter "#". 
3: Será a porta aberta, por onde o usuário pode passar para mudar de etapa, representada pelo caráter "=".
4: Será a porta fechada, que funciona como uma parede, representada pelo caráter "D".
5: Será o teletransportador, representado pelo caráter ">".
6: Será o botão especial, aperte para descobrir o que ele faz.
Além disso, em todos os mapas, tem uma chave que abre as portas, designado pelo caráter "@". Por fim, para interagir com alguns elementos, como NPCs e a chave, é preciso digitar a tecla "i".

Movimentação do usuário:
A movimentação do personagem é controlada pelo teclado, usando as teclas WASD, as quais "w" vai pra cima, "a" para esquerda, "s" para baixo e "d" para direita, A movimentação é implementada com a função getch() combinada com kbhit() para verificar se alguma tecla foi pressionada, evitando que o jogo trave esperando entrada do usuário. Outrossim, a movimentação é conectada com as matrizes dos mapas, logo a movimentação em cima de paredes e portas fechadas é bloqueada. As variáveis CPX (posição horizontal) e CPY (posição vertical) representam a posição atual do jogador. Quando o jogador se move, essas variáveis são atualizadas:
- CPY++ → move para baixo.
- CPY-- → move para cima.
- CPX++ → move para a direita.
- CPX-- → move para a esquerda.

Movimentação dos inimigos:
-Inimigo que se move aleatoreamente(X): Foi utilizado a função rand, a qual, a cada ciclo, é esccolhido um numero de 0 a 3 de forma aleatória. Com isso é designado a movimentação do inimigo da seguinte forma:
0 → Se move para cima 
1 → Se move para baixo
2 → Se move para esquerda
3 → Se move para direita
Além disso, ao jogaador dividir a coordenada com o monstro, é descontado um ponto de vida do usuário.

-Inimigo que persegue o jogador(Y): A cada 2 ciclos de jogo, ele calcula a direção mais próxima para alcançar o jogador, sendo dx a distância horizontal e dy a distância vertical. Se dx for maior que dy, ele se movimenta logo no eixo x e as mesmas limitações do mapa para o jogaador, como paredes e portas, servem para ele, caso o dy seja maior, ocorre a mesma coisa só que com o eixo y. Além disso, assim como o outro inimigo, ao jogaador dividir a coordenada com o monstro, é descontado um ponto de vida do usuário.

1 Fase do RPG (Vila):
O momento inicial do jogo é o jogador chegando na vila, nessa primeira fase o usuário conversa com os dois NPCs, os quais são designados pelo caráter "P", o primeiro NPC introduz o enredo, já o segundo que é o chefe, dá os 
detalhes da missão e o objetivo do joagador, após falar com os NPCs, o usuário vai até a chave, designada pelo caráter "@", o qual desbloqueia a passagem que antes estava fechada, após o jogador atravessar a porta, ele entra na masmorra e avança para a próxima fase.

2 Fase do Rpg (Mapa 1):
O objetivo do mapa é atravessar o labirinto, evitar os espinhos (#) e pegar a chave (@), para abri as portas, caso o usuário toque nos espinhos um ponto de vida é descontado, ao zerar o jogador perde. Nessa fase, já existe a presença de um teletransporte, o mapa possuí um tamnho de 10x10.

3 Fase do Rpg (Mapa 2):
O objetivo do mapa é fugir de um inimigo que se move aleatoriamente (X) e alcançar a chave, o mapa também apresenta  espinhos e teletransporte. Além disso, a fase possuí um botão "O" que tem uma função especial que aparecem mais espinhos no mapa, o tamanho do mapa é 20x20. 

4 Fase do Rpg (Mapa 3):
Esta é a última fase da masmorra, onde está localizado o objetivo pricipal do jogador. A fim de zerar o jogo, o jogador precisa interagir com a chave, que nesta fase está junto com o tesouro e com o amuleto, assim pegando o objetivo e abrindo a porta para fugir do perigo. Ao mesmo tempo, nesta fase o mapa possui um tamanho de 40x40, alén de possuir espinhos, um inimigo que se move aleatoriamente, o teletransporte e o chefão final, que perssegue o usuário a todo momento. 

5 Fase (Vila):
Após  concluir a missão, o jogador volta praa vila e conversa com um simples aldeão e com o chefe da vila, o qual o parabeniza e pega o amuleto de volta. Após as interações, o  jogador finaliza o  jogo e aparece uma menssagem final.
