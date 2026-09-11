# Desafio-Criativo: Prompt para automação no N8N

Prompt formatado em **Markdown**, pronto para ser copiado e usado num LLM.

```markdown
# Prompt para Automação de Confirmação de Pagamentos no N8N

## Instrução do Prompt

Atue como um especialista sênior em automação de processos com N8N. Crie um guia detalhado para construir um workflow de confirmação de pagamentos a fornecedores.

---

### Objetivo e Público-Alvo
* **Objetivo:** Registrar pagamentos de fornecedores e notificar automaticamente as equipes responsáveis.
* **Público/Usuários:** Setores Financeiro e de Vendas.

---

### Sistemas Envolvidos
* **Gatilho:** Google Forms (Entrada de dados).
* **Banco de Dados:** Google Sheets (Registro).
* **Comunicação:** Serviço de E-mail (Gmail/SMTP).

---

### Fluxo de Trabalho Detalhado
1. **Captura:** Receber os dados do formulário a cada novo envio (Mapear campos: *Nome do Fornecedor*, *Valor Pago*, *Data do Pagamento*, *Anexo do Comprovante* e *E-mail do Solicitante/Notificado*).
2. **Validação & Limpeza:** 
   * Verificar se o campo de e-mail contém um formato válido usando regex ou validação nativa do nó.
   * Se o e-mail for inválido, interromper a execução para aquele registro sem disparar erros no sistema.
3. **Persistência:** Registrar uma nova linha na aba *"Pagamentos Realizados"* do Google Sheets.
4. **Notificação:** Enviar um e-mail formatado em HTML para o setor financeiro e para a equipe de vendas com o resumo da transação.

---

### Regras de Negócio e Tratamento de Exceções
* Ignorar e descartar registros que não possuam um e-mail válido.
* Garantir que o envio de e-mail contenha um layout claro e organizado, destacando os dados cruciais: **Fornecedor, Valor, Data e ID da Transação**.

---

### Instruções de Resposta Esperadas
1. Liste todos os **Nós (Nodes)** específicos do N8N necessários para este fluxo (ex: *Webhook/Google Forms Trigger*, *Filter/If*, *Google Sheets*, *EmailReadWrite/Gmail*).
2. Explique a **lógica de conexão** passo a passo entre cada nó.
3. Forneça o **código JSON do workflow** ou o passo a passo de configuração dos nós para importação direta no N8N.

```
