# HashSet
Os HashSets (Conjunto de Dispersão) é um tipo de estrutura que tenta otimizar o trabalho de uma Lista para que contenha apenas valores únicos. Além disso, a garantia de unicidade também facilida o trabalho de busca por determinado item, uma vez em que o HashSet categoriza os items armazenados de forma que consiga garantir de forma eficiente que não há nenhum elemento duplicado. Os HashSets depedem diretamente da função **.GetHashCode()** que pertence à Classe Object do C#, essa função retorna um código único**¹** para cada objeto o que garante que cada objeto contido no Conjunto é único. 

Assim como LinkedLists implementam um Array primitivo que armazena os objetos passados, os HashSets implementam uma estrutura de Dicionário que recebe dois valores, o valor passado em si e o objeto que representa se o objeto passado já está inserido ou não. 

<div align="center">
  <figure>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/7d/Hash_table_3_1_1_0_1_0_0_SP.svg/320px-Hash_table_3_1_1_0_1_0_0_SP.svg.png">
    <br>
     <figcaption>
        <i style="font-size=6px;">Exemplo de HashTable - Dicionário - que armazena os elementos.</i>
     </figcaption>  
   </figure>
</div>

## Implementação básica em C#
- [MyHashSet.cs](https://github.com/Camilotk/aprendendo_csharp/blob/master/Data%20Structures/Sets/HashSet/Implementation/MyHashSet.cs)

## Imports
**Linhas 1 e 2**

Para que possamos utilizar a estrutura de dicionário padrão do C# para implementar nosso HashSet é necessário primeiro importar as coleções genéricas.

```C#
using System;
using System.Collections.Generic;
```

### Propriedades
**Linhas 17 a 22**

A propriedade **map** é a HashTable (Tabela de Disperção) que guarda os objetos passados, a maior parte das implementações já vem por default dos métodos que a classe Dictionary<T, K> das collections de C# possui.

A propriedade PRESENT é uma propriedade imutável do tipo objeto sem implementação derivada que representa o objeto adicionado, ele serve para checar se um dos objetos inseridos já está no conjunto ou se o objeto buscado está presente no conjunto.

A propriedade do tipo unsigned integer (inteiro positivo ou I<sup>+</sup>) é o número de elementos já adicionados ao conjunto.

```C#
Dictionary<T, Object> map;
private static readonly Object PRESENT = new Object();
private uint numberOfElements;
```
### Método Construtor
**Linhas 24 a 28**

O método construtor público e sem parâmetros simplesmente inicializa o número de elementos em 0 e instancia o novo dicionário que irá guardar os elementos do HashSet. 

```C#
public MyHashSet()
{
  numberOfElements = 0;
  map = new Dictionary<T, object>();
}
```

### Método .Add()
**Linhas de 34 a 58**

O método **.Add(** *Object* **)** recebe um item do tipo genérico do HashSet e utiliza a estrutura de try-catch para tentar adicionar esse elemento no dicionário **map**, caso seu Hash já esteja registrado em map, irá retornar uma exeção **ArgumentException** que será tratada e irá imprimir no console que esse objeto já está adicionado ao map. Qualquer outra exceção retorna falso.

```C#
public bool Add(T item)
{
  try
  {
    map.Add(item, PRESENT);
    numberOfElements++;
    return true;
  }
  catch(ArgumentException e)
  {
    Console.WriteLine(e.Message);
    return false;
  }
  catch(Exception)
  {
    return false;
  }
}
```

### Método .Clear()
**Linhas 60 a 64**

Simplesmente limpa o map, utiliza-se da própria implantação do mesmo.
```C#
public void Clear()
{
  map.Clear();
}
```

### Método .Contains()
**Linhas 66 a 71**

Retorna um valor booleano se o elemento do tipo genérico passsado está presente no HashSet, utiliza-se da própria implantação do mesmo.
```C#
public bool Contains(T item)
{
  return map.ContainsKey(item);
}
```

### Método .Remove()
**Linhas 78 a 82**

No caso de C# - diferentemente de Java - a função .Remove() de map retorna um valor booleano que diz se o objeto foi corretamente removido, o que nos permite dispensar o uso de try-catch simplesmente retornando o retorno da função de map.

```C#
public bool Remove(T item)
{
  return map.Remove(item);
}
```

## Exemplo de Uso
Podemos passar todos os itens de uma lista para um conjunto com a finalidade de garantir que não haja itens repetidos.

```C#
using System;
using System.Collections.Generic;
using SetsTest.HashSet;

namespace SetsTest
{
    class Program
    {
        // Oranges, peach, pears, plums, syringes
        static void Main(string[] args)
        {
            List<string> fruits = new List<string>(){
                "apples",
                "oranges",
                "peaches",
                "pears",
                "oranges",
                "pears",
                "blueberrys",
                "apples"

            };

            MyHashSet<string> fruits_group = new MyHashSet<string>();
            Console.WriteLine("---------");
            foreach (var fruit in fruits)
            {
                fruits_group.Add(fruit);
            }
            Console.WriteLine("---------");
            foreach (var fruit in fruits_group)
            {
                Console.WriteLine(fruit);
            }
            Console.WriteLine("---------");
            Console.WriteLine("Elementos no Conjunto: {0}", fruits_group.Count);
        }
    }
}
```
**Output:**
```
---------
An item with the same key has already been added. Key: oranges
An item with the same key has already been added. Key: pears
An item with the same key has already been added. Key: apples
---------
apples
oranges
peaches
pears
blueberrys
---------
Elementos no Conjunto: 5
```
# Referências
 - [How HashSet is internally implemented in Java?](https://codepumpkin.com/hashset-internal-implementation/)
 - [VERY simple C# Set implementation](https://codereview.stackexchange.com/questions/126263/very-simple-c-set-implementation/126266)
 - [Lidando com conjuntos](https://www.caelum.com.br/apostila-csharp-orientacao-objetos/lidando-com-conjuntos/)
 - [Set - Wikipedia](https://en.wikipedia.org/wiki/Set_(abstract_data_type))
 - [HashTable - Wikipedia](https://en.wikipedia.org/wiki/Hash_table)
