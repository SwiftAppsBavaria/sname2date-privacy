# Ajuda do sName2Date

## O que o aplicativo faz

O sName2Date procura uma data no nome do arquivo e a grava como data de captura no arquivo
de imagem, de filme ou de áudio. Se ainda não houver data de captura, ela é criada.

Para isso, há no alto da janela duas caixas de seleção, que não se excluem:

| | |
|---|---|
| **Gravar a data no arquivo** | grava a data como data de captura dentro do próprio arquivo — a tarefa principal do aplicativo |
| **Converter os nomes de arquivo** | coloca o nome na grafia ISO, para arquivos de **qualquer** tipo |

As duas juntas são o caso normal. Se só a segunda estiver marcada, o aplicativo não abre
nenhum arquivo e apenas renomeia.

## Primeiros passos

1. Escolha o arquivo em “Escolher arquivo…” ou arraste-o para a janela. A versão completa
   aceita também pastas inteiras, com as subpastas.
2. A lista mostra, para cada arquivo, a data reconhecida e, se houver, a data de captura já
   definida.
3. “Gravar data” executa a alteração.

## Perguntas frequentes

**Em um arquivo aparece “Nenhuma data encontrada no nome”.**
O nome não contém nenhuma indicação de data reconhecível. São reconhecidos, entre outros,
`2024-01-15 10-30-00`, `IMG_20240115_103000`, `2024-01-15`, `2024 01 15`, `2024_01_15`,
`15.01.2024`, `15-01-2024`, `15.01.24`, bem como nomes de mês por extenso, como
`15 jan. 2024`, `15 março 2024` ou `January 15 2024`. Também `2016 04` e `04-2016` são
lidos — nesse caso vale o primeiro do mês, e a linha informa isso.

Os nomes de mês o aplicativo reconhece no idioma do seu sistema e em inglês. Grafias sem os
acentos — `15 marco 2024` em vez de `15 março 2024` — não são reconhecidas; nesse caso,
informe a data manualmente, à direita na linha.

**Uma data é lida com o dia errado.**
3 de abril se escreve `3/4` em português e `4/3` em inglês — os mesmos dois números com
significado invertido. Em `15-03-2024` isso não faz diferença, pois não existe mês 15. Só
quando ambos os números podem ser mês (`03-05-2024`) é preciso decidir: aí aparece acima da
lista uma faixa laranja com as duas leituras para escolher, e as linhas afetadas ficam
marcadas. O padrão é a grafia da região do seu sistema.

**O nome contém duas indicações de data.**
A primeira vence: em `IMG_20240115_editado_2019-03-02`, portanto, a captura, e não a
anotação posterior. Uma indicação com horário sempre tem precedência sobre uma sem.

**O nome contém apenas uma data, sem horário.**
Nesse caso um horário é presumido — por padrão, 12 horas, meio-dia. Ele pode ser alterado nas
configurações.

**Quero datar uma foto antiga digitalizada.**
É possível: as datas informadas manualmente alcançam até 1826, o ano da fotografia mais
antiga preservada.

**Minha foto perde qualidade?**
Não. Os dados de imagem são transferidos sem alteração, um JPEG não é comprimido novamente.
Em filmes, as faixas são repassadas, sem nova codificação.

**Quais formatos são compatíveis?**
Dentro do próprio arquivo, o aplicativo grava a data de captura em imagens (JPEG, PNG, TIFF,
HEIC, GIF), filmes (MP4, MOV, M4V) e gravações de áudio (M4A, M4B) — aí a marca na linha fica
verde.

Mas a lista aceita **qualquer** arquivo. Quando o formato não aceita data de captura — um
PDF, por exemplo, um arquivo de texto ou uma planilha —, o aplicativo define em vez disso a
data de criação e de modificação do arquivo; a marca fica então laranja. Aplicativos, aliases
e documentos em formato de pacote não aparecem na lista.

**Com meu arquivo HEIF, WebP ou AVI, a marca fica azul.**
Esses três formatos não aceitam data de captura. Por isso o aplicativo a grava em um arquivo
acompanhante com o mesmo nome e a extensão `.xmp`, que programas de fotos como Lightroom ou
digiKam também leem.

Com HEIF, muitas vezes a extensão já resolve: os mesmos dados, como `.heic`, são outro
formato, e aí a data é gravada dentro do próprio arquivo.

**Quero apenas organizar os nomes de arquivo, sem tocar nos arquivos.**
No alto da janela, desmarque “Gravar a data no arquivo” e marque “Converter os nomes de
arquivo”. Aí o aplicativo não abre nenhum arquivo e altera só o nome e, se estiver ativado
nas configurações, a data de criação e de modificação — `Fatura 15.03.2024.pdf` vira
`2024-03-15 12-00-00 Fatura.pdf`, e a pasta passa a ser ordenada por data no Finder. Isso vale
para qualquer tipo de arquivo, também PDF, texto ou planilhas.

Se a data deve permanecer onde estava no nome, desligue “Data no início”.

Renomear altera a entrada da pasta, e para isso o macOS exige a permissão para a pasta. Se
você escolher a pasta logo de início na versão completa, ela já está concedida. Se você
escolheu arquivos avulsos — no sName2Date Lite, sempre —, o aplicativo pergunta uma vez pela
pasta; uma pasta superior basta, e a liberação vale também depois de reiniciar. Na versão
completa, o botão “Escolher pasta” traz as últimas utilizadas em um menu.

**Ao lado do meu arquivo há um arquivo com a extensão `.xmp`.**
Ou ele vem de outro programa — Lightroom e digiKam criam esses acompanhantes —, ou o
sName2Date o criou porque o formato não aceita a data de captura dentro de si (HEIF, WebP,
AVI; a marca fica então azul). ⌘Z desfaz também um acompanhante criado assim. Um já
existente é atualizado pelo aplicativo quando ele altera a data de captura: do contrário, o
arquivo diria uma coisa e o acompanhante outra, e a maioria dos programas lê o acompanhante
primeiro.

**Com uma pasta grande, o aplicativo pergunta se deve continuar a leitura.**
Isso vale só para a versão completa; o sName2Date Lite não aceita pastas. A partir de
5 000 arquivos — por exemplo, com a pasta de usuário e as subpastas — ele para e pergunta.
Durante a leitura e a análise, mostra um contador e uma barra de progresso; só é possível
gravar quando a lista estiver completa. Fica mais rápido com uma pasta menor ou sem
“Incluir subpastas”.

**Posso desfazer uma alteração?**
Sim. ⌘Z desfaz uma execução inteira — data de captura, data de criação e de modificação e,
se estiver ligado, também o nome de arquivo alterado. ⌘⇧Z refaz.

Mesmo assim, uma observação: faça uma cópia de segurança antes de processar uma coleção
grande. O desfazer restaura os valores, mas não substitui uma cópia de segurança.

**O renomear não funcionou, mas a data está no arquivo.**
Se foi escolhido um arquivo avulso, o aplicativo pode trabalhar apenas nesse arquivo, não na
pasta dele — e renomear altera a entrada da pasta. Escolha a pasta em vez do arquivo avulso,
ou conceda a liberação quando o aplicativo perguntar. Uma liberação concedida uma vez vale
também depois de reiniciar e abrange todas as subpastas.

## Algo deu errado?

Configurações → Diagnóstico → “Salvar registro…” grava as mensagens dos últimos sete dias em
um arquivo de texto. Envie-o junto com a descrição do erro.

## Contato

SwiftAppsBavaria · SwiftAppsBavaria@gmx.net
