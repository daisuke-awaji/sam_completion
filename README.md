# AWS SAM bash-completion

[AWS SAM Local](https://github.com/awslabs/aws-sam-local#invoke-functions-locally)
用のbash補完ツールです。

## Installation

### 前提

[bash_completion](https://github.com/scop/bash-completion)をインストールしている必要があります。事前に設定しておいてください。

### インストール
以下を実行して`bash_completion`で読み込めるようにします。
```
$ wget https://github.com/daisuke-awaji/sam_completion/blob/master/sam_completion \
-P /usr/local/etc/bash_completion.d/
```

## Usage
samコマンドに続いてTABを押せば補完されます。
```
$ sam <TAB>
deploy    help      local     package   validate
```
