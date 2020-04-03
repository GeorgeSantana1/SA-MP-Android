SAMP-Android
Bifurcada a partir do SAMP-Android

Zero. Declaração
1. Declaração pessoal
1. Todo o processo deste artigo foi testado pelo Windows 10 x64, outros sistemas podem teoricamente, mas alguns detalhes podem ser inconsistentes, resolva você mesmo

2. O "diretório raiz" neste artigo refere-se ao diretório absoluto da pasta em que a biblioteca está localizada (por exemplo: C: \ SAMP-Android)

2. Eu não sou responsável por quaisquer problemas decorrentes do projeto

3. Qualquer pessoa pode usar o método fornecido neste artigo, qualquer pessoa pode realizar desenvolvimento e distribuição secundários, mas não pode excluir os direitos autorais do autor de origem.

4. Não forneço suporte técnico pago ou não (explique que, se você não me incomoda, não me faça perguntas confusas, a menos que haja um problema)

Se você tiver circunstâncias especiais, entre em contato comigo QQ1270329917

Agradecimentos especiais: IGTA-fading

2. Assuntos que precisam de atenção
1. O chinês atualmente não é suportado. Os chineses serão transcodificados para russo ou ilegíveis por padrão? Use iconv para transferir o fluxo de mensagens da codificação UTF8 para GBK, desenvolva você mesmo

2. A grande maioria dos servidores não está concluída! Não tente abri-lo para fast food

3. O teclado virtual embutido suporta apenas inglês, números e russo.Não tente usar o método de entrada chinês embutido (você pode criar um conjunto de métodos de entrada chineses um por um e usá-lo para samp?). Encontre o seu próprio caminho

4. Flash de volta depois de abrir o jogo? O arquivo de configuração do SAMP deve ser colocado no lugar errado. Estude onde você deve colocá-lo no seu celular ou se tiver um problema com a embalagem / assinatura!

1. Prepare o meio ambiente
1. Coisas para baixar
Esta biblioteca não precisa de explicação

Android NDK-R14b compilado

JDK assina o apk reembalado

Adicionais: jogo de pacote de dados código de extração: g4fp

2. Configuração do ambiente do sistema
Coloque esta biblioteca em um local fixo "diretório raiz"

Recentemente adicionado à variável de ambiente "Path": 1. O diretório em que o NDK está localizado 2. O diretório bin no diretório em que o jdk está localizado 3. O diretório raiz \ files

Compilar
Abra o PowerShell ou cmd

>  CD raiz \ J Ni
 > NDK-root build.cmd NDK_PROJECT_PATH = -B NDK_DEBUG = 0
3. Desembalar
>  CD raiz \ F Iles
 > . \ AO pktool raiz D \ F Iles \ B uild69.apk -o raiz \ F Iles \ Um -f PK
Pacote Quatro.
Primeiro substitua o diretório raiz \ libs \ armeabi-v7a \ libsamp.so pelo diretório raiz \ files \ lib \ armeabi-v7a (caso contrário, você não fará nada por um longo tempo ...)

>  diretório raiz do CD \ f iles
 > . \ a diretório raiz do pktool b \ f iles \ a pk -o diretório raiz \ f iles \ a pk \ d ist \ b uild69.apk -f
V. Assinatura
Existem muitos materiais relacionados nesta seção na Internet, você pode consultar os métodos em outros lugares

1. Gere uma assinatura
> chcp 936 # Console GBK (também não pode ser executado, mas em alguns casos a saída JDK pode ser ilegível) 
>  diretório raiz do CD \ iles
 > keytool -genkey -v -keystore sampandroid.jks -keyalg RSA -keyize 2048 -validity 10000- sampandroid Alias
 # em seguida, siga as instruções para inserir informações sobre 
> a keytool -importkeystore -srckeystore sampandroid.jks -destkeystore sampandroid.jks -deststoretype PKCS12
2. Assinatura
>  CD raiz \ F Iles \ Um PK \ D IST
 > o jarsigner -verbose -sigalg SHA1withRSA -digestalg Shal -keystore raiz \ F Iles \ S ampandroid.jks build69.apk sampandroid
O diretório raiz \ files \ apk \ dist \ build69.apk é a versão final instalável

6. Preparação no telefone
Exclua o GTASA original (se houver pacotes de dados, faça backup com antecedência)

Diretório raiz da instalação \ files \ apk \ dist \ build69.apk

Pacote de recuperação

Copie o diretório no diretório raiz \ diretório de dados para o Android e o diretório (a maioria dos celulares funciona dessa maneira, alguns celulares funcionam inconsistentemente)

7. Configuração
Abra Android \ obb \ com.rockstargames.gtasa \ files \ SAMP \ settings.ini no telefone e modifique as informações relevantes na seção [client] (como o apelido do jogo IP do servidor)

8. Divirta-se jogando ♂ 玩 ♂
Abra o GTA: SA no celular e entre na interface principal.A segunda tecla é Multiplayer.
