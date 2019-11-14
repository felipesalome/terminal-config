# terminal-config
Configuração do terminal linux

## Instalação

### Clonar o repositório:

```bash
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
```

### Opcional, criar um backup para configuração existente `~/.zshrc` file:

```bash
cp ~/.zshrc ~/.zshrc.orig
```

### Criar uma nova configuração zsh

```bash
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

### Mudando o shell padrão

```bash
chsh -s $(which zsh)
```

### Baixar e instalar o FiraCode

Baixar o `zip` da última versão da fonte disponível aqui: [Fira Code](https://github.com/tonsky/FiraCode/releases)

Configurar o terminal com essa fonte.

### Instalar tema para o terminal (Spaceship)

```bash
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

### Criar links simbólicos
```bash
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

## Configurar o terminal

### Alterando o tema

```js
ZSH_THEME="spaceship"
```

### Mudando visual de exibição

No fim do arquivo `~/.zshrc` adicionar:

```js
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)
SPACESHIP_USER_SHOW=always
SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_PROMPT_SEPARATE_LINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "
```

### Plugins zsh

Configurando o ZPlugin

#### Automático
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zplugin/master/doc/install.sh)"
```

#### Manual
```bash
mkdir ~/.zplugin
git clone https://github.com/zdharma/zplugin.git ~/.zplugin/bin
```
> Adicionar no arquivo `~/.zshrc`:
>```js
>source ~/.zplugin/bin/zplugin.zsh
>autoload -Uz _zplugin
>(( ${+_comps} )) && _comps[zplugin]=_zplugin
>```

Após essa instalação abrir o arquivo `~/.zshrc`, e abaixo da instalação do ZPlugin adicionar:

```js
zplugin light zdharma/fast-syntax-highlighting
zplugin light zsh-users/zsh-autosuggestions
zplugin light zsh-users/zsh-history-substring-search
zplugin light zsh-users/zsh-completions
zplugin light buonomo/yarn-completion
```


> Arquivo com tudo disponível em: [~/.zshrc](https://gist.github.com/diego3g/b0513d5ff6d9d983c48bed3fd8f10cdb)
