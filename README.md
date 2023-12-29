# API de Gerenciamento SSH

## Descrição

A API de Gerenciamento SSH proporciona a criação de logins SSH com validade de 31 dias e a realização de testes em servidores VPS. É uma solução fácil e eficiente para gerenciar acessos remotos.

## Recursos Principais

1. **Criar Login SSH de 31 Dias**
   - **Endpoint:** `/api?type=ssh30`
   - **Método:** POST
   - **Parâmetros:**
     - `token` (string): Token de autenticação.
     - `query` (string): Consulta ou teste a ser executado.
     - `server_ofc` (string): Endereço IP do servidor VPS.
     - `senha_ofc` (string): Senha associada ao servidor VPS.

2. **Criar Login SSH TESTE**
   - **Endpoint:** `/api?type=ssh`
   - **Método:** POST
   - **Parâmetros:**
     - `token` (string): Token de autenticação.
     - `query` (string): Consulta ou teste a ser executado.
     - `server_ofc` (string): Endereço IP do servidor VPS.
     - `senha_ofc` (string): Senha associada ao servidor VPS.

## Como Usar

### 1. Criar Login SSH de 31 Dias

- **Exemplo de Requisição:**
  ```bash
  curl -X POST "http://teste.minerdapifoda.xyz:8080/api?type=ssh30&token=SEU_TOKEN&query=teste&server_ofc=IP-DO-VPS&senha_ofc=SENHA-VPS"
  ```

- **Exemplo de Resposta:**
  ```json
  {
    "statusCode": 200,
    "resultado": "📱CRIADO COM SUCESSO📱\n✅ OBRIGADO PELA PREFERENCIA ✅\n\nUSUARIO: teste113\nLIMITE: 1\nSENHA: 20114\n\n⏳ Expira em: 29-01-2024\n"
  }
  ```

### 2. Criar Login TESTE SSH

- **Exemplo de Requisição:**
  ```bash
  curl -X POST "http://teste.minerdapifoda.xyz:8080/api?type=ssh&token=SEU_TOKEN&query=teste&server_ofc=IP-DO-VPS&senha_ofc=SENHA-VPS"
  ```

- **Exemplo de Resposta:**
  ```json
  {
    "statusCode": 200,
    "resultado": "📱TESTE GERADO COM SUCESSO📱\n\n\nUSUARIO: teste216\nSENHA: 17429\nLimite: 1\n\n⏳ Expira em: 3 Horas\n"
  }
  ```

## Observações

- Certifique-se de incluir os parâmetros corretos, como `token`, `query`, `server_ofc` e `senha_ofc`.
- A resposta da API inclui um código de status (`statusCode`) e o resultado da operação (`resultado`).
- Personalize os exemplos de requisição com seus próprios valores de token, IP de VPS e senha.
- A API é projetada para fornecer facilidade na criação de logins SSH e na execução de testes em servidores VPS.

## Exemplos de Saida da API

### 1. Resposta da Criação de SSH 31 Dias

```json
{
  "statusCode": 200,
  "resultado": "📱CRIADO COM SUCESSO📱\n✅ OBRIGADO PELA PREFERENCIA ✅\n\nUSUARIO: teste113\nLIMITE: 1\nSENHA: 20114\n\n⏳ Expira em: 29-01-2024\n"
}
```

### 2. Resposta do Teste SSH

```json
{
  "statusCode": 200,
  "resultado": "📱TESTE GERADO COM SUCESSO📱\n\n\nUSUARIO: teste216\nSENHA: 17429\nLimite: 1\n\n⏳ Expira em: 3 Horas\n"
}
```
