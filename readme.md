These are the instructions to activate git autocomplete:

For Zsh (macOS Catalina and later)
Zsh is the default shell on modern Macs. You can enable basic autocompletion by ensuring compinit is loaded. For full Git command and branch name completion, you need the specific Git completion script. 

    Download the Git completion scripts from the official Git repository to a local directory:
    bash

    mkdir -p ~/.zsh
    curl -o ~/.zsh/git-completion.bash https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash
    curl -o ~/.zsh/_git https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.zsh

    Update your ~/.zshrc file to use these scripts. Open the file in a text editor (e.g., nano ~/.zshrc) and add the following lines:
    bash

    fpath=(~/.zsh $fpath)
    autoload -Uz compinit
    compinit
    zstyle ':completion:*:*:git:*' script ~/.zsh/git-completion.bash

    Save the file and reload your terminal configuration by either restarting the terminal or running:
    bash

    source ~/.zshrc
