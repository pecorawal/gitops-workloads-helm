# GitOps Manifestos de Workloads em Helm para Deploy de Aplicações e Promoção de Ambientes.

Nesse repositório estão definidos os padrões para deploy de aplicações em seus diferentes ambientes. 

No diretório da aplicação, há um arquivo values-<ambiente>.yaml, defina os detalhes para sua aplicação e solicite um Pull Request. 



<!-- readme-tree start -->
```
.
├── .github
│   └── workflows
│       └── readme-tree.yml
├── .gitignore
├── README.md
├── apps
│   ├── checkout-frontend
│   │   ├── Chart.yaml
│   │   ├── templates
│   │   │   ├── deployment.yaml
│   │   │   ├── route.yaml
│   │   │   └── service.yaml
│   │   ├── values-dev.yaml
│   │   ├── values-prod.yaml
│   │   └── values-qa.yaml
│   └── pagamentos-api
│       ├── Chart.yaml
│       ├── templates
│       │   ├── deployment.yaml
│       │   └── service.yaml
│       ├── values-dev.yaml
│       ├── values-prod.yaml
│       └── values-qa.yaml
└── tree.bak

8 directories, 17 files
```
<!-- readme-tree end -->

## Passos para aplicação iniciar o deploy:

- acessar o diretorio apps
- entrar no diretorio da sua aplicação (ex: checkout-frontend)
- crie os manifestos k8s que necessita para sua aplicação.
- altere o arquivo values-<ambiente>.yaml referente ao ambiente que deseja
- solicite um pull request para a branch main
- assim que confirmado o commit a aplicação será sincronizada com o repositório gitops-infra
- O repositório gitops-infra contem os application sets e varre no argocd em busca dos clusters elegiveis para deploy de acordo com o ambiente solicitado.

