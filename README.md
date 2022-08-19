# Programação funcional em Scala

## Funções de alta ordem em scala

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








