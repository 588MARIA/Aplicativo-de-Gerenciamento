# Banco de Dados — Galpão360

## 1. Condomínios

Cada condomínio será uma organização independente dentro da plataforma.

Dados principais:
- ID
- Nome
- CNPJ
- Endereço
- Cidade
- Estado
- CEP
- Síndico
- Administradora
- Telefone
- E-mail
- Status
- Data de cadastro

## 2. Galpões / Unidades

Cada unidade pertence a um condomínio.

Dados principais:
- ID
- ID do condomínio
- Código da unidade
- Nome
- Área total
- Área construída
- Proprietário
- Ocupante
- Status de ocupação
- Número da matrícula
- IPTU
- Endereço
- Observações

Status:
- Disponível
- Ocupado
- Em manutenção
- Reservado
- Inativo

## 3. Pessoas e Empresas

Cadastro de proprietários, ocupantes, administradores e responsáveis.

Dados principais:
- ID
- Tipo
- Nome ou razão social
- CPF ou CNPJ
- E-mail
- Telefone
- Endereço
- Responsável
- Status

## 4. Contratos

Controle dos contratos relacionados às unidades.

Dados principais:
- ID
- Condomínio
- Unidade
- Proprietário
- Ocupante
- Tipo de contrato
- Data de início
- Data de término
- Valor
- Índice de reajuste
- Data do próximo reajuste
- Garantia
- Status
- Documento

## 5. Financeiro

Controle financeiro de cada condomínio.

### Contas a receber
- ID
- Condomínio
- Unidade
- Cliente
- Descrição
- Valor
- Vencimento
- Data de pagamento
- Status
- Forma de pagamento

### Contas a pagar
- ID
- Condomínio
- Fornecedor
- Categoria
- Descrição
- Valor
- Vencimento
- Data de pagamento
- Status

### Categorias
- Manutenção
- Segurança
- Limpeza
- Energia
- Água
- Administração
- Impostos
- Serviços
- Outros

## 6. Manutenção

Controle de solicitações e serviços.

Dados principais:
- ID
- Condomínio
- Unidade
- Solicitante
- Categoria
- Descrição
- Prioridade
- Prestador
- Orçamento
- Data de abertura
- Prazo
- Data de conclusão
- Status
- Fotos
- Observações

Prioridades:
- Baixa
- Média
- Alta
- Urgente

## 7. Ocorrências

Registro de problemas e acontecimentos.

Dados principais:
- ID
- Condomínio
- Unidade
- Data
- Hora
- Categoria
- Descrição
- Responsável
- Providências
- Status
- Fotos
- Documentos

## 8. Documentos

Centralização dos documentos do condomínio e das unidades.

Tipos:
- Contratos
- Laudos
- Projetos
- ART
- RRT
- Licenças
- AVCB
- Certificados
- Documentos fiscais
- Documentos dos proprietários
- Documentos dos ocupantes

Dados principais:
- ID
- Condomínio
- Unidade
- Tipo
- Nome
- Arquivo
- Data de emissão
- Data de validade
- Responsável
- Status

## 9. Agenda

Controle de compromissos e vencimentos.

Eventos:
- Reuniões
- Manutenções
- Inspeções
- Vencimentos
- Renovações
- Licenças
- Contratos
- Serviços

Dados principais:
- ID
- Condomínio
- Título
- Descrição
- Data
- Hora
- Responsável
- Tipo
- Status

## 10. Prestadores

Cadastro de fornecedores e prestadores.

Dados principais:
- ID
- Condomínio
- Empresa
- CNPJ
- Responsável
- Telefone
- E-mail
- Serviço prestado
- Avaliação
- Status

## 11. Usuários

Controle de acesso à plataforma.

Dados principais:
- ID
- Nome
- E-mail
- Telefone
- Senha criptografada
- Perfil
- Status
- Último acesso

Perfis:
- Superadministrador
- Administrador
- Síndico
- Gestor
- Proprietário
- Ocupante
- Prestador

## 12. Notificações

Sistema de alertas automáticos.

Exemplos:
- Contrato próximo do vencimento
- Documento próximo do vencimento
- Cobrança em atraso
- Manutenção pendente
- Nova ocorrência
- Novo comunicado
- Evento próximo

## 13. Comunicação

Permitir comunicação entre administração, proprietários, ocupantes e prestadores.

Recursos:
- Comunicados
- Avisos
- Mensagens
- Notificações
- Histórico de comunicação

## 14. Auditoria

Registrar alterações importantes realizadas no sistema.

Dados:
- Usuário
- Data
- Hora
- Ação
- Módulo
- Registro alterado
- Informação anterior
- Nova informação
- Endereço IP

## 15. Relacionamentos principais

Condomínio
→ possui várias unidades

Unidade
→ pertence a um condomínio

Unidade
→ possui proprietário

Unidade
→ pode possuir ocupante

Unidade
→ pode possuir vários contratos

Condomínio
→ possui receitas e despesas

Unidade
→ pode possuir manutenções

Condomínio
→ possui ocorrências

Condomínio e unidade
→ possuem documentos

Condomínio
→ possui usuários

Usuários
→ possuem diferentes níveis de permissão

## 16. Multi-tenant

Todos os dados operacionais deverão estar vinculados a um condomínio.

Um usuário de um condomínio não poderá acessar dados de outro condomínio sem autorização específica.

O Superadministrador poderá administrar toda a plataforma.

## 17. Segurança

O sistema deverá utilizar:

- Autenticação segura
- Senhas criptografadas
- Controle de permissões
- Isolamento dos dados por condomínio
- Registro de auditoria
- Backup
- Proteção de dados
- Preparação para LGPD
