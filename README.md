# Python YouTube MP3

![GitHub repo size](https://img.shields.io/github/repo-size/lucasgfabris/python-youtube-mp3?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/lucasgfabris/python-youtube-mp3?style=for-the-badge)

> Aplicativo com interface grafica (Tkinter) para baixar playlists do YouTube e extrair o audio em MP3 usando yt-dlp e ffmpeg.

<img src="imagem.png" alt="Python YouTube MP3">

## Pre-requisitos

Antes de comecar, verifique se voce atendeu aos seguintes requisitos:

### Para o binario (.exe)

- `yt-dlp.exe` disponivel no PATH ou na mesma pasta do executavel
  - Download: [Releases do yt-dlp](https://github.com/yt-dlp/yt-dlp/releases)
- `ffmpeg.exe` disponivel no PATH ou na mesma pasta do executavel
  - Download: [FFmpeg - Downloads](https://ffmpeg.org/download.html)

### Para rodar pelo codigo-fonte

- Python 3.8+ (Windows)
- yt-dlp e ffmpeg instalados no PATH

## Instalando

### Download rapido (binario)

1. Baixe o ZIP: [Baixar Python YouTube MP3](https://github.com/lucasgfabris/python-youtube-mp3/archive/refs/heads/main.zip)
2. Extraia o `.zip` em uma pasta de sua preferencia
3. Entre na pasta extraida e localize a subpasta `dist`
4. Abra o arquivo `python-youtube-mp3.exe`

### Instalar pelo codigo-fonte

```bash
git clone https://github.com/lucasgfabris/python-youtube-mp3.git
cd python-youtube-mp3
pip install -e .
# ou: pip install -r requirements.txt
```

## Usando

Para usar o Python YouTube MP3, siga estas etapas:

### Executar o binario

1. Abra o `python-youtube-mp3.exe` (em `dist`)
2. No campo "YouTube playlist link:", cole o link da playlist
3. No campo "Destination folder path:", escolha a pasta de destino
4. Clique em "Download Playlist"

### Executar pelo codigo-fonte

```bash
python main.py
```

### Detalhes importantes

- O aplicativo extrai o audio da playlist em MP3 usando o yt-dlp
- Os arquivos sao salvos com o padrao: titulo do video + extensao
- Caso haja erro em algum item, o link e registrado em `errors.txt`

### Variavel de ambiente (opcional)

Defina `DOWNLOAD_PATH` para pre-preencher o campo de destino:

```
Painel de Controle > Sistema > Configuracoes avancadas > Variaveis de Ambiente
```

## Gerando o executavel

Com PyInstaller instalado:

```bash
pip install pyinstaller
pyinstaller main.spec
```

O executavel sera gerado em `dist`.

## Tecnologias

| Categoria | Tecnologias |
|-----------|-------------|
| Linguagem | Python 3.8+ |
| Interface | Tkinter |
| Download | yt-dlp |
| Conversao | ffmpeg |
| Build | PyInstaller |

## Estrutura do Projeto

```
python-youtube-mp3/
├── main.py           # Codigo principal (Tkinter + yt-dlp)
├── pyproject.toml    # Metadados e dependencias
├── requirements.txt  # Dependencias (alternativa)
├── main.spec         # Configuracao do PyInstaller
├── dist/             # Pasta do executavel gerado
└── LICENSE           # Licenca MIT
```

## Solucao de problemas

| Problema | Solucao |
|----------|---------|
| yt-dlp nao encontrado | Coloque `yt-dlp.exe` no PATH ou na pasta do executavel |
| ffmpeg nao encontrado | Coloque `ffmpeg.exe` no PATH ou na pasta do executavel |
| Permissoes de escrita | Verifique se a pasta de destino tem permissoes |
| Links com erro | Consulte `errors.txt` na pasta de destino |

## Contribuindo

Para contribuir com Python YouTube MP3, siga estas etapas:

1. Bifurque este repositorio.
2. Crie um branch: `git checkout -b <nome_branch>`.
3. Faca suas alteracoes e confirme-as: `git commit -m '<mensagem_commit>'`
4. Envie para o branch original: `git push origin <nome_branch>`
5. Crie a solicitacao de pull.

## Aviso Legal

Este projeto e apenas para fins educacionais e de uso pessoal. Respeite os termos de servico do YouTube e as leis de direitos autorais da sua regiao.

## Licenca

Esse projeto esta sob licenca MIT.
