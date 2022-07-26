# Vetores-em-Java-exp-teste-vetor

Ir para o conteúdo principal
Damares Costa de Souza 
Moodle - IFRS

Programação Básica com Java III - Turma 2022B
Painel Meus cursos  PBJIII2022B 2. Vetores  2.4. Uso de Vetores em Java
2.4. Uso de Vetores em Java
A linguagem Java, como a grande maioria das linguagens de programação de alto nível, permite que trabalhemos com vetores. Assim como vimos para os algoritmos, todo vetor em Java será uma variável, e como toda variável precisa ser declarado. A declaração de um vetor em Java é feita do seguinte modo:

tipo nome_da_variavel[] = new tipo [ tamanho ];

que também pode ser escrita em duas etapas, como segue:



tipo nome_da_variavel[];

nome_da_variavel = new tipo [ tamanho ];



Por exemplo, para declararmos um vetor numeros, com 20 posições, cada uma sendo capaz de armazenar um valor do tipo int, escrevemos:

int numeros[] = new int[20];

ou



int numeros[];

numeros = new int[20];


O operador new, utilizado na declaração do vetor acima, serve para a alocação do espaço de memória para o vetor. Alocar significa reservar, ou seja, aquele espaço de memória não poderá ser utilizado por outra variável ou vetor. Todas as variáveis que declaramos com tipos primitivos são alocadas automaticamente. Vetores em Java não. Por isso, é necessário o uso do operador new, pois um vetor só poderá ser utilizado após sua alocação.

Note que ao contrário dos algoritmos, não especificamos em Java a posição inicial e a posição final, mas somente o número de elementos. Em Java, o primeiro elemento sempre é representado pelo número zero. Logo, a declaração acima em pseudocódigo seria feita da seguinte forma:

var numeros : vetor [0..19] de inteiro

O último elemento sempre será representado pelo índice equivalente ao número de elementos do vetor menos 1. Por exemplo, no código acima, a última posição do vetor numeros será 19 e não 20.

Ao declarar um vetor, o tipo dos elementos e os colchetes podem ser combinados no início da declaração para indicar que todos os identificadores na declaração representam vetores, como em

double[] array1, array2;

que declara array1 e array2 como vetores do tipo double.

O programa abaixo mostra que o acesso a elementos de um vetor em Java é feita da mesma forma que em pseudocódigo, escrevendo-se o nome da variável seguida pelo número da posição desejada entre colchetes. 

public class TesteVetor {

public static void main(String[] args) {

int[] numeros = new int[20];

 

for(int pos = 1; pos <= 20; pos++)

numeros[pos - 1] = pos;

 

System.out.println(“Numeros de 1 a 20: ”);

for(int pos = 1; pos <= 20; pos++)

System.out.println(numeros[pos - 1]);

}


}


Vamos analisar o primeiro for. Este for coloca, em cada posição do vetor numeros, um número diferente de 1 a 20. A variável pos varia de 1 a 20. Como as posições do vetor são numeradas de 0 a 19 (pois o vetor foi alocado com 20 elementos), o número da posição foi calculado pela expressão pos – 1. Isso foi necessário, pois se deixássemos o acesso com o valor armazenado na variável pos aconteceria que, quando o for atingisse o número 20, o programa terminaria com um erro, pois foi acessada uma posição inválida do vetor. Uma solução semelhante foi feita no segundo for, utilizado para mostrar o conteúdo do vetor.

Existe uma outra forma de se alocar vetores em Java. Esta segunda forma nos permite alocar e inicializar os elementos do vetor de uma só vez. Para isso, basta escrevermos um sinal de igual e uma lista de inicializadores separados por vírgulas e colocados entre chaves, como mostrado abaixo:

int n[] = {10, 20, 30, 40, 50};

Essa instrução declarará um vetor n de elementos do tipo int, com a primeira posição contendo o valor 10, a segunda contendo o valor 20, a terceira contendo o valor 30, e assim por diante. O tamanho do vetor será determinado pelo número de elementos na lista de inicializadores, no caso acima 5. Observe que essa declaração não precisa do operador new para alocar o vetor.
O programa abaixo mostra uma reimplementação do programa anterior utilizando uma lista de inicializadores para criar o vetor numeros. Note que o primeiro for que utilizamos na primeira solução não foi mais necessário.



public class TesteVetor2 {

public static void main(String[] args) {

int[] numeros = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20 };

 

for(int pos = 1; pos <= 20; pos++)

System.out.println(numeros[pos - 1]);

}


 }



Um cuidado importante ao lidar com vetores em Java é não acessar posições inválidas do vetor. Índices negativos ou com valores maiores ou iguais ao tamanho do vetor geram erros de execução no programa conhecidos como exceções, que levam o programa a ser encerrado.

Para operações que envolvam todas as posições de um vetor (como fizemos em todos os problemas tratados até aqui neste capítulo), podem-se reduzir as chances de erros fazendo-se uso do fato de o vetor possuir uma propriedade chamada length. Esta propriedade armazena o tamanho do vetor . Poderíamos, por exemplo, reescrever a estrutura for do exemplo anterior dessa forma:



for(int pos = 1; pos <= números.length; pos++)

            System.out.println(numeros[pos - 1]);


Note que precisamos primeiro digitar o nome da variável que contém o vetor, seguida de um ponto e depois o nome da propriedade (length). Essa alternativa é, sem dúvida, mais adequada para a solução de problemas que envolvam o vetor como um todo. Supondo que, no futuro, o vetor números mude de tamanho, essa segunda expressão continuaria válida, enquanto a primeira teria de ser localizada e alterada.

Última atualização: domingo, 1 nov 2020, 18:36
Seguir para...
Academi
Dúvidas? 
Perguntas frequentes

Fale conosco | Suporte | Contato

Informação
Termos e Condições de Uso
Aviso de Privacidade e Proteção de Dados Pessoais
Contato
Rua Gen. Osório, 348, Bento Gonçalves/RS
Siga-nos
Copyright © 2017 - Desenvolvido por LMSACE.com. Distribuído por Moodle
