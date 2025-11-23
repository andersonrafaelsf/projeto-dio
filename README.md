# projeto-dio

🔐 1. Mitigações para Ataques de Força Bruta em FTP
Problemas identificados

FTP sem criptografia (porta 21)

Senhas fracas e usuários padrão

Login anônimo habilitado

Ausência de bloqueio automático após falhas

Recomendações

Desabilitar FTP e utilizar SFTP/SSH (comunicação criptografada).

Implementar política de senhas fortes (complexidade mínima).

Habilitar Fail2Ban para bloquear IPs após tentativas repetidas.

Remover ou desativar usuários padrão e login anônimo.

Restringir acesso por firewall apenas a IPs autorizados.

Manter o serviço sempre atualizado.


🌐 2. Mitigações para Ataques em Formulários Web (DVWA)
Problemas identificados

Formulário sem proteção contra automação

Sem limite de tentativas

Senhas fracas permitidas

Recomendações

Adicionar CAPTCHA após tentativas falhas.

Implementar timeout entre tentativas de login.

Ativar MFA (autenticação multifator).

Aplicar rate limiting (limitar requisições por minuto).

Bloquear usuário após múltiplas falhas.

Usar algoritmos modernos de hashing de senha (bcrypt, argon2).

Proteger a aplicação com um WAF.

Exigir senhas fortes desde o cadastro.


🖧 3. Mitigações para SMB e Enumeração de Usuários
Problemas identificados

Enumeração de usuários disponível

Senhas fracas exploráveis via password spraying

SMBv1 ativo (inseguro)

Falta de monitoramento e restrições de rede

Recomendações

Desabilitar SMBv1 imediatamente.

Bloquear portas 139/445 de acesso externo via firewall.

Habilitar políticas de bloqueio de conta após tentativas falhas.

Restringir SMB apenas a hosts internos confiáveis.

Desabilitar null sessions (logins anônimos).

Aplicar políticas de senha forte e renovação periódica.

Ativar monitoramento com SIEM/IDS.

Manter Samba/Windows atualizados.


🧱 4. Boas Práticas Gerais para Fortalecimento do Ambiente

Segregação de redes (VLANs / zonas de segurança).

Manutenção de SOs e serviços sempre atualizados.

Desativação de serviços desnecessários.

Adoção de SSH com chave pública no lugar de senha.

Logs centralizados e coleta contínua de eventos.

Implementação de rotinas de backup com testes regulares.

Monitoramento contínuo de tentativas de login suspeitas.
