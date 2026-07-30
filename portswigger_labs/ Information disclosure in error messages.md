# Information disclosure in error messages

![Platform](https://img.shields.io/badge/Platform-PortSwigger%20Web%20Security-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-easy-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

# Informações Gerais

| Campo | Valor |
|--------|-------|
| Máquina | Information disclosure in error messages |
| Dificuldade | Easy |
| Categoria | Web / Information Disclosure |
| Data | 30/07/2026 |

---

# Objetivo

- Identificar uma vulnerabilidade de divulgação de informações através de mensagens de erro.
- Extrair informações sensíveis reveladas pela aplicação.

---

# Escopo

Este laboratório foi realizado em um ambiente autorizado exclusivamente para fins educacionais.

Nenhum teste foi realizado fora do escopo disponibilizado pela plataforma.

---

# Ferramentas Utilizadas

- ExploitDB (pesquisa de vulnerabilidades relacionadas ao framework identificado)
- Navegador

---

# Descoberta do alvo

Ao acessar a aplicação, encontramos uma loja virtual contendo diversos produtos.

Durante a análise inicial, observamos que os produtos eram acessados através do parâmetro:

```
/product?productId=
```

Esse parâmetro parecia receber um identificador numérico referente ao produto.

---

# Identificação do erro

Foi realizado um teste alterando o valor esperado do parâmetro para um caractere inválido:

```
/product?productId=.
```

A aplicação retornou um erro interno contendo informações detalhadas sobre o processamento da requisição.

![Erro](./../images/portswigger_labs/Information%20disclosure%20in%20error%20messages/erro.png)

---

# Análise do Stack Trace

A mensagem de erro revelou detalhes internos da aplicação:

```
java.lang.NumberFormatException: For input string: "."
```

O erro indica que a aplicação tentou converter o valor recebido para um número inteiro utilizando:

```
Integer.parseInt()
```

Porém, o valor enviado não era um número válido.

Além disso, o stack trace revelou informações sobre a tecnologia utilizada:

```
Apache Struts 2 2.3.31
```

Essa informação poderia auxiliar um atacante na identificação de vulnerabilidades conhecidas relacionadas à versão utilizada.

![Stack Trace](./../images/portswigger_labs/Information%20disclosure%20in%20error%20messages/erro%20stack.png)

---

# Impacto

A exposição de mensagens detalhadas de erro pode revelar:

- Versões de frameworks utilizados;
- Estrutura interna da aplicação;
- Nomes de classes e métodos;
- Informações úteis para exploração de vulnerabilidades conhecidas.

Neste caso, a aplicação revelou que utiliza:

```
Apache Struts 2.3.31
```

permitindo que um atacante pesquise vulnerabilidades específicas relacionadas a essa versão.

---

Como pode ser visto no ExploitDB e searchsploit de exemplo
![ExploitDB](./../images/portswigger_labs/Information%20disclosure%20in%20error%20messages/erro%20stack.png)

# Resolução

Após identificar a informação solicitada pelo laboratório através da mensagem de erro, a solução foi enviada para a plataforma.

![Concluído](./../images/portswigger_labs/Information%20disclosure%20in%20error%20messages/concluido.png)

---

# Considerações Finais

Este laboratório demonstrou a importância do tratamento adequado de erros em aplicações web.

Mensagens de erro detalhadas podem parecer inofensivas, porém podem fornecer informações valiosas para um atacante durante a fase de reconhecimento.

Como boa prática, aplicações em produção devem evitar retornar stack traces completos aos usuários e utilizar mensagens genéricas de erro.

---

# Laboratório de Referência

<div align="center">

🛡️ **PortSwigger Web Security Academy**

### Information disclosure in error messages

[🔗 Acessar laboratório](https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-in-error-messages)

</div>

---