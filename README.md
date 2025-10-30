# 🔄 EKS-AWS-GITOPS

Este repositório faz parte do projeto [EKS-AWS](https://github.com/igorrodriguesss/EKS-AWS) e é utilizado como fonte GitOps para o ArgoCD. Ele armazena os manifests Kubernetes e Helm charts que são automaticamente sincronizados com o cluster EKS provisionado via Terraform.

---

## 🚀 Como funciona o GitOps com ArgoCD

1. O cluster EKS é provisionado via Terraform no repositório [EKS-AWS](https://github.com/igorrodriguesss/EKS-AWS)
2. O ArgoCD é instalado e configurado no cluster
3. O ArgoCD é apontado para este repositório (`EKS-AWS-GITOPS`)
4. Toda alteração neste repositório é automaticamente aplicada no cluster

---

## 🧭 Fluxo de Deploy

- Ao fazer um `git push` com alterações em `apps/dev` ou `apps/prod`, o ArgoCD detecta e sincroniza os recursos no cluster
- Os arquivos `argo-apps/*.yaml` definem as aplicações que o ArgoCD monitora
- É possível configurar sincronização automática ou manual via interface do ArgoCD

---

## 📌 Boas práticas

- Utilize branches separados para ambientes (`main`, `dev`, `prod`)
- Versione os manifests com clareza
- Teste localmente com `kubectl apply -f` antes de subir para produção
- Mantenha os arquivos `Application` do ArgoCD organizados e nomeados por ambiente

---

