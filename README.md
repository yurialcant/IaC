# Primeiro teste com terraform e ansible
| 🪧 Vitrine.Dev |     |
| -------------  | --- |
| ✨ Nome        | Teste com terraform e ansible
| 🏷️ Tecnologias | Terraform e Ansible
| 🚀 URL         | https://github.com/yurialcant/Primeiro-teste-terraform-e-ansible
| 🤿 Desafio     | Montar o primeiro projeto usando o terraform e o ansible

<h1>Primeiro teste utilizando terraform para criar uma máquina virtual no AWS EC2 e acessa-la remotamente via SSH</h1>

Em nosso main.tf usamos os dois primeiros blocos de código para definir a fonte de nosso provedor, a versão dele e qual o provedor que estaremos utilizando, nesse caso o AWS, importante selecionar a região que utilizaremos, em nosso caso iremos usar a us-east-2 (Leste dos EUA - Ohio).

![Captura de Tela (521)](https://github.com/yurialcant/Primeiro-teste-terraform-e-ansible/assets/102321564/dcfb8548-2a4f-4d6d-8c96-d0692d6781ed)

Em nosso terceiro de bloco de código, identificamos o recurso que iremos utilizar no caso como desejamos iniciar uma instância EC2 na AWS, iremos utilizar aws_instance, nele passaremos alguns parâmetros como a ami do OS que desejamos utilizar, o tipo de instância o nome da chave para poder realizar o acesso SSH e uma tag passando o nome para identificarmos nossa instância no EC2. No user_data quando utilizamos o terraform podemos passar um código feito no padrão git/bash para a criação do nosso arquivo index.html, passando todos os parâmetros desejados e identificando o formato do arquivo que desejamos criar.


![Captura de Tela (522)](https://github.com/yurialcant/Primeiro-teste-terraform-e-ansible/assets/102321564/c0197a43-240d-4b94-bc7a-a45cd2bdf598)

<h1>Utilizando o Ansible</h1>

Para utilizarmos o Ansible necessitamos criar dois arquivos o hosts e o playbook, ambos recebendo o formato yml, no hosts iremos identificar o que estamos utilizando no caso terraform com ansible e passaremos o ip de nossa instância criada no EC2.

![Captura de Tela (523)](https://github.com/yurialcant/Primeiro-teste-terraform-e-ansible/assets/102321564/3af83f91-11f1-4d1c-b1b5-5ba2630dc8b7)

Em nosso arquivo playbook passamos todas as tarefas que desejamos que o ansible execute, no caso a criação do nosso arquivo html e do nosso servidor, passando todos os parâmetros necessários.

![Captura de Tela (524)](https://github.com/yurialcant/Primeiro-teste-terraform-e-ansible/assets/102321564/79d5d0ff-d7a4-4911-ab0d-370f65a8050b)

