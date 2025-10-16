# Estudo Arduino
Repositório criado para estudos e projetos com Arduino.

## Blink - Piscar LED (Interno)

<div align="center">
  <img src="/assets/blink.gif" alt="Blink Interno" width="500"/>
</div>


Código:
```cpp
const int ledPin = LED_BUILTIN;  

int estadoLed= LOW;  

unsigned long previousMillis = 0;  
const long intervalO = 1000;  // define o intervalo pra 1 sec
void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  unsigned long currentMillis = millis();
  if (currentMillis - previousMillis >= intervalO) {

    previousMillis = currentMillis;


    if (estadoLed == LOW) {
      estadoLed = HIGH;
    } else {
      estadoLed = LOW;
    }
    digitalWrite(ledPin, estadoLed);
  }
}
```

## Blink - Piscar LED (Externo)
<a href="https://www.tinkercad.com/things/fSUKC8K3kRB/editel?sharecode=qyGqongasKDWY-93Q95CTBGea8U8OLad5e_bY3WLHBM" target="_blank">Link do projeto no Tinkercad</a>

<div align="center">
  <img src="/assets/tinkercad-print.png" alt="Blink Externo" width="'300"'/>

</div>

## Bônus - Semáforo com LED

&ensp;Mini projeto de semáforo utilizando LEDs.
<div align="center">
  <img src="/assets/semafaro.jpg" alt="Semáforo" width="300"/>
</div>

<div align="center">
  <img src="/assets/semaforoo.gif" alt="Semáforo" width="300"/>

</div>

Código:
```cpp
#define vermelho 2
#define amarelo 3
#define verde 4

void setup() {
 pinMode(vermelho, OUTPUT);
 pinMode(amarelo, OUTPUT);
pinMode(verde, OUTPUT);

}

void acendeVermelho(int tempo) {
  digitalWrite(vermelho, HIGH);
   digitalWrite(amarelo, LOW);
 digitalWrite(verde, LOW);
 delay(tempo);
}

void acendeAmarelo(int tempo) {
  digitalWrite(vermelho, LOW);
   digitalWrite(amarelo, HIGH);
 digitalWrite(verde, LOW);
 delay(tempo);
}

void acendeVerde(int tempo) {
  digitalWrite(vermelho, LOW);
   digitalWrite(amarelo, LOW);
 digitalWrite(verde, HIGH);
 delay(tempo);
}


void loop () {
  acendeVermelho(1500);
  acendeAmarelo(300);
  acendeVerde(1500);
}
