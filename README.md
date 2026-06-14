# Fonte de Tensão Ajustável

## Descrição

Fonte de tensão ajustável projetada para a disciplina SSC0180 – Eletrônica para Computação no ICMC-USP, do docente Eduardo do Valle Simões. Nele, busca-se projetar uma fonte de tensão ajustável entre 3v e 12v, com uma corrente de 100mA(máx.). Segue-se a tabela dos materiais utilizados e seus respectivos custos, os cálculos que justificam a arquitetura da fonte, a simulação realizada no Falstad e as esquemáticas do projeto no Tinkercad e no Eagle.

## Componentes
---
| Quantidades   | Componentes   | Preço |
| ------------- |:-------------:| -----:|
| 1      | Capacitor (1000uF x 25V)      | R$2,00  |
| 1      | LED 5mm vermelho              | R$0,50  |
| 4      | Diodos (Ponte)                | R$0,60  |
| 1      | Potenciômetro 5K - linear     | R$7,00  |
| 1      | Transistor 2N3904 NPN         | R$1,60  |
| 1      | Diodo Zener 1N4743 (13V / 1W) | R$0,50  |
| 10     | Resistor 1K - (1/4W)          | R$0,70  |
| 10     | Resistor 100 - (1/4W)         | R$0,70  |
| 10     | Resistor 120 - 5W             | R$1,40  |
| 1      | Protoboard - 400 furos        | R$23,80 |
| 10     | Kit Jumper - Macho-Macho      | R$7,00  |
| 50     | Total                         | R$45,80 |

### Transformador

O transformador atua na redução da amplitude da tensão proveniente da rede elétrica, atenuando-a de 180V para 18,1V. Esse processo de conversão fundamenta-se na variação do fluxo magnético através das espiras do componente, o que gera o fenômeno da indução eletromagnética.

### Ponte de Diodo

A ponte de diodos tem por função assegurar a unidirecionalidade do fluxo de corrente elétrica ao longo do circuito. Essa retificação faz-se necessária visto que a tensão de entrada possui caráter senoidal, apresentando alternâncias negativas. Dessa forma, o arranjo composto por quatro diodos impede a inversão da corrente, retificando a onda.

### Capacitor

O capacitor desempenha o papel de manter o fornecimento de tensão ao circuito durante os intervalos em que a onda senoidal apresenta taxa de variação negativa (períodos de descarga). Desse modo, o componente armazena energia em seu campo elétrico nos momentos de pico de tensão e a restitui ao sistema quando a tensão externa decai abaixo do potencial acumulado.

### Resistor

O resistor destina-se à limitação da intensidade da corrente elétrica direcionada a um determinado componente. Essa atenuação visa preservar os limites nominais de potência do dispositivo em questão, garantindo sua integridade operacional e prevenindo sobrecargas.

### LED

O diodo emissor de luz (LED) atua como um sinalizador visual do comportamento dinâmico do circuito. O objetivo de sua aplicação é que permaneça constantemente energizado, atestando de forma empírica que a corrente elétrica foi retificada com sucesso e encontra-se em regime contínuo (ou aproximadamente estável).

### Diodo Zenner

O diodo Zener é empregado com a finalidade de regular e limitar a tensão máxima do sistema. Na presente configuração, o componente estabiliza o potencial em 13V que, após a respectiva queda de tensão na junção do transistor, estabelece-se em 12,3V.

### Transistor

O transistor é responsável pela amplificação do sinal elétrico de entrada, atuando de forma a prover uma capacidade de corrente de 100 mA na seção de saída do circuito.

### Potenciômetro

O potenciômetro viabiliza o ajuste e o controle analógico da tensão de saída do circuito, permitindo a variação contínua da faixa operacional entre os limites de 3V e 12V.

---
## Circuitos:

### Falstad
https://shorturl.at/jkgNi


![Circuito no Falstad](circuit-20260526-0831.png)


### Tinkercad


![Circuito no Tinkercad](Circuito_Tinkercad.jpg)


### Eagle


![Circuito no Eagle](Circuito_Eagle.png)



![Circuito no Eagle - PCB](Circuito_PCB.png)


### Real Life

![Circuito na Vida Real](circuitovidareal.jpg)

### Vídeo de Explicação

https://youtu.be/debH5PX0NH0
---

## Cálculos:

### Transformador
```
Vprimário V1 = 127V (RMS)            | V1 Pico = 127 * √2 ~ 180V
Vsecundário V2 = 127/7 ~ 18,1 (RMS)  | V2 Pico = 18,1 * √2 ~ 25,6V
                        |_ Razão de espiras (1 : 7)
````

### Correntes
````
Icarga (Resistor 120Ω) = Vmax / Rcarga = 12,2/120 ~ 101mA
Ipotenciômetro |Vponte + Vresisitor| / Rpotenciômetro + R(em baixo pot) = 9 + 4 / 5000 + 2.200 = 13/7200 ~ 1,9mA
Izenner = |Vzenner + Vresisitor| / R(em cima zenner) = |(-13) + (9)| / 1000 = 4mA
Iled = |Vled + Vresisitor| / R (em baixo led) = 2 + 20 / 2000 = 22/2000 == 11mA
Itotal = Icarga + Ipot + Izenner + Iled = 101 + 1,9 + 4 + 11 ~ 118mA
````

### Capacitor
````
Vcapacitor = V2 Pico - (2 * 0,7) = 25,6 - 1,4 = 24,2V
Ripple desejado: < 10% => 24,2 * 0,1 = 2,42V
Frequênica: 120Hz (60Hz  * 2)
Capacitãncia (C) = Itotal / f * ripple = 0,118 / 120 * 2,42 ~ 406µ
````
---
---

# Jogo da Velha

## Introdução

Para este projeto, utilizaremos a plataforma de prototipagem Arduino Uno para desenvolver o famigerado jogo da velha, porém com o diferncial de ser contra uma "Inteligência Artificial".

## Componentes

| Componentes   |
| ------------- |
| Arduino Uno                |
| Teclado Matricial 4x4      |
| Display OLED SSD1306 (I2C) |
| Buzzer                     |

## Código da "IA"
```
// Aqui vai estar o código
```
---
## Participantes:
---
#### Arthur Nunes de Castro Zille - 17870441

#### Felipe Quierelli de Souza - 17831346

#### Giovanni Pansera Tondello - 17893040

