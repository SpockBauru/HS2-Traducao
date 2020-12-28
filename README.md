# Tradução para HS2

Projeto de fãs para traduzir Honey Select 2 (HS2) para o português brasileiro. As traduções são aplicadas em tempo de execução e não requerem substituição ou modificação de nenhum arquivo do jogo.

## Pré-requisitos

- [BepInEx 5.3](https://github.com/BepInEx/BepInEx/releases/tag/v5.3)
- [BepisPlugins para HS2](https://github.com/bbepis/BepisPlugins/releases)
- [XUnity.AutoTranslator](https://github.com/bbepis/XUnity.AutoTranslator)
- [HS2_TextResourceRedirector](https://github.com/IllusionMods/TranslationTools#textresourceredirector) (necessário para a maioria dos recursos)
- [HS2_Subtitles](https://github.com/DeathWeasel1337/KK_Plugins#subtitles) (necessário para ver as legendas)
- [HS2_TranslationHelper.v1.0.zip](https://github.com/GeBo1/GeBoPlugins/releases/tag/r14) (opcional, mas recomendado. Traduz nomes japoneses para o alfabeto ocidental sem tentar traduzir para o português evitando erros como 悟飯=Comida ao invés de 悟飯=Gohan).

## Instalação

1. Certifique-se de ter os pré-requisitos instalados.
2. Vá para a página de "releases" acima e baixe a versão mais recente. Como alternativa, os usuários avançados podem obter as traduções beta mais recentes clicando no botão "Clone or download" acima. Se você é tradutor, leia as seções abaixo para ver como contribuir com as traduções.
3. Extraia o zip e coloque a pasta Translation na pasta BepInEx. Recomenda-se excluir sua pasta de tradução antiga para evitar conflitos de tradução.
4. Instale o [AutoTranslatorConfig.ini] mais recente (config/AutoTranslatorConfig.ini) (ou compare-o com o arquivo existente e certifique-se de que as entradas nas seguintes seções conferem: `Files`,` TextFrameworks`, `Behaviour`, `Texture`,` ResourceRedirector`)

## Contribuição

Toda ajuda é bem vinda. Independentemente de sua habilidade de tradução e conhecimento de japonês, você ainda pode ajudar com as traduções. Mesmo se você não tiver experiência, pode ajudar revisando ou usando o Google Translate ou outros serviços de tradução e, em seguida, limpando a tradução usando o bom senso e um pouco de lógica. A tradução feita puramente por máquina deve ser mantida na pasta designada, mas é preferível evitá-la.

As traduções estão todas dentro da pasta `Bepinex\Translation\pt\`. Eles são então divididos nas seguintes pastas:
- `RedirectedResources` - Substituições para palavras embutidas em arquivos de recursos. Preferível em relação à `Text` devido sua precisão e desempenho.
- `Text` - Substituições e modificações de texto normal.
- `Text\Localizations` - Palavras nesta pasta foram despejadas via TextDump. As traduções podem ser adicionadas para entradas ausentes, mas as novas entradas não devem ser adicionadas ou será difícil mesclar despejos futuros.
- `Text\zz_MachineTranslations` - Todas as traduções feitas por máquinas (como o google tradutor) vão aqui. As entradas limpas ou traduzidas manualmente devem ser enviadas corretamente para outras pastas. O objetivo é traduzir adequadamente até que esta pasta fique vazia.
- `Texture` - Substituições de imagens.

As traduções serão revisadas antes de serem adicionadas via "pull-request". Sendo assim nem toda tradução irá automaticamente entrar na base de dados.

### Como adicionar ou melhorar traduções

- Se quiser fazer uma edição simples, basta abrir o arquivo em questão e clicar em "edit". Depois de terminar a edição, confirme as alterações e faça uma solicitação "pull request".
- Se você tiver mais traduções para enviar [Faça um fork] (https://help.github.com/articles/fork-a-repo/). Faça upload de suas alterações para o "fork" e, em seguida, [envie uma "pull request"] (https://help.github.com/articles/about-pull-requests/). Sua solicitação de "pull request" será revisada e aceita após uma verificação de qualidade. Novamente, evite traduções feita puramente por máquina. São essenciais o correto uso de maiúsculas e minúsculas, a pontuação e a ortografia adequada.

## Tradução de texto

### Níveis de escopo conhecidos

| Nível | Descrição              |
|------:| -----------------------|
| -1    | (global)               |
| 0     | Diálogos               |
| 1     | Menu de Configurações  |
| 2     | Menu Principal         |
| 3     | Editor de Personagens |
| 4     | Meu Quarto             |
| 6     | Cenas de Diálogo ADV   |
| 7     | Cenas de Sexo          |
| 8     | Recepção               |
| 9     | Quarto da Fur          |
| 10    | Uploader de Cartas     |
| 11    | Downloader HS2 / AI    |
| 13    | Tela Inicial da Rede   |
| 14    | Busca de personagens   |
| 15    | Recepção VIP           |

## Tradução de recursos

- `adv` - Diálogos principais do jogo
- `etcetra/list/config` - Personalidade
- `etcetra/list/parametername` - Peculiaridades, fetiches, estado
- `gamedata/Achivement/Achivement` - Conquistas
- `gamedata/achievement/exchange` - Desbloqueáveis/upgrades,
- `gamedata/bgmname` - Música de fundo
- `gamedata/eventcontent` - atividade/necessidade atual
- `map/list/mapinfo` - nomes de mapas
- `list/characustom` - coisas do editor de personagens
- `list/h/animationinfo` - posições (versões do jogo)
- `list/h/sound` - Legendas
- `spr/list/*/planname` - Nomes de serviços VIP
- `studio` - Coisas do estúdio

### Traduções ADV

Cada arquivo translation.txt tem o texto japonês original que precisa de tradução. Cada um começa comentado (`//` no início), portanto não será carregado. Para que o seu texto seja exibido corretamente no jogo, coloque a tradução no lado direito do sinal de igual e remova o `//` no início da linha. Não edite o texto em japonês ou a tradução não funcionará.

A pasta `assets` dentro de `Bepinex\Translation\pt\ RedirectedResources` pode ser compactada em um arquivo .zip para ser lido pelo jogo (simplesmente clique com o botão direito na pasta de recursos e depois comprima para .zip). Arquivos descompactados em `assets` também são carregados. O jogo deve ser reiniciado para ver as traduções atualizadas.

O plugin [TextResourceRedirector] (https://github.com/IllusionMods/TranslationTools#textresourceredirector) é necessário para essas traduções.

### Linhas de tradução especializadas

Existem alguns recursos especializados tratados pelo TextResourceRedirector que requerem algum tratamento adicional.

#### Formatar strings

As strings de formato têm substituições processadas por [`String.Format`] (https://docs.microsoft.com/en-us/dotnet/api/system.string.format?view=netframework-4.6#Starting). As seções que são substituídas pelo mecanismo de jogo serão semelhantes a `{0}`, `{1}`, `{2}`, etc. Normalmente são o nome de um personagem ou o nome de algum item. As mesmas substituições encontradas na string original devem existir na string traduzida.

Exemplo:
```
{0}と仲がいいと思ってるわ=Acho que sou um bom amigo de {0}.
```

#### ADV Choices

Como essas strings são codificadas em uma entrada maior nos arquivos de recursos, elas exigem tratamento especial por TextResourceRedirector para garantir que o texto que não deve ser substituído permaneça intocado, enquanto permite que o texto exibido seja traduzido. Essas linhas começarão com `CHOICE:` seguido pelo texto que precisa ser traduzido. No lado direito de `=` você só precisa incluir o texto traduzido sem o prefixo `CHOICE:`.

Exemplo:
```
CHOICE:受け取る=Aceitar
```

#### Prefixos opcionais

Existem vários recursos que suportam o uso de prefixação opcional para obter uma correspondência mais exata. Isso permite traduções mais específicas nos casos em que vários ativos podem corresponder ao mesmo código de substituição. A correspondência para esses ativos tentará primeiro a correspondência prefixada e, em seguida, voltará para a correspondência não prefixada padrão. Dado o seguinte arquivo de tradução:

```
PREFIX1:こんにちは=Oi!
こんにちは=Olá.
```
Tentar corresponder `こんにちは` para um recurso usando `PREFIX1` retornará `Oi! `, mas um recurso usando`PREFIX2` retornará `Olá`.

| localização do recurso       | prefixo       | Notas                                                                               |
|------------------------------|---------------|-------------------------------------------------------------------------------------|
| `etcetra/list/parametername` | `HATTRIBUTE:` |                                                                                     |
| `etcetra/list/parametername` | `MIND:`       |                                                                                     |
| `etcetra/list/parametername` | `STATE:`      |                                                                                     |
| `etcetra/list/parametername` | `TRAIT:`      |                                                                                     |
#### Personalidades

| ID | Nome   | Nome Port.   | Dialog (`adv/scenario/`) | Subtitles (`list/h/sound/voice/*/`) |
|----|--------|--------------|--------------------------|-------------------------------------|
| 0  | クール  | Calma          | `c00`                    | `hvoicestart_c00_*`, `hvoice_c00*`  |
| 1  | 普通   | Normal        | `c01`                    | `hvoicestart_c01_*`, `hvoice_c01_*`  |
| 2  | 苦労人  | Trabalhadora   | `c02`                    | `hvoicestart_c02_*`, `hvoice_c02_*`  |
| 3  | 女友達  | Namoradeira   | `c03`                    | `hvoicestart_c03_*`, `hvoice_c03_*`  |
| 4  | ギャル  | Na Moda       | `c04`                    | `hvoicestart_c04_*`, `hvoice_c04_*`  |
| 5  | 気弱   | Tímida        | `c05`                    | `hvoicestart_c05_*`, `hvoice_c05_*`  |
| 6  | 母性的  | Maternal      | `c06`                    | `hvoicestart_c06_*`, `hvoice_c06_*`  |
| 7  | ドS   | Sádica        | `c07`                    | `hvoicestart_c07_*`, `hvoice_c07_*`  |
| 8  | オープン | Aberta         | `c08`                   | `hvoicestart_c08_*`, `hvoice_c08_*`  |
| 9  | 天然   | Cabeça Oca    | `c09`                    | `hvoicestart_c09_*`, `hvoice_c09_*`  |
| -1 | フュル  | Fur           | `c-1`                    |                                      |
| -2 | シトリー | Sitri         | `c-2`                    |                                      |

### Ferramentas

- [Release Tool](https://github.com/IllusionMods/KoikatsuStoryTranslation/tree/master/tools/ReleaseTool) - Ferramenta que limpa os arquivos de tradução para remover quaisquer partes não traduzidas desnecessárias.
- [Yomichan](https://foosoft.net/projects/yomichan/) - Este plugin do navegador permite que você veja a definição de palavras japonesas colocando o mouse sobre elas no navegador e pressionando shift.
- Dicionários:
  - https://jisho.org/  
  - http://www.romajidesu.com/  
