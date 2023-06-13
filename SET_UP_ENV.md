# ~/.bashrc example
```
# add git branch
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
PS1="\[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\[\033[00;32m\]\$(parse_git_branch)\[\033[00m\]\$ "

# export PATH
export PATH=$PATH:/usr/local/go/bin
export PATH=$PATH:/opt/gradle/gradle-8.0/bin
export PATH=$PATH:/opt/azcopy/azcopy_linux_amd64_10.18.1/azcopy

# kubectl
source /usr/share/bash-completion/bash_completion
source <(kubectl completion bash)
alias k=kubectl
complete -o default -F __start_kubectl k
export KUBECONFIG=${KUBECONFIG}:${HOME}/.kube/config

# aws complete
export PATH=$PATH;/usr/local/bin/aws_completer
# endpoint url local
export EUL='--endpoint-url http://localhost:8000'
complete -C '/usr/local/bin/aws_completer' aws

# export vim home folder
export VIMRUNTIME=/usr/share/vim/vim82

# K9s colors terminal mode
export TERM=xterm-256color

# Generated for envman. Do not edit.
[ -s "$HOME/.config/envman/load.sh" ] && source "$HOME/.config/envman/load.sh"

```
