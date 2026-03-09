# teste-qajr-4blue
Teste Técnico — QA Jr

Objetivo:

Este teste tem como objetivo analisar um microssistema web contendo funcionalidades de login e criação de conta, identificando possíveis problemas relacionados a:

Bugs funcionais

Problemas de experiência do usuário (UX)
Problemas básicos de segurança
Classificação de severidade e prioridade dos bugs encontrados

O sistema analisado foi:

https://qa-play-sim.lovable.app/

Estratégia de Testes

Foi realizada uma análise exploratória nas funcionalidades disponíveis no sistema, com foco nas seguintes áreas:

Validação de campos do formulário de cadastro

Validação de autenticação no login

Consistência das mensagens apresentadas ao usuário

Testes de dados inválidos ou incompletos

Avaliação da experiência visual da interface

Durante os testes foram analisados diferentes cenários, incluindo:

Campos vazios

Dados inválidos

Duplicidade de informações

Regras de senha

Mensagens retornadas pelo sistema

Bugs Identificados:

Bug 1 — Sistema permite criar conta sem preencher campos obrigatórios

Descrição

O sistema permite criar uma conta mesmo sem preencher nenhum campo do formulário de cadastro.

Passos para reproduzir:

Acessar a tela Criar Conta

Deixar todos os campos vazios

Clicar em Criar Conta

Resultado atual:

O sistema retorna a mensagem:

Conta criada com sucesso

Sua conta foi criada. Você já pode acessar a plataforma.

Resultado esperado:

O sistema deveria impedir a criação da conta e solicitar o preenchimento dos campos obrigatórios.

Severidade: Crítico
Prioridade: Alta

Bug 2 — Sistema permite criar múltiplos usuários vazios ou duplicados

Descrição:

O sistema permite criar múltiplos usuários sem dados e também permite criar diversas contas utilizando o mesmo email.

Passos para reproduzir:

Criar conta sem preencher dados

Repetir o processo

Ou

Criar conta com dados válidos

Criar nova conta utilizando o mesmo email

Resultado atual:

O sistema cria múltiplas contas inválidas ou duplicadas.

Resultado esperado:

O sistema deveria exigir o preenchimento dos campos obrigatórios e impedir cadastros duplicados utilizando o mesmo email.

Severidade: Crítico
Prioridade: Alta

Bug 3 — Sistema permite login sem preencher email e senha

Descrição:

Foi possível realizar login sem preencher os campos de email e senha após a criação de usuários inválidos.

Passos para reproduzir:

Criar conta sem dados

Acessar tela de login

Deixar campos vazios

Clicar em Login

Resultado atual:

O login é realizado com sucesso.

Resultado esperado:

O sistema deveria exigir o preenchimento de email e senha antes de permitir o login.

Severidade: Crítico
Prioridade: Alta

Bug 4 — Sistema permite criação de conta com confirmação de senha diferente

Descrição:

O sistema permite criar conta mesmo quando o campo Confirmar senha possui valor diferente da senha informada.

Passos para reproduzir:

Acessar Criar Conta

Inserir senha válida

Inserir confirmação de senha diferente

Criar conta

Resultado atual:

Conta criada com sucesso.

Resultado esperado:

O sistema deveria impedir o cadastro e informar que as senhas não coincidem.

Severidade: Crítico
Prioridade: Alta

Bug 5 — Sistema permite cadastro com email inválido ou com espaços

Descrição:

O sistema aceita emails inválidos ou contendo espaços, permitindo criação de conta e login com esses dados.

Passos para reproduzir:

Inserir email inválido ou com espaços no cadastro

Criar conta

Realizar login com o mesmo email

Resultado atual

Conta criada e login realizado com sucesso.

Resultado esperado:

O sistema deveria validar o formato do email e impedir cadastro com valores inválidos.

Severidade: Alto
Prioridade: Alta

Bug 6 — Sistema não valida regra mínima de senha

Descrição:

Apesar da interface informar que a senha deve conter no mínimo 8 caracteres e 1 caractere especial, o sistema permite criar contas com senhas que não seguem essa regra.

Passos para reproduzir:

Inserir senha com menos de 8 caracteres ou sem caractere especial

Criar conta

Resultado atual:

Conta criada com sucesso.

Resultado esperado:

O sistema deveria validar a regra de senha antes de permitir o cadastro.

Severidade: Alto
Prioridade: Alta

Bug 7 — Campo telefone aceita letras e quantidade ilimitada de caracteres

Descrição:

O campo telefone permite inserir letras e grande quantidade de caracteres sem validação.

Passos para reproduzir:

Inserir letras ou sequência longa no campo telefone

Criar conta

Resultado atual:

Conta criada normalmente.

Resultado esperado:

O campo telefone deveria aceitar apenas números e possuir limite de caracteres.

Severidade: Médio
Prioridade: Média

Bug 8 — Mensagem incorreta ao tentar login com senha errada

Descrição:

Ao tentar realizar login utilizando um e-mail válido já cadastrado no sistema, mas inserindo uma senha incorreta, o sistema apresenta uma mensagem de erro inadequada.

Passos para reproduzir:

Acessar a página de login.

Inserir um e-mail já cadastrado no sistema.

Digitar uma senha incorreta.

Clicar em Entrar / Login.

Resultado atual:

O sistema exibe a mensagem:
“Conta não encontrada. Crie uma conta primeiro.”

Resultado esperado:
-
O sistema deveria informar que a senha está incorreta, por exemplo:
“Senha incorreta. Tente novamente.”

Severidade: Médio
Prioridade: Média

Bug 9 — Mensagens contraditórias após login

Descrição:

Após realizar login com sucesso, o sistema apresenta simultaneamente uma mensagem de sucesso e uma mensagem de erro inesperado.

Resultado atual:

Mensagem de sucesso e erro aparecem ao mesmo tempo.

Resultado esperado:

Como o login foi realizado corretamente, o sistema deveria exibir apenas a mensagem de sucesso.

Severidade: Médio
Prioridade: Média

Bug 10 — Problema de layout na tela de cadastro

Descrição:

Na tela de criação de conta os campos apresentam problemas visuais:

campos se sobrepõem;

ultrapassam os limites da borda da interface;

layout fica desconfigurado;

Isso prejudica a experiência do usuário.

Passos para reproduzir

Acessar Criar Conta
Observar o layout dos campos

Resultado atual:

Campos ultrapassam o limite do container e ficam desorganizados.

Resultado esperado:

Os campos deveriam permanecer dentro dos limites da interface com layout alinhado.

Severidade: Baixo
Prioridade: Média

----------------------------------------------------------------------------------------------
Quais 2 bugs você corrigiria primeiro e por quê?

Os dois bugs que eu corrigiria primeiro seriam:

Bug 1 — Sistema permite criar conta sem preencher campos obrigatórios

Esse problema compromete diretamente a integridade dos dados do sistema, permitindo a criação de usuários inválidos e podendo impactar todo o fluxo de autenticação.

Bug 4 — Sistema permite criação de conta com confirmação de senha diferente

Esse bug compromete o processo de autenticação, pois permite que o usuário crie uma conta com senhas diferentes, podendo impedir o acesso posterior à própria conta.

A correção desses dois problemas garante maior confiabilidade no fluxo de cadastro e autenticação do sistema.

------------------------------------------------------------------------------------------------
Sugestões de melhorias

Algumas melhorias que poderiam ser implementadas:

Implementar validações em tempo real nos campos do formulário;
Melhorar a clareza das regras de senha exibidas ao usuário;
Padronizar e melhorar as mensagens de erro do sistema;
Implementar validação de duplicidade de email no momento do cadastro;
Corrigir problemas de layout da tela de cadastro para melhorar a experiência do usuário;
