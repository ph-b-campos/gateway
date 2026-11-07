# Livraria Resolve — Partes Interessadas e Desejos (MoSCoW)

**Disciplina:** EEL873 – Engenharia de Software (2026/2) — Grupo C
**Tarefa:** Quais os desejos de suas partes interessadas?
**Fonte da elicitação:** visita simulada à Livraria Resolve
(<https://jogodeanalisedesistemas.xexeo.net>), com entrevistas de todos os
funcionários disponíveis.

---

## 1. O negócio, em uma página

A Livraria Resolve foi fundada há 30 anos por Arnaldo Américo e atua na
**venda sob encomenda de livros de arte, raros e de colecionador**, para
clientes no mundo todo. O negócio **não trabalha com estoque**: a cada pedido,
a livraria procura o exemplar em editoras, distribuidoras, outras livrarias,
sebos e leilões — inclusive no exterior — e o revende. Nas palavras do
proprietário, é "uma espécie de empresa de corretagem, que facilita a vida de
colecionadores".

São **sete pessoas** e o processo é **inteiramente manual** (fichas, cadernos e
uma planilha), o que já produz erros, retrabalho e reclamações. O pedido ao
nosso grupo é um **site de atendimento a clientes**.

**Fluxo atual:** cliente cadastrado envia pedido (e-mail, telefone ou fax) →
vendedor procura cada livro e levanta custo, prazo e frete → gerente geral
define o preço de venda → vendedora monta e envia a proposta → cliente aceita
em ~24 h → **nas sextas-feiras** a livraria emite as requisições aos
fornecedores → livros chegam e a nota de entrega é conferida contra a
requisição → quando o pedido está completo, emite-se cobrança, o cliente paga,
e só então a nota fiscal e o livro são enviados (DHL/FedEx) → cópias da NF e do
boleto vão para o contador terceirizado. Livro não entregue em **30 dias** é
cancelado junto ao fornecedor, retirado do pedido e o cliente é avisado.

---

## 2. Partes interessadas e usuários

Seguimos a distinção da disciplina: **parte interessada** é qualquer
indivíduo, grupo ou organização que pode afetar, ser afetado ou perceber que
será afetado pelo sistema; **usuário** é quem de fato usa o sistema com algum
objetivo. Todo usuário é parte interessada, mas nem toda parte interessada é
usuária.

Legenda das colunas:

- **Usuário?**: *Final* (usa o sistema no seu objetivo de negócio), *Amplo*
  (usa para operar, manter ou administrar) ou *Não*.
- **Tipo de informante** (como cada um descreve o sistema nas entrevistas):
  *Onisciente* (visão de negócio, fala do todo, não necessariamente dos
  detalhes), *Usuário final* (descreve o processo atual e suas falhas) e
  *Parte do sistema* (conhece as regras exatas do processo atual e pode ser
  substituído por ele).

### 2.1 Internas

| # | Parte interessada | Papel | Interesse no sistema | Influência | Usuário? | Tipo de informante |
|---|---|---|---|---|---|---|
| 1 | **Arnaldo Américo** | Proprietário e fundador | Vender livros raros pela internet; já reservou verba. Aprova cadastro de clientes e negocia desconto com fornecedores | **Alta** — patrocinador, decide | Final (aprova cadastros) | Onisciente |
| 2 | **Armando Américo** | Diretor, filho do proprietário | Informatizar para crescer sem contratar; relacionamento com o cliente; relatórios gerenciais. Sucessor do negócio | **Alta** | Final (relatórios, aprovação) | Onisciente |
| 3 | **Bruna Berílio** | Gerente geral, sócia de longa data | Define o preço de venda de cada livro; controla a agenda de entregas em cadernos. **Resistente à mudança** | **Alta** — poder de veto informal | Final (preço, agenda) | Parte do sistema |
| 4 | **Carlos Castelo** | Gerente de TI (equipe de um) | Define as restrições técnicas; vai manter o sistema sozinho | **Média** — decide o "como" | Amplo (mantém e opera) | Usuário final |
| 5 | **Felipe Franciscano** | Vendedor (mestrado) | Busca os livros nos catálogos e contatos; monta a lista de custo, prazo e frete | **Média** — usuário diário | Final | Usuário final |
| 6 | **Gabriela Gambra** | Vendedora antiga | Mantém os arquivos de clientes; fecha a venda (fatura, NF, boleto, expedição) | **Média** — usuária diária | Final | Usuário final / Parte do sistema |
| 7 | **Débora Dina** | Recepcionista e secretária | Atende porta e telefone, agenda reuniões; recebe pedidos por telefone | **Baixa** | A confirmar (registrar pedidos por telefone?) | Usuário final |

### 2.2 Externas

| # | Parte interessada | Interesse no sistema | Influência | Usuário? |
|---|---|---|---|---|
| 8 | **Clientes colecionadores** (Brasil e exterior) | Encomendar e acompanhar pedidos; pagar de forma simples. **Pouco hábito com computador**, mas usam celular | **Média** — a adesão deles define o sucesso do site, mas não participam das decisões do projeto | Final |
| 9 | **Fornecedores** (editoras, distribuidoras, livrarias, sebos, leilões, contatos em NY, Paris e Londres) | Receber requisições corretas e sem duplicidade | **Baixa** | Não (recebem a requisição emitida pelo sistema) |
| 10 | **Contador terceirizado** | Receber cópia de toda nota fiscal e boleto | **Baixa** | Não |
| 11 | **Transportadoras** (DHL, FedEx, Correios) | Receber os dados de expedição | **Baixa** | Não |

### 2.3 Sistemas externos (não são partes interessadas)

| Sistema | Relação com o novo sistema |
|---|---|
| **Sistema de contas a pagar e a receber** (ERP em implantação) | Consome os dados financeiros gerados pelo novo sistema; usa o mesmo banco MySQL (ver R2) |

### 2.4 Poder × interesse e engajamento

Análise do grupo a partir das entrevistas. Poder corresponde à coluna
*Influência*; o engajamento segue a escala Desconhece → Resistente → Neutro →
Apoiador → Líder.

| Quadrante | Partes interessadas | Estratégia |
|---|---|---|
| **Alto poder, alto interesse** — gerenciar de perto | Arnaldo, Armando, Bruna | Envolver nas decisões e validar cada entrega |
| **Alto poder, menor interesse** — manter satisfeito | — (nenhuma identificada) | — |
| **Menor poder, alto interesse** — manter informado | Carlos, Felipe, Gabriela, clientes colecionadores | Consultar sobre o processo e as restrições técnicas; validar a usabilidade com clientes cedo (R1) |
| **Menor poder, menor interesse** — monitorar | Débora, fornecedores, contador, transportadoras | Informar sobre mudanças que os afetem |

| Parte interessada | Engajamento atual | Engajamento desejado | Evidência |
|---|---|---|---|
| Arnaldo | Líder | Líder | "Eu quero vender esses livros raros via internet." |
| Armando | Apoiador | Líder | Propôs o site de encomendas e os relatórios |
| Bruna | **Resistente** | Apoiador | "Nosso diferencial (...) será perdido com um site de vendas" |
| Felipe | Apoiador | Apoiador | Relata as dores da operação diária |
| Gabriela | Apoiador | Apoiador | "Temos que resolver o pagamento urgente." |
| Carlos | Neutro (a confirmar) | Apoiador | Definiu restrições, mas não opinou sobre o produto |
| Débora | Desconhece (a confirmar) | Neutro | Não há fala registrada sobre o sistema |

---

## 3. Os cinco desejos principais

Os cinco desejos abaixo foram os mais repetidos e os de maior impacto no
negócio. Cada um traz a fala que o originou e sua classificação MoSCoW
consolidada (detalhada na Seção 4).

| Desejo | Resumo | MoSCoW | Justificativa |
|---|---|---|---|
| **D1** | Vender e atender o cliente pela internet | **Must** | É o pedido do patrocinador e o objetivo do projeto |
| **D2** | Suportar a operação diária de pedidos, ponta a ponta | **Must** | Sem ele nenhum outro desejo funciona |
| **D3** | Acabar com a informação repetida e com o livro "órfão" | **Must** | É a principal fonte de erro e reclamação hoje |
| **D4** | Resolver o pagamento | **Must** na regra (M12), **Should** no meio de pagamento (S1) | O boleto e o depósito já funcionam, então o site opera sem pagamento on-line. Mas a regra "cliente paga antes do fornecedor" não pode ser quebrada. O pagamento on-line é o primeiro Should a entrar, dado o "urgente" da Gabriela, e depende de decidir a questão das taxas (Divergência 3) |
| **D5** | Enxergar o negócio: agenda e relatórios | **Must** na agenda (M13), **Should** nos relatórios (S2–S4) | A agenda de entregas controla a operação diária e substitui os cadernos da gerente. Os relatórios já são feitos no Excel, com retrabalho, mas sem impedir a operação |

### D1 — Vender e atender o cliente pela internet
> "Eu quero que você escute todos e faça um software que apoie o pessoal de
> vendas para vender por internet. (...) Já estamos perdendo clientes. (...)
> **Eu quero vender esses livros raros via internet.**"
> — Arnaldo Américo

Reforçado por Armando ("pensei se não seria interessante vender livros pela
Internet, com um site para os clientes fazerem encomendas") e delimitado por
Carlos: web responsivo, simples, **sem instalar nada** — "basicamente é só
fazer e acompanhar pedido para eles".

### D2 — Suportar a operação diária de pedidos, ponta a ponta
> "Claramente, a primeira coisa que qualquer sistema deve fazer é **suportar o
> nosso funcionamento diário**. Estou falando da operação básica de atendimento
> aos clientes, não da contabilidade."
> — Felipe Franciscano

É o desejo que sustenta todos os outros: pedido do cliente, cotação com
fornecedores, proposta, requisição de sexta-feira, recebimento, conferência,
faturamento e expedição em um único fluxo.

### D3 — Acabar com a informação repetida e com o livro "órfão"
> "Temos muita informação repetida, pois temos que controlar os pedidos dos
> clientes e as requisições aos fornecedores, que se cruzam. **Muitas vezes
> recebemos um livro e por um problema de anotação não sabemos para qual
> cliente se destina.** Então gastamos um bom tempo procurando, cliente por
> cliente, ficha por ficha."
> — Felipe Franciscano

Mesma dor do lado da Gabriela: "algumas vezes esquecemos de requisitar a um
fornecedor um ou mais livros pedidos pelo cliente. Isso atrasa o atendimento e
resulta em reclamações."

### D4 — Resolver o pagamento
> "A gente está muito atrasado. A desculpa eram as taxas, mas quem paga por
> transferência internacional paga as taxas e considera um custo adicional,
> sempre reclamam. É falta de sistema mesmo. **Temos que resolver o pagamento
> urgente.**"
> — Gabriela Gambra

Hoje só boleto ou depósito internacional, com três dias para confirmar e
pedidos de segunda via. Os clientes pedem **cartão, Pix e PayPal**. Há uma
restrição de negócio a preservar: *"nós temos que fazer o cliente pagar antes
de nós pagarmos o fornecedor"* (Felipe).

### D5 — Enxergar o negócio: agenda de entregas e relatórios gerenciais
> "A gente precisa ter uma **agenda de entregas**. Tudo que tem que ser entregue
> e um status dizendo se já foi pedido, já foi recebido, já foi enviado e se já
> foi pago. Eu faço isso com cadernos, mas são muitos livros agora."
> — Bruna Berílio

> "Dois relatórios são muito importantes: um **relatório de vendas em um
> período** e um **relatório de gastos por fornecedor**. Hoje faço no Excel, mas
> tenho que digitar tudo de novo. (...) Outro é o de **pedidos não atendidos**."
> — Armando Américo

---

## 4. Classificação MoSCoW — todos os usuários

Critério adotado: **Must** = sem isso o site não entra em operação (fator
crítico de sucesso); **Should** = dor relatada com alto valor, mas o sistema
funciona sem; **Could** = melhoria desejada por alguém e sem consenso ou sem
urgência; **Won't** = explicitamente fora do escopo desta versão.

As **restrições** (Seção 4.5) não entram na priorização: são condições
obrigatórias para qualquer versão do sistema.

### 4.1 Must have

| ID | Requisito desejado | Desejo | Quem pediu |
|---|---|---|---|
| M1 | Cadastro de cliente pelo site, com **aprovação** do proprietário ou do diretor antes de liberar pedidos | D1 | Arnaldo |
| M2 | Registro do pedido do cliente (um ou vários livros), aceito **somente de cliente cadastrado** | D1, D2 | Arnaldo, Felipe |
| M3 | Acompanhamento do pedido pelo cliente, pelo site, sem instalar nada | D1 | Carlos, Armando |
| M4 | Registro da busca de cada livro por fornecedor, com **custo, prazo de entrega e estimativa de frete** | D2 | Felipe |
| M5 | Definição do **preço de venda** por livro pela gerência, sobre a lista de custos | D2 | Bruna, Felipe |
| M6 | Emissão da **proposta** ao cliente e registro do aceite (total ou parcial) | D2 | Gabriela |
| M7 | Emissão das **requisições aos fornecedores**, agrupadas no fechamento de sexta-feira | D2, D3 | Arnaldo |
| M8 | **Vínculo permanente livro ↔ pedido ↔ cliente ↔ requisição**, eliminando o livro "órfão" e a digitação repetida | D3 | Felipe, Gabriela |
| M9 | Conferência da **nota de entrega do fornecedor contra a requisição**, com devolução das divergentes | D2, D3 | Arnaldo |
| M10 | **Cancelamento** do livro não entregue em 30 dias, com aviso ao cliente e ao fornecedor (a automação está em S11) | D2 | Arnaldo |
| M11 | Fechamento da venda: recálculo de custo e preço, fatura, nota fiscal e boleto; envio de cópia ao contador | D2 | Gabriela, Arnaldo |
| M12 | Regra de negócio: **expedição só após a confirmação do pagamento** do cliente | D2, D4 | Felipe |
| M13 | **Agenda de entregas** com status (pedido, recebido, enviado, pago) | D5 | Bruna |

### 4.2 Should have

| ID | Requisito desejado | Desejo | Quem pediu |
|---|---|---|---|
| S1 | **Pagamento on-line**: Pix e cartão no Brasil, PayPal no exterior, com baixa automática. **Primeiro Should a entrar** | D4 | Gabriela, Felipe, clientes |
| S2 | Relatório de **vendas por período** | D5 | Armando |
| S3 | Relatório de **gastos por fornecedor** | D5 | Armando |
| S4 | Relatório de **pedidos não atendidos** (livros procurados e não encontrados no mercado) | D5 | Armando, Bruna |
| S5 | **Histórico de livros vendidos por cliente**, para ofertar exemplares semelhantes | D1, D5 | Armando |
| S6 | **Classificação do cliente por tipo de livro** que costuma comprar | D1, D5 | Bruna |
| S7 | Alerta de **cliente frequente que parou de comprar** | D5 | Armando |
| S8 | Situação do cliente (pedido em andamento, atendido não pago, frequente, outros) e **lista de inadimplentes** em tela, substituindo os cadernos e a planilha | D3, D5 | Gabriela |
| S9 | **Integração com o sistema de contas a pagar e a receber** já em implantação | D2 | Bruna, Armando |
| S10 | Registro do **desconto negociado** com o fornecedor e do repasse ao cliente | D2 | Felipe |
| S11 | **Cancelamento automático** ao completar 30 dias, sem ação manual | D2 | Arnaldo |

### 4.3 Could have

| ID | Requisito desejado | Desejo | Quem pediu | Observação |
|---|---|---|---|---|
| C1 | **Mala direta / catálogo** com os livros encalhados em estoque | D1 | Bruna | Armando discorda: "catálogos só dão trabalho" |
| C2 | Site **institucional** de divulgação, com formas de contato | D1 | Bruna | Alternativa dela ao site de vendas |
| C3 | Controle do pequeno **estoque residual** (livros comprados e não retirados) | D2 | Bruna | O negócio não é de estoque |
| C5 | Registro das **cotações em moeda estrangeira** com a taxa de câmbio aplicada | D2 | Felipe, Bruna | Hoje feito na experiência da gerente |

### 4.4 Won't have (nesta versão)

| ID | Fora de escopo | Justificativa |
|---|---|---|
| W1 | Contabilidade, fiscal e contas a pagar/receber | "Para essas vamos ter sistemas prontos, já sabemos disso" (Felipe); o ERP já está em implantação |
| W2 | Aplicativo instalável para cliente | "Não queremos nenhuma necessidade de instalar ou baixar algum software" (Carlos) |
| W3 | Servidor local próprio | "Decidimos terceirizar tudo para a nuvem" (Carlos) |
| W4 | Venda de livros comuns, de catálogo corrente | "Nós não trabalhamos com livros comuns" (Arnaldo) |
| W5 | Gestão de pessoas e contratação | Armando descartou contratar em favor de informatizar |
| W6 | Passar cartão presencialmente | "No passado a gente chegou a passar o cartão na mão, mas hoje não é mais possível" (Felipe) |

### 4.5 Restrições (obrigatórias, fora da priorização)

| ID | Restrição | Quem definiu |
|---|---|---|
| R1 | Interface **muito simples**, responsiva, para usuários com pouco hábito de computador | Carlos |
| R2 | Hospedagem **em nuvem**, **Linux Ubuntu**, **software livre** e banco **MySQL** (o mesmo do ERP) | Carlos |

### 4.6 Hipóteses a validar com o cliente

Itens que ninguém pediu, deduzidos pelo grupo. Só entram no MoSCoW se uma
parte interessada confirmar.

| ID | Hipótese | Origem |
|---|---|---|
| H1 | Integração de **rastreio com DHL/FedEx** | Dedução do fluxo de expedição |

### 4.7 Visão por usuário

Os itens que cada usuário pediu ou que mudam o seu trabalho diretamente.

| Usuário | Must | Should | Could |
|---|---|---|---|
| Clientes colecionadores | M1, M2, M3 | S1 | — |
| Arnaldo | M1, M2, M7, M9, M10, M11 | S11 | — |
| Armando | M1, M3 | S2, S3, S4, S5, S7, S9 | — |
| Bruna | M5, M13 | S4, S6, S9 | C1, C2, C3, C5 |
| Felipe | M2, M4, M5, M8, M12 | S1, S10 | C5 |
| Gabriela | M6, M8, M11 | S1, S8 | — |
| Carlos | M3 (mais R1 e R2) | — | — |
| Débora | A confirmar: M2, se registrar os pedidos recebidos por telefone | — | — |

---

## 5. Divergências e ambiguidades encontradas

Registradas por afetarem diretamente a priorização e por exigirem decisão do
cliente antes do projeto detalhado:

1. **Vender pela internet × preservar o contato pessoal.** Arnaldo e Armando
   querem o site de vendas; Bruna resiste: *"Nosso diferencial, que é o contato
   com os clientes, será perdido com um site de vendas"*. Como ela é a gerente
   geral e define preços, o projeto precisa acomodá-la — por exemplo, mantendo
   a proposta com preço definido por pessoa (M5, M6), e não um preço automático
   de prateleira.
2. **Catálogo × site** (C1 contra D1), entre Bruna e Armando.
3. **Pagamento on-line × taxas.** Desejado pelos vendedores e pelos clientes;
   Carlos levanta a dúvida das taxas e Felipe lembra do risco de estorno com
   cartão, preferindo boleto e Pix. É o que mantém S1 como Should, e não Must.
4. **Termos diferentes para a mesma coisa:** *pedido* (do cliente), *encomenda*,
   *requisição* (ao fornecedor) e *proposta* foram usados de forma intercambiável
   pelos entrevistados. O glossário do projeto precisa fixá-los.
5. **Nome da gerente geral:** anotado como *Bruna Belítro* na agenda e citado
   como *Bruna Berílio* pelo proprietário.
6. **Nome da empresa:** Bruna se refere à *"Livraria ABC"* ao falar dos outros
   sistemas, e não à Livraria Resolve.
7. **Linguagem de programação:** Carlos não fixou a linguagem — apenas o banco
   (MySQL) é inegociável. A definição depende de nova conversa com ele.
8. **Papel da Débora:** não está claro se ela registrará no sistema os pedidos
   recebidos por telefone ou se apenas os repassará aos vendedores.

---

## 6. Próximo passo

As histórias do usuário serão derivadas destes desejos na próxima tarefa, com
as partes interessadas da Seção 2 na primeira aba da planilha.
