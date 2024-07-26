# DiagramasArquitetura-2024-07
Exemplos e recomendações para a elaboração de diagramas de arquitetura utilizando Excalidraw, Mermaid e Draw.io. Conteúdo apresentado no dia 25/07/2024.

## Rascunho do fluxo em Excalidraw

![alt](docs/mfa-rascunho.svg)

## Representação do fluxo em Mermaid

```mermaid
sequenceDiagram
    actor Usuário
    participant Aplicativo
    participant AzureADB2C
    participant ProvedorOTP

    Usuário->>+Aplicativo: Acessa a página de login
    Aplicativo->>+AzureADB2C: Redireciona para a página de login do Azure AD B2C
    AzureADB2C->>Usuário: Exibe a página de login
    Usuário->>+AzureADB2C: Insere credenciais (usuário e senha)
    AzureADB2C->>+ProvedorOTP: Envia solicitação de OTP
    ProvedorOTP->>Usuário: Exibe o código OTP no autenticador
    Usuário->>+AzureADB2C: Insere OTP recebido
    AzureADB2C->>AzureADB2C: Valida OTP
    AzureADB2C-->>-Aplicativo: Redireciona com token de autenticação
    Aplicativo-->>Usuário: Acesso concedido
```

## Componentes utilizados (draw.io)

![alt](docs/mfa-components.svg)