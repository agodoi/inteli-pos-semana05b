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

A partir de agora, você entenderá como funciona o mapeamento de sub-rede, que pode ser implementado tanto numa rede Local quanto numa VPC (Virtual Private Cloud) como AWS, Azure, etc.

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
- Quantidade de hosts possíveis: 14


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

a) Formar grupos em duplas;

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
* Para ter 4 sub-redes, congele 2 bits mais significativos do 4º octeto. Portanto você terá um **CIDR = /26**. Observe os passos para entender:

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

|Dispositivo|Endereço IP|Máscara|Gateway|Observação|
|-|-|-|-|-|
|PC0|192.168.0.1|255.255.255.192|192.168.0.62|Rede A|
|PC1|192.168.0.2|255.255.255.192|192.168.0.62|Rede A|
|SW0|não tem|não tem|não tem|Não é gerencíavel|
|R0-GigaEth0/0|192.168.0.62|255.255.255.192|não tem|Último IP útil de A, Gateway de PC0 e PC1, Interface 0/0 de R0|
|R0-GigaEth0/1|192.168.0.126|255.255.255.192|não tem|Último IP útil de B, Interface 0/1 de R0|
|R1-GigaEth0/1|192.168.0.125|255.255.255.192|não tem|Penúltimo IP útil de B, Interface 0/1 de R1|
|R1-GigaEth0/0|192.168.0.190|255.255.255.192|não tem|Último IP útil de C, Gateway de PC2 e PC3, Interface 0/0 de R1|
|SW1|não tem|não tem|não tem|Não é gerencíavel|
|PC2|192.168.0.129|255.255.255.192|192.168.1.190|Rede C|
|PC3|192.168.0.130|255.255.255.192|192.168.1.190|Rede C|

l) Sua rede física está pronta, mas ela ainda não funciona, pois precisamos configurar manualmente os roteadores com as devidas tabelas de roteamento. Isso impacta no desempenho geral da rede. E sem tabela de roteamento, os roteadores não aprendem sobre os caminhos lógicos disponíveis nas sub-redes.

Pense em quais as redes estão diretamente interligadas em cada roteador, isto é, quais os cabos estão saindo e chegando nele. Essas redes diretamente ligadas já são de conhecimento do respectivo roteador.

* Roteador 0 conhece as redes 192.168.0.0 e 192.168.0.64
* Roteador 1 conhece as redes 192.168.0.0 e 192.168.0.128

Porém:

**Roteador 0 não conhece a rede 192.168.0.128 / 255.255.255.192**

**Roteador 1 não conhece a rede 192.168.0.0 / 255.255.255.192**

m) Abra o Roteador 0 e vá em **Config** e depois **Static**.

n) Em **Static Routes**, coloque em **Network** a rede que A não conhece, coloque 192.168.0.128 / 255.255.255.192 e no campo **Next hope** coloque o IP do próximo passo: 192.168.0.125 (que faz parte da 192.168.0.64). Essa interface GigaEthernet (192.168.0.125) é a porta de entrada mais próxima da sub-rede de A para chegar em B. Internamente, o roteador vai interconectar a 192.168.0.64 com a 192.168.0.128. Feito isso, clique em **Add**

o) Faça o mesmo para o Roteador 1, vá em **Config** e depois **Static**. No campo **Network**, coloque a rede que B não conhece, que é a rede A, lado interface 0/0: 192.168.0.0 / 255.255.255.192 e no campo **Next hoje**, coloque o IP 192.168.0.126 e clique em **Add**. 

p) Para testar a rede, clique no botão **Simulation** que fica no canto inferior direito, clique no botão **Edit Filters**, desmarque tudo, e só deixei o **ICMP** (protocolo de ping).

q) Pegue um ícone de evelope fechado que está **Add simple PDU (P)** e arraste e solte encima do PC0 e depois arraste para cima do PC3.

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/cartinha.png">
   <img alt="Estrela Estendida" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/inteli-pos-semana05b/blob/main/imgs/cartinha.png)">
</picture>

r) Dê um play e observe o pacote indo e voltando em direção ao PC3. Se o pacote foi e voltou, **SUCESSO!**. Se não, delete o pacotinho e repita o passo (q).

---
## Cartinha indo do PC0 em direção ao PC3

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/inteli-pos-semana05b/blob/main/cartinha2.png">
   <img alt="IPV4 vs IPV6" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/inteli-pos-semana05b/blob/main/cartinha2.png)">
</picture

---
## Cartinha voltando do PC3 em direção ao PC0

<picture>
   <source media="(prefers-color-scheme: light)" srcset="https://github.com/agodoi/inteli-pos-semana05b/blob/main/cartinha3.png">
   <img alt="IPV4 vs IPV6" src="[YOUR-DEFAULT-IMAGE](https://github.com/agodoi/inteli-pos-semana05b/blob/main/cartinha3.png)">
</picture

# Exercício

1) Faça um mapeamento de IP para ter 256 endereços de host e 3 sub-redes A B C.
2) Monte a rede LAN no Packet Tracer.
3) Faça o primeiro computador da rede A mandar um ping para o último computador da sua rede C.


## Simulação ao Ataque de um IoT

Nessa parte da aula, vamos simular um ataque a um dispostivo IoT que controla uma válvula importante de gás, que se fechada, corta o fornecimento de gás nas residências em pleno inverno.

Regras:

a) Trabalho em dupla;

b) Use qualquer tipo de programação que achar necessária;

c) O IoT é um ESP32;

d) Há 2 LEDs para você atacar.

Alguns levantamentos por meio da engenharia social:

1) O dispositivo pode estar nas redes A ou B do mapeamento feito no Packet Tracer;
2) Para controlar o dispositivo, usa-se a URL:
   
   a) X.X.X.X/pino/on (LIGA)
   
   b) X.X.X.X/pino/off (DESLIGA)
   
4) Sua missão é atacar esse dispositivo fazendo-o desligar (DESLIGAR O LED VERDE). 
5) Qual é a sua estratégia?
6) Faça o ataque e se funcionar, monte uma apresentação que será apresentada à turma.

## Montando o seu Dispositivo IoT

Agora, vamos montar o seu dispositivo IoT que você mesmo atacou.

Sabe gravar um programa usando o Arduino IDE?

### 1. Pré-requisitos
- **Arduino IDE instalado** (versão 1.8.19 ou superior).
  - Baixe a IDE no site oficial: [https://www.arduino.cc/en/software](https://www.arduino.cc/en/software).
- **Cabo USB** para conectar o ESP32 ao computador.
- **Placa ESP32** (qualquer modelo compatível, como DevKit V1 ou NodeMCU-32S).

---

### Passos

### 2. Passo a Passo para Instalação

#### Passo 1: Abra o Arduino IDE
- Inicie o Arduino IDE no seu computador.

#### Passo 2: Adicione o Gerenciador de Placas ESP32
1. Vá para o menu **File** (ou **Arquivo**) e clique em **Preferences** (ou **Preferências**).
2. Na janela de Preferências, localize o campo **Additional Board Manager URLs** (ou **URLs Adicionais para Gerenciadores de Placas**).
3. Insira a URL abaixo no campo (caso já tenha outras URLs, separe-as por vírgula):
   ```
   https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
   ```
4. Clique em **OK** para salvar.

#### Passo 3: Instale as Placas ESP32
1. Vá para o menu **Tools** (ou **Ferramentas**) > **Board** (ou **Placa**) > **Boards Manager** (ou **Gerenciador de Placas**).
2. Na barra de busca, digite **ESP32**.
3. Clique em **Install** (ou **Instalar**) na entrada "esp32 by Espressif Systems".
4. Aguarde o download e a instalação serem concluídos.

#### Passo 4: Selecione a Placa ESP32
1. Conecte sua placa ESP32 ao computador usando o cabo USB.
2. No Arduino IDE, vá para **Tools** > **Board** > **ESP32 Arduino**.
3. Escolha a placa que corresponde ao seu modelo, como:
   - **ESP32 Dev Module** (para a maioria das placas DevKit V1).

#### Passo 5: Configure a Porta Serial
1. Ainda no menu **Tools**, vá para **Port**.
2. Selecione a porta correspondente ao ESP32 (geralmente é algo como `COM3`, `COM4`, etc., no Windows, ou `/dev/ttyUSB0` no Linux/Mac).

#### Passo 6: Teste a Instalação
1. Abra o exemplo básico de piscar LED integrado:
   - Vá para **File** > **Examples** > **Basics** > **Blink**.
2. Substitua o número do pino no código, se necessário, para o LED embutido no ESP32:
   ```cpp
   void setup() {
       pinMode(2, OUTPUT); // Pino 2 geralmente é o LED embutido
   }

   void loop() {
       digitalWrite(2, HIGH);
       delay(1000);
       digitalWrite(2, LOW);
       delay(1000);
   }
   ```
3. Clique em **Upload** (ou pressione `Ctrl + U`).
4. Aguarde o código ser enviado. Se aparecer "Done Uploading", o LED do ESP32 começará a piscar.

---

### 3. Solução de Problemas
- **Problema: Porta Serial não aparece**:
  - Verifique se o driver USB está instalado. Baixe o driver CP2102 ou CH340 (dependendo da sua placa) no site do fabricante.
- **Problema: Erro ao enviar código**:
  - Pressione e mantenha o botão **BOOT** no ESP32 enquanto o código é carregado.

---

Com esses passos, o ESP32 estará configurado e pronto para ser usado na Arduino IDE! Se precisar de mais ajuda, é só perguntar.


```
// Load Wi-Fi library
#include <WiFi.h>

// Replace with your network credentials
const char* ssid = "RedeIoT";
const char* password = "inteli123";

// Set web server port number to 80
WiFiServer server(80);

// Variable to store the HTTP request
String header;

// Auxiliar variables to store the current output state
String output26State = "off";
String output27State = "off";

// Assign output variables to GPIO pins
const int output26 = 26;
const int output27 = 27;

// Current time
unsigned long currentTime = millis();
// Previous time
unsigned long previousTime = 0; 
// Define timeout time in milliseconds (example: 2000ms = 2s)
const long timeoutTime = 2000;

void setup() {
  Serial.begin(115200);
  // Initialize the output variables as outputs
  pinMode(output26, OUTPUT);
  pinMode(output27, OUTPUT);
  // Set outputs to LOW
  digitalWrite(output26, LOW);
  digitalWrite(output27, LOW);

  // Connect to Wi-Fi network with SSID and password
  Serial.print("Connecting to ");
  Serial.println(ssid);
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  // Print local IP address and start web server
  Serial.println("");
  Serial.println("WiFi connected.");
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
  server.begin();
}

void loop(){
  WiFiClient client = server.available();   // Listen for incoming clients

  if (client) {                             // If a new client connects,
    currentTime = millis();
    previousTime = currentTime;
    Serial.println("New Client.");          // print a message out in the serial port
    String currentLine = "";                // make a String to hold incoming data from the client
    while (client.connected() && currentTime - previousTime <= timeoutTime) {  // loop while the client's connected
      currentTime = millis();
      if (client.available()) {             // if there's bytes to read from the client,
        char c = client.read();             // read a byte, then
        Serial.write(c);                    // print it out the serial monitor
        header += c;
        if (c == '\n') {                    // if the byte is a newline character
          // if the current line is blank, you got two newline characters in a row.
          // that's the end of the client HTTP request, so send a response:
          if (currentLine.length() == 0) {
            // HTTP headers always start with a response code (e.g. HTTP/1.1 200 OK)
            // and a content-type so the client knows what's coming, then a blank line:
            client.println("HTTP/1.1 200 OK");
            client.println("Content-type:text/html");
            client.println("Connection: close");
            client.println();
            
            // turns the GPIOs on and off
            if (header.indexOf("GET /26/on") >= 0) {
              Serial.println("GPIO 26 on");
              output26State = "on";
              digitalWrite(output26, HIGH);
            } else if (header.indexOf("GET /26/off") >= 0) {
              Serial.println("GPIO 26 off");
              output26State = "off";
              digitalWrite(output26, LOW);
            } else if (header.indexOf("GET /27/on") >= 0) {
              Serial.println("GPIO 27 on");
              output27State = "on";
              digitalWrite(output27, HIGH);
            } else if (header.indexOf("GET /27/off") >= 0) {
              Serial.println("GPIO 27 off");
              output27State = "off";
              digitalWrite(output27, LOW);
            }
            
            // Display the HTML web page
            client.println("<!DOCTYPE html><html>");
            client.println("<head><meta name=\"viewport\" content=\"width=device-width, initial-scale=1\">");
            client.println("<link rel=\"icon\" href=\"data:,\">");
            // CSS to style the on/off buttons 
            // Feel free to change the background-color and font-size attributes to fit your preferences
            client.println("<style>html { font-family: Helvetica; display: inline-block; margin: 0px auto; text-align: center;}");
            client.println(".button { background-color: #4CAF50; border: none; color: white; padding: 16px 40px;");
            client.println("text-decoration: none; font-size: 30px; margin: 2px; cursor: pointer;}");
            client.println(".button2 {background-color: #555555;}</style></head>");
            
            // Web Page Heading
            client.println("<body><h1>ESP32 Web Server</h1>");
            
            // Display current state, and ON/OFF buttons for GPIO 26  
            client.println("<p>GPIO 26 - State " + output26State + "</p>");
            // If the output26State is off, it displays the ON button       
            if (output26State=="off") {
              client.println("<p><a href=\"/26/on\"><button class=\"button\">ON</button></a></p>");
            } else {
              client.println("<p><a href=\"/26/off\"><button class=\"button button2\">OFF</button></a></p>");
            } 
               
            // Display current state, and ON/OFF buttons for GPIO 27  
            client.println("<p>GPIO 27 - State " + output27State + "</p>");
            // If the output27State is off, it displays the ON button       
            if (output27State=="off") {
              client.println("<p><a href=\"/27/on\"><button class=\"button\">ON</button></a></p>");
            } else {
              client.println("<p><a href=\"/27/off\"><button class=\"button button2\">OFF</button></a></p>");
            }
            client.println("</body></html>");
            
            // The HTTP response ends with another blank line
            client.println();
            // Break out of the while loop
            break;
          } else { // if you got a newline, then clear currentLine
            currentLine = "";
          }
        } else if (c != '\r') {  // if you got anything else but a carriage return character,
          currentLine += c;      // add it to the end of the currentLine
        }
      }
    }
    // Clear the header variable
    header = "";
    // Close the connection
    client.stop();
    Serial.println("Client disconnected.");
    Serial.println("");
  }
}
```


