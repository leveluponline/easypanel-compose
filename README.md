# easypanel-compose

Copia do modelo de Supabase do Easypanel (https://github.com/easypanel-io/compose, ramo 18-05-2026, pasta supabase), usada pela Clinica Sentido.

Unica mudanca em relacao ao original: o banco usa a imagem `supabase/postgres:17.6.1.084` (PostgreSQL 17) no lugar de `supabase/postgres:15.8.1.085`, para ficar na mesma versao do banco atual da clinica.

Este repositorio nao guarda senhas nem chaves. Elas ficam so nas variaveis de ambiente do Easypanel.

Segunda mudanca (03/10/2026): o banco grava em pastas novas, `volumes/db/data17` e o volume `db-config17`, em vez de `volumes/db/data` e `db-config`. Motivo: uma primeira instalacao com PostgreSQL 15 deixou dados nas pastas antigas, e o PostgreSQL 17 nao consegue iniciar em cima delas. Para o banco novo nascer do zero com as senhas novas, ele usa pastas limpas. As pastas antigas ficam sem uso e podem ser apagadas no servidor.
