# bbRobotEsp32
Um robô do tipo "self-balancing" que usa um algoritmo PID e um sensor MPU6050 para controlar a sua inclinação, todas as peças não eletrônicas foram impressas numa impressora 3d, exceto os parafusos.
# Créditos
Esse robô foi criado com base nos STLs do B-robot EVO2 da JJRobots: [STLs B-robot](https://www.thingiverse.com/thing:2306541) .

O código original usava uma placa com dois microcontroladores, o esp12-e para comunicação por Wi-Fi e um ATSAMD21G18, usado no Arduino Zero. O código usado é uma adaptação para o ESP32, em que os timers para o driver do motor foram adaptados, e a comunicação, processamento e controle foram fundidos em apenas um microcontrolador: [Código para o ESP32](https://github.com/ghmartin77/B-ROBOT_EVO2_ESP32).

O [site](https://www.jjrobots.com/much-more-than-a-self-balancing-robot/) com informações sobre o robô, controle e desenvolvimento é bem útil para entender os princípios e o funcionamento do robô. 

# Sensor ângulo
O sensor usado foi o MPU6050, que combina um acelerômetro e um giroscópio, combinando os dados num filtro complementar conseguimos eliminar a sensibilidade do acelerômetro e o erro no tempo do giroscópio.

<p align="center">
  <img src="https://github.com/JoaoYukio/bbRobotEsp32/blob/main/Mpu6050.jfif">
  
 # Motores e drivers
 O motor usado foi o Nema17, que é um motor de passo unipolar usado geralmente em impressoras 3d e CNCs.
 

