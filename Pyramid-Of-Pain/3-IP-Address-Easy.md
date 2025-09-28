## Endereços IP como Indicadores

Você talvez tenha aprendido a importância de um Endereço IP na sala "What is Networking?". Um endereço IP é usado para identificar qualquer dispositivo conectado a uma rede. 

Esses dispositivos variam de desktops a servidores e até mesmo câmeras de CFTV (CCTV)! Nós dependemos de endereços IP para enviar e receber informações pela rede. Mas não vamos nos aprofundar na estrutura e funcionalidade do endereço IP. Como parte da Pirâmide da Dor, avaliaremos como os endereços IP são usados como um indicador.

Na Pirâmide da Dor, os endereços IP são indicados pela cor verde. Você pode estar se perguntando por que e com o que você pode associar a cor verde.
 
Do ponto de vista da defesa, conhecer os endereços IP que um adversário usa pode ser valioso. 

Uma tática de defesa comum é **bloquear, descartar ou negar** requisições de entrada a partir de endereços IP em seu perímetro ou firewall externo. Essa tática geralmente não é à prova de falhas, pois é **trivial** para um adversário experiente se recuperar simplesmente usando um novo endereço IP público.

**Conexões IP Maliciosas (app.any.run):**

![IPs](/Pyramid-Of-Pain/IMAGE-3.png)

> **ATENÇÃO!** Não tente interagir com os endereços IP mostrados acima. Eles são maliciosos.

Uma das maneiras pelas quais um adversário pode dificultar o bloqueio de IP bem-sucedido é usando o *Fast Flux*.

Segundo a Akamai, Fast Flux é uma técnica de DNS usada por botnets para esconder atividades de phishing, web proxying, entrega de malware e comunicação de malware atrás de hosts comprometidos que atuam como proxies. 

O objetivo de usar a rede Fast Flux é tornar a comunicação entre o malware e seu servidor de comando e controle (C&C) difícil de ser descoberta por profissionais de segurança.

Portanto, o conceito principal de uma rede Fast Flux é ter múltiplos endereços IP associados a um nome de domínio, que estão em constante mudança. 

A Palo Alto criou um ótimo cenário fictício para explicar o Fast Flux no artigo (em inglês): ["Fast Flux 101: How Cybercriminals Improve the Resilience of Their Infrastructure to Evade Detection and Law Enforcement Takedowns"](https://unit42.paloaltonetworks.com/fast-flux-101/)