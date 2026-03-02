# Proj-modelagem-de-software
## Projeto 1 - Diagrama de Casos de Uso ##

<img width="5552" height="3524" alt="image" src="https://github.com/user-attachments/assets/02e93ea1-9ae6-48c4-a001-8a56a82d7cbc" />

## Tabela de Casos de Uso — Sistema de Reservas de Cinema

## Tabela de Casos de Uso — Sistema de Reservas de Cinema

| ID | Nome do UC | Atores | Descrição breve | Fluxo |
|---|---|---|---|---|
| UC001 | Manter Sessões e Salas | Administrador | Cadastra e atualiza salas e sessões do cinema. | Acessa admin → cria/edita sala e sessão → valida conflitos (horário/sala) → salva/publica. **Durante o cadastro de sessão, o admin precisa vincular um filme do catálogo (depende de “Manter Filmes”).** |
| UC002 | Manter Filmes | Administrador | Cadastra, edita e inativa filmes do catálogo. | Abre catálogo → cria/edita/inativa filme → valida campos → salva/disponibiliza para uso nas sessões. |
| UC003 | Importar Títulos da ANCINE | Administrador, ANCINE (Sistema Externo) | Importa a lista oficial de títulos e atualiza o catálogo local. | Admin solicita importação → sistema consulta serviço da ANCINE → valida lista recebida → atualiza catálogo local (registrando/atualizando filmes no sistema) → registra resultado (data, status, quantidade importada). |
| UC004 | Gerar Relatórios Gerenciais | Administrador | Consolida dados (vendas/reservas/renda/meia-entrada) e gera relatórios por período/sessão/filme. | Seleciona filtros (período, filme, sala, sessão) → sistema busca histórico de vendas/reservas → calcula indicadores (ingressos, renda, meia-entrada etc.) → gera relatório → exibe/baixa. **Se for um relatório obrigatório, o sistema já prepara o envio para a ANCINE.** |
| UC005 | Consultar Histórico de Vendas | Administrador | Consulta vendas/reservas registradas por filtros e detalhes. | Informa filtros → sistema lista vendas/reservas → abre detalhes (sessão, assentos, valores, tipo de ingresso) → exibe status e totais. |
| UC006 | Gerar Relatório Automático Pós-Sessão | Sistema (Timer) | Ao fim da sessão, consolida automaticamente vendas/reservas e gera relatório. | Timer detecta fim da sessão → sistema consolida vendas/reservas da sessão → calcula totais e meia-entrada → gera relatório automático → **em seguida já deixa pronto/aciona o envio do relatório obrigatório para a ANCINE** → registra execução. |
| UC007 | Enviar Relatórios Obrigatórios à ANCINE | ANCINE (Sistema Externo) | Envia ao serviço da ANCINE relatórios obrigatórios e registra retorno (status/protocolo). | Sistema prepara dados/arquivo → envia para o serviço da ANCINE → recebe status/protocolo → registra retorno no sistema (para auditoria/controle). |
| UC008 | Consultar Filmes e Sessões | Cliente, Cliente Fidelidade | Exibe filmes em cartaz e sessões disponíveis para escolha. | Cliente pesquisa/filtra filmes → sistema lista sessões/horários → ao selecionar uma sessão, o sistema **mostra a disponibilidade de assentos** → cliente decide se vai reservar/comprar ou apenas consultar. |
| UC009 | Realizar Reserva de Ingressos | Cliente, Cliente Fidelidade | Realiza reserva/compra de ingressos para uma sessão escolhida. | Seleciona sessão → sistema carrega mapa e **verifica disponibilidade de assentos** → cliente escolhe assentos → informa tipo de ingresso → **se escolher meia-entrada, o sistema valida a meia-entrada** → **se for cliente fidelidade, o sistema pode aplicar benefícios** → confirma pagamento/reserva → **após confirmar, o sistema emite o ingresso (digital/impresso).** |
| UC010 | Verificar Disponibilidade de Assento | Cliente, Sistema | Mostra assentos livres/ocupados da sessão selecionada (tempo real). | Sistema carrega mapa da sala → consulta ocupação atual → marca assentos disponíveis/ocupados → atualiza conforme seleção do cliente. **Esse UC é usado quando o cliente consulta sessões e quando vai reservar.** |
| UC011 | Emitir Ingresso (Digital/Impresso) | Cliente, Sistema | Gera o ingresso após confirmação da compra/reserva. | Confirmação de compra/reserva → sistema gera identificador/QR → monta ingresso → disponibiliza (digital/impresso) → registra emissão. **Acontece ao final da reserva/compra.** |
| UC012 | Validar Meia-Entrada | Cliente (e/ou Verificador Meia-Entrada) | Valida elegibilidade e aplica desconto de meia-entrada conforme regras. | Cliente seleciona meia-entrada → informa categoria/documento → sistema valida regras → aplica desconto → registra. **Só ocorre quando, durante a reserva/compra, o cliente escolhe meia-entrada.** |
| UC013 | Aplicar Benefício Fidelidade | Cliente Fidelidade | Aplica regras do programa de fidelidade (ex.: melhor assento, ingresso grátis no mês). | Identifica cliente fidelidade → sistema valida condições (ex.: antecedência de 2 dias, mês de aniversário etc.) → calcula benefício → aplica no total/assentos → registra. **Só ocorre como parte da reserva/compra quando o cliente é fidelidade.** |


## Projeto 1 - Diagrama de Classes ##

<img width="903" height="590" alt="image" src="https://github.com/user-attachments/assets/4c3b386b-aa99-40d9-8e33-d9fb2fc46021" />
