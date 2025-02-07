# 🚨 Clickjacking no G1: Uma Falha de Segurança

## 📌 Descrição
Este repositório demonstra uma falha de segurança do tipo **Clickjacking** presente no site do **G1**. A vulnerabilidade permite que um invasor carregue o site dentro de um **iframe**, sobrepondo elementos maliciosos para enganar o usuário.

## ⚠️ O Que é Clickjacking?
Clickjacking (também conhecido como UI Redressing) é um ataque que engana o usuário, fazendo-o interagir com uma página legítima sem perceber. Isso pode ser explorado para:
- **Roubar credenciais**
- **Executar ações não intencionais**
- **Enganar o usuário para baixar malware**

## 🔥 Como a Falha Funciona?
O código HTML deste repositório carrega o site do **G1** dentro de um iframe de **tela cheia** e exibe um **popup falso** sugerindo o download de um aplicativo.

Os riscos incluem:
- O usuário pode ser induzido a clicar em links ou baixar arquivos maliciosos.
- O site não implementa cabeçalhos de segurança adequados, como `X-Frame-Options` ou `Content-Security-Policy`.

## 🛡️ Como Corrigir?
Para mitigar ataques de **Clickjacking**, os administradores do site devem:
1. **Adicionar o cabeçalho `X-Frame-Options`** para impedir o carregamento em iframes:
   ```
   X-Frame-Options: DENY
   ```
2. **Implementar `Content-Security-Policy (CSP)`** para restringir iframes:
   ```
   Content-Security-Policy: frame-ancestors 'none';
   ```
3. **Utilizar JavaScript** para detectar e bloquear iframes não autorizados.

## 📚 Referências de Segurança
### OWASP Top 10
Clickjacking é um problema de segurança reconhecido pelo **OWASP Top 10**, um dos principais guias de segurança de aplicações web. Ele se encaixa na categoria **A06:2021 - Vulnerabilidades de Componentes Externos Mal Configurados**, pois a ausência de cabeçalhos de proteção contra iframes expõe usuários a ataques.

Mais informações: [OWASP Clickjacking](https://owasp.org/www-community/attacks/Clickjacking)

### MITRE ATT&CK
No framework **MITRE ATT&CK**, o Clickjacking é classificado sob a técnica **T1204 - User Execution**, pois explora a interação do usuário para realizar ações sem consentimento.

Mais informações: [MITRE ATT&CK - T1204](https://attack.mitre.org/techniques/T1204/)

## 📢 Aviso
Este repositório é apenas para fins educacionais e de pesquisa em segurança. **Não utilize este código para fins maliciosos!**

## Provas de Conceito [PoC]

