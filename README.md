# Programação funcional em Scala

### Motivação: 
Testar paradigmas estudados em Haskell presentes em uma linguagem diferente, aprendendo conceitos, 
testando exemplos, criando pequenos códigos e fazendo contrapontos entre as semelhanças.

## Funções de alta ordem em Scala

### Filter:

A função filter() é utilizada para selecionar todos os elementos de uma lista que satisfaçam um predicado declarado.

* O retorno será uma nova lista composta por todos os elementos da lista que satisfassam o predicado fornecido.

#### Implementação:
```
object FuncF
{ 
    // metodo main
    def main(args:Array[String])
    {
        // criando nossa lista
        val lista = List(2, 10, 22, 13)
          
        // aplicando a funcao filter()
        val resultado = lista.filter(_ < (6*2)) 
        // Note que podemos usar usar a aritmetica dentro do filter, como por exemplo (6*2)
          
        // saida
        println(resultado)
    }
}
```

Nossa saída seria algo do tipo: "List(2, 10)"

### Map:

A função map() aplica uma função a cada elemento de uma lista. Tem uma implementação bem simples e retorna uma nova 
lista do mesmo tipo que a lista de origem.

#### Implementação usando função anônima:

```

object FuncMap
{     
    // metodo main
    def main(args:Array[String])
    {
        // criando nossa lista
        val lista = List(25, 8, 19, 84, 37)
  
        // transformando a lista
        val nova_lista = lista.map(x => ((x - (x*2))))
        // Assim como no filter, podemos usar usar a aritmetica dentro do map, como por exemplo ((x - (x*2))),
        // mas também é possivel passar os argumentos de uma função, como no exemplo a seguir:
        
        println(nova_lista)
    }
}
```
Nossa saída vai ser: "List(-25, -8, -19, -84, -37)"

#### Implementação usando função definida:

```
object FuncMapD
{
    // funcao para transformar o numero em negatico
    def negative(x:Int):Int
    =
    {
        ((x - (x*2)))
    }
  
    // metodo main
    def main(args:Array[String])
    {
        // criando a nossa lista
        val lista = List(25, 8, 19, 84, 37)
      
        // transformando a lista
        val nova_lista = lista.map(negative)
        // agora estamos utilizando os argumentos passados pela funcao(negative) no map
        
        println(nova_lista)
    }
}
```
Novamente nossa saída vai ser: "List(-25, -8, -19, -84, -37)"

#### Implementação de uma integração entre as duas funções:

```
object FuncMF
{     
    def main(args:Array[String])
    {
        val lista = List(25, 8, 19, 84, 37)

        val nova_lista = lista.map(x => ((x - (x*2))))
        
        val resultado = nova_lista.filter(_ > 0)

        println(resultado)
    }
}
```
Nossa saída vai ser: "List()", pois como todos os valores foram passados para sua forma negativa, o filter não encontrou 
nenhum valor maior do que zero.

### Função Reverse:

A função reverse() é utilizada para retornar uma pilha com a ordem invertida.

#### Implementação:

```

import scala.collection.mutable._
//eh necessario importar essa biblioteca
object GfG 
{ 
    // metodo main
    def main(args:Array[String]) 
    { 
      
        // criando a pilha
        val pilha = Stack(5, 4, 3, 2, 1) 

        // aplicando a funcao reverse()
        val resultado = pilha.reverse
          
        // printando a pilha invertida:
        print("Reversed " + resultado) 
    } 
} 
```

Nossa saída vai ser: "Reversed Stack(1, 2, 3, 4, 5)"

### Função DropWhile:

O método dropWhile() é utilizado para eliminar o prefixo de elementos mais longo do conjunto que satisfaça a condição declarada.

Obs: Eu fiquei confuso nessa função aqui e apesar de ser simples, demorei bastante para entender o funcionamento dela.

#### Implementação:

```

object GfG 
{ 
    // Main method 
    def main(args:Array[String]) 
    { 
      
        // Creating a list 
        var s1 = Set(1, 3, 5, 4, 2) 
          
        // Print the set
        println(s1)
          
        // Applying dropWhile method 
        var res = s1.dropWhile(x => {x % 2 != 0}) 
          // peguei esse código pronto e pelo que eu entendi, ele remove o primeiro e último elemento 
          //que satisfaçam a condição expressa, foi oque consegui compreender executando e modificando o código algumas vezes.
          // a ordem de impressão ainda me deixou um pouco confuso.
          
        // Displays output 
        println(res)  
    } 
}
```

### Referências:
https://acervolima.com/metodo-scala-set-dropwhile-com-exemplo/
https://www.geeksforgeeks.org/scala-list-filter-method-with-example/
https://www.geeksforgeeks.org/scala-map-method/






