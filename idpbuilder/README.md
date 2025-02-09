# idpbuilder

https://cnoe.io

## Installation

### Download and binary configuration
```
mkdir -p ~/code/lab/idpbuilder
cd mkdir -p ~/code/lab/idpbuilder

arch=$(if [[ "$(uname -m)" == "x86_64" ]]; then echo "amd64"; else uname -m; fi)
os=$(uname -s | tr '[:upper:]' '[:lower:]')

idpbuilder_latest_tag=$(curl --silent "https://api.github.com/repos/cnoe-io/idpbuilder/releases/latest" | grep '"tag_name":' | sed -E 's/.*"([^"]+)".*/^A/')
curl -LO https://github.com/cnoe-io/idpbuilder/releases/download/$idpbuilder_latest_tag/idpbuilder-$os-$arch.tar.gz
tar xvzf idpbuilder-$os-$arch.tar.gz

ln -s /Users/ashrestha/code/lab/idpbuilder ~/.local/bin/idpbuilder
```

### Bringing online idpbuilder environment
```
./idpbuilder create
```

### Access UI

#### ArgoCD UI

- https://argocd.cnoe.localtest.me:8443/
- retrieve secrets using `idpbuilder get secrets -p argocd`

#### gitea UI

- https://gitea.cnoe.localtest.me:8443
- retrieve secrets using `idpbuilder get secrets -p gitea`

  
