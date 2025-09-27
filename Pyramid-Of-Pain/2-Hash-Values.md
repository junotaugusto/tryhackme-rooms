## Valores de Hash (Trivial) 🔐

De acordo com a Microsoft, um **valor de hash** é um valor numérico de comprimento fixo que identifica dados de forma **única**. Um valor de hash é o resultado de um algoritmo de hashing. A seguir estão alguns dos algoritmos de hashing mais comuns:

* **MD5** (Message Digest, definido pela [RFC 1321](https://www.ietf.org/rfc/rfc1321.txt)) - foi projetado por Ron Rivest em 1992 e é uma função de hash criptográfica amplamente utilizada com um valor de hash de 128 bits. Hashes MD5 **NÃO** são considerados criptograficamente seguros. Em 2011, a IETF publicou a [RFC 6151](https://www.ietf.org/rfc/rfc6151.txt), "Considerações de Segurança Atualizadas para o Message-Digest MD5 e os Algoritmos HMAC-MD5", que mencionou vários ataques contra hashes MD5, incluindo a **colisão de hash**.

* **SHA-1** (Secure Hash Algorithm 1, definido pela [RFC 3174](https://www.ietf.org/rfc/rfc3174.txt)) - foi inventado pela Agência de Segurança Nacional dos Estados Unidos (NSA) em 1995. Quando os dados são processados pelo Algoritmo de Hashing SHA-1, ele gera um valor de hash de 160 bits como uma string de 40 dígitos hexadecimais. O NIST descontinuou o uso do SHA-1 em 2011 e baniu seu uso para assinaturas digitais no final de 2013 por ser suscetível a ataques de força bruta. Em vez disso, o NIST recomenda a migração do SHA-1 para algoritmos de hash mais fortes das famílias **SHA-2 e SHA-3**.

* **O SHA-2** (Secure Hash Algorithm 2) - foi projetado pelo Instituto Nacional de Padrões e Tecnologia (NIST) e pela Agência de Segurança Nacional (NSA) em 2001 para substituir o SHA-1. O SHA-2 tem muitas variantes, e provavelmente a mais comum é o **SHA-256**. O algoritmo SHA-256 retorna um valor de hash de 256 bits como um número hexadecimal de 64 dígitos.

Um hash **não é considerado criptograficamente seguro** se dois arquivos diferentes tiverem o mesmo valor de hash ou *digest*.

## Aplicação Prática
Profissionais de segurança geralmente usam valores de hash para obter informações sobre uma **amostra de malware** específica, um arquivo malicioso ou suspeito, e como uma forma de identificar e referenciar de forma única o artefato malicioso.

Você provavelmente já leu relatórios sobre ransomware, nos quais pesquisadores de segurança fornecem os hashes relacionados aos arquivos maliciosos no final do relatório. Você pode conferir o [The DFIR Report](https://thedfirreport.com/) e os [Blogs de Pesquisa da Trellix](https://www.trellix.com/en-us/blogs/research.html) se tiver interesse em ver um exemplo.

Várias ferramentas online podem ser usadas para pesquisar hashes, tais como:
* [VirusTotal](https://www.virustotal.com/)
* [Metadefender Cloud - OPSWAT](https://metadefender.opswat.com/)

![Virus Total](/Pyramid-Of-Pain/IMAGE-1.png)

Na imagem abaixo, encontra-se a hash descrita na imagem acima, que você pode ver pelo nome do arquivo. Neste caso é `"m_croetian.wnry"`.

![Meta Defender Cloud](/Pyramid-Of-Pain/IMAGE-2.png)

Como você deve ter notado, é **muito fácil** identificar um arquivo malicioso se tivermos o hash em nosso arsenal. No entanto, para um atacante, modificar um arquivo em apenas um único bit é **trivial**, o que produziria um **valor de hash diferente**. 

Com tantas variações e instâncias de malwares ou ransomwares conhecidos, a caça a ameaças (threat hunting) usando hashes de arquivo como `IOC (Indicadores de Comprometimento)` pode se tornar difícil.

Vamos ver um exemplo de como você pode alterar o valor de hash de um arquivo simplesmente adicionando uma string ao final dele usando o comando `echo`:

**Hash do Arquivo (Antes da Modificação)**
PS C:\Users\THM\Downloads> Get-FileHash .\OpenVPN_2.5.1_I601_amd64.msi -Algorithm MD5
Algorithm Hash                             Path                                                 
_________ ____                             ____                                                 
MD5       D1A008E3A606F24590A02B853E955CF7 C:\Users\THM\Downloads\OpenVPN_2.5.1_I601_amd64.msi