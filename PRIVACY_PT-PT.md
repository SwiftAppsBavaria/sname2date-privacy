# Política de privacidade do sName2Date

Atualizado em: 2026-09-25

Esta política de privacidade aplica-se ao sName2Date e ao sName2Date Lite.

## Em resumo

O sName2Date **não** recolhe, não guarda e não transmite quaisquer dados pessoais. A
aplicação funciona exclusivamente no seu Mac e não estabelece qualquer ligação à Internet.

## Que dados a aplicação trata

O sName2Date lê os ficheiros que lhe são entregues expressamente — por seleção na caixa de
diálogo de abertura ou arrastando-os para a janela. São lidos o nome do ficheiro e os
metadados do ficheiro; é escrita a data de captura exatamente nesses ficheiros.

Se assim o quiser, a aplicação muda também o nome desses ficheiros (desativado por
predefinição). Além disso, define a data de criação e de modificação (ativado por predefinição,
pode ser desativado nas Definições). Nos ficheiros que não podem conter uma data de captura —
por exemplo, PDF ou texto —, define em vez disso sempre apenas estas duas datas.

Se a caixa **Escrever a data no ficheiro** estiver desassinalada, a aplicação **não abre um
único ficheiro**: lê apenas o nome e altera apenas o nome e, se estiver configurado, a data de
criação e de modificação. O conteúdo não é lido nem escrito.

Sem a seleção do utilizador, a aplicação não acede a ficheiro nenhum. O macOS impõe-o através da
sandbox de aplicações.

Quando a aplicação percorre uma pasta que contém a pasta «Música», o macOS pode perguntar se
ela pode aceder a «Multimédia e Apple Music». A aplicação não lê a biblioteca nem o
histórico de reprodução do utilizador. Aí, como em todo o lado, trabalha apenas com ficheiros e escreve a
data em ficheiros de áudio e de vídeo cujo nome contenha uma.

## O que a aplicação guarda no seu Mac

- **As definições**, num ficheiro `config.json` na pasta protegida da aplicação.
- **Um registo de diagnóstico**, na mesma área, que é apagado automaticamente ao fim de sete
  dias. Contém momentos e números de operações. Pode ser guardado e enviado através de
  Definições → Diagnóstico; de resto, não sai do Mac.
- **Os caminhos das pastas que foram autorizadas**, juntamente com a permissão do macOS para as
  voltar a abrir no arranque seguinte. Só assim a aplicação não tem de perguntar de cada vez.
  A lista contém caminhos de pastas, não conteúdos de ficheiros, e o botão «Escolher pasta»
  mostra-a.

Tudo isto é removido com a aplicação, quando é eliminada.

**Ao lado dos seus ficheiros, a aplicação só cria algo num caso:** se um ficheiro de
fotografia, vídeo ou áudio não puder conter ele próprio a data de captura (por exemplo, HEIF,
WebP ou AVI), a aplicação escreve-a num ficheiro acompanhante com o mesmo nome e a extensão
`.xmp`, que muitos programas de fotografia também leem. ⌘Z volta a removê-lo. Ao lado de outros
ficheiros, como PDF ou texto, nunca surge nenhum. Se já existir aí um ficheiro acompanhante —
proveniente, nesse caso, de outro programa de imagem —, a data de captura nele contida é
atualizada também, para que o ficheiro e o seu acompanhante não digam coisas diferentes. O que
a aplicação não entende nesse ficheiro fica intacto.

## Sem transmissão, sem análise

Não há publicidade, não há serviços de análise, não há relatórios de falhas para terceiros e
não há contas.

## Contacto

Andreas Heiligtag · SwiftAppsBavaria@gmx.net
