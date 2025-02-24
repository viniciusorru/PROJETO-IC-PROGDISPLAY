README - Sistema de Cultura Automática


~Visão Geral:

Este código implementa um sistema de cultura automática utilizando um display LCD e duas bombas controladas por um Arduino. O sistema permite automatizar o processo de renovação do meio de cultura em ciclos programados.


~Hardware Necessário:

-Arduino

-Display LCD (16x2) com interface LiquidCrystal

-Dois botões (Start e Stop)

-Duas bombas controladas por relés

-Fios de conexão


~Funcionamento:

-Inicialização:

O sistema aguarda que o botão de start seja pressionado.

Exibe mensagens no LCD para orientar o usuário.

-Cultura Automática:

O sistema inicia uma contagem regressiva para renovação do meio de cultura.

Após a contagem, a bomba de extração remove o meio antigo.

A bomba de reposição adiciona o meio novo.

O processo se repete por um número determinado de ciclos.

-Parada Manual:

O botão Stop pode ser pressionado a qualquer momento para interromper o processo.


~Parâmetros Importantes

-Tempo de Contagem:

O tempo entre cada renovação do meio de cultura é definido no início do código:

unsigned long totalSeconds = 12L*60L*60L; // 12 horas em segundos

Se for necessário alterar o intervalo entre as renovações, modifique este valor. Por exemplo, para um intervalo de 6 horas, use:

unsigned long totalSeconds = 6L*60L*60L;

Tempo no Loop da Cultura Automática

Dentro da função Culturautomatica(), o tempo de renovação também é redefinido após cada ciclo:

totalSeconds = 12L*60L*60L;

Se alterar o valor no início, lembre-se de modificar também essa linha para garantir a consistência do intervalo entre as renovações.


-Ciclos de Renovação:

O sistema executa 5 ciclos antes de finalizar automaticamente. Esse número pode ser modificado alterando a condição no loop:

while (ciclo < 5) {

Se desejar aumentar ou diminuir o número de ciclos, basta ajustar esse valor.

Considerações Finais

Certifique-se de que os botões e bombas estejam corretamente conectados aos pinos especificados no código.

Antes de iniciar, verifique se os tempos configurados estão adequados para seu experimento.

O botão Stop permite interromper o processo a qualquer momento.

O sistema exibe mensagens no LCD para indicar o status da cultura.

