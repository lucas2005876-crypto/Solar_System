# Solar_System

NOMES: Lucas e Vinicius

Etapa 2

O theta representa o ângulo que indica a posição do planeta ou da Lua durante a sua órbita. Ele é atualizado dentro do método update() através de theta += orbitspeed, 
fazendo com que sua posição mude a cada atualização.  O orbitspeed define quanto o theta vai mudar em cada atualização. Assim, quanto maior for esse valor, maior será a 
mudança do ângulo e mais rápido será o movimento do objeto na órbita.

Para os planetas, o valor fica entre 0.01 e 0.03, então o theta sempre aumenta. Por isso, os planetas se movimentam sempre no mesmo sentido. Já para as luas, 
o valor pode ficar entre -0.1 e 0.1. Se o valor for positivo, o theta aumenta e a Lua gira em um sentido. Se for negativo, o theta diminui e ela gira no sentido contrário.
A diferença entre os dois update() é que o da Lua apenas atualiza o seu próprio theta. Já o update() do planeta também chama moon.update(),
fazendo com que a Lua tenha seu movimento atualizado junto com o planeta.

Etapa 4

Onde você aplicou pushMatrix()/popMatrix() e por quê?

Utilizamos pushMatrix() e popMatrix() no Sol, nos planetas e nas luas para isolar as transformações de cada objeto. Assim, as rotações e translações de um objeto não interferem nos outros.

O que mudaria se invertêssemos rotate() e translate() no planeta ou na lua?

No planeta, rotate(theta) antes de translate(distance, 0) faz o planeta orbitar ao redor do Sol. Se invertermos a ordem, o planeta seria deslocado primeiro e depois giraria em torno de sua própria posição, deixando de realizar a órbita corretamente. O mesmo acontece com a lua em relação ao planeta.

Como garantiu que cada órbita é independente das demais?

Cada planeta possui suas próprias características e suas próprias luas através da composição Planet → Moon. Além disso, cada objeto atualiza seu próprio theta e orbitspeed separadamente no método update(). O uso de matrizes aninhadas com pushMatrix() e popMatrix() também mantém as transformações de cada objeto isoladas.
