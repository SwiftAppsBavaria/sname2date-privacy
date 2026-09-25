# Ajuda do sName2Date

## O que a aplicação faz

O sName2Date procura uma data no nome do ficheiro e escreve-a como data de captura no
ficheiro de imagem, de filme ou de áudio. Se ainda não houver data de captura, ela é criada.

Para isso, há no topo da janela duas caixas de verificação, que não se excluem uma à outra:

| | |
|---|---|
| **Escrever a data no ficheiro** | escreve a data como data de captura dentro do próprio ficheiro — a tarefa principal da aplicação |
| **Converter o nome do ficheiro** | põe o nome na grafia ISO, para **qualquer** espécie de ficheiro |

As duas em conjunto são o caso normal. Se só a segunda estiver assinalada, a aplicação não
abre nenhum ficheiro e apenas muda o nome.

## Primeiros passos

1. Escolha o ficheiro em «Escolher ficheiro…» ou arraste-o para a janela. A versão completa
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

Os nomes de mês são reconhecidos no idioma do sistema e em inglês. Transliterações não
são reconhecidas — em alemão, por exemplo, um nome como `15 Maerz 2024`, com ae/oe/ue em vez
do trema; nesse caso, indique a data à direita, na própria linha.

**Uma data é lida com o dia errado.**
3 de abril escreve-se em português `3/4` e em inglês `4/3` — os mesmos dois números com
significado invertido. Em `15-03-2024` isso não faz diferença: um mês 15 não existe. Só
quando ambos os números passam por mês (`03-05-2024`) é preciso decidir: aparece então, por
cima da lista, uma barra cor de laranja com as duas leituras à escolha, e as linhas em causa
ficam assinaladas. A predefinição é a grafia da região do sistema.

**O nome contém duas indicações de data.**
Ganha a primeira: em `IMG_20240115_editado_2019-03-02`, portanto, a captura e não a nota
posterior. Uma indicação com hora tem sempre precedência sobre uma sem hora.

**O nome contém apenas uma data, sem hora.**
Nesse caso, é assumida uma hora — por predefinição, o meio-dia. Pode alterá-la nas
definições.

**Quero datar uma fotografia antiga digitalizada.**
É possível: as datas indicadas manualmente alcançam até 1826, o ano da fotografia mais antiga
que se conservou.

**A minha fotografia perde qualidade?**
Não. Os dados de imagem são retomados sem alteração, um JPEG não é recomprimido. Nos filmes,
as faixas são passadas tal como estão, não há recodificação.

**Que formatos são suportados?**
Dentro do próprio ficheiro, a aplicação escreve a data de captura em imagens (JPEG, PNG,
TIFF, HEIC, GIF), filmes (MP4, MOV, M4V) e gravações de áudio (M4A, M4B) — o visto na linha
fica então verde.

A lista aceita, no entanto, **qualquer** ficheiro. Quando o formato não acolhe uma data de
captura — um PDF, por exemplo, um ficheiro de texto ou uma folha de cálculo —, a aplicação
define em vez disso a data de criação e de modificação do ficheiro; o visto fica então cor de
laranja. Aplicações, aliases e documentos em formato de pacote não aparecem na lista.

**No meu ficheiro HEIF, WebP ou AVI, o visto está azul.**
Estes três formatos não acolhem uma data de captura. Por isso, a aplicação escreve-a num
ficheiro acompanhante com o mesmo nome e a extensão `.xmp`, que programas de fotografia como
o Lightroom ou o digiKam também leem.

No caso do HEIF, muitas vezes basta a extensão: os mesmos dados chamam-se, como `.heic`, um
outro formato, e são então escritos dentro do próprio ficheiro.

**Só quero arrumar os nomes dos ficheiros, sem tocar nos ficheiros.**
No topo da janela, desligue «Escrever a data no ficheiro» e ligue «Converter o nome do
ficheiro». A aplicação não abre então um único ficheiro e altera apenas o nome e, se estiver
ligado nas definições, a data de criação e de modificação — `Fatura 15.03.2024.pdf` passa a
`2024-03-15 12-00-00 Fatura.pdf`, e a pasta fica ordenada por data no Finder. Isto vale para
qualquer espécie de ficheiro, também PDF, texto ou folhas de cálculo.

Se a data se deve manter onde estava no nome, desligue «Data no início».

Mudar o nome altera a entrada na pasta, e para isso o macOS exige a autorização para a pasta.
Se, na versão completa, for escolhida logo a pasta, a autorização fica assim concedida. Se
tiverem sido escolhidos ficheiros individuais — no sName2Date Lite, sempre —, a aplicação
pede uma vez a pasta; basta uma pasta superior, e a autorização vale também depois de
reiniciar. Na versão completa, o botão «Escolher pasta» apresenta as últimas utilizadas num
menu.

**Ao lado do meu ficheiro está um ficheiro com a extensão `.xmp`.**
Ou vem de outro programa — o Lightroom e o digiKam criam acompanhantes desses —, ou foi o
sName2Date que o criou, porque o formato não acolhe a data de captura em si mesmo (HEIF,
WebP, AVI; o visto fica então azul). ⌘Z anula também um acompanhante criado desta forma. Um
já existente é atualizado pela aplicação quando esta altera a data de captura: de outro modo,
o ficheiro diria uma coisa e o seu acompanhante outra, e a maioria dos programas lê primeiro
o acompanhante.

**Numa pasta grande, a aplicação pergunta se deve continuar a leitura.**
Pastas inteiras de uma só vez são lidas pela versão completa. A partir
de 5 000 ficheiros — por exemplo, na pasta de utilizador com as subpastas — faz uma pausa e
pergunta. Durante a leitura e a análise, mostra um contador e uma barra de progresso; só é
possível escrever quando a lista estiver completa. É mais rápido com uma pasta mais pequena
ou sem «Incluir subpastas».

**Posso anular uma alteração?**
Sim. ⌘Z anula uma passagem inteira — data de captura, data de criação e de modificação e,
se estiver ligado, também o nome de ficheiro alterado. ⌘⇧Z volta a aplicá-la.

Ainda assim, uma indicação: antes de tratar uma coleção grande, faça uma cópia de segurança.
A anulação repõe os valores, mas não substitui uma cópia de segurança.

**A mudança de nome não resultou, mas a data está no ficheiro.**
Se foi escolhido um ficheiro individual, a aplicação só pode trabalhar nesse ficheiro, não na
pasta dele — e mudar o nome altera a entrada na pasta. Escolha a pasta em vez do ficheiro
individual, ou conceda a autorização quando a aplicação a pedir. Uma autorização concedida
vale também depois de reiniciar e abrange todas as subpastas.

## Alguma coisa corre mal?

Definições → Diagnóstico → «Guardar registo…» reúne as mensagens dos últimos sete dias num
ficheiro de texto. Envie-o com a descrição do erro.

## Contacto

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
