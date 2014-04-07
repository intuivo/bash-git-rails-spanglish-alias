Bash git-rails Spanish Aliases and shortcuts
===========================================

Bash aliases for developing under Linux for rails, and git

### Concept:
> Since everything in English is a reserved word. Spanish or any other language happens to be very useful, because it allows me the liberty of adding more commands. There are also many ways of saying something in Spanish.


### Install:
> Just copy past it in your `.bashrc` or `.bash_profile`
files then `source ~/.bash_profile` to it.


### Code:
```
function guardar {
   git commit -m $@
}


function agregar {
   git add .
}

alias amazon='ssh -i ~/.ssh/your_amazon_key.pem ec2-user@ec2-12-345-67-89.us-east-0.compute.amazonaws.com'

function cambiar {
   git checkout $1
}
alias checar='cambiar $1'
alias compilar='bundle exec rake assets:precompile'
alias consola='bundle exec rails console'
alias correr='bundle exec rails server'
alias crear='bundle exec rake db:create:all'
alias culpar='git blame $1'
alias datar='crear && migrar && llenar'
alias escupir='bundle exec rake db:schema:dump'
alias gemiza='rvm gemset create $1'
alias gemizas='rvm gemset list'
alias gemusar='rvm gemset use $1'

alias iniciar='git init'
alias instalar='bundle && bundle install && datar'
alias jalar='git pull origin master'
alias llenar='bundle exec rake db:seed'
alias migrar='bundle exec rake db:migrate'
alias origen='git remote add origin $1'
alias poner='agregar $$ guardar $1'
function pushar {
	git push origin master
}
function subir {
	agregar
	guardar $@
	pushar
}
alias rama='cambiar $1'
alias ramas='git branch'
alias remoto='origen $1'
alias version='bundle exec rails -v'
alias comandos='echo -e "

 agregar = git add .
 amazon = ssh -i ~/.ssh/your_amazon_key.pem ec2-user@ec2-12-345-67-89.us-east-0.compute.amazonaws.com
 cambiar = git checkout $1
 compilar = bundle exec rake assets:precompile
 consola = bundle exec rails console
 correr = bundle exec rails server
 crear = bundle exec rake db:create:all
 culpar = git blame $1
 datar = crear && migrar && llenar
 escupir = bundle exec rake db:schema:dump
 gemiza = rvm gemset create $1
 gemizas = rvm gemset list
 gemusar = rvm gemset use $1
 guardar = git commit -m $1
 iniciar = git init
 instalar = bundle && bundle install && datar
 jalar = git pull origin master
 llenar = bundle exec rake db:seed
 migrar = bundle exec rake db:migrate
 origen = git remote add origin $1
 poner = agregar $$ guardar $1
 pushar = git push origin master
 ramas = git branch
 remoto = origen $1
 subir = agregar && guardar $1 && pushar
 version = bundle exec rails -v
"'
alias ayuda="comandos"
alias commandos="comandos"

```
