# Kubernetes

#### O que é kubernetes? 
Um orquestrador de containers
>> O que é um orquestrador de containers?

Imagine que sua aplicacao necessita de diversos containers para funcionar, e precisa de alta escabilidade e disponibilidade, ou seja, você **não** pode ficar fora do ar. Então é ai que o kubernetes entra. Ele tem inteligência para poder substituir os containers que "morrem". Ou seja se eu coloco meus containers dentro de um cluster Kubernetes agora ele que toma conta de gerenciar meus containers da maneira que eu configurei

#### Recursos

O kubernetes tem diversos Recursos(resources) que o ajudam a conseguir fazer esse gerenciamento de containers, por exemplo, se eu coloco um novo container no meu cluster kubernetes ele sabe qual máquina que é melhor para colocar meu container, então eu não preciso ficar preocupado com isso pois sei que o kubernetes está fazendo isso por mim.
Ou por exemplo, caso algum container da minha aplicacao fique down e morra, ele tem inteligia para poder substituir o container caído.

###### POD
Dentre os Recursos existentes o mais famoso é o POD que basicamente encapsula 1 ou + containers dentro e faz esses containers trabalharem dentro do mesmo contexto rede, ou seja eles conseguem fazer a comunicaćão localhost. 
Quando um pod é criado ele é criado com um ip, e os containers dentro dele compartilham o mesmo ip, sendo assim se eu criar um pod com ip x, e colocar dentro dele um container mysql, para acessar meu banco mysql eu preciso apenas me conectar com o ip x:3306. 



## Dentro do cluster

