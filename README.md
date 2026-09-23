# Solar_System
Sistema Solar com Processing - Etapa 2


O theta representa o ângulo que indica a posição do planeta ou da Lua durante a sua órbita. Ele é atualizado dentro do método update() através de theta += orbitspeed, 
fazendo com que sua posição mude a cada atualização.  O orbitspeed define quanto o theta vai mudar em cada atualização. Assim, quanto maior for esse valor, maior será a 
mudança do ângulo e mais rápido será o movimento do objeto na órbita.

Para os planetas, o valor fica entre 0.01 e 0.03, então o theta sempre aumenta. Por isso, os planetas se movimentam sempre no mesmo sentido. Já para as luas, 
o valor pode ficar entre -0.1 e 0.1. Se o valor for positivo, o theta aumenta e a Lua gira em um sentido. Se for negativo, o theta diminui e ela gira no sentido contrário.
A diferença entre os dois update() é que o da Lua apenas atualiza o seu próprio theta. Já o update() do planeta também chama moon.update(),
fazendo com que a Lua tenha seu movimento atualizado junto com o planeta.
