# Estrutura de Dados
Estrutura de Dados, são coleções - _sets_ (conjuntos) - de dados. Cada estrutura define formas de organizar essas coleções para que atendam determinada necessidade do Programa, seja performace, segurança... Em linguagens Orientadas a Objetos como Java e C#, as coleções são construídas através de Objetos, enquanto em liguagens procedurais como Pascal e C são construídas através de Records/Structs e Ponteiros, ou seja em C#, as Estruturas de Dados também são Objetos, assim como os dados que armazenam. 

Existem interfaces que definem as ações genéricas que cada grupo de coleções deve implementar. A **tabela abaixo** as interfaces usadas. 

Também é possivel usar essas interfaces para fazer as próprias implementações. As classes das coleções são partes do **namespace** System.Collections[¹](https://docs.microsoft.com/pt-br/dotnet/api/system.collections?view=netcore-2.2) que contêm todas as interfaces e classes que são necessárias para implementar coleções, divididas em Coleções (Classes e Interfaces usadas *somente* pelas implementações padrões da linguagem) e as Coleções Genéricas (Permitem especificar o tipo exato que será armazenado em uma coleção e fornecem os benefícios da verificação de tipo em tempo de compilação — o compilador emite mensagens de erro se você usar tipos inadequados nas coleções. Depois de especificar o tipo armazenado em uma coleção genérica, qualquer referência que você recupera da coleção terá esse tipo). 

| Interface             | Motivo                                                                                                                                                        | Doc.                                                                                                                           | Doc. Genérica                                                                                                                     |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| IEnumerable           | Enumera a coleção para dar suporte (permitir) o comando foreach.                                                                                              | [IEnumerable](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.ienumerable?view=netcore-2.2)                     | [IEnumerable&#60;T&#62;](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.generic.ienumerable-1?view=netcore-2.2)   |
| ICollection           | Implementa todas as ações que todas as coleções devem possuir, como o método CopyTo() assim como as propriedades Count, ISReadOnly, ISSynchronized e SyncRoot | [ICollection](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.icollection?view=netcore-2.2)                     | [ICollection&#60;T&#62;](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.generic.icollection-1?view=netcore-2.2)           |
| IComparer             | Compara dois objetos em uma coleção para que a coleção possa ser ordenada.                                                                                    | [IComparer](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.icomparer?view=netcore-2.2)                         | [IComparer&#60;T&#62;](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.generic.icomparer-1?view=netcore-2.2)               |
| IList                 | Implementa todas as ações de coleções que podem ser acessadas por índice.                                                                                     | [IList](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.ilist?view=netcore-2.2)                                 | [IList&#60;T&#62;](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.generic.ilist-1?view=netcore-2.2)                       |
| IDictionary           | Implementa todas as ações de coleções que são baseadas em chave-valor, como HashTable e SortedList.                                                           | [IDictionary](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.idictionary?view=netcore-2.2)                     | [IDictionary<TKey,TValue>](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.generic.idictionary-2?view=netcore-2.2) |
| IDictionaryEnumerator | Permite enumerar a coleção para dar suporte (permitir) o comando foreach quando ela implementa um IDictionary                                                 | [IDictionaryEnumerator](https://docs.microsoft.com/pt-br/dotnet/api/system.collections.idictionaryenumerator?view=netcore-2.2) |                                                                                                                                   |

**Obs:** Evite reinventar a roda — em vez de construir suas próprias estruturas de dados, utilize as interfaces e coleções da estrutura das coleções do C#, que foram cuidadosamente testadas e ajustadas para atender aos requisitos da maioria dos aplicativos. Este repositório e estudo é para entender como as coisas funcionam e não com o objetivo de _reescrever_ algo que foi implementado pela linguagem.

### Relação das Interfaces e Collections
![Relação das Interfaces](https://github.com/Camilotk/aprendendo_csharp/blob/master/Data%20Structures/interfaces_csharp.png)

## Indice de Estruturas de Dados
* básicas:
  - [Lists](https://github.com/Camilotk/aprendendo_csharp/tree/master/Data%20Structures/Lists)
  - [Sets](https://github.com/Camilotk/aprendendo_csharp/tree/master/Data%20Structures/Sets)
  - Dictionaries
* derivadas:
  - Heap
  - Queue
  - Tree
