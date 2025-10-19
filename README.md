# Análise e Implementação do Algoritmo de Dijkstra (Busca de Custo Uniforme)

## Informações do Projeto

* **Disciplina:** Inteligência Artificial (IA)
* **Instituição:** Universidade Estadual de Santa Cruz (UESC)
* **Professor:** Esbel Tomas Valero Orellana
* **Alunos:** Gabriel Rosa Galdino, Rodrigo Almeida Piropo
* **Contexto:** Este trabalho foi desenvolvido como resposta a uma prova oral da disciplina, focando na análise, implementação e aplicação do Algoritmo de Dijkstra.

## Visão Geral

Este projeto, contido no Jupyter Notebook `dijkstra.ipynb`, explora o Algoritmo de Dijkstra, também conhecido como Busca de Custo Uniforme (UCS), desde seus fundamentos teóricos até sua aplicação prática e limitações.

## Estrutura do Notebook

O notebook está dividido em quatro seções principais:

### 1. Análise da Busca de Custo Uniforme (Dijkstra)

Uma análise teórica do algoritmo, definindo-o como uma busca de "Melhor Primeira Escolha" que utiliza uma fila de prioridades ordenada pelo custo do caminho acumulado ($g(n)$).

As propriedades analisadas incluem:
* **Completude:** Sim, desde que os custos das ações sejam positivos.
* **Otimização:** Sim, o algoritmo sempre encontra a solução de menor custo.
* **Complexidade:** A complexidade de tempo é analisada, notando-se $O(E + V \log V)$ com implementações otimizadas (como heaps).

### 2. Comparativo: UCS (Dijkstra) vs. BFS vs. A\*

O caderno apresenta uma tabela comparativa detalhada entre a Busca de Custo Uniforme (UCS/Dijkstra), a Busca em Largura (BFS) e a Busca A\*. Esta seção foi incluída para aprofundar a análise, dado que o A\* foi citado durante a prova oral.

O comparativo destaca a relação fundamental entre os algoritmos:
* Dijkstra (UCS) é uma generalização da BFS (aplicável quando os custos são uniformes).
* Dijkstra (UCS) é um caso especial do A\* (onde a função heurística $h(n) = 0$).

### 3. Implementação Prática (Problema da Rota)

Esta seção contém a implementação em Python do Algoritmo de Dijkstra, utilizando a biblioteca `heapq` (min-heap) para gerenciar eficientemente a fila de prioridade.

* **Aplicação:** O algoritmo é testado no "Grafo da Romênia" para encontrar o caminho mais curto e o custo total da rota entre as cidades 'Arad' e 'Bucharest'.
* **Resultado (Dijkstra):** O caminho ótimo encontrado foi `Arad -> Sibiu -> Rimnicu Vilcea -> Pitesti -> Bucharest` com um custo total de `418`.
* **Comparação:** Também é realizada uma análise comparativa de eficiência (nós explorados) e otimização de custo deste algoritmo contra a **Busca em Largura (BFS)** e a busca informada **A* (A-Star)**, demonstrando as vantagens e desvantagens de cada abordagem.

### 4. Análise e Implementação: O Problema das 8 Rainhas

A seção final aborda uma aplicação inadequada do Dijkstra (UCS) para demonstrar suas limitações: a resolução do Problema das 8 Rainhas.

* **Análise Teórica:** Explica que, por ser um Problema de Satisfação de Restrições (CSP), o objetivo não é encontrar um "caminho de menor custo". Ao forçar o uso do Dijkstra com custo `1` por passo, o algoritmo se torna funcionalmente idêntico à Busca em Largura (BFS).
* **Conclusão:** Esta abordagem (Dijkstra/BFS) é computacionalmente inviável e uma das piores formas de resolver o problema, que é mais adequado para algoritmos como o Backtracking (DFS).
* **Implementação (Prova de Conceito):** O código é fornecido para demonstrar como o UCS exploraria o espaço de estados, encontrando todas as 92 soluções, mas de forma extremamente ineficiente.

## Como Executar

1.  Certifique-se de ter o Python 3 e o Jupyter Notebook (ou Jupyter Lab) instalados.
2.  Clone este repositório.
3.  Abra o terminal na pasta do projeto e inicie o Jupyter:
    ```bash
    jupyter notebook
    ```
4.  Abra o arquivo `dijkstra.ipynb` e execute as células. Nenhuma biblioteca externa é necessária, pois o projeto utiliza apenas `math` e `heapq`, que são nativas do Python.