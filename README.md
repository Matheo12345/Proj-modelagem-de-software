# Proj-modelagem-de-software
## Projeto 1 - Diagrama de Casos de Uso ##

<img width="5552" height="3532" alt="image" src="https://github.com/user-attachments/assets/5c6e81c2-925f-4cde-a084-feee648a2f33" />


## Tabela de Casos de Uso — Sistema de Reservas de Cinema

| ID | Nome do UC | Atores | Descrição breve | Fluxo |
|---|---|---|---|---|
| UC001 | Manter Sessões e Salas | Administrador | Cadastra e atualiza salas e sessões do cinema (inclui definição de filme, sala e horários). | Acessa área admin → cadastra/edita sala → cadastra/edita sessão (define filme, sala e horário) → valida conflitos (horário/sala) → salva/publica. |
| UC002 | Manter Filmes | Administrador | Cadastra, edita e inativa filmes do catálogo. | Abre catálogo → cria/edita/inativa filme → valida campos → salva/disponibiliza para uso nas sessões. |
| UC003 | Importar Títulos da ANCINE | Administrador (ator principal), ANCINE (Sistema Externo) | Importa a lista oficial de títulos e atualiza o catálogo local. | Admin solicita importação → sistema consulta serviço da ANCINE → valida lista recebida → registra/atualiza filmes no catálogo → registra resultado (data, status, quantidade). |
| UC004 | Gerar Relatórios Gerenciais | Administrador | Consolida dados (vendas/reservas/renda/meia-entrada) e gera relatórios por período/sessão/filme. | Seleciona filtros (período, filme, sala, sessão) → sistema busca dados do histórico → calcula indicadores → gera relatório → exibe/baixa. Se necessário, prepara dados para envio obrigatório à ANCINE. |
| UC005 | Consultar Histórico de Vendas | Administrador | Consulta vendas/reservas registradas por filtros e detalhes. | Informa filtros → sistema lista vendas/reservas → abre detalhes (sessão, assentos, valores, tipo de ingresso) → exibe status e totais. |
| UC006 | Gerar Relatório Automático Pós-Sessão | Sistema (Timer) | Ao fim da sessão, consolida automaticamente vendas/reservas e gera relatório. | Timer detecta fim da sessão → sistema consolida vendas/reservas → calcula totais/meia-entrada → gera relatório automático → aciona/prepara o envio obrigatório à ANCINE → registra execução. |
| UC007 | Enviar Relatórios Obrigatórios à ANCINE | Sistema (ator principal), ANCINE (Sistema Externo) | Envia relatórios obrigatórios à ANCINE e registra retorno (status/protocolo). | Sistema prepara dados/arquivo → envia ao serviço da ANCINE → recebe status/protocolo → registra retorno para auditoria/controle. |
| UC008 | Consultar Filmes e Sessões | Cliente, Cliente Fidelidade | Exibe filmes em cartaz e sessões disponíveis. | Cliente pesquisa/filtra filmes → sistema lista sessões/horários → cliente seleciona sessão → sistema exibe disponibilidade de assentos → cliente decide se continuará para reserva/compra. |
| UC009 | Realizar Reserva de Ingressos | Cliente, Cliente Fidelidade | Realiza reserva/compra de ingressos para uma sessão. | Seleciona sessão → sistema carrega mapa e verifica disponibilidade → cliente escolhe assentos → informa tipo de ingresso → se for meia-entrada, valida meia → se for fidelidade, aplica benefício → confirma reserva/compra → sistema emite ingresso (digital/impresso). |
| UC010 | Verificar Disponibilidade de Assento | Cliente, Sistema | Mostra assentos livres/ocupados da sessão (tempo real). | Ao selecionar a sessão, sistema carrega mapa da sala → consulta ocupação atual → marca assentos disponíveis/ocupados → atualiza conforme seleção do cliente. |
| UC011 | Emitir Ingresso (Digital/Impresso) | Sistema, Cliente | Gera o ingresso após confirmação da compra/reserva. | Compra/reserva confirmada → sistema gera identificador/QR → monta ingresso → disponibiliza (digital/impresso) → registra emissão. |
| UC012 | Validar Meia-Entrada | Cliente (e/ou Verificador Meia-Entrada) | Valida elegibilidade e aplica desconto de meia-entrada. | Cliente seleciona meia-entrada → informa categoria/documento → sistema valida regras → aplica desconto → registra. (Ocorre durante a reserva/compra.) |
| UC013 | Aplicar Benefício Fidelidade | Cliente Fidelidade | Aplica regras do programa de fidelidade (ex.: melhores assentos por antecedência; ingresso grátis no mês). | Sistema identifica cliente fidelidade → valida regras/condições → calcula benefício → aplica no total/assentos → registra. (Ocorre durante a reserva/compra.) |


## Projeto 1 - Diagrama de Classes ##

<img width="1271" height="1028" alt="image" src="https://github.com/user-attachments/assets/de9800a1-93eb-4213-adac-3c8cc3044813" />




