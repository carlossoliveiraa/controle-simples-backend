## ✅ BACKEND – ControleSimples (.NET 9 + DDD + CQRS + SOLID)

### 📦 Estrutura de Soluções

```
ControleSimples.Backend/
├── API/                        # Controllers, Auth, Swagger, Middlewares
├── Application/               # CQRS: Commands, Queries, Handlers, DTOs
├── Domain/                    # Entidades, Aggregates, ValueObjects, Interfaces
├── Infrastructure/            # EF Core, Repositories, External Services
├── Identity/                  # Perfis, Claims, JWT, Supabase integração
├── Payments/                  # Módulo para gateways (Stripe, Pagar.me)
├── Notifications/             # Serviço de envio (e-mail, WhatsApp, etc)
├── Workers/                   # Tarefas em background (ServiceBus, retries)
├── SharedKernel/              # Result, Error, DomainEvent, Enums, etc
├── tests/                     # Unitários e de Integração
└── docker-compose.yml         # Banco e API
```

### 🧠 Princípios e Padrões

| Técnica / Padrão      | Aplicação                                                                 |
|------------------------|---------------------------------------------------------------------------|
| **DDD**               | Separação por contexto com entidades ricas                                |
| **CQRS**              | Commands/Queries com `MediatR`                                             |
| **SOLID**             | Aplicado em todas as camadas                                               |
| **Object Calisthenics** | No `Domain`                                                              |
| **Repository Pattern**| Repositórios com interfaces genéricas                                     |
| **Service Bus Ready** | Azure Service Bus, com tópicos e filas preparados                         |
| **Logging Profissional** | Serilog estruturado + correlação entre requests                         |
| **Feature Toggle**    | Controle de recursos ativáveis por tenant                                 |
| **Multitenancy**      | Isolamento por empresa usando schema ou campo `TenantId`                  |

### 🔐 Segurança e Identidade

- Supabase Auth (JWT)
- Roles: `Admin`, `Gestor`, `Colaborador`
- Claims por permissões e empresas
- Auditoria via eventos + logs

### 🔁 Microserviços Planejados

| Serviço            | Descrição                                      |
|--------------------|-----------------------------------------------|
| **API Gateway**    | Autenticação e roteamento                      |
| **Users Service**  | Gerenciamento de usuários                      |
| **Stock Service**  | Produtos, entradas, saídas                     |
| **Agenda Service** | Agendamentos, calendários                      |
| **Orders Service** | Vendas, status, pagamentos                     |
| **Payments Service** | Integração com gateways externos              |
| **Notifications Service** | Envio de e-mails e mensagens via fila     |

