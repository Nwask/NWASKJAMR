
  <img src="https://r2.e-z.host/555d8d65-caa2-47a0-afde-f9df96f35733/s2yt089a.png" alt="NWASKJAMR">
  <h3 align="center">Jamming é ILEGAL! Apenas para fins educacionais!</h3>
</div>


<h4 align="center">
  <a href="#pinagem-e-conexões">Esquemático</a>
    <span> | </span>
  <a href="#pcb">Layout do hardware</a>
    <span> | </span>
  <a href="#canais-de-operação">Canais</a>
    <span> | </span>
  <a href="#gravando-o-firmware">Firmware</a>
    <span> | </span>
  <a href="#apoie-me">Apoie-me</a>
</h4>


## NWASKJAMR
O NWASKJAMR (Jammer de Bluetooth, BLE, WiFi e RC) interrompe vários dispositivos usando um ESP32 e módulos nRF24, causando muito ruído e enviando pacotes desnecessários (DoS).

Ele interfere em:  
**Toda a banda larga de 2.4GHz!** Tudo que funciona em 2.4GHz está sendo interferido, como:
áudio em alto-falantes sendo transmitido via bluetooth, microfones em 2.4GHz, conexões de smartphones, WiFi, Drones RC, dispositivos IoT, gadgets inteligentes, teclado e mouse sem fio, qualquer coisa em 2.4GHz!

Ideal para interrupção controlada e testes de segurança. Baseado em comunicação 2.4GHz.

Possui um grande alcance (mais de 50 metros+ - pode variar dependendo da sua antena e configuração de hardware!) nas versões mais recentes de Bluetooth com antenas 2.4GHz casuais, você pode facilmente aumentar isso também pegando algumas antenas de roteador "maiores" simples.
Um amplificador (2.4GHz) pode ser uma boa opção também!

Lembre-se que jamming é ilegal e não deve ser usado com intenção maliciosa!


## Vídeos e demonstrações (creditos nos videos :) )
[Demonstração completa](link-para-demo-1)

[Demonstração completa (se o link anterior não estiver disponível)](link-alternativo-demo-1)

---

[Demonstração de alcance](link-para-demo-2)

[Demonstração de alcance (se o link anterior não estiver disponível)](link-alternativo-demo-2)

---

[Processo de gravação do firmware](link-para-flashing)

[Processo de gravação (se o link anterior não estiver disponível)](link-alternativo-flashing)

---


## Canais de operação
- **Bluetooth** = 79CH  
  Faixa de frequência: 2.402 GHz a 2.480 GHz  
  Largura do canal: 1 MHz

- **BLE** = 40CH  
  Faixa de frequência: 2.400 GHz a 2.4835 GHz  
  Largura do canal: 2 MHz

- **WiFi** = 14CH  
  Faixa de frequência: 2.400 GHz a 2.4835 GHz  
  Largura do canal: Tipicamente 20 MHz, mas pode ser 22 MHz ou 40 MHz em alguns casos

- **Drones RC, etc.** = 1-125CH  
  Faixa de frequência: 2.400 GHz a 2.525 GHz  
  Largura do canal: 1 MHz


## Como usar?
Para interromper vários canais na banda 2.4GHz, faça o seguinte para ativar seu NWASKJAMR:
- Cada modo inicia imediatamente após ligar o dispositivo! Não há botão adicional para iniciar o ataque!
- Ele simplesmente interfere imediatamente após ser ligado!

### Firmware Combo-Channel-Select_BT-BLE-WiFi-RC:
- use o botão "Boot" no ESP32 para alternar entre os modos de canal no Firmware Combo!
- o OLED exibirá seu canal de operação atual
- o LED de status informa sobre o estado atual em que você está:  
1 piscada = BT  
2 piscadas = BLE  
3 piscadas = WiFi  
4 piscadas = RC  
- a saída serial do seu NWASKJAMR exibirá as seguintes linhas ao trocar de modo:  
Estado 1: Bluetooth  
Estado 2: Bluetooth Low Energy  
Estado 3: WiFi  
Estado 4: RC  

### todos os outros firmwares:
- o firmware que você escolher indica o canal de operação pelo seu nome, isso significa:

Bluetooth_80_CH - interfere em Bluetooth clássico  
Faixa de frequência: 2.402 GHz a 2.480 GHz  

BluetoothLowEnergy_40_CH - interfere em Bluetooth Low Energy  
Faixa de frequência: 2.400 GHz a 2.4835 GHz  

Bluetooth-BluetoothLowEnergy_40-80_CH - interfere em Bluetooth clássico & Bluetooth Low Energy  
Faixa de frequência: 2.402 GHz a 2.480 GHz & 2.400 GHz a 2.4835 GHz  

Bluetooth-WiFi_14-80_CH - interfere em Bluetooth clássico & WiFi  
Faixa de frequência: 2.402 GHz a 2.480 GHz & 2.400 GHz a 2.4835 GHz  

WiFi_14_CH - interfere em WiFi  
Faixa de frequência: 2.400 GHz a 2.4835 GHz  

2.4GHzRemoteControl(Drones etc.)_1-125_CH - interfere em RC (Drones etc.)  
Faixa de frequência: 2.400 GHz a 2.525 GHz  

### (Mudancas Futuras) Para aparafusar o case impresso em 3D você deve ter:

- **Parafusos M3x16** (2x)  
- **Porcas M3** (2x)  
Pegue este kit M3 em vez disso:
- **[Kit de parafusos e porcas M3](https://s.click.aliexpress.com/e/_oC24YXH)**


## Antenas
Uma pergunta frequente é se as antenas são necessárias e para que serve a terceira antena, aqui está a resposta:
Sim, você precisa de pelo menos ambas as antenas para os nRF24's! Por quê? Para ter funcionamento em um alcance decente!
O alcance médio com antenas 2.4GHz chinesas padrão conhecidas é de cerca de 20-30 metros. Fazer upgrade dessas antenas ajudará muito a obter mais alcance!

2 antenas são para os módulos nRF24 HSPI e VSPI!

A 3ª antena é conectada ao chip ESP32 em si, via IPEX.
Para que serve a 3ª antena? A terceira antena conectada ao chip ESP32 em si ajuda com interferência confiável de longo alcance. Ela garante um melhor sinal intermediário e estabilidade ao interferir!


## Gravando o firmware
### via webflasher (Fácil) 
Use um webflasher para tornar super fácil para você gravar seu chip ESP32 com o firmware de sua escolha!  
- Visite [Flasher](https://esp32-bluejammerflasher.pages.dev) ou [Smoochie Flasher](https://smoochiee.github.io/Noisy-boy-esp32-Bluetooth-jammer/flash)
- Primeiro, escolha o tipo de firmware, "Genérico" ou "OLED 0.96"" ou "Smoochiee"
- escolha o firmware que você deseja gravar
- Conecte seu ESP32 via cabo USB
- Grave o firmware de sua escolha

Se o seu ESP32 não estiver aparecendo na lista de dispositivos ou não for reconhecido, você precisará ter [ESTES DRIVERS INSTALADOS](https://www.silabs.com/documents/public/software/CP210x_Windows_Drivers.zip)


## Pinagem e conexões
Aqui estão ambas as pinagens para HSPI e VSPI. Você precisa de ambos os módulos nRF24L01 conectados para alcançar a capacidade total do dispositivo.  
[Pinagem do nRF24L01+](link-para-imagem-pinagem)

### HSPI
| Pino do 1º módulo nRF24L01 | Pino HSPI (ESP32) | Capacitor 10uf |
|----------------------------|-------------------|----------------|
| VCC                        | 3.3V              | (+) capacitor  |
| GND                        | GND               | (-) capacitor  |
| CE                         | GPIO 16           |                |
| CSN                        | GPIO 15           |                |
| SCK                        | GPIO 14           |                |
| MOSI                       | GPIO 13           |                |
| MISO                       | GPIO 12           |                |
| IRQ                        |                   |                |

### VSPI
| Pino do 2º módulo nRF24L01 | Pino VSPI (ESP32) | Capacitor 10uf |
|----------------------------|-------------------|----------------|
| VCC                        | 3.3V              | (+) capacitor  |
| GND                        | GND               | (-) capacitor  |
| CE                         | GPIO 22           |                |
| CSN                        | GPIO 21           |                |
| SCK                        | GPIO 18           |                |
| MOSI                       | GPIO 23           |                |
| MISO                       | GPIO 19           |                |
| IRQ                        |                   |                |

### LED de Status
| ESP32    | Resistor 4.7k Ohm | LED de Status 3mm (azul) |
|----------|-------------------|--------------------------|
| GND      |                   | (-) LED                  |
|          | Resistor          | (+) LED                  |
| GPIO 27  | Resistor          |                          |

### Display OLED I2C (adicional - certifique-se de usar o firmware correto!)
| Display OLED 0.96" I2C | ESP32   |
|------------------------|---------|
| GND                    | GND     |
| VCC                    | 3.3V    |
| SCL                    | GPIO 5  |
| SDA                    | GPIO 4  |

### Modificação de bateria (adicional)
| Bateria Li-Ion 3.7V | Conector JST-PH2 | Módulo de Carregamento TP4056 | Mini Interruptor Deslizante | ESP32 |
|---------------------|------------------|-------------------------------|------------------------------|-------|
| (+) Bateria         | (+) JST-PH2      | Bat +                         |                              |       |
| (-) Bateria         | (-) JST-PH2      | Bat -                         |                              |       |
|                     |                  | OUT +                         | Entrada do interruptor       |       |
|                     |                  | OUT -                         |                              | GND   |
|                     |                  |                               | Saída do interruptor         | 3V3   |


<h3 align="center">Esquematico</h3>

![Esquematico](https://r2.e-z.host/555d8d65-caa2-47a0-afde-f9df96f35733/96hjibzi.png)


## PCB

<h3 align="center">É assim que os componentes são posicionados (Tamanho da PCB = 7cm x 5.5cm - Tamanhos maiores NÃO caberão no case!)</h3>

![DIYPCB](https://camo.githubusercontent.com/2bf35750381e5bc803e185b66d4dc729b62d218b1a9397267ad16f2e2564be1b/68747470733a2f2f64776477706c642e70616765732e6465762f4449595043422e6a7067)


## Sobre o NWASKJAMR e meu código-fonte
- **O meu NWASKJAMR realmente funciona?**  
  Sim! Meu NWASKJAMR é totalmente funcional, e ninguém pausa o som no vídeo de demonstração. Muitas pessoas construíram seu próprio Jammr e confirmaram que funciona!

## Apoie-me
Via [este link](https://pixgg.com/nwask), você pode deixar uma donate para me manter motivado desenvolvendo projetos futuros! Obrigado pelo seu apoio :)


<h1 align="center"> AVISO LEGAL </h1>

<h4 align="center">Por favor, note que o uso desta ferramenta é inteiramente por sua conta e risco. Ela é destinada estritamente para fins educacionais e não deve ser usada para atividades ilegais ou antiéticas. Jamming é ilegal e pode te colocar em grandes problemas!</h4>
<h4 align="center">Não sou responsável por suas ações! </h4>
