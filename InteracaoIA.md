# Registro de Interações Relevantes com a IA (Diário de IA)

Abaixo estão listadas as cinco interações mais significativas ocorridas entre a equipe e o agente de IA durante o desenvolvimento do Analisador de Investimentos.

---

## 1. Delimitação do problema e definição do MVP

**DATA:** 25/09/2026  
**OBJETIVO:** Delimitar o problema e definir o MVP (Passo 1).

### PROMPT UTILIZADO

> "Analise a opção 1. Descreva o usuário, a decisão que precisa tomar, as entradas disponíveis e a saída que o ajudará. Proponha um caso fictício simples e delimite o produto mínimo viável. Aponte informações faltantes. Não escreva código nesta etapa."

### VERIFICAÇÃO REALIZADA

A IA propôs focar exclusivamente em fluxos líquidos de caixa, assumindo que impostos não entrariam no cálculo, mantendo o VPL focado estritamente no fator tempo (TMA).

### DECISÃO HUMANA

Aceitamos a sugestão de escopo. A restrição faz sentido para um MVP focado em Engenharia de Software e não em contabilidade complexa.

---

## 2. Validação do modelo matemático

**DATA:** 25/09/2026  
**OBJETIVO:** Validar o modelo matemático contra cálculo independente (Passo 3).

### PROMPT UTILIZADO

> "...Desenvolva o caso Investimento Inicial (C_0): R$ 25.000... o resultado que a sua aplicação deve exibir com esses novos dados é R$ 2.941,46..."

### VERIFICAÇÃO REALIZADA

Conferimos se as fórmulas e o modelo (modelo_calculos.md) gerados pela IA iriam colidir com o nosso gabarito feito à mão.

### DECISÃO HUMANA

Sugestão de cálculo aceita e mantida. A IA comprovou o resultado com centavos exatos (R$ 2.941,46) e confirmamos que a regra de negócio estava pronta para virar código.

---

## 3. Entrega visual da interface

**DATA:** 25/09/2026  
**OBJETIVO:** Cobrar a entrega visual da interface que ficou incompleta.

### PROMPT UTILIZADO

> "no index.html não mudou nada, não consigo testar"

### VERIFICAÇÃO REALIZADA

A IA havia se adiantado entregando apenas a "casca" do HTML num passo anterior e ignorado a construção visual real até o Passo 6, o que causou confusão nos testes.

### DECISÃO HUMANA (REJEIÇÃO DE ENTREGA)

A equipe rejeitou a versão apresentada pela IA. Exigimos que o HTML contivesse de fato os formulários para testes. A IA corrigiu a falha gerando todo o front-end, gráficos em CSS e conectando os eventos.

---

## 4. Modelagem da funcionalidade "Adiar"

**DATA:** 25/09/2026  
**OBJETIVO:** Esclarecer o uso prático da ferramenta e a modelagem do "Adiar".

### PROMPT UTILIZADO

> "se eu colocar os mesmos dados na opção A e B vai dar o mesmo valor, eu preciso saber se eu desenvolvo ou adio a funcionalidade. Não entendi o pq esta dando o mesmo valor"

### VERIFICAÇÃO REALIZADA

A equipe notou que a ferramenta não tomava a decisão sozinha e dava empate. A IA explicou a semântica da Engenharia Econômica, mostrando que para simular o "atraso", o custo de investimento precisava ser lançado manualmente no futuro (ex: Mês 2) com sinal negativo.

### DECISÃO HUMANA

Revisão de entendimento acatada pela equipe. Entendemos que a matemática não sabe o que é "adiar", e que cabe ao usuário preencher a grade temporal deslocada para a direita.

---

## 5. Revisão final e auditoria das entregas

**DATA:** 25/09/2026  
**OBJETIVO:** Revisão final e auditoria das entregas exigidas (Passo 8).

### PROMPT UTILIZADO

> "Atue como revisor do projeto. Compare os requisitos com o código e execute os testes disponíveis. Revise fórmulas, sinais, taxas, horizonte, dupla contagem de gastos e mensagens de erro. Verifique o funcionamento dos cenários e da exportação. Liste problemas com evidências, corrija os confirmados e atualize o README com instruções de instalação, execução, testes, limitações e exemplo de uso. Diferencie o que foi executado do que depende de conferência manual."

### VERIFICAÇÃO REALIZADA

Ao rodar o prompt de auditoria, a própria IA constatou que nós (a equipe) havíamos pulado o Passo 7 (Cenários) e que ela própria esqueceu a Tabela de Descontos (REQ06) e a Exportação (REQ07) no passo 6.

### DECISÃO HUMANA

A equipe aceitou a proatividade da revisão. A IA corrigiu e gerou automaticamente o código faltante para as tabelas, botão de exportar JSON e adicionou botões de Cenários (+ Otimista / - Pessimista) para compensar a omissão.
