# AWS SAM bash-completion

It is a bash completion tool for [AWS SAM Local](https://github.com/awslabs/aws-sam-local#invoke-functions-locally).

## Installation

[bash_completion](https://github.com/scop/bash-completion) must be installed. Please set in advance.

Execute the following and make it readable by `bash_completion`.
```
$ wget https://raw.githubusercontent.com/daisuke-awaji/sam_completion/master/sam_completion \
-P /usr/local/etc/bash_completion.d/
```

## Usage
You can complement by pressing `sam` followed by TAB.
```
$ sam <TAB>
deploy    help      local     package   validate
```

<img src="https://user-images.githubusercontent.com/20736455/38767300-7a215544-4019-11e8-983c-20c0a2d6cf14.gif" width="900px">
