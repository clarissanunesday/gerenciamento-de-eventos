# Sistema de Gerenciamento de Eventos

Este projeto implementa um sistema de gerenciamento de eventos, permitindo o cadastro de eventos, participantes e inscrições. A aplicação realiza operações como consultas, inserções, atualizações e exclusões de dados, utilizando banco de dados relacional.

## Funcionalidades

- **Gerenciamento de Eventos**: Criação e manutenção de eventos, incluindo nome, data, local e descrição.
- **Gestão de Participantes**: Cadastro de participantes com informações de contato (nome, e-mail e telefone).
- **Controle de Inscrições**: Registro das inscrições dos participantes nos eventos.
- **Consultas e Relatórios**: Relatórios sobre eventos, participantes e inscrições.
- **Atualizações e Deleções**: Funcionalidades para atualizar e excluir dados de eventos, participantes e inscrições.

## Estrutura do Banco de Dados

O sistema é composto por três tabelas principais:

1. **Eventos**: Contém os eventos disponíveis.
2. **Participantes**: Armazena informações dos participantes.
3. **Inscrições**: Relaciona os eventos com os participantes que se inscreveram.

### Diagrama de Relações

- **Eventos** (1) ----> (N) **Inscrições**
- **Participantes** (1) ----> (N) **Inscrições**

## Tabelas

- **Eventos**:
  - `EventoID`: Chave primária
  - `NomeEvento`: Nome do evento
  - `DataEvento`: Data do evento
  - `LocalEvento`: Local onde o evento será realizado
  - `Descricao`: Descrição do evento

- **Participantes**:
  - `ParticipanteID`: Chave primária
  - `NomeParticipante`: Nome do participante
  - `Email`: E-mail do participante (único)
  - `Telefone`: Telefone de contato

- **Inscrições**:
  - `InscricaoID`: Chave primária
  - `EventoID`: Chave estrangeira que faz referência à tabela de eventos
  - `ParticipanteID`: Chave estrangeira que faz referência à tabela de participantes
  - `DataInscricao`: Data em que a inscrição foi realizada

## Consultas Principais

- **Consulta 1**: Listar todos os eventos disponíveis.
  
  ```sql
  SELECT * FROM Eventos;
