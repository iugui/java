# Estrutura de dados

## 1 - Collection

![1717425425724](image/resumo/1717425425724.png)

## 2 - Interfaces

### 2.1 - List

Nos permitem criar uma coleção de dados ordenados.

- Podemos acessar os elementos através dos indices
- Podemos armazenar elementos nulos em listas

As 3 principais classes que implementam a interface List são:

- ArrayList
- LinkedList
- Stack

**Principais métodos de List**

| Método                     | Descrição                                                         |
| --------------------------- | ------------------------------------------------------------------- |
| add(int indice, elemento)   | Adiciona um elemento em uma posição específica                   |
| add(elemento)               | Adiciona um elemento ao final da lista                              |
| clear()                     | Limpa a lista                                                       |
| get(int indice)             | Pega o valor no indice específicado                                |
| isEmpty()                   | Verifica se a lista está vazia                                     |
| contains(elemento)          | Retorna true se o elemento está na lista e false se não estiver   |
| indexOf(elemento)           | Retorna o índice de um elemento, caso não encontre retornará -1. |
| remove(indice)              | Remove o elemento do índice especificado;                          |
| remove(elemento)            | Remove a primeira ocorrência do elemento especificado              |
| set(indice, elemento)       | Substitui o novo elemento no indice especificado                    |
| sort(Comparador)            | Ordena a lista de acordo com o comparator                           |
| subList(doIndice,ateIndice) | Pega um intervalo específico da lista                              |
| size()                      | Retorna o tamanho de uma lista                                      |

Referência: https://www.javatpoint.com/java-list

**Criando uma lista utilizando o ArrayList**

```java
import java.util.List;
import java.util.ArrayList;

public class App {
    public static void main(String[] args){
        // Criando uma lista através da classe ArrayList
        List<String> nomes = new ArrayList<String>();

        // Adicionando itens a lista
        nomes.add("Maria");
        nomes.add("Joana");
        nomes.add("Beatriz");

        // Imprimindo os itens de uma lista
        for (String nome : nomes){
            System.out.println(nome);
        }

        // Ordenando uma lista com a classe Collection
        nomes.sort(null);

        // Imprimindo a lista ordenada
        for (String nome : nomes){
            System.out.println(nome);
        }
    }
}
```

### 2.2 - Queue

É uma lista ordenada de objetos onde a inserção de um elemento ocorre ao final (Tail) da lista e a remoção de um elemento ocorre no início (Head) da lista.

![1717436553674](image/resumo/1717436553674.png)

As principais classes que implementam a interface Queue são

* LinkedList
* PriorityQueue

As duas Classes acima não são implementações seguras de thread. PriorityBlockingQueue é uma opção para esse caso.

- Utiliza o conceito de First In First Out (FIFO) para inserção e exclusão de elementos de uma queue.
- A NullPointerException é lançada se alguma operação null ocorrer em BlockingQueues

**Principais métodos de queue**

| Método         | Descrição                                                                      |
| --------------- | -------------------------------------------------------------------------------- |
| add(elemento)   | Insere um elemento e retorna true em caso de sucesso.                            |
| offer(elemento) | Insere um elemento na queue                                                      |
| remove()        | Retorna e remove o elemento da queue                                             |
| poll()          | Retorna e remove o elemento da queue. Retorna null se a queue estiver vazia      |
| element()       | Retorna mas não remove o elemento da frente da queue                            |
| peek()          | Retorna e não remove o elemento da queu ou retorna null se a queu estiver vazia |

### 2.3 - Deque

É uma coleção linear que suporta inserção e exclusão de elementos pelos dois finais.
O nome deque é uma abreviação de double-ended queue.

**Principais métodos de Deque:**

| Método                         | Descrição                                                                                          |
| ------------------------------- | ---------------------------------------------------------------------------------------------------- |
| add(elemento)                   | Insere um elemento                                                                                   |
| addFirst(elemento)              | Insere um elemento na frente do Deque                                                                |
| addLast(elemento)               | Insere um elemento ao final do Deque                                                                 |
| contains(elemento)              | Retorna true se o Deque contém o elemento                                                           |
| element()                       | Retorna o elemento da frente do Deque                                                                |
| getFirst()                      | Pega o elemento da frente do Deque mas não o exclui                                                 |
| getLast()                       | Pega o elemento do rabo do Deque mas não o exclui                                                  |
| offer(elemento)                 | Insere o elemento no Deque e retorna true se houver sucesso e falso e não tiver espaço disponível |
| offerFirst()                    | Insere o elemento na Cabeça do Deque a menos que viole a capacidade de restrição                  |
| offerLast()                     | Insere o elemento no Rabo do deque a menos que viole a restrição de capacidade                     |
| peek()                          | Retorna mas não move o cabeça do Deque ou retorna null se o Deque estiver vazio                    |
| peekFirst()                     | Retorna mas não move o primeiro elemento do Deque ou retorna null se o Deque estiver vazio          |
| peekLast()                      | Retorna mas não remove o elemento no rabo do Deque ou retorna null se o Deque estiver vazio.        |
| poll()                          | Retorna e remove o elemento cabeça do Deque ou retorna null se o Deque estiver vazio                |
| pollFirst()                     | Retorna e remove o primeiro elemento do Deque ou retorna null se o Deque estiver vazio.              |
| pollLast()                      | Retorna e remove o último elemento do Deque ou retorna null se estiver vazio                        |
| pop()                           | Retira um elemento da pilha                                                                          |
| push()                          | Empurra um elemento na pilha                                                                         |
| remove()                        | Retorna e remove o cabeça da queue representado pelo Deque                                          |
| remove(elemento)                | Remove a primeira ocorrência do elemento                                                            |
| removeFirst()                   | Retorna e remove o primeiro elemento do Deque                                                        |
| removeFirstOccurrence(elemento) | Remove a primeira ocorrência do elemento                                                            |
| removeLast()                    | Retorna e remove o último elemento do Deque                                                         |
| removeLastOccurrence(elemento)  | Remove a última ocorrência do elemento do Deque                                                    |
| size()                          | Retorna o tamanho do Deque                                                                           |

## 3 - Classes

### 3.1 - ArrayList

Funcionam de forma parecidas com os arrays, porém, não possuem tamanho fixo. Podemos adicionar ou remover elementos.
O ArrayList implementa a interface List, logo, todos os métodos vistos em List estão disponíveis em ArrayList.

- Não possuem tamanho fixo
- Pode conter elementos duplicados
- Mantém a ordem de inserção
- A classe ArrayList não é sincronizada
- A manipulação de ArrayLists é um pouco mais lenta do que em LinkedList.
- Não podemos criar ArrayLists de tipos primitivos, precisamos utilizar wrapper class.

**Para declarar um ArrayList**

```java
import java.util.ArrayList;
ArrayList<Tipo> nomeDoArrayList = new ArrayList<tipo>();
```

**Métodos (além dos métodos do List)**

| Método                          | Descrição                                                  |
| -------------------------------- | ------------------------------------------------------------ |
| removeIf(filtro)                 | Remove um item de acordo com o filtro                        |
| removeRange(doIndice, ateIndice) | Remove um intervalo de um indice inicial até o indice final |

**Exemplo:**

```java
import java.util.ArrayList;

public class App {
    public static void main(String[] args){
        // Declarando uma variável do tipo ArrayList
        ArrayList<String> nomes = new ArrayList<String>();

        // Adicionando itens a listas
        nomes.add("Maria");
        nomes.add("Carlos");
        nomes.add("Joana");

        // Pegando o tamanho de um ArrayList
        int tam = nomes.size();
        System.out.println(tam);

        // Desempacotando um ArrayList
        String nome1 = nomes.get(0);
        System.out.printf("O primeiro nome é %s \n", nome1);

        // Imprimindo os itens de uma lista
        for (String nome : nomes){
            System.out.println(nome);
        }

        // Mudando o valor de um elemento
        nomes.set(0, "Mariana");

        // Removendo itens de ArrayLists
        nomes.remove(2);
        for (String nome : nomes){
            System.out.println(nome);
        }

        // Limpando uma lista
        nomes.clear();
        System.out.println(nomes.size());

        // Criando um ArrayList do tipo Inteiro
        ArrayList<Integer> numeros = new ArrayList<Integer>();

        numeros.add(1);
        numeros.add(2);
        numeros.add(3);

        numeros.forEach(elemento -> imprimeQuadrado(elemento));
    }

    static void imprimeQuadrado(int num){
        System.out.println(Math.pow(num,2));
    }
}
```

**Exemplo 2:**

```java
import java.util.ArrayList;

public class App {
    public static void main(String[] args){
        // Criando um ArrayList
        ArrayList<Integer> numeros = new ArrayList<Integer>();

        // Adicionando elementos
        numeros.add(524);
        numeros.add(-333);
        numeros.add(53);
        numeros.add(-5);

        // Removendo elementos menos que zero
        numeros.removeIf(numero -> numero < 0);

        // Imprimindo um ArrayList
        for (int numero : numeros){
            System.out.println(numero); // 524 53
        }

    }
}
```

### 3.2 - LinkedList

### 3.3 - PriorityQueue

Nos permitem criar filas de prioridades.

- Não permitem objetos null.
- Podemos adicionar apenas objetos comparáveis em PriorityQueue
- A fila de prioridade é construída como um heap mínimo, uma espécie de árvore binária. O elemento mínimo é uma raiz. Os objetos da fila de prioridade são ordenados por padrão em ordem natural.
- Podemos usar o comparator se precisarmos ordenação personalizada.
- PriorityQueue não é thread-safe, então é melhor usar PriorityBlockingQueue para trabalhar em um ambiente simultâneo.
- PriorityQueue fornece tempo O(log(n)) para métodos add e poll e O(1) para obter elementos mínimos.

Para ler mais sobre: https://codegym.cc/pt/groups/posts/pt.306.java-priority-queue-nao-e-uma-fila-classica