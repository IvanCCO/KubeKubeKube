# Kubernetes

## O que é kubernetes?

Um orquestrador de containers

> O que é um orquestrador de containers?

Imagine que sua aplicação necessita de diversos containers para funcionar,
e precisa de alta escabilidade e disponibilidade,
ou seja, você **não** pode ficar fora do ar.
Então é ai que o kubernetes entra.
Ele tem inteligência para poder substituir os containers que "morrem".
Ou seja se eu coloco meus containers dentro de um cluster Kubernetes
agora ele que toma conta de gerenciar meus containers da maneira que eu configurei

### Recursos

O kubernetes tem diversos Recursos(resources)
que o ajudam a conseguir fazer esse gerenciamento de containers,
por exemplo, se eu coloco um novo container no meu cluster
kubernetes ele sabe qual máquina que é melhor para colocar meu container,
então eu não preciso ficar preocupado com isso
pois sei que o kubernetes está fazendo isso por mim.
Ou por exemplo, caso algum container da minha aplicacao fique downe morra,
ele tem inteligia para poder substituir o container caído.

#### POD

Dentre os Recursos existentes o mais famoso é o POD que
basicamente encapsula 1 ou + containers dentro
e faz esses containers trabalharem dentro do mesmo contexto rede,
ou seja eles conseguem fazer a comunicaćão localhost.
Quando um pod é criado ele é criado com um ip, e os containers dentro dele
compartilham o mesmo ip, sendo assim se eu criar um pod com ip x,
e colocar dentro dele um container mysql, para acessar meu banco mysql
eu preciso apenas me conectar com o ip x:3306.

## Dentro do cluster

Dentro do cluster vamos ter diversas máquinas trabalhando e compartilhando recursos,
e vamos ter máquinas principais (**master**),
e máquinas que vão ser responsáveis apenas pelo trabalho duro
de executar os containers dos pods(**nodes**).

### Master

Nas máquinas master que vamos nos conectar para cordenar nosso cluster kubernetes,
onde faremos a criaćão ou remoção de recursos.

- Gerencia o cluster
- Mantém o estado
- Vai receber os comandos para alterar os recursos -> Control Plane

### Nodes

Responsável apenas por executar a aplicação

A gente não tem controle sobre qual ip vai ser atribuido ao POD

Então como que uma aplicação no pod x que está se comunicando com outra
aplicação no pod y consegue continuar se comunicando caso o pode y
caia e ele volte com outro ip?

Para isso tem um recurso chamado **_Service_**

- Prove ip fixo para comunicação
- Fazem o balanceamento de carga
- Proveem um dns para um ou + pods

## Tipos de serviço

### Cluster IP

Serve para fazer a comunicação de diferentes pods dentro de um mesmo cluster.
