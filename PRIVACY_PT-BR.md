# Política de Privacidade do sName2Date

Situação: 2026-09-25

Esta Política de Privacidade vale para o sName2Date e para o sName2Date Lite.

## Resumo

O sName2Date **não** coleta, armazena nem transmite dados pessoais. O aplicativo funciona
exclusivamente no seu Mac e não estabelece nenhuma conexão com a internet.

## Quais dados o aplicativo processa

O sName2Date lê os arquivos que você lhe entrega expressamente — pela seleção na caixa de
diálogo de abertura ou arrastando-os para a janela. São lidos o nome do arquivo e os
metadados do arquivo; é gravada a data de captura exatamente nesses arquivos.

Se você quiser, o aplicativo também renomeia esses arquivos (desativado de fábrica). Além
disso, ele define a data de criação e de modificação deles (ativado de fábrica, pode ser
desligado nas Configurações). Em arquivos que não podem conter uma data de captura — como PDF
ou texto —, ele define sempre apenas essas duas datas.

Se a caixa **Gravar a data no arquivo** estiver desmarcada, o aplicativo **não abre nenhum
arquivo**: ele lê apenas o nome e altera apenas o nome e, se estiver configurado, a data de
criação e de modificação. O conteúdo não é lido nem gravado.

Sem a sua seleção, o aplicativo não acessa arquivo algum. O macOS garante isso por meio da
sandbox do aplicativo.

Quando o aplicativo percorre uma pasta que contém a pasta “Música”, o macOS pode perguntar se
ele pode acessar “Mídia e Apple Music”. O aplicativo não lê a sua biblioteca nem o seu
histórico de reprodução. Ali, como em qualquer lugar, ele trabalha apenas com arquivos e grava
a data em arquivos de áudio e de vídeo cujo nome contenha uma.

## O que o aplicativo guarda no seu Mac

- **As configurações**, em um arquivo `config.json` na pasta protegida do aplicativo.
- **Um registro de diagnóstico**, na mesma área, apagado automaticamente após sete dias. Ele
  contém horários e quantidades de operações. Você pode salvá-lo e repassá-lo em
  Configurações → Diagnóstico; fora isso, ele não sai do seu Mac.
- **Os caminhos das pastas que você liberou**, junto com a permissão do macOS para abri-las
  novamente na próxima inicialização. Só assim o aplicativo não precisa perguntar toda vez. A
  lista contém caminhos de pastas, não conteúdos de arquivos, e o botão “Escolher pasta” a
  mostra para você.

Tudo isso é removido junto com o aplicativo quando você o apaga.

**Ao lado dos seus arquivos, o aplicativo só cria algo em um caso:** se um arquivo de foto,
vídeo ou áudio não puder conter a data de captura por si só (como HEIF, WebP ou AVI), o
aplicativo a grava em um arquivo acompanhante com o mesmo nome e a extensão `.xmp`, que muitos
programas de fotos também leem. ⌘Z o remove novamente. Ao lado de outros arquivos, como PDF ou
texto, nunca surge um. Se já houver ali um arquivo acompanhante — ele vem, nesse caso, de outro
programa de imagem —, a data de captura dele é atualizada junto, para que arquivo e
acompanhante não digam coisas diferentes. O que o aplicativo não entende ali permanece
intocado.

## Nenhum repasse, nenhuma análise

Não há publicidade, nem serviços de análise, nem relatórios de falha para terceiros, nem
contas.

## Contato

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
