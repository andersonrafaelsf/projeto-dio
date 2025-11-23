# Projeto DIO — Pentest com Medusa, Kali Linux e Metasploitable

## Sumário  
1. Objetivo  
2. Ambiente de Teste  
3. Enumeração (Nmap)  
4. Ataques  
   - Ataque FTP (Medusa)  
   - Ataque Web (DVWA)  
   - Ataque SMB (Password Spraying)  
5. Resultados / Acessos Obtidos  
6. Mitigações Recomendadas  
7. Aprendizados / Conclusão  
8. Como Executar o Projeto  
9. Evidências (imagens)  

## 1. Objetivo  
Simular ataques, testar credenciais, documentar e propor defesas.

## 2. Ambiente de Teste  
- Kali Linux
- Metasploitable 2 (IP: 192.168.56.101)  
- Rede: Host-Only  

## 3. Enumeração (Nmap)  
- Comando: `nmap -sV -p- 192.168.56.101`  
- Resultados esperados vs resultado obtido  
- Interpretação das portas abertas

## 4. Ataques  
- 4.1 Ataque FTP
- 4.2 Ataque Web (DVWA) 
- 4.3 Ataque SMB  

## 5. Resultados / Acessos Obtidos  
Durante os testes realizados com o Kali Linux e o Metasploitable, consegui identificar serviços vulneráveis e realizar alguns acessos bem-sucedidos. No FTP, após o scan com Nmap, confirmei que o serviço estava aberto e consegui autenticar usando credenciais fracas, validando a vulnerabilidade do serviço. No DVWA, após configurar o ambiente no navegador, consegui acessar o painel utilizando as credenciais padrão do aplicativo, demonstrando como senhas simples permitem o acesso ao sistema. Já no SMB, usei o enum4linux para identificar usuários válidos e, com isso, consegui autenticar utilizando uma senha fraca, comprovando a fragilidade do serviço e a importância de políticas de senha mais rigorosas. As imagens adicionadas ao repositório mostram os scans realizados, os serviços identificados e os acessos obtidos durante o processo.

## 6. Mitigações Recomendadas  
- Durante os testes realizados, identifiquei vulnerabilidades comuns em serviços como FTP, DVWA e SMB. Para reduzir riscos e fortalecer a segurança, seguem as medidas de mitigação aplicáveis:
- Alteração de credenciais padrão para senhas fortes e únicas.
- Implementação de bloqueio após múltiplas tentativas de login sem sucesso.
- Desativação de serviços que não estão em uso para diminuir a superfície de ataque.
- Atualização contínua dos sistemas e serviços para evitar exploração de falhas conhecidas.
- Ajuste das configurações dos serviços para evitar permissões excessivas ou acessos abertos.
- Uso de firewall para limitar portas expostas e controlar acessos.
- Monitoramento constante por meio de logs e alertas.
- Separação de ambientes para evitar movimentação lateral em caso de comprometimento.

## 7. Aprendizados / Conclusão  
Este projeto me ajudou a entender na prática como ataques de força bruta funcionam em serviços diferentes e como o Kali Linux, o Medusa e ferramentas de enumeração se complementam na análise. Aprendi a configurar um ambiente vulnerável, interpretar respostas dos serviços, validar acessos obtidos e compreender melhor onde estão as falhas exploradas.
Os principais desafios foram ajustar corretamente a rede entre as VMs, lidar com detalhes do Kali que ainda eram novos para mim e interpretar alguns retornos das ferramentas até entender seu funcionamento real. Isso exigiu paciência, repetição e atenção aos passos.
Se fosse refazer o projeto, organizaria melhor a preparação do ambiente, registraria cada teste durante a execução para agilizar a documentação e exploraria outros serviços vulneráveis além dos usados no exemplo, para ganhar mais prática e comparar cenários diferentes.

## 8. Como Executar o Projeto  
Passo a passo para reproduzir:  
1. Iniciar as VMs (Kali Linux + Metasploitable 2)
2. Configurar a rede em modo Host-Only
3. Executar a varredura com Nmap
4. Selecionar o serviço vulnerável
5. Realizar ataques com Medusa
6. Validar os acessos obtidos
7. Documentar todo o processo no README

## 9. Evidências (imagens)  

Abaixo estão algumas evidências do processo, usando os arquivos da pasta `/Images`:

- [Bruteforce no FTP](Images/01-medusa-bruteforce-ftp.png)
- [IP do Metasploitable](Images/02-ip-config-metasploitable.png)
- [DVWA](Images/03-dvwa-home.png)
- [Login DVWA](Images/04-dvwa-login.png)
- [Medusa](Images/05-medusa-comando-executado.png)
- [Comando BF](Images/06-comando-bruteforce-medusa.png)
- [Enumeração SMB](Images/07-enumeracao-usuarios-smb.png)
- [Invasão](Images/08-acesso-obtido.png)
- [Wordlists ataque](Images/08-acesso-obtido.png)
