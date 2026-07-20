# Machine Name

![Platform](https://img.shields.io/badge/Platform-Hack%20The%20Box-green)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-orange)
![OS](https://img.shields.io/badge/OS-Linux-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

> **PTES-based Write-up**
>
> Este documento descreve a metodologia utilizada durante o laboratório, focando no processo de enumeração, exploração e pós-exploração.
>
> **Não contém flags, credenciais, payloads destrutivos ou informações que comprometam a experiência do laboratório.**

---

# Informações Gerais

| Campo | Valor |
|--------|-------|
| Máquina | Machine Name |
| Sistema Operacional | Linux |
| Dificuldade | Medium |
| Categoria | Web / Linux / Windows |
| Data | DD/MM/YYYY |

---

# Objetivos

- Identificar a superfície de ataque
- Enumerar serviços
- Encontrar vetor inicial
- Obter acesso inicial
- Escalar privilégios
- Documentar todo o processo

---

# Escopo

Este laboratório foi realizado em ambiente autorizado exclusivamente para fins educacionais.

Nenhum teste foi realizado fora do escopo da plataforma.

---

# Metodologia (PTES)

- ✔ Pré-engajamento
- ✔ Coleta de informações
- ✔ Modelagem de ameaças
- ✔ Análise de vulnerabilidades
- ✔ Exploração
- ✔ Pós-exploração
- ✔ Documentação

---

# Ferramentas Utilizadas

- Nmap
- Burp Suite
- Gobuster / Feroxbuster
- ffuf
- Netcat
- LinPEAS / WinPEAS
- BloodHound (quando aplicável)
- Metasploit (caso utilizado)
- Python
- Bash
- Outras ferramentas auxiliares

---

# Reconhecimento

## Descoberta do alvo

Descrição breve do laboratório.

---

## Enumeração de portas

**Objetivo**

Identificar serviços expostos.

### Evidências

> Inserir print do scan (opcional)

```
(Resumo dos serviços encontrados)
```

### Observações

- Porta X aberta
- Serviço Y identificado
- Possível vetor inicial

---

# Enumeração

## Serviço HTTP

### Observações

- Tecnologias identificadas
- Diretórios encontrados
- Páginas interessantes

> Inserir prints

---

## Enumeração SMB / FTP / SSH / LDAP

Documentar apenas o processo.

Evitar publicar:

- senhas
- hashes
- usuários válidos
- credenciais

---

# Modelagem da Superfície de Ataque

Possíveis vetores identificados:

- Web
- Upload
- API
- SMB
- SSH
- Banco de dados
- Configuração insegura

---

# Vulnerabilidade Identificada

## Descrição

Explicar o problema encontrado sem revelar a solução completa.

### Impacto

Descrever:

- Confidencialidade
- Integridade
- Disponibilidade

---

# Exploração

## Objetivo

Obter acesso inicial.

### Processo

Descrever:

- raciocínio
- metodologia
- decisões tomadas

Evite publicar:

- payloads completos
- credenciais
- comandos específicos que entreguem a solução

---

### Evidências

Inserir apenas prints do acesso obtido.

---

# Pós-Exploração

## Enumeração Local

Itens investigados:

- permissões
- serviços
- processos
- cron jobs
- sudo
- capabilities
- arquivos sensíveis

---

## Escalação de Privilégios

Descrever:

- hipótese
- vulnerabilidade explorada
- por que funcionou

Sem divulgar a exploração completa.

---

# Evidência de Conclusão

## Máquina concluída

Inserir apenas a captura da tela da plataforma mostrando:

- Machine Owned
- Room Completed
- Pwned
- Root Obtained

Exemplo:

```
![Completed](images/completed.png)
```

---

# Lições Aprendidas

- Técnicas praticadas
- Ferramentas utilizadas
- Conceitos reforçados
- Erros cometidos
- Como evitar esses erros futuramente

---

# Mitigações

Caso fosse um ambiente real:

- Atualizações
- Hardening
- Princípio do menor privilégio
- Correções de configuração
- Monitoramento
- Segmentação de rede
- MFA
- Gestão de patches

---

# Referências

- PTES
- OWASP
- MITRE ATT&CK
- GTFOBins
- LOLBAS
- HackTricks
- Documentação oficial das ferramentas

---

# Timeline

| Etapa | Status |
|--------|--------|
| Reconhecimento | ✅ |
| Enumeração | ✅ |
| Análise | ✅ |
| Exploração | ✅ |
| Pós-exploração | ✅ |
| Escalada | ✅ |
| Documentação | ✅ |

---

# Competências Exercitadas

- Reconhecimento
- Enumeração
- Web Security
- Linux
- Windows
- Active Directory
- Privilege Escalation
- Network Enumeration
- Pentest Methodology
- Report Writing

---

# Considerações Finais

Este write-up tem finalidade exclusivamente educacional.

O foco é demonstrar metodologia, pensamento analítico e documentação técnica, preservando a experiência do laboratório e respeitando as políticas da plataforma.

Não são disponibilizadas flags, credenciais, exploits completos ou qualquer informação que permita reproduzir a solução diretamente.
