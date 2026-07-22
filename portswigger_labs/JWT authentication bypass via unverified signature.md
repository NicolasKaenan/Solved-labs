# JWT authentication bypass via unverified signature

![Platform](https://img.shields.io/badge/Platform-PortSwigger%20Web%20Security-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-easy-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

# Informações Gerais

| Campo | Valor |
|--------|-------|
| Máquina | Machine Name |
| Dificuldade | Easy |
| Categoria | Web / JWT |
| Data | 21/07/2026 |

---

# Objetivos

- Ganhar acesso ao painel administrativo
- Remover o usuário Carlos

---

# Escopo

Este laboratório foi realizado em um ambiente autorizado exclusivamente para fins educacionais.

Nenhum teste foi realizado fora do escopo disponibilizado pela plataforma.

# Ferramentas Utilizadas

- Burp Suite

---

## Descoberta do alvo

O site "We Like to Blog" é um blog simples contendo alguns posts. No canto superior direito existem as opções "home" e "my account".

![Tela inicial](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/telainicial-jwt.png)

---

### Login

Primeiramente, precisamos obter um token de autenticação. O exercício disponibiliza as credenciais `wiener:peter`, que podem ser utilizadas para realizar login no blog.

![Login](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/tela-de-login-jwt.png)

### Token

Após o login, podemos visualizar o token JWT através do intercept do Burp Suite. Esse token é utilizado pela aplicação para identificar nossa sessão e validar nosso acesso às páginas.

![Token](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/token-jwt.png)

### /admin

Ao tentar acessar o painel administrativo, observamos que a aplicação exige um token válido. Portanto, precisamos encontrar uma forma de obter privilégios administrativos.

![Admin](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/tela-dashboard-jwt.png)

### Interceptando

Utilizando o Burp Suite, interceptamos a requisição enviada para o endpoint `/admin`. Ao analisar o token JWT, verificamos que ele contém informações sobre o usuário autenticado.

O campo `sub` continha o valor `wiener`, referente ao usuário utilizado no login. A partir disso, verificamos se seria possível alterar esse valor para outro usuário e se a aplicação realizaria a validação correta do token.

![Token JWT interceptado](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/token-burp-jwt.png)

Alteramos o valor do campo `sub:wiener` para `sub:administrator`, utilizando o usuário administrador indicado pela própria aplicação.

![Token JWT alterado](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/alterando-token.png)

### Tela admin

Após a alteração do token, conseguimos acessar o painel administrativo da aplicação.

![Dashboard administrativo](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/dashboard-autenticado.png)

### Removendo usuário

Com acesso ao painel administrativo, realizamos a remoção do usuário Carlos mantendo o token adulterado.

### Concluído

Desafio simples, porém um bom exercício para entender manipulação de JWT e utilização de web proxy para análise de requisições.

![Concluído](./../images/portswigger_labs/JWT%20authentication%20bypass%20via%20unverified%20signature/concluido.png)

---

# Considerações Finais

Este write-up tem finalidade exclusivamente educacional.

O objetivo é demonstrar a metodologia utilizada, o raciocínio durante a análise e a documentação técnica do processo, respeitando as políticas da plataforma.
