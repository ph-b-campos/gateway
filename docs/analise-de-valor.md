# Análise de Valor do Gateway: Pirâmides B2B e B2C

Base: *The B2B Elements of Value* (Almquist, Cleghorn e Sherer, Bain/HBR, 2018) e *The Elements of Value* (Almquist, Senior e Bloch, Bain/HBR, 2016), conforme os slides da aula "Valor em Marketing" (EEL873, prof. Geraldo Xexéo).

**O produto.** O Gateway recebe uma lista de componentes eletrônicos, busca em vários fornecedores, checa estoque, compara preços e devolve carrinhos de compra prontos. Se algum componente não for encontrado, o sistema avisa com uma mensagem de erro.

**Público principal: B2B.** Equipes e empresas de desenvolvimento de hardware que compram componentes com frequência. O cliente tem duas camadas: a **organização**, que paga, e o **engenheiro ou comprador**, que usa a ferramenta e responde pela compra.

**Público secundário: B2C.** O hobbista ou maker que compra componentes para projetos pessoais, com o próprio dinheiro.

---

## 1. Pirâmide B2B

| Nível / subgrupo | Elemento | Funcionalidade do Gateway | Por que escolhemos |
|---|---|---|---|
| Quesitos básicos | **Atende às especificações** | Geração de carrinhos a partir da lista | O carrinho precisa conter exatamente os componentes (part numbers) e as quantidades pedidos. Um carrinho com peça errada não tem utilidade nenhuma. Não diferencia o Gateway, mas sem isso ele nem seria considerado. |
| Quesitos básicos | **Preço razoável** | Modelo de uso da ferramenta | O custo de usar o Gateway precisa ser menor que a economia que ele gera nas compras. Caso contrário, a empresa continua comprando manualmente. |
| Quesitos básicos | **Padrões éticos** | Comparação de preços | A comparação precisa ser neutra, sem favorecer um fornecedor de forma escondida. Se não for, a recomendação perde credibilidade. |
| Funcional / Econômico | **Reduzir custos** | Comparação de preços entre fornecedores | Para cada componente, o Gateway aponta a opção mais barata entre os fornecedores consultados. Numa empresa que compra com frequência, a diferença acumulada é relevante. |
| Facilidade / Produtividade | **Economizar tempo** | Busca simultânea em vários fornecedores | Sem o Gateway, o engenheiro pesquisa cada componente em cada site, um por um. Com ele, uma única consulta substitui dezenas de buscas. |
| Facilidade / Produtividade | **Reduzir esforços** | Geração automática de carrinhos | O trabalho manual de copiar códigos, conferir quantidades e montar um carrinho em cada loja passa a ser feito pelo sistema. |
| Facilidade / Produtividade | **Evitar aborrecimentos** | Checagem de estoque | O sistema confere o estoque antes de montar o carrinho. Isso evita descobrir só no checkout que um item está esgotado e ter que recomeçar a busca. |
| Facilidade / Produtividade | **Informar** | Aviso de componente faltante; preço e estoque por fornecedor | O usuário fica sabendo de imediato o que não foi encontrado e quanto custa cada opção. Com isso, decide com dados se vai trocar a peça, esperar ou comprar fora. |
| Facilidade / Operacional | **Organizar** | Carrinhos separados por fornecedor | Uma lista solta de componentes vira um conjunto de pedidos agrupados por loja, prontos para aprovação e compra. |
| Facilidade / Operacional | **Integrar** | Busca em vários fornecedores numa única interface | Fontes que antes eram consultadas separadamente ficam reunidas num só fluxo de compra. Segundo a Bain, Integrar é um dos 5 elementos que mais geram lealdade em B2B. |
| Facilidade / Acesso | **Disponibilidade** | Checagem de estoque em vários fornecedores | O Gateway não vende componentes. O que ele faz é mostrar onde cada peça está disponível agora, ampliando o acesso da equipe ao que existe em estoque no mercado. |
| Facilidade / Estratégico | **Reduzir riscos** | Checagem de estoque + aviso de falta | Diminui o risco de comprar o componente errado ou de descobrir a falta tarde demais, quando isso já atrasaria o projeto. Reduzir riscos também está entre os 10 elementos que mais geram lealdade. |
| Individual / Pessoal | **Redução da ansiedade** | Comparação de preços + aviso de falta | O engenheiro não fica com a dúvida de "será que paguei caro?" ou "esqueci alguma peça?". O sistema confere isso por ele. |
| Individual / Carreira | **Garantia de reputação** | Carrinhos verificados (estoque e lista) | Quem adotou ou recomendou o Gateway na equipe não leva a culpa por um pedido errado ou caro. A ferramenta protege a imagem profissional dessa pessoa. |

### Elementos que decidimos não usar

| Elemento | Por que não |
|---|---|
| Qualidade dos componentes | Na pirâmide, o elemento significa que o fornecedor melhora a qualidade percebida do **produto do cliente**. O Gateway melhora a compra das peças, não o produto final. |
| Capacidade de resposta, Competência, Compromisso, Estabilidade | São qualidades da empresa fornecedora e do time por trás dela, como suporte e conhecimento do setor. Um projeto acadêmico não tem como sustentar esses elementos. |
| Gerar receita | O Gateway reduz custos, mas não aumenta o faturamento do cliente diretamente. |
| Inovação | Já existem buscadores de componentes no mercado. A proposta melhora o processo, mas não traz uma inovação de fato. |
| Valor de inspiração (Visão, Otimismo, Responsabilidade social) | A proposta não tem relação com propósito ou impacto social. |

---

## 2. Pirâmide B2C (hobbista / maker)

| Nível | Elemento | Funcionalidade do Gateway | Por que escolhemos |
|---|---|---|---|
| Funcional | **Reduzir custos** | Comparação de preços | O hobbista paga do próprio bolso, então cada real economizado faz diferença para ele. |
| Funcional | **Economizar tempo** | Busca simultânea | O tempo livre que ele gastaria pesquisando loja por loja pode ir para o projeto. |
| Funcional | **Simplificar** | Lista → carrinhos prontos | O hobbista não precisa conhecer cada fornecedor nem entender os detalhes de cada site. Basta enviar a lista. |
| Funcional | **Informar** | Aviso de componente faltante | Ele descobre antes de comprar que uma peça não está disponível e pode procurar um substituto. |
| Emocional | **Reduzir ansiedade** | Comparação de preços + checagem de estoque | Tira a insegurança de quem compra pouco e não sabe se está pagando caro ou esquecendo algum item. |

**Limitação da análise B2C.** O cliente principal do Gateway é a equipe ou empresa, por isso a análise B2C é secundária. Além disso, o hobbista compra poucas peças de baixo valor, então a economia gerada é pequena. Para que ele adote a ferramenta, o custo de uso (tempo para aprender e para formatar a lista) precisa ser muito baixo. O Gateway não entrega elementos dos níveis superiores, "Valor na própria vida" e "Valor na vida da sociedade", e isso é esperado para um produto essencialmente funcional.
