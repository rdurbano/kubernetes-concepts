# kubernetes-start

![image](https://user-images.githubusercontent.com/12244452/135544523-867a9838-81d3-4f9d-afb0-fe33c300b209.png)


- Escalabilidade
- Balanceamento de carga entre as réplicas
- Alta disponibilidade
- Resiliência
- Estratégia de atualização adequada
- Gestão unificada dos Kubernetes
- Formado por um cluster (conjunto de máquinas)

# Kubernetes Control Pane
- Gerencia os nodes, maestro.
- Necessário mais de um control Pane para garantir a disponibilidade
- Kube API Server = Comunicação com o cluster.
- ETCD = banco de dados chave valor do Kubernetes, acessa através do Kube API Server
- Kube Scheduler = Componentes organiza cada processo será executado, analisa as especificações e define quais nodes podem ser executados.
- Kube Controller Manager = Administra a tomada de decisão do Kubernetes, autenticação exemplo.
- Pode ser criado mais de um dentro do cluster para dar mais resiliência ao cluster. Em caso de falha de um control pane o outro é ativado.

# Kubernetes Nodes
- Executa toda a carga
- Kubelet = interage com o Kube API Server e execução dos containers
- KubeProxy = comunicação de rede com o cluster
- CRI = especificações necessárias para que um CRI seja executado.
- Docker foi descontinuado pois utiliza um adaptador, no entanto é o mais recomendado para criação das imagens e execução de containers fora do Kubernetes.
- Para execução dentro do Kubernetes podem ser usadas outras ferramentas como:
- Container DI
- Cri-o

# Formas de criar Kubernetes
- OnPremise
  - Kubeadm
  - Kubespray
  - RKE
  - K3S
  - MicroK8S
- Kube As a Service
  - AKS
  - EKS
  - GKE
- Local
  - Minikube
  - Kind
  - K3D
  - MicroK8S
  - K3S


# Instalação Local

Utilização KIND 
- https://docs.chocolatey.org/en-us/choco/setup
- https://kind.sigs.k8s.io/docs/user/quick-start/ (criação dos ambiente kubernetes em containers)
- https://kubernetes.io/docs/tasks/tools/   (comunicação com o control-plane)

Especificação de arquivo YAML para configurar a configuração do cluster. Em caso de ter mais de um nó automaticamente é criado um load balance para gerenciar a carga.

# Elementos de um Deploy 
<b>Pod </b>
- local de execução dos containers
- pode haver mais de um container
- podem compartilhar IP e file system
- não colocar tudo dentro do POD , pois tudo será escalado.
- Para cada POD deve ser colocado um pedaço da aplicação, de mandeira geral , vai ficar 1 container 1 POD.

![image](https://user-images.githubusercontent.com/12244452/135544728-8ccc3c35-8303-4895-9631-4fe1d708e958.png)

<b> Label e Selector </b>
Labels e Selector, todo objeto interage com outros , no entanto precisa selecionar o objeto para saber qual objeto precisa interagir. Label elemento chave valor , no meu POD ou qualquer outro objeto. Selector , através de seletores eu defino qual objeto deve ser selecionado

![image](https://user-images.githubusercontent.com/12244452/135544774-d868b720-88eb-4c7f-b89f-65f447959a07.png)
