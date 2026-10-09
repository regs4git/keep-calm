# Keep Calm

PWA simples para criar posters no formato 2:3, sem contas, backend ou dependências externas.

## Funcionalidades

- Texto inicial «KEEP / CALM / AND» e mensagem editáveis.
- Paletas visuais e selecção livre para fundo e tinta.
- Coroa, coração, avião, café ou taça; símbolo opcional.
- Toque no topo do poster para ilustração, centro para texto/tinta e parte inferior para fundo.
- Ícones no topo para repor, descarregar PNG e partilhar.
- PNG de 2000 × 3000 píxeis, com o mesmo desenho da pré-visualização.
- Preferências guardadas automaticamente no dispositivo.
- Instalação como PWA e funcionamento offline após a primeira visita completa.

## Publicar no GitHub Pages

1. Cria um repositório, por exemplo `keep-calm`.
2. Extrai este ZIP e coloca **os ficheiros directamente na raiz do repositório**, sem uma pasta intermédia.
3. No GitHub, abre **Settings → Pages**.
4. Em **Build and deployment**, selecciona **Deploy from a branch**.
5. Escolhe a branch `main` e a pasta **/(root)**, depois **Save**.
6. Aguarda a publicação e abre o endereço apresentado pelo GitHub Pages: normalmente `https://UTILIZADOR.github.io/keep-calm/`.

Os caminhos são relativos: podes escolher outro nome para o repositório. Não precisas de configurar chaves, instalar pacotes ou compilar. A disponibilidade de Pages em repositórios privados depende do teu plano GitHub.

## Instalar

- **Android:** abre no Chrome e usa «Instalar aplicação» ou «Adicionar ao ecrã principal». O botão de instalação surge na app quando o browser o disponibiliza.
- **iPhone:** abre no Safari → Partilhar → Adicionar ao ecrã principal.

O alojamento tem de usar HTTPS; localhost também serve para desenvolvimento. Abrir `index.html` como ficheiro não permite instalar a PWA nem activar o Service Worker.

## Executar localmente

Na pasta do projecto:

```bash
python3 -m http.server 8080
```

Abre `http://localhost:8080`.

## Ficheiros

| Ficheiro | Função |
| --- | --- |
| `index.html` | Interface, desenho do poster, edição e exportação |
| `manifest.json` | Metadados de instalação |
| `sw.js` | Cache offline e actualizações |
| `icon-192.png`, `icon-512.png` | Ícones da aplicação |
| `SPEC.md` | Especificação técnica e decisões |
| `.nojekyll` | Publicação estática sem processamento Jekyll |
| `.gitignore` | Exclusões de ficheiros temporários |

## Actualizações e dados

O Service Worker tenta obter os ficheiros pela rede e usa a cache quando não existe ligação. Depois de publicares alterações, volta a abrir ou recarrega a app com Internet; uma página já aberta não muda automaticamente. Para mudanças no Service Worker ou na lista de recursos, incrementa o identificador `CACHE` em `sw.js`.

As preferências usam a chave `keep-calm-v1` em `localStorage`. Não alteres esta chave sem prever uma migração. Limpar os dados do site elimina as preferências. Não existe sincronização, telemetria ou envio dos textos para um backend da app; o alojamento pode manter os seus próprios registos de acesso.

## Limitações e validação

A instalação e a partilha de ficheiros dependem do browser. Quando a partilha directa não estiver disponível, descarrega o PNG. A fonte usa alternativas locais, pelo que a tipografia pode variar entre dispositivos. Os emojis identificam as opções; as ilustrações exportadas são vectores monocromáticos desenhados no canvas.

Sintaxe JavaScript e referências dos controlos verificadas. Validação visual e testes de instalação/offline em Android e iPhone ainda pendentes. Após publicar, confirma edição, download, partilha, persistência depois de reabrir e funcionamento em modo avião.
