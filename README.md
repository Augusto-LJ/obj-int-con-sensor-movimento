# Descrição do projeto
Trata-se de um sistema inteligente de controle de iluminação, que utiliza o sensor de movimento PIR para detectar movimento em um ambiente.
O módulo de comunicação escolhido é a placa Arduino Uno, responsável pelo controle de toda a prototipagem. Ela é conectada pela porta USB serial com um notebook, que serve como intermediário através do protocolo Firmata e do Node-RED para estabelecer a conexão entre os componentes e o MQTT broker Mosquitto. Foi utilizada uma protoboard de 400 pontos para integrar o Arduino, o sensor e o atuador (Módulo Relé 5v).

Quando o sensor PIR detecta um movimento, ele transmite um sinal para o Arduino, que, por sua vez, transmite um sinal para o relé ativar uma lâmpada. A lâmpada fica acesa enquanto houver algum movimento sendo detectado ou após 7 segundos sem movimento. O tempo escolhido de 7 segundos foi parametrizado para que seja possível realizar testes com mais facilidade.

Toda a informação fica registrada no Mosquitto, sendo então possível ver um gráfico que informa os momentos (horas, minutos e segundos) em que houve movimentação em determinado ambiete, bem como o tempo que a lâmpada ficou acesa.

# Como executar o projeto
1. Instale o Arduino IDE;
2. Faça o upload do arquivo "code-StandardFirmata.ino" para o Arduino Uno. Desta maneira, a placa fica habilitada para a utilização do protocolo Firmata através do USB serial;
3. Instale o Node.js na versão LTS mais recente;
4. Instale o Node-RED;
5. Instale os pacotes adicionais serialport e node-red-node-arduino;
6. Importe o arquivo "code_node-red.json" para a instância do Node-RED que está sendo executada em sua máquina. Antes de implementá-la, verifique se as portas COM dos nodes do Arduino estão conforme as portas utilizadas em seu computador.
