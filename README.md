## PyTube — Baixar playlist do YouTube em MP3 (Windows)

Aplicativo simples em interface gráfica (Tkinter) para baixar playlists do YouTube e extrair o áudio em MP3 usando `yt-dlp` e `ffmpeg`.

---

### Download rápido (binário)
- **ZIP do projeto:** [Baixar PyTube](https://github.com/lucasgfabris/PyTube/archive/refs/heads/main.zip)
- Extraia o `.zip` em uma pasta de sua preferência.
- Entre na pasta extraída e localize a subpasta `dist`.
- Abra o arquivo `PyTube.exe` que está dentro de `dist`.

Observação: dependendo da sua build, o executável pode se chamar `main.exe`. Se for o seu caso, basta utilizá-lo do mesmo jeito.

---

### Requisitos (para o binário)
Para que a conversão para MP3 funcione, o `yt-dlp` utiliza o `ffmpeg`:
- `yt-dlp.exe` disponível no PATH do Windows ou na mesma pasta do `PyTube.exe`.
  - Download: [Releases do yt-dlp](https://github.com/yt-dlp/yt-dlp/releases)
- `ffmpeg.exe` disponível no PATH do Windows (ou na mesma pasta do executável).
  - Download: [FFmpeg - Downloads](https://ffmpeg.org/download.html)

Se preferir, você pode copiar `yt-dlp.exe` e `ffmpeg.exe` para a mesma pasta do `PyTube.exe` (dentro de `dist`).

---

### Como usar
1. Abra o `PyTube.exe` (em `dist`).
2. No campo "YouTube playlist link:", cole o link da playlist do YouTube.
3. No campo "Destination folder path:", escolha a pasta onde deseja salvar os arquivos MP3.
4. Clique em "Download Playlist".

Detalhes importantes:
- O aplicativo extrai o áudio da playlist em MP3 usando o `yt-dlp` com as opções `-x --audio-format mp3`.
- Os arquivos são salvos com o padrão de nome: título do vídeo + extensão, por exemplo: `Nome do Vídeo.mp3`.
- Caso haja erro em algum item da playlist, o link é registrado em `errors.txt` dentro da pasta de destino.

---

### Criar atalho do executável (Windows)
Para facilitar o acesso:
1. Navegue até a pasta `dist` do projeto.
2. Clique com o botão direito em `PyTube.exe`.
3. Escolha uma das opções:
   - "Enviar para" > "Área de trabalho (criar atalho)", ou
   - "Criar atalho" e depois mova o atalho para onde preferir (por exemplo, a Área de Trabalho).

---

### Executar pelo código-fonte (opcional)
Se preferir rodar direto pelo Python:

1. Requisitos:
   - Python 3.8+ (Windows)
   - `yt-dlp` e `ffmpeg` instalados/visíveis no PATH
2. Instale as dependências Python:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute:
   ```bash
   python main.py
   ```

Opcional: para pré-preencher o campo de destino, defina a variável de ambiente do Windows `DOWNLOAD_PATH` com o caminho desejado (Painel de Controle > Sistema > Configurações avançadas > Variáveis de Ambiente).

---

### Build do executável (opcional)
Há um arquivo `main.spec` para uso com PyInstaller.

Com PyInstaller instalado (`pip install pyinstaller`), você pode gerar o executável com:
```bash
pyinstaller main.spec
```
O executável será gerado em `dist`.

---

### Solução de problemas
- **Erro: yt-dlp não encontrado**
  - Garanta que `yt-dlp.exe` esteja no PATH ou na mesma pasta do `PyTube.exe`.
- **Erro: ffmpeg não encontrado / conversão para MP3 falha**
  - Instale o `ffmpeg` e garanta que `ffmpeg.exe` esteja no PATH ou na mesma pasta do executável.
- **Permissões de escrita**
  - Verifique se a pasta de destino tem permissões de escrita.
- **Link(s) com erro**
  - Consulte o arquivo `errors.txt` gerado na pasta de destino para ver quais links falharam.

---

### O que este app faz internamente
- Interface gráfica simples com Tkinter (campos para URL da playlist e pasta de destino).
- Executa `yt-dlp.exe` via `subprocess` com as flags necessárias para extrair áudio em MP3.
- Cria a pasta de destino automaticamente caso não exista.
- Em caso de erro, registra o link problemático em `errors.txt`.

---

### Estrutura do projeto (resumo)
- `main.py`: código-fonte principal (Tkinter + chamada ao yt-dlp)
- `requirements.txt`: dependências Python (ex.: `python-dotenv`)
- `main.spec`: configuração de build do PyInstaller
- `dist/`: pasta onde o executável é gerado (ex.: `PyTube.exe`)

---

### Aviso legal
Este projeto é apenas para fins educacionais e de uso pessoal. Respeite os termos de serviço do YouTube e as leis de direitos autorais da sua região.

---

### Créditos
Repositório: `lucasgfabris/PyTube`


