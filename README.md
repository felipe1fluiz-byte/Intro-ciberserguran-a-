#📘 Aula: Persistência no Windows via Chaves de Inicialização do Registro

##1. Introdução

Em sistemas Windows, diversos mecanismos permitem que programas sejam executados automaticamente durante o processo de inicialização ou no momento do logon do usuário. Esses mecanismos são amplamente utilizados por softwares legítimos, como antivírus, ferramentas corporativas e aplicativos de produtividade.

No entanto, os mesmos recursos também podem ser explorados de forma indevida, o que torna seu estudo essencial para áreas como cibersegurança, forense digital e defesa de sistemas (Blue Team).

Esta aula aborda especificamente a persistência via chaves “Run” do Registro do Windows, com foco educacional e defensivo, em ambientes controlados.

#2. O que é persistência?

Persistência é a capacidade de um programa continuar sendo executado mesmo após:

reinicialização do sistema

logoff e logon do usuário

encerramento manual do processo

Em segurança da informação, persistência é um conceito crítico, pois:

softwares legítimos precisam dela para funcionar corretamente

códigos maliciosos a utilizam para manter acesso ao sistema

#3. O Registro do Windows

O Registro do Windows é um banco de dados hierárquico que armazena:

configurações do sistema operacional

informações de usuários

parâmetros de softwares instalados

Ele é dividido em hives, como:

    HKEY_CURRENT_USER (HKCU)

    HKEY_LOCAL_MACHINE (HKLM)

Algumas dessas chaves são processadas automaticamente pelo Windows durante o logon.

#4. Chaves de inicialização automática (Run Keys)

As chaves mais conhecidas para execução automática são:

🔹 Execução para o usuário atual

      HKCU\Software\Microsoft\Windows\CurrentVersion\Run


Executa programas quando o usuário atual faz login

Não requer privilégios administrativos

Muito usada por aplicações legítimas

🔹 Execução para todos os usuários

    HKLM\Software\Microsoft\Windows\CurrentVersion\Run


Executa programas para todos os usuários

Requer privilégios de administrador

Cada entrada nessas chaves aponta para um executável que será iniciado automaticamente.

#5. Uso legítimo dessas chaves

Essas chaves são usadas, por exemplo, por:

antivírus

agentes corporativos

clientes de backup

aplicativos de sincronização

ferramentas de acessibilidade

Portanto, sua existência não indica, por si só, algo malicioso.

6. Uso indevido e contexto de segurança

Historicamente, softwares maliciosos passaram a usar essas chaves para:

garantir execução após reboot

manter persistência simples

evitar execução manual repetida

Por esse motivo, essa técnica é amplamente conhecida e documentada em frameworks de segurança.

#📌 No MITRE ATT&CK, ela aparece como:

T1547.001 – Registry Run Keys / Startup Folder

7. Situação atual (cenário moderno)

Hoje em dia:

Antivírus e EDRs monitoram essas chaves em tempo real

Alterações nelas são logadas e analisadas

É considerada uma técnica:

básica

ruidosa

fácil de detectar

Ela ainda aparece em:

malware simples

scripts educacionais

provas de conceito

ambientes mal protegidos

Ataques mais sofisticados utilizam métodos de persistência mais avançados.

8. Importância para estudo e defesa

Apesar de simples, estudar essas chaves é fundamental para:

aprendizado de análise de persistência

práticas de forense digital

entendimento de detecção de ameaças

uso de ferramentas como:

Autoruns (Sysinternals)

Windows Defender

EDRs corporativos

Elas servem como porta de entrada conceitual para técnicas mais complexas.

9. Boas práticas defensivas

Monitorar alterações no Registro

Revisar programas de inicialização

Utilizar ferramentas de inventário e EDR

Manter políticas de privilégio mínimo

Testar técnicas apenas em laboratórios autorizados

10. Conclusão

As chaves de inicialização automática do Registro:

continuam existindo

continuam sendo usadas

são relevantes para estudo

mas não são mais eficazes sozinhas contra sistemas modernos

Compreender essas técnicas é essencial para formar profissionais capazes de detectar, analisar e responder a incidentes de segurança.
