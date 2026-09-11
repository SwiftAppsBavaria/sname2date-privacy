# Ajuda do sName2Date

## O que a aplicação faz

O sName2Date procura uma data no nome do ficheiro e escreve-a como data de captura no
ficheiro de imagem ou de filme. Se ainda não houver data de captura, ela é criada.

Para isso, a versão completa tem **dois modos**, comutáveis no topo da janela:

| | |
|---|---|
| **Data de captura** | escreve a data no ficheiro — a tarefa principal da aplicação |
| **Nomes de ficheiro** | põe apenas o nome na grafia ISO, para **quaisquer** ficheiros |

## Primeiros passos

1. Escolhe o ficheiro em «Escolher ficheiro…» ou arrasta-o para a janela. A versão completa
   aceita também pastas inteiras, com as respetivas subpastas.
2. A lista mostra, para cada ficheiro, a data reconhecida e, se existir, a data de captura já
   definida.
3. «Escrever data» executa a alteração.

## Perguntas frequentes

**Num ficheiro aparece «Nenhuma data encontrada no nome».**
O nome não contém nenhuma indicação de data reconhecível. São reconhecidos, entre outros,
`2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`, `2024_01_15`,
`15.01.2024`, `15-01-2024`, `15.01.24`, bem como nomes de mês por extenso, como
`15 jan. 2024`, `15 março 2024` ou `January 15 2024`. Também `2016 04` e `04-2016` são
lidos — vale então o primeiro do mês, e a linha di-lo.

Os nomes de mês são reconhecidos no idioma do teu sistema e em inglês. Transliterações não
são reconhecidas — em alemão, por exemplo, um nome como `15 Maerz 2024`, com ae/oe/ue em vez
do trema; nesse caso, indica a data à direita, na própria linha.

**Uma data é lida com o dia errado.**
3 de abril escreve-se em português `3/4` e em inglês `4/3` — os mesmos dois números com
significado invertido. Em `15-03-2024` isso não faz diferença: um mês 15 não existe. Só
quando ambos os números passam por mês (`03-05-2024`) é preciso decidir: aparece então, por
cima da lista, uma barra cor de laranja com as duas leituras à escolha, e as linhas em causa
ficam assinaladas. A predefinição é a grafia da tua região do sistema.

**O nome contém duas indicações de data.**
Ganha a primeira: em `IMG_20240115_editado_2019-03-02`, portanto, a captura e não a nota
posterior. Uma indicação com hora tem sempre precedência sobre uma sem hora.

**O nome contém apenas uma data, sem hora.**
Nesse caso, é assumida uma hora — por predefinição, o meio-dia. Podes alterá-la nas
definições.

**Quero datar uma fotografia antiga digitalizada.**
É possível: as datas indicadas manualmente alcançam até 1826, o ano da fotografia mais antiga
que se conservou.

**A minha fotografia perde qualidade?**
Não. Os dados de imagem são retomados sem alteração, um JPEG não é recomprimido. Nos filmes,
as faixas são passadas tal como estão, não há recodificação.

**Que formatos são suportados?**
No modo *Data de captura*: imagens JPEG, PNG, TIFF, HEIC e GIF, filmes MP4, MOV e M4V. Em
todos eles, a aplicação escreve a data dentro do próprio ficheiro.

No modo *Nomes de ficheiro* não conta **extensão nenhuma** — aí só o nome é alterado, e nome
tem-no qualquer ficheiro.

**O meu ficheiro HEIF, WebP ou AVI nem sequer aparece na lista.**
Estes três formatos não acolhem uma data de captura — a aplicação só poderia pôr a data ao
lado, em vez de a escrever lá dentro, e não é para isso que ela existe. Por isso são
ignorados ao carregar, no modo *Data de captura*; uma linha por cima da lista indica quantos
foram.

Mudar-lhes o nome é, ainda assim, possível: para isso, comuta para *Nomes de ficheiro*.

No caso do HEIF, muitas vezes basta a extensão: os mesmos dados chamam-se, como `.heic`, um
outro formato, e são então escritos.

**Só quero arrumar os nomes dos ficheiros, sem tocar nos ficheiros.**
Comuta para *Nomes de ficheiro*, no topo da janela. A aplicação não abre então um único
ficheiro e altera apenas o nome — `Fatura 15.03.2024.pdf` passa a
`2024-03-15 12-00-00 Fatura.pdf`, e a pasta fica ordenada por data no Finder. Isto vale para
qualquer espécie de ficheiro, também PDF, texto ou folhas de cálculo.

Se a data se deve manter onde estava no nome, desliga «Data no início».

⚠️ Neste modo, a aplicação aceita apenas **pastas**, não ficheiros individuais. A razão está
na própria mudança de nome: ela altera a entrada na pasta, e para isso o macOS exige a
autorização para a pasta — que nasce do facto de a escolheres. Uma vez escolhida, a aplicação
guarda-a; o botão «Escolher pasta» apresenta as últimas utilizadas num menu.

**Ao lado do meu ficheiro está um ficheiro com a extensão `.xmp`.**
Esse vem de outro programa — o Lightroom e o digiKam criam acompanhantes desses. O
sName2Date não cria nenhum, mas atualiza um já existente quando altera a data de captura.
De outro modo, o ficheiro diria uma coisa e o seu acompanhante outra, e a maioria dos
programas lê primeiro o acompanhante.

**Posso anular uma alteração?**
Sim. ⌘Z anula uma passagem inteira — data de captura, data de criação e de modificação e,
se estiver ligado, também o nome de ficheiro alterado. ⌘⇧Z volta a aplicá-la.

Ainda assim, uma indicação: antes de tratares uma coleção grande, faz uma cópia de segurança.
A anulação repõe os valores, mas não substitui uma cópia de segurança.

**A mudança de nome não resultou, mas a data está no ficheiro.**
Se foi escolhido um ficheiro individual, a aplicação só pode trabalhar nesse ficheiro, não na
pasta dele — e mudar o nome altera a entrada na pasta. Escolhe a pasta em vez do ficheiro
individual, ou concede a autorização quando a aplicação a pedir. Uma autorização concedida
vale também depois de reiniciar e abrange todas as subpastas.

## Alguma coisa corre mal?

Definições → Diagnóstico → «Guardar registo…» reúne as mensagens dos últimos sete dias num
ficheiro de texto. Envia-o com a descrição do erro.

## Contacto

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
