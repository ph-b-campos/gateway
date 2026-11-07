# Descrição informal do projeto da cadeira

**Projeto Gateway: automatizando a compra de componentes eletrônicos**

Pedro Henrique Campos  
Guilherme Cerqueira Lopes  
Maria Fernanda Debatin

## 1 Problema

O desenvolvimento de placas eletrônicas envolve, para cada projeto, a aquisição de dezenas de componentes distintos. Antes da fabricação, a equipe responsável precisa verificar quais materiais já estão disponíveis, determinar a quantidade que ainda deve ser adquirida, comparar preços entre fornecedores e organizar os respectivos pedidos de compra.

Atualmente, esse processo é realizado de forma predominantemente manual. Essa característica torna a atividade lenta e suscetível a falhas, como erros na quantidade solicitada, seleção equivocada de componentes ou escolha inadequada de fornecedores. Como consequência, podem ocorrer desperdício de recursos, atrasos e retrabalho. Além disso, uma tarefa operacional e repetitiva acaba consumindo um tempo que poderia ser dedicado às etapas de projeto e desenvolvimento das placas.

## 2 Proposta do sistema

Nosso objetivo é projetar um sistema que automatize esse processo de compra, realizando a busca em diferentes fabricantes, checando estoques e comparando preços.

Ele vai Receber a lista de compras e deve devolver um ou mais carrinhos de compras contendo todos os componentes presentes na lista. Caso não seja possível, por falta de algum componente, ele deve enviar uma mensagem de erro ao usuário para cada componente que faltou.

---

[← Voltar à página inicial](index.md)
