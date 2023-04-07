# Projeto de Análise de Planos Pré-pagos da Megaline

## Objetivo
Analisar o comportamento dos clientes e determinar quais planos pré-pagos da Megaline geram mais receita, para ajustar o orçamento de publicidade.

## Planos
- Surf - Preço mensal: $20 - Inclui 500 minutos, 50 mensagens de texto e 15GB de dados. Após exceder os limites, são cobrados 3 centavos por minuto, mensagem de texto ou 10 dólares por GB de dados.
- Ultimate - Preço mensal: $70 - Inclui 3000 minutos, 1000 mensagens de texto e 30GB de dados. Após exceder os limites, são cobrados 1 centavo por minuto, mensagem de texto ou 7 dólares por GB de dados.

## Dados
- megaline_calls.csv - dados de chamadas
- megaline_internet.csv - dados de sessões web
- megaline_messages.csv - dados de mensagens de texto
- megaline_plans.csv - dados sobre os planos
- megaline_users.csv - dados sobre os usuários

## Preparação dos dados

- Conversão dos dados para os tipos necessários;
- Identificação e eliminação de erros;
- Cálculo do número de chamadas feitas, minutos usados por mês, número de mensagens de texto enviadas por mês, volume de dados por mês e receita mensal para cada usuário.

## Análise dos dados

- Descrição do comportamento dos clientes;
- Cálculo da média, variância e desvio padrão dos minutos, mensagens de texto e volume de dados utilizados por mês;
- Construção de histogramas;
- Descrição das distribuições.

## Teste de Hipóteses

- Hipótese nula: A receita média dos usuários dos planos Ultimate e Surf são iguais.
- Hipótese alternativa: A receita média dos usuários dos planos Ultimate e Surf são diferentes.
- Hipótese nula: A receita média dos usuários da área de NY-NJ é igual à receita média de usuários de outras regiões.
- Hipótese alternativa: A receita média dos usuários da área de NY-NJ é diferente da receita média de usuários de outras regiões.
Valores alfa serão escolhidos posteriormente.

## Descrição dos dados
Lembre-se! A Megaline arredonda segundos para minutos e megabytes para gigabytes. Para chamadas, cada chamada individual é arredondada para cima: mesmo se uma chamada tenha durado apenas um segundo, será contado como um minuto. Para trafego de web, sessões individuais de web não são arredondadas para cima.. Ao invés disso, o total do mês é arredondado para cima. Se alguém usar 1025 megabytes esse mês, eles serão cobrados por 2 gigabytes.

A tabela users (dados sobre usuários):

* `user_id` — identificação do usuário
* `first_name` — nome do usuário
* `last_name` — último sobrenome do usuário
* `age` — idade do usuário (em anos)
* `reg_date` — data da inscrição (dd, mm, aa)
* `churn_date` — a data que o usuário parou de usar o serviço (se o valor for ausente, o plano estava sendo usado quando esse dado foi gerado)
* `city` — cidade de residência do usuário
* `plan` — nome do plano

A tabela calls (dados sobre as chamadas)

* `id` — identificador de chamada unívoco
* `call_date` — data da chamada
* `duration` — duração da chamada (em minutos)
* `user_id` — o identificador do usuário que faz a chamada

A tabela messages (dados nas mensagens de texto):

* `id` — identificador unívoco de mensagem de textos
* `message_date` — data da mensagem de texto
* `user_id` — o identificador do usuário que envia a mensagem de texto

A tabela internet (dados sobre sessões web):

* `id` — identificador de sessão unívoco
* `mb_used` — o volume de dados gasto durante a sessão ( em megabytes)
* `session_date` — data da sessão web
* `user_id` — identificador do usuário

A tabela plans (dados sobre os planos):

* `plan_name` — o nome do plano de chamadas
* `usd_monthly_fee` — preço mensal em dólares dos EUA
* `minutes_included` — pacote de minutos mensal
* `messages_included` — pacote de mensagens de texto mensal
* `mb_per_month_included` — pacote de volume de dados (em megabytes)
* `usd_per_minute` — preço por minuto depois de exceder o limite do pacote (por exemplo, se o pacote inclui 100 minutos, o primeiro minuto excedente será cobrado)
* `usd_per_message` — preço por mensagem de texto depois de exceder o limite do pacote
* `usd_per_gb` — preço por gigabyte extra de dados após exceder o limite do pacote (1 GB = 1024 megabytes)
