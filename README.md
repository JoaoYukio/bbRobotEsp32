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
 O motor usado foi o [Nema17](https://www.curtocircuito.com.br/motor-de-passo-nema-17-4-8-kgf-cm-1-0a.html), que é um motor de passo unipolar usado geralmente em impressoras 3d e CNCs.
 
<p align="center">
  <img src="https://github.com/JoaoYukio/bbRobotEsp32/blob/main/nema17.jfif">

 O driver escolhido para tal motor foi o [DRV8825](https://www.curtocircuito.com.br/catalog/product/view/id/602/s/driver-motor-passo-drv8825/) como podemos ver a seguir esse driver precisa de apenas dois sinais de controle e alguns pinos de nível lógico para habilitar o driver.

<p align="center">
  <img src="https://github.com/JoaoYukio/bbRobotEsp32/blob/main/drv8825_pinout.jfif">
 
 # Alimentação
 Para alimentar o circuito foram usadas três baterias do tipo [18650](https://produto.mercadolivre.com.br/MLB-1180892186-bateria-18650-samsung-22p-original-2200mah-kit-4-_JM?matt_tool=87716990&matt_word=&matt_source=google&matt_campaign_id=12413740998&matt_ad_group_id=119070072438&matt_match_type=&matt_network=g&matt_device=c&matt_creative=500702333978&matt_keyword=&matt_ad_position=&matt_ad_type=pla&matt_merchant_id=286070357&matt_product_id=MLB1180892186&matt_product_partition_id=337120033364&matt_target_id=pla-337120033364&gclid=Cj0KCQjw6-SDBhCMARIsAGbI7UikUZ_6_U8vLhcKe0_e3_CLAEMUrqb8R12e0rYv31URLC03qVRrQAsaAkiAEALw_wcB) em série, tendo uma tensão máxima de 12,6V. E para o controle desse banco de baterias foi usada uma [BMS 3s](https://www.curtocircuito.com.br/catalog/product/view/id/1460/s/carregador-de-bateria-li-ion-protecao-bms-3s-10a/) .
  
<p align="center">
  <img src="https://github.com/JoaoYukio/bbRobotEsp32/blob/main/Baterias.jpg">
  
  # Esquemático
  Foi usado o seguinte [esquemático](https://blogdaichan.hatenablog.com/entry/%3Fp%3D7129) para a montagem do robô:
  <p align="center">
  <img src="https://github.com/JoaoYukio/bbRobotEsp32/blob/main/esquem%C3%A1tico.jpg" height ="600" width ="700">
