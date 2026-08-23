# Ajuda do sName2Date

## O que o aplicativo faz

O sName2Date procura uma data no nome do arquivo e a grava como data de captura no arquivo
de imagem ou de filme. Se ainda não houver data de captura, ela é criada.

Para isso, a versão completa tem **dois modos**, alternáveis no alto da janela:

| | |
|---|---|
| **Data de captura** | grava a data no arquivo — a tarefa principal do aplicativo |
| **Nomes de arquivo** | apenas coloca o nome na grafia ISO, para arquivos de **qualquer** tipo |

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
No modo *Data de captura*: as imagens JPEG, PNG, TIFF, HEIC e GIF, e os filmes MP4, MOV e
M4V. Em todos eles o aplicativo grava a data dentro do próprio arquivo.

No modo *Nomes de arquivo*, **nenhuma extensão importa** — ali só o nome é alterado, e nome
todo arquivo tem.

**Meu arquivo HEIF, WebP ou AVI nem aparece na lista.**
Esses três formatos não aceitam data de captura — o aplicativo só poderia deixar a data ao
lado deles, em vez de gravá-la dentro, e não é para isso que ele existe. Por isso eles são
ignorados no carregamento, no modo *Data de captura*; uma linha acima da lista informa
quantos eram.

Renomeá-los, ainda assim, é possível: para isso, mude para *Nomes de arquivo*.

Com HEIF, muitas vezes a extensão já resolve: os mesmos dados, como `.heic`, são outro
formato, e aí a gravação acontece.

**Quero apenas organizar os nomes de arquivo, sem tocar nos arquivos.**
Mude para *Nomes de arquivo*, no alto da janela. Aí o aplicativo não abre nenhum arquivo e
altera só o nome — `Fatura 15.03.2024.pdf` vira `2024-03-15 12-00-00 Fatura.pdf`, e a pasta
passa a ser ordenada por data no Finder. Isso vale para qualquer tipo de arquivo, também PDF,
texto ou planilhas.

Se a data deve permanecer onde estava no nome, desligue “Data no início”.

⚠️ Nesse modo o aplicativo aceita apenas **pastas**, não arquivos avulsos. O motivo é o
próprio renomear: ele altera a entrada da pasta, e para isso o macOS exige a permissão para a
pasta — que surge quando você a seleciona. Uma vez escolhida, o aplicativo a guarda; o botão
“Escolher pasta” traz as últimas utilizadas em um menu.

**Ao lado do meu arquivo há um arquivo com a extensão `.xmp`.**
Ele vem de outro programa — Lightroom e digiKam criam esses acompanhantes. O sName2Date não
cria nenhum, mas atualiza um já existente quando altera a data de captura. Do contrário, o
arquivo diria uma coisa e o acompanhante outra, e a maioria dos programas lê o acompanhante
primeiro.

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

Andreas Heiligtag · andreas.heiligtag@gmx.de
