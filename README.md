# Introdução ao Dart

## Dart - Criando uma base 🧱

**[Dart](https://dart.dev/)** é uma linguagem de programação criada pela **[Google](https://pt.wikipedia.org/wiki/Google)** voltada ao desenvolvimento ágil de aplicativos para qualquer plataforma.

Ela foi apresentada na GOTO Conference de 2011, que aconteceu de 10 a 11 de outubro de 2011, naquela época a ideia inicial era de substituir o JavaScript como a linguagem embutida nos navegadores.

Em novembro de 2013, foi lançada a primeira versão estável, Dart 1.0. Em agosto de 2018 foi lançado o Dart 2.0, um *reboot* da linguagem, otimizando para o desenvolvimento client-side para Web e dispositivos móveis.

Hoje em dia o Dart contempla inúmeras funcionalidades que várias outras linguagens modernas implementam de maneira majestosa. Irei apresentar algumas delas nesse artigo, **espero que goste** 😁.

<!--more-->

## 1. Características

Por ser uma linguagem bem moderna e ainda com muito desenvolvimento, *NÃO ME ENTENDA MAL*, hoje em dia a linguagem não deixa a desejar em nada! *Bom pelo menos para mim*, tem tudo que necessítamos para uma boa codificação. A ideia da Google, é pegar tudo que **há de bom nas linguagem mais populares** e melhorar ainda o que essas mesmas tem de "ruim"... bem vamos as suas características.

* Segue o paradigma de orientação a objetos;
* Segue a sintaxe [C-like](https://en.wikipedia.org/wiki/C_syntax), deixando familiar a maioria das linguagens mais populares;
* Segue o conceito de ser uma linguagem fortemente tibada, por mais que contemple o tipo [dynamic](https://dart.dev/guides/language/type-system);
* Segue a conceito do "[Type inference](https://en.wikipedia.org/wiki/Type_inference)", tem a capacidade de inferir o tipo da variável conforme a atribuição de valor.
* Segue um conceito de ser minimalista na implementação, como no exemplo de Java, para tornar algo privado escreve-se `private` na frente, no caso do dart somente `_` colocando um underline basta. Além disso possibilitar a implementação do mesmo trecho de código de forma breve e consistênte, como explicarei logo abaixo.
* Segue conceito de compilação [ahead-of-time (AOT)](https://pt.wikipedia.org/wiki/Compila%C3%A7%C3%A3o_AOT), quando código é compilado diretamente para binário (código de máquina) o que possibilita a alta performance nativa;
* Segue conceito de compilação **just-in-time (JIT)**, possibilitando a compilação diretamente no *device*, com a aplicação ainda em execução, facilitando muito no ciclo do desenvolvimento. O que chamamos hoje de [hot-reload](https://flutter.dev/docs/development/tools/hot-reload);
* Segue com o conceito de [plugins](https://dart.dev/tools) para [IDE's](https://pt.wikipedia.org/wiki/Ambiente_de_desenvolvimento_integrado), não foi criado uma IDE propria para o seu desenvolvimento, em vez de tirar o desenvolver do conforto de sua IDE, ele proporciona ao instalar um plugin possa utilizar da mesma para o desenvolvimento em Dart/Flutter;
* Segue o conceito de linguagem [case sensitive](https://pt.wikipedia.org/wiki/Case-sensitive);
* Segue [open-source](https://github.com/dart-lang);
* Segue com boa documentação e uma comunidade em constante crescimento;

Bem eu sei que posso ter esquecido de algo, pois para cada desenvolvedor que se aventura no mundo de cada linguagem, para ele vai existir boas e más características.... Sempre que lembrar de algo irei editar o artigo.


## 2. Preparando o ambiente

Por ser uma linguagem moderna e bem documentada, mantida pela Google, navegando pela internet encontramos vários e vários tutoriais que nos ensinam a preparar um ambiente para desenvolvimento/teste em Dart, irei deixar um artigo em que escrevi sobre preparar o **[ambiente Flutter no Linux](https://www.paulocagol.dev.br/2021/04/00002-linux-install-flutter-ambient/)**, e ainda o **[DartPad](dartpad.dev)**, uma pagina que possibilita testar essa magnifica linguagem.

Como meu ambiente já está preparado e já temos instruções sobre a preparação vou seguir do principio que irá utilizar do meu artigo, ou do DartPad.

## 3. Boas praticas a codificação

Caso deseje ler as boas praticas de codificação em que a Google nos passa sobre a linguagem basta acessar o link **[Dart Guides](https://dart.dev/guides)** que ao finalizar essa leitura muitas dúvidas e maneira de como proceder em diversos casos serão sanadas.

Tentarei resumir o máximo que puder nesse trecho sobre o assunto.

O que nos é apresentado logo de cara, é que a linguagem sempre, ou na grande maioria das vezes nos proporcionará dois tipos de escrita, a **breve** e a **consistente**. 

A breve, se resume em codificar algo de forma "curta" (menos linhas) e a consistente em codificar algo de forma mais "explicativa" ou, legível, onde no mesmo documento é relatado a não utilização excessiva da forma breve pois pode ocasionar a difícil interpretação de código. Abaixo irei dar dois exemplos do que estou falando.

**Consistente**:
```dart
class Pessoa {
  String nome = '';
  
  Pessoa(String nome) {
    this.nome = nome;
  }
}

void main() {
  Pessoa pessoa = new Pessoa('Paulo');  
  print(pessoa.nome);
}

saída ~> Paulo
```

**Breve**:
```dart
class Pessoa {
  String nome;
  
  Pessoa(this.nome);
}

void main() {
  var pessoa = Pessoa('Paulo');  
  print(pessoa.nome);
}

saída ~> Paulo
```

Claro que possivelmente esse não seja o melhor exemplo sobre dificultar a interpretação de código mas, já da pra se ter uma base.

Ainda na documentação nos é recomentado ativar os **[linter rules](https://dart.dev/guides/language/analysis-options#enabling-linter-rules)** para que o Dart possa notificar de acordo com as regras escolhidas.

Um exemplo bem básico sobre lint que é pego pelo [dart analyzer](https://pub.dev/packages/analyzer) é criar uma função que retorna algo, mas não implementar o seu retorno.

{{< image src_s="content/images/posts/2021-04-21-16-57-38.png" src_l="content/images/posts/2021-04-21-16-57-38.png">}}

Porém tudo isso é configurável via de regra.

## 4. Tipos de dados 🎲

Uma das características fundamentais em uma linguagem de programação é o conjunto de tipos de dados que ela suporta. Esses são os tipos de valores que podem ser representados e manipulados em uma linguagem de programação. No caso do Dart, podemos ver abaixo.

| Tipo de dados  | Key | Descrição  |
|---|---|---|
| Número | int, double, num  | Os números no Dart São usados para representar literais numéricos |
| Caracteres | String | Respresenta um conjunto de caracteres  |
| Valores Condicionais | bool | Interpreta valores condicionais `true` e `false` |
| Listas | List | Representa um grupo de objetos |
| Mapas | Map | Representa um conjunto de valores com pares composto de `key` e `value` |

### 4.1. Tipos numéricos 🔢

Como explicado os números podem ser classificados de três formas.

* `int` é utilizado para representar números inteiros, como números de 16 bits;
  * ```dart
    int num1 = 2; 
    ```
* `double` é utilizado para representar números de ponto flutuante de 64 bits;
  * ```dart
    double num2 = 1.5;  
    ```
* `num` é utilizado para representar um número inteiro ou de ponto flutuante. Não muito utilizado.

### 4.2. Tipo caracteres 🔤

Utilizado para representar um conjunto de caracteres, é uma sequencia de unidades de código [UTF-16](https://pt.wikipedia.org/wiki/UTF-16). A palavra reservada `String` é usada para representar valores literais em texto. Os valores são incorporados em aspas simples ou duplas.

```dart
String string = "Dart"; 
String str = 'Dart'; 
String str1 = string + str;  
```

### 4.3. Tipos condicionais 🆗

Representa valores condicionais `true` ou `false`. A palavra reservada é `bool`.

```dart
String string = "Dart"; 
String str = 'Dart'; 

bool val = (string == str);
bool val1 = true;
bool val2 = false;
```

### 4.4. Tipo lista ✔️

O tipo de dado lista é semelhante a matrizes. Uma lista é usada para representar uma coleção de objetos.

```dart
List strings = new List(4);
strings[0] = 'String1';
strings[1] = 'String2';
strings[2] = 'String3';
strings[3] = 'String4';
```

### 4.2. Tipo mapa 🗺️

O tipo de dado mapa é um objeto de "par" chave e valor. Chaves e valores em um mapa podem ser de qualquer tipo. É uma coleção dinâmica.

```dart
Map map = new Map();
map['primeiro'] = 1;
map['segundo'] = 2;
map['terceiro'] = 3;
map['quarto'] = 4;
```

## 5. Operações aritméticas ➗

Os tipos numéricos (int, double e num) mencionados anteriormente fornecem alguns métodos e propriedades que podem ser utilizados para transformações/operações. Além disso fornecem também a capacidade para expressões utilizando operadores `+ (adição)`, `— (subtração)`, `* (multiplicação)`, `/ (divisão)` e `% (resto da divisão)`.

Vou listar abaixo alguns métodos que podem ser utilizados sobre essa tipagem. Note que esses métodos podem ser utilizados como [helpers](https://en.wikipedia.org/wiki/Helper_class).

| Método | Descrição |
|---|---|
| `abs()`  | Retorna o valor absoluto do número.  |
| `ceil()`  | Retorna o último inteiro imediatamente superior.  |
| `ceilToDouble()`  | Retorna o último número imediatamente superior com o tipo double.  |
| `clamp(num min, num max)`  | Se o número estiver dentro do limite, retorna o número. Se não, retorna o limite o qual ele extrapolou.  |
| `compareTo(num outro)` | Compara com outro número, retornando 1 quando forem diferentes e 0 quando forem iguais.  |
| `floor()`  | Funções matemáticas |
| `floorToDouble()`  |  Arredonda o número para o número inteiro anterior no tipo double. |
| `remainder(num outro)`  | Retorna a sobra da divisão com outro número.  |
| `round()`  | Arredonda o número para o inteiro mais próximo.  |
| `roundToDouble()`  | Arredonda o número para o valor inteiro mais próximo no tipo double.  |
| `toDouble()`  | Converte o número para Double.  |
| `toInt()`  | Converte o número para Int.  |
| `toString()`  | Converte o número em uma String. |
| `toStringAsExponential([int digitos])`  | Converte para string com exponencial.  |
| `toStringAsFixed(int decimais)`  | Converte para String contendo N casas decimais.  |
| `toStringAsPrecision(int digitos)`  | Converte para String contendo N dígitos.  |
| `truncate()`  | Retira as casas decimais, retornando um inteiro.  |
| `truncateToDouble()`  | Retira as casas decimais, retornando um double.  |

## 6. Operadores relacionais

| Operadores  | Descrição  |  Uso |
|---|---|---|
| >  | Menor que  | `2 > 1`  |
| <  | Maior que  | `1 < 2`  |
| >=  | Maior ou igual  | `2 >= 2` |
| <=  | Menor ou igual  | `1 <= 2`  |
| ==  | Igual  | `1 == 1`  |
| !=  | Diferente  | `0 != 1`  |


## 7. Estrutura de condição

Como em qualquer outra linguagem precisamos trabalhar com condições, no caso de Dart e como na grande maioria das linguagens estamos bem servidos com `if`, `else`, `? :` (if ternário), `??` (checagem de valor nulo) e `switch`. Irei demostrar cada um deles em código abaixo.

* Condicional **`if`**
```dart
  if (2 > 1) {
    print('2 é maior que 1');
  }
```

* Condicional **`else`**
```dart
  if (1 > 2) {
    print('1 é maior que 2');
  } else {
    print('1 não é maior que 2');
  }
```

* Condicional **`? :`**
```dart
  print(1 > 2 ? '1 é maior que 2' : '1 não é maior que 2');
```

* Condicional **`??`**
```dart
  String valor;
  print(valor ?? 'Não informado');

  String valor = 'Valor';
  print(valor ?? 'Informado');
```

* Condicional **`switch`**
```dart
  String cor = 'verde';
  
  switch(cor){
    case 'vermelho':
      print('É vermelho');
      break;
    case 'amarelo':
      print('É amarelo');
      break;
    case 'verde':
      print('É verde');
      break;
    default:
      print('Cor não encontrada');
  }
```

## 8. Estrutura de repetição 🔁

Agora iremos falar sobre sobre os "loop" ou laços de repetição, em dart como nas demais linguagens temos, `for`, `for...in`, `forEach`, `while` e o `do while`.

### 8.1. Laço "for"

Normalmente utilizado em listas, quando já sabemos a quantidade de elementos que temos que percorrer.

```dart
List<String> listaDeNomes = ['Paulo', 'José', 'Cagol'];
for(int i = 0; i < listaDeNomes.length; i++) {
  print(listaDeNomes[i]);
}
```

#### 8.1.1. Laço "for...in"

```dart
List<String> listaDeNomes = ['Paulo', 'José', 'Cagol'];
for(String nome in listaDeNomes) {
  print(nome);
}
```

### 8.2. Laço "forEach"

Um método helper das listas que realiza uma ação programada para cada elemento percorrido.

```dart
List<String> listaDeNomes = ['Paulo', 'José', 'Cagol'];
listaDeNomes.forEach((nome) {
  print(nome);
});
```

### 8.3. Laço "while"

O while é um laço que executa um determinado bloco de código enquanto uma condição for verdadeira. Normalmente utilizado quando não sabemos a quantidade de vezes que deve percorrer os elementos.

```dart
int contador = 0;
while(contador < 10) {
  print(contador);
  contador++;
}
```

### 8.4. Laço "do while"

Muito parecido com o `while` em si, porém o `do while` chega a condição de saída no final. 

```dart
int contador = 0;
do {
  print(contador);
  contador++;
} while(contador < 10);
```

## 9. Estrutura de funções

As funções são blocos de código que executam alguma operação. Quando utilizadas sozinhas, são chamadas de funções. Quando associadas a algum objeto, são chamadas de métodos.

A função `main()`. Em Dart é a função mais importante, é onde o código começa executar, caso entre nesse momento no [DartPad](https://dartpad.dev/) verá que a mesma já vem codificada.

```dart
void main() {
  ...
}
```

A palavra reservada `void` indica que a função não tem retorno, quer dizer que ela somente executa uma instrução de código mas não resulta nada a partir dela, de certa forma. Por exemplo abaixo demostro uma função denominada `somar` com retorno, no caso resultando a soma de dois valores.

```dart
double somar(double a, double b) {
  return a + b;
}

void main() {
  var soma = somar(somar(1, 1));
  print(soma);
}
```

Note que entre parenteses `"(double a, double b)"` foi declarado duas variáveis, em métodos e funções isso se chama [`parâmetros`](https://pt.wikipedia.org/wiki/Par%C3%A2metro_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o)#:~:text=Na%20ci%C3%AAncia%20da%20computa%C3%A7%C3%A3o%2C%20um,comportamento%20em%20tempo%20de%20execu%C3%A7%C3%A3o.), você pode passar qualquer tipo de variável por parâmetro em uma função, até mesmo outra função!! Isso é feito muito no Flutter, quando abordar Flutter em um artigo demostrarei.

----

Bem irei finalizar o artigo por aqui, falando sobre funções, porém o Dart como qualquer outra linguagem envolve muito mais do que escrevi, conforme vai se aprofundando, estudando cada vez mais, conseguirá notar a grande variedade de alternativas para implementações... Como tudo em nossa área, nunca deixe de continuar estudando e se aperfeiçoando, pois sempre tem novidade para aprender, fico por aqui, grande abraço e até a próxima 👋

---

> Fonte: [Paulo J. Cagol](www.paulocagol.dev.br)
