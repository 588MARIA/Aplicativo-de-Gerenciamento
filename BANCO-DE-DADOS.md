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
## 10. Estoque e Materiais

Controle dos materiais, peças, ferramentas e itens mantidos pelo condomínio para uso operacional, manutenção e reposição.

Cada estoque deverá estar vinculado a um condomínio.

### Cadastro de materiais

Dados principais:

- ID
- Condomínio
- Código do material
- Nome
- Categoria
- Descrição
- Unidade de medida
- Quantidade atual
- Estoque mínimo
- Estoque máximo
- Valor unitário
- Fornecedor
- Localização no estoque
- Data de cadastro
- Status
- Observações

### Categorias

- Elétrica
- Hidráulica
- Civil
- Pintura
- Segurança
- Limpeza
- Ferramentas
- EPI
- Peças de reposição
- Jardinagem
- Outros

### Movimentações de estoque

Toda entrada ou saída deverá gerar um registro de movimentação.

Dados principais:

- ID
- Condomínio
- Material
- Tipo de movimentação
- Quantidade
- Data
- Responsável
- Motivo
- Ordem de manutenção
- Ocorrência
- Fornecedor
- Valor
- Observações

Tipos de movimentação:

- Entrada por compra
- Entrada por devolução
- Saída para manutenção
- Saída para utilização
- Transferência
- Perda
- Descarte
- Ajuste de inventário

### Estoque mínimo

O sistema deverá permitir definir uma quantidade mínima para cada material.

Quando a quantidade atual atingir ou ficar abaixo do estoque mínimo, o sistema deverá gerar um alerta de estoque baixo.

### Integração com Manutenção

Os materiais utilizados em uma manutenção poderão ser vinculados à respectiva ordem de manutenção.

Exemplo:

Manutenção → Ordem de Serviço → Material utilizado → Quantidade → Baixa automática do estoque.

O sistema deverá registrar:

- Material utilizado
- Quantidade utilizada
- Data
- Responsável
- Ordem de manutenção
- Custo do material

### Inventário

O sistema deverá permitir a realização de inventários periódicos para conferência do estoque físico e ajuste das quantidades registradas no sistema.

### Alertas

O sistema poderá gerar alertas para:

- Estoque abaixo do mínimo
- Material sem estoque
- Necessidade de reposição
- Inventário pendente
- Materiais próximos de validade, quando aplicável
## 11. Prestadores

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
## 12. Compras e Suprimentos

Módulo responsável pelo controle das solicitações, cotações, compras e recebimento de materiais e serviços do condomínio.

### Solicitações de compra

Permitir que a administração registre solicitações de materiais ou serviços necessários para o funcionamento e manutenção do condomínio.

Dados principais:

- ID
- Condomínio
- Solicitante
- Data da solicitação
- Descrição
- Categoria
- Prioridade
- Quantidade
- Unidade de medida
- Motivo
- Manutenção relacionada
- Ocorrência relacionada
- Status
- Observações

### Cotações

Permitir o registro e comparação de propostas de diferentes fornecedores.

Dados principais:

- ID
- Solicitação de compra
- Fornecedor
- Data da cotação
- Item
- Quantidade
- Valor unitário
- Valor total
- Prazo de entrega
- Condição de pagamento
- Validade da proposta
- Observações

### Pedido de compra

Após aprovação da compra, o sistema deverá permitir a geração de um pedido de compra.

Dados principais:

- ID
- Condomínio
- Solicitação
- Fornecedor
- Responsável pela aprovação
- Data do pedido
- Itens
- Quantidades
- Valor total
- Condição de pagamento
- Previsão de entrega
- Status

### Recebimento

O recebimento de materiais deverá permitir a conferência da quantidade e dos itens recebidos.

Dados principais:

- Pedido de compra
- Data do recebimento
- Responsável
- Nota fiscal
- Itens recebidos
- Quantidades recebidas
- Quantidades pendentes
- Observações

Quando o material for recebido, o sistema poderá gerar automaticamente a entrada correspondente no estoque.

### Integração com Estoque

Compras de materiais deverão estar integradas ao módulo de Estoque e Materiais.

Fluxo:

Solicitação → Cotação → Aprovação → Pedido de compra → Recebimento → Entrada no estoque

### Status da compra

- Solicitação
- Em cotação
- Aguardando aprovação
- Aprovada
- Pedido realizado
- Parcialmente recebido
- Recebido
- Cancelado

### Integração com Financeiro

As compras aprovadas poderão gerar lançamentos financeiros relacionados a:

- Fornecedor
- Valor
- Data de vencimento
- Forma de pagamento
- Número da nota fiscal
- Categoria da despesa
- Centro de custo
- Status do pagamento
## 13. Usuários

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

## 14. Notificações

Sistema de alertas automáticos.

Exemplos:
- Contrato próximo do vencimento
- Documento próximo do vencimento
- Cobrança em atraso
- Manutenção pendente
- Nova ocorrência
- Novo comunicado
- Evento próximo

## 15. Comunicação

Permitir comunicação entre administração, proprietários, ocupantes e prestadores.

Recursos:
- Comunicados
- Avisos
- Mensagens
- Notificações
- Histórico de comunicação

## 16. Auditoria

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

## 17. Relacionamentos principais

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

## 18. Multi-tenant

Todos os dados operacionais deverão estar vinculados a um condomínio.

Um usuário de um condomínio não poderá acessar dados de outro condomínio sem autorização específica.

O Superadministrador poderá administrar toda a plataforma.

## 19. Segurança

O sistema deverá utilizar:

- Autenticação segura
- Senhas criptografadas
- Controle de permissões
- Isolamento dos dados por condomínio
- Registro de auditoria
- Backup
- Proteção de dados
- Preparação para LGPD
