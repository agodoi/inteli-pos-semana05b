# (1) Tipos de Rede

### (1.1) PAN (Personal Area Network)

Basicamente feita de dispositivos de curto alcance, em especial, os sem fio, via bluetooth;

### (1.2) LAN (Local Area Network)

Feita de cabos UTP ou STP, WiFi, conectando computadores, notebooks, TVs, projetores, Alexa, dispositivos IoT, impressores e servidores.
 
### (1.3) MAN (Metropolitan Area Network)

Feita de fibra óptica e rádio tipo minilink conectando empresas, hospitais, faculdades de diferentes endereços dentro de uma região metropolitana. Uma empresa ISP (Internet Service Provider) que alcança usuários dentro de uma cidade ou região metropolitana possui topologia física e lógica MAN.

### (1.4) WAN (Wide Area Network)

Feita de fibra óptica e satélite. A Internet se mistura com uma WAN.


## (2) Importância do Modelo OSI em Redes

Ambas as redes servem para conectar os hosts (que são end-devices numa grande rede chamada Internet).

Os hosts se comunincam usando diversos protocolos que trabalham de **camada N para camada N**.


<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/SubRedes/blob/main/imgs/modelo_osi.png">
   <img alt="Modelo OSI" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/SubRedes/blob/main/imgs/modelo_osi.png)">
</picture>

Alguns detaques da figura:

* O Modelo OSI (Opened Standard Interconnection) possui 7 camadas. É uma pilha de camadas totalmente abstrata, isto é, não existe essas camadas na vida real e não correspondem à nenhuma placa específica do computador;

## (2.1) Modelo OSI

* **Camada 07 - Aplicação :** cuida de tudo o que aparece na sua tela, é a aplicação;
* **Camada 06 - Apresentação :** é o tradutor com criptografia/descriptografia;
* **Camada 05 - Sessão :** é a camada de intercomunicação entre hosts. É como se fosse uma sessão de cinema que tem hora para começar e acabar, isto é, o serviço ficará disponível para você por X minutos ou horas;
* **Camada 04 - Transporte :** é a camada de transferência de dados fim a fim. É o frete de pacotes. É a cada do TCP e UDP. TCP garante a entrega, UDP transporta, mas não garante a entrega de pacotes;
* **Camada 03 - Redes :** determina o caminho e a lógica de roteamento de pacotes. É a cada do IPV4 e IPV6;
* **Camada 02 - Enlace :** é a camada que trata do endereço físico dos dispositivos de redes, isto é, o chassis da placa que trafega dados;
* **Camada 01 - Física :** é a camada dos padrões elétricos, eletrônicos e mecânicos.



## (2.2) Protocolo IPV4 vs IPV6

A figura a seguir aponta as principais diferenças. Contudo, na rede local, só se usa o IPV4.

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/SubRedes/blob/main/imgs/ipv4_vs_ipv6.png">
   <img alt="IPV4 vs IPV6" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/SubRedes/blob/main/imgs/ipv4_vs_ipv6.png)">
</picture


## (3) Redes e Sub-redes

As redes de computadores servem para criar hierarquias de estações de trabalho dentro de numa organização. Por exemplo, numa instituição de ensino, existe a rede de alunos, a de professores e a administrativa. As redes geralmente não se conversam e há critérios de segurança entre elas.

E as sub-redes são redes menores que nascem a partir de uma rede, e para isso, precisamos do CIDR (Classes Inter-Domain Routing) para organizar essas redes dentro de redes.

## Basicamente, o que você precisa saber pra dominar esse trem?

| Fazer conversão de binária para decimal.|
|-|

## Exemplo 01:

### Dado o IP 10.0.0.0/26
#### a) Qual é o endereço de rede?
#### b) Qual é o primeiro IPV4 disponível?
#### c) Qual é o endereço de broadcast na rede?
#### d) Qual é o último endereço IPV4 útil disponível?

O /26 significa que o CIDR = 26, então significa 26 bits são fixos, isto é, uma máscara de 26 bits "1" e 6 bits irrelevantes marcados por x.

Então, você pode brincar com os bits flexíveis marcados por **X**, mas não pode mudar os bits marcados por **1**.

|1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 X X X X X X |
|-|-|-|-|
| 255 | 255 | 255 | 192 |

Olhando para **10.0.0.0/26** sua missão é:

a) Qual é a máscara de rede?

b) Qual é o endereço de rede?

c) Qual é o primeiro IPV4 disponível?

d) Qual é o endereço de broadcast na rede?

e) Qual é o último endereço IPV4 útil disponível?

f) Quantos hosts cabem nessa rede?

### a) Máscara de rede

Máscara de sub-rede é um valor numérico que é usado em redes de computadores para dividir uma rede IP em sub-redes menores. Essa máscara é usada em conjunto com um endereço IP para determinar quais bits no endereço IP representam a rede e quais bits representam o host dentro dessa rede.

A parte da rede é indicada com **1**. A parte de hosts é indicada com **0** ou **X**. Vamos adotar o **X**, que significa, *irrelevante* (será uma faixa de valores e não um valor único). Para o exemplo dado **/26** teremos:

|1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 X X X X X X |
|-|-|-|-|
| 255 | 255 | 255 | 192 |


### b) Endereço de rede é o primeiro endereço da faixa (quando os bits X são só ZERO): 

Pega o IP original dado no enunciado:

| 10 | 0 | 0 | 0 |
|-|-|-|-|

Compare com a máscara e encontre os bits flexíveis **X** e não mexa com os bits marcados em **1**:

|1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 X X X X X X |
|-|-|-|-|
| 255 | 255 | 255 | 192 |

Resulta em:

| 0 0 0 0 1 0 1 0 | 0 0 0 0 0 0 0 0 | 0 0 0 0 0 0 0 0 | 0 0 X X X X X X |
|-|-|-|-|
| 10 | 0 | 0 | 0 0 X X X X X X |

Finalmente, coloque **0** no lugar dos **X** para encontrar o endereço da rede, porque endereço de rede é sempre o primeiro endereço possível:

| 10 | 0 | 0 | 0 0 0 0 0 0 0 0 |
|-|-|-|-|

Que é o mesmo que **10.0.0.0**

### c) Qual é primeiro IP útil disponível?

É sempre o primeiro após o endereço da rede. Portanto:

| 10 | 0 | 0 | 0 0 0 0 0 0 0 1 |
|-|-|-|-|
| 10 | 0 | 0 | 1 |


### d) Qual o endereço de broadcast da rede? 

Quando os **X** flexíveis são semopre **1**: 

| 10 | 0 | 0 | 0 0 1 1 1 1 1 1 |
|-|-|-|-|

Resulta em:

| 10 | 0 | 0 | 63 |
|-|-|-|-|

porque 1 1 1 1 1 1 = 63

### e) Qual é o último endereço ÚTIL da faixa?

É sempre o penúltimo endereço do broadcast.

| 10 | 0 | 0 | 62 |
|-|-|-|-|


### f) Qual é a quantidade de hosts possíveis nessa rede?

É só contar a quantidade de endereços do 1º até um antes do broadcast, que nesse caso será do 1 ao 62, portanto, 62 hosts possíveis de serem endereçados nessa rede. Em outras palavras, cabem 62 máquinas ou end-points nessa rede.

**Respostas:**
- Máscara de sub-rede: 255.255.255.192
- Endereço de rede: 10.0.0.0
- 1º endereço útil: 10.0.0.1
- Endereço de broadcast: 10.0.0.63 (último endereço)
- Último endereço útil: 10.0.0.62
- Quantidade de hosts possíveis: 62


## Exemplo 02: dado o IP 172.16.1.43/28

#### a) Qual é máscara de sub-rede?
#### b) Qual é o endereço de rede?
#### c) Qual é o primeiro IPV4 disponível?
#### d) Qual é o endereço de broadcast na rede?
#### e) Qual é o último endereço IPV4 útil disponível?
#### f) Quantos hosts são possíveis?

**Respostas:**
- Máscara de sub-rede: 255.255.255.240
- Endereço de rede: 172.16.1.32
- 1º IPV4: 172.16.1.33
- Endereço de broadcast: 172.16.1.47 (último)
- Último IPV4 útil: 172.16.1.46
- Quantidade de hosts possíveis: 13


## Exemplo 03: dado o IP 10.0.8.0/21

#### a) Qual é máscara de sub-rede?
#### b) Qual é o endereço de rede?
#### c) Qual é o primeiro IPV4 disponível?
#### d) Qual é o endereço de broadcast na rede?
#### e) Qual é o último endereço IPV4 útil disponível?
#### f) Quantos hosts são possíveis?

**Respostas:**
- Máscara de sub-rede: 255.255.248.0
- Endereço de rede: 10.0.8.0
- 1º IPV4: 10.0.8.1
- Endereço de broadcast: 10.0.15.255
- Último IPV4 útil: 10.0.15.254
- Quantidade de hosts possíveis: 2046


## Exemplo 04: 10.0.128.0/17

### Dado o IP
#### a) Qual é máscara de sub-rede?
#### b) Qual é o endereço de rede?
#### c) Qual é o primeiro IPV4 disponível?
#### d) Qual é o endereço de broadcast na rede?
#### e) Qual é o último endereço IPV4 útil disponível?
#### f) Quantos hosts são possíveis?

**Respostas:**
- Máscara de sub-rede: 255.255.128.0
- Endereço de rede: 10.0.128.0
- 1º IPV4: 10.0.128.1
- Endereço de broadcast: 10.0.255.255
- Último IPV4 útil: 10.0.255.254
- Quantidade de hosts possíveis: 2^15 - 2 = 32.766

## Exemplo 05: 10.0.1.64/26

### Dado o IP
#### a) Qual é máscara de sub-rede?
#### b) Qual é o endereço de rede?
#### c) Qual é o primeiro IPV4 disponível?
#### d) Qual é o endereço de broadcast na rede?
#### e) Qual é o último endereço IPV4 útil disponível?
#### f) Quantos hosts são possíveis?

**Respostas:**
- Máscara de sub-rede: 255.255.255.192
- Endereço de rede: 10.0.1.64
- 1º IPV4: 10.0.1.65
- Endereço de broadcast: 10.0.1.127
- Último IPV4 útil: 10.0.1.126
- Quantidade de hosts possíveis: 2^6 - 2 = 62


# Agora pense!

Considere que você colocou no seu roteador a seguinte rede principal: **192.168.0.0/22**.

### Dado o IP 192.168.0.0/22

#### a) Qual é máscara de sub-rede?
#### b) Qual é o endereço de rede?
#### c) Qual é o primeiro IPV4 disponível?
#### d) Qual é o endereço de broadcast na rede?
#### e) Qual é o último endereço IPV4 útil disponível?
#### f) Quantos hosts são possíveis?

## E considerando que vocÊ criou uma sub-rede A com IP 192.168.0.0/24 e outra sub-rede B com 192.168.1.0/24

#### a) Qual é máscara de cada sub-rede?
#### b) Qual é o endereço de rede de cada sub-rede?
#### c) Qual é o primeiro IPV4 disponível de cada sub-rede?
#### d) Qual é o endereço de broadcast em cada rede-sub?
#### e) Qual é o último endereço IPV4 útil disponível em cada sub-rede?
#### f) Quantos hosts são possíveis em cada sub-rede?

### g) As sub-redes de fato estão dentro da rede principal? Justique!

A título de curiosidade, as faixas de IP gratuitas utilizadas em redes locais são:

- Faixa Classe: 10.0.0.0 a 10.255.255.255 

- Faixa Classe: 172.16.0.0 a 172.31.255.255

- Faixa Classe: 192.168.0.0 a 192.168.255.255

# Desafio. Descubra o CIDR de cada faixa endereços gratuitos abaixo:

- Faixa Classe: 10.0.0.0 a 10.255.255.255
  
- Faixa Classe: 172.16.0.0 a 172.31.255.255

- Faixa Classe: 192.168.0.0 a 192.168.255.255

## BOAS PRÁTICAS [60min] - Como configurar sub-redes usando Packet Tracer?

Nessa prática, vamos simular uma rede LAN com 2 sub-redes usando a ferramenta da Cisco chamada Packet Tracer.

Portanto, o objetivo é instalar o Packet Tracer em seu PC e fazer algumas simulações de rede e sub-redes.

### Material Necessário

a) Formar grupos de até 5 alunos;

b) Instalar o software Packet Tracer;

Atenção: para instalar o Packet Tracer, você precisa abrir uma conta no Cisco Networking Academy.

### Procedimentos

a) Abra esse link [https://www.netacad.com/pt/courses/getting-started-cisco-packet-tracer?courseLang=pt-BR](https://www.netacad.com/pt/courses/getting-started-cisco-packet-tracer?courseLang=pt-BR) e clique em **Self-Paced**

b) Se autentique clicando no botão **Google** (essa etapa abre a sua conta);

c) Encontre um botão chamado **Retornar ao curso**;

d) Logo no **Módulo 1: Baixar e Usar o Cisco Packet Tracer**, tem um link como esse [https://www.netacad.com/resources/lab-downloads](https://www.netacad.com/resources/lab-downloads) que permite você baixar o Packet Tracer de acordo com o sistema operacional do seu computador. Baixe o Packet Tracer compatível com o seu Sistema Operacional.

e) Abra o Packet Tracer, adicione os seguintes componentes:

* 02 roteadores modelo 1941 (3ª opção da esquerda para a direita);
* 02 switches modelo 2960 (1ª opção da esquerda para a direita);
* 4 PCs (end device) 

f) Monte a seguinte topologia física conforme a figura, sem ligar os cabos

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/topologia-01.png">
   <img alt="Estrela Estendida" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/topologia-01.png)">
</picture>

g) Conecte um **cabo direto** dos PC 0 e 1 até o Switch 0 e outros **cabos diretos** dos PC 2 e 3 até o Switch 1. Use as portas **Fast Ethernet**.

h) Faça o mesmo conectando **cabo direto** entre Switch0 até o Roteador0 e do Switch1 até o Roteador1. 

i) Conecte um **cabo cruzado** entre os dois Roteadores. O uso do cabo cruzado é porque equipamentos iguais são sempre interligados por cabos cruzados (TX ligado no RX e vice-versa).

Sua montagem deve ficar igual à imagem a seguir.

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/topologia-02.png">
   <img alt="Estrela Estendida" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/topologia-02.png)">
</picture>

E na imagem a seguir, você encontra os nomes das portas de cada dispositivo para conferir se fez igual.

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/topologia-02b.png">
   <img alt="Estrela Estendida" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/topologia-02b.png)">
</picture>

j) Agora pare e pense! Faça os cálculos dos IP e máscaras para você montar 3 sub-redes e com 64 endereços em cada sub-rede.

* Não é possível fazer 3 sub-redes, porque 3 não é múltiplo de 2. Então, você terá que mirar em 4 sub-redes e usar 3.
* Para ter 4 sub-redes, congele 2 bits mais significativos do 4º octeto. Observe os passos para entender:

  |Passos| 1º octeto | 2º octeto | 3º octeto | 4º octeto | Observação|
  |-|-|-|-|-|-|
  |1|? ? ? ? ? ? ? ?|? ? ? ? ? ? ? ?|? ? ? ? ? ? ? ?|? ? ? ? ? ? ? ?|Formato do IP|
  |2|? ? ? ? ? ? ? ?|? ? ? ? ? ? ? ?|? ? ? ? ? ? ? ?|congela congela x x x x x x|Demanda do projeto|
  |3|8 bits congelados|8 bits congelados|8 bits congelados|1 1 x x x x x x|Aplicando máscara 192|
  |4|1 1 1 1 1 1 1 1|1 1 1 1 1 1 1 1|1 1 1 1 1 1 1 1|1 1 x x x x x x|Bits congelados (1) e livres (x)|
  |5|255|255|255|192|Cálculo realizado|
  
  
* Suas sub-redes serão:
  
  | Sub-rede A | Sub-rede B | Sub-rede C | Sub-rede D |
  |-|-|-|-|
  |192.168.0.0 /192| 192.168.0.64 /192 | 192.168.0.128 /192 | 192.168.0.192 /192 |
  |PC0 + PC1 + SW0 + R0 | R0 + R1 | PC2 + PC3 + SW1 + R1| Não usado |

* Quais os endereços de cada Sub-rede?

  |Sub-Rede |End. Rede | 1º End. Útil | Último End. Útil | End. Broadcast |Máscara |
  |-|-|-|-|-|-|
  |A|192.168.0.0|192.168.0.1|192.168.0.62|192.168.0.63|255.255.255.192|
  |B|192.168.0.64|192.168.0.65|192.168.0.126|192.168.0.127|255.255.255.192|
  |C|192.168.0.128|192.168.0.129|192.168.0.190|192.168.0.191|255.255.255.192|
  |D|192.168.0.192|192.168.0.193|192.168.0.254|192.168.0.255|255.255.255.192|

k) Volte no circuito, e configure manualmente os IP para cada dispositivo. Note que agora temos o endereço do Gateway. Adotamos o último endereço útil de cada sub-rede para colocar a porta Giga respectiva voltada para o seu Switch como Gateway. É sempre assim? Não! Você escolhe qual será o endereço do Gateway e que fácil de memorizar.

|Dispositivo|Endereço IP|Máscara|Gateway|
|-|-|-|-|
|PC0|192.168.0.1|255.255.255.192|192.168.0.62|
|PC1|192.168.0.2|255.255.255.192|192.168.0.62|
|SW0|não tem|não tem|não tem|
|R0-Giga0/0|192.168.0.62|255.255.255.192|não tem|
|R0-Giga0/1|192.168.0.126|255.255.255.192|não tem|
|R1-Giga0/0|192.168.0.190|255.255.255.192|não tem|
|R1-Giga0/1|192.168.0.125|255.255.255.192|não tem|
|SW1|não tem|não tem|não tem|
|PC2|192.168.0.129|255.255.255.192|192.168.1.190|
|PC3|192.168.0.130|255.255.255.192|192.168.1.190|
