# Lab 279 — Introdução ao AWS Identity and Access Management (IAM)

## Objetivo

Compreender como o AWS Identity and Access Management (IAM) controla o acesso aos recursos da AWS por meio de usuários, grupos e políticas de permissões.

## Atividades realizadas

- Configuração de uma política de senhas para a conta.
- Análise dos usuários, grupos e políticas do IAM.
- Associação de usuários a grupos de acordo com suas responsabilidades.
- Testes de permissões de acesso ao Amazon S3 e ao Amazon EC2.
- Verificação de como o IAM bloqueia ações não autorizadas.

## Usuários, grupos e permissões

| Usuário | Grupo | Permissões |
|---|---|---|
| user-1 | S3-Support | Acesso somente para leitura ao Amazon S3 |
| user-2 | EC2-Support | Acesso somente para leitura ao Amazon EC2 |
| user-3 | EC2-Admin | Visualizar, iniciar e parar instâncias EC2 |

## Principais conceitos

- **Usuários do IAM:** identidades que podem receber permissões para acessar recursos da AWS.
- **Grupos do IAM:** conjuntos de usuários que compartilham permissões.
- **Políticas:** documentos que definem quais ações são permitidas ou negadas.
- **Princípio do menor privilégio:** conceder somente as permissões necessárias para cada atividade.

## Validação dos acessos

Os testes demonstraram que cada usuário possui permissões diferentes, conforme o grupo ao qual pertence.

O usuário `user-2`, por exemplo, conseguiu consultar informações do EC2, mas não pôde parar uma instância. A operação foi negada porque nenhuma política de permissões vinculada à identidade autorizava a ação `ec2:StopInstances`.

## Evidências

As capturas de tela que documentam os usuários, grupos, permissões e a tentativa de acesso negada estão disponíveis na pasta `screenshots/`.

## O que aprendi

O IAM permite organizar as permissões por meio de grupos, evitando a necessidade de configurar individualmente cada usuário. Os testes de acesso ajudam a verificar se as permissões concedidas correspondem às responsabilidades de cada identidade.
