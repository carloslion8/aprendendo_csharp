# Lists
Uma List (às vezes chamada de sequência) é uma coleção ordenada que pode conter elementos duplicados. Como os arrays, índices de uma lista seguem a numeração baseada em zero (Zero-based numbering)[¹](https://en.wikipedia.org/wiki/Zero-based_numbering). As listas ordenadas herdam das interfaces IEnumerable, ICollection e IList. Nessa categoria estão as estruturas **ArrayList** e **LinkedList**.  A classe ArrayListé uma implementação de array redimensionável. 
## Diferenças de Performance
Inserir um elemento entre os elementos existentes de um ArrayList é uma operação ineficiente — todos os elementos depois do novo devem ser removidos, o que pode ser uma operação cara em uma coleção com um grande número de elementos. Uma LinkedList permite a inserção (ou remoção) eficiente dos elementos no meio de uma coleção, mas é muito menos eficiente que um ArrayList para pular para um elemento específico na coleção.
|          | ArrayList | LinkedList      |
|----------|-----------|-----------------|
| get()    | O(1)      | O(n)            |
| add()    | O(1)      | O(1) amortizado |
| remove() | O(n)      | O(n)            |