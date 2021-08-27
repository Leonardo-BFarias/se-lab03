# se-lab03
Repositório sobre atividades realizadas no laboratório 03 da disciplina Sistemas Embarcados. 
Este laboratório consistia em por em prática os conceitos de concorrência dentro de um sistema embarcado, introduzindo conceitos de tempo e Threads ao decorrer dos exercícios.

## Ferramenta
A ferramenta utilizada neste projeto foi a [Autodesk Tinkercad](https://www.tinkercad.com/), um programa de modelegam tridimensional que também permite a criação de circuitos eletrônicos acessíveis atravéis de um navegador. A escolha dessa ferramenta foi justamente pela facilidade de uso da mesma.

## Exercícios

- Criar um Blink com LED;
- Exibir estado de um botão no dispositivo;
- Criar um semáforo.

### 1° Exercício - Blink

Um exercício muito simples e rápido de ser feito, apenas conectar o LED à placa de arduino e inserir o código para fazer o blink.
```c++
void setup() {
 pinMode(LED_BUILTIN, OUTPUT); // Inicializando LED
}
void loop() {
 digitalWrite(LED_BUILTIN, HIGH); // Ligando LED
 delay(1000); // Esperando por 1 segundo
 digitalWrite(LED_BUILTIN, LOW); // Desligando LED
 delay(1000); // Esperando por 1 segundo
}
```

### 2° Exercício - Estado Botão

Para este exercício é preciso "printar" na tela o estado do botão a medida que ele é ou não pressionado. Para isso, foi utilizado o *Serial Monitor* um funcionalidade do Tinkercad que simula a tela do dispositivo à qual o arduino está conectado.
```c++
int pushButton = 2; // Salvando ID do Botão (neste caso Botão ligado ao pin 2)
void setup() {
 Serial.begin(9600); // Inicializando Comunicação Serial em 9600 bits
 pinMode(pushButton, INPUT); // Disparando INPUT ao apertar botão
}
void loop() {
 int buttonState = digitalRead(pushButton); // Capturando estado do botão
 Serial.println(buttonState); // Printando estado do botão
 delay(1); // Adicionando delay entre leituras.
}
```

### 3° Exercício - Semáforo

Para o último exercício foi utilizado a programação em blocos oferecida pelo programa da Tinkercad. Mais com um sentido de testar e apresentar a funcionalidade para os demais estudantes durante a apresentação. Ao utilizar a programação em blocos o usuário também tem acesso ao código fonte gerado.
```c++
// C++ code
//
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(12, OUTPUT);
}

void loop()
{
  digitalWrite(13, HIGH);
  delay(4000); // Wait for 4000 millisecond(s)
  digitalWrite(13, LOW);
  digitalWrite(11, HIGH);
  delay(6000); // Wait for 6000 millisecond(s)
  digitalWrite(11, LOW);
  digitalWrite(12, HIGH);
  delay(2000); // Wait for 2000 millisecond(s)
  digitalWrite(12, LOW);
}
```

## Conclusão

Este projeto foi simples, porém com espaço e liberdade para transformar os exercícios em projetos mais complexos (principalmente o de semáforo). Abordou bem os conceitos básicos e incentiva os alunos a buscarem por soluções dentro do escopo de sistemas embarcados.
