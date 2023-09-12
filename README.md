Nesse Repositório vocês vão encontrar dois arquivos yaml configurados para criação de um cluster kubernetes local utilizando
kind para essa função, e um um yaml criando um pod.

Para poder executar os arquivos localmente conferir os pré requisitos instalados na máquina;
1 - docker instalado.
2 - kind instalado.
3 - kubectl instaldo.

Para instalação do kubectl recomendo esse link direto da documentação do kubernetes https://kubernetes.io/docs/tasks/tools/
Para instalação do kind recomendo esse link https://kind.sigs.k8s.io/docs/user/quick-start/
Para instalação do Docker recomendo esse link https://docs.docker.com/engine/install/

Para todas as instalações temos opção para Linux, Mac, e Windows.

No arquivo kind-cluster.yaml estamos criando um cluster contendo um control plane e dois workers
No arquivo pod.yaml estamos iniciando um pod rodando o Nginx.

Após instalado todos os programas podemos iniciar o processo do teste criando o cluster pelo Kind.
Para criar utilizando o arquivo devemos podemos utilizar o comando a baixo, alterando o nome para oque preferir.
kind create cluster --name meu-cluster --config kind-cluster.yaml

Para validar se criou podemos rodar o comando;
kind get clusters

Após esse processo podemos criar o nosso primeiro pod utilizando o arquivo "pod.yaml"
kubectl apply -f pod.yaml

Para validar podemos rodar o comando;
kubectl get pods 

Para deleter o pod e cluster após os testes podemos utilizar os comandos a seguir;

Para apagar o pod podemos utilizar o arquivo .yaml;
kubectl delete -f pod.yaml

Para apagar o cluster podemos rodar o seguinte comando;
kind delete clusters $(kind get clusters)



