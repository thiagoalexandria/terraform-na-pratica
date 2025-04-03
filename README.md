# Terraform Azure Network Lab

Este repositório contém um projeto em Terraform que cria uma estrutura básica de rede no Azure, com o objetivo de ser **refatorado e otimizado** pela equipe durante o treinamento.

---

## Objetivo

Você receberá um código propositalmente manual, repetitivo e com boas práticas **não aplicadas**.

O desafio é utilizar os conhecimentos adquiridos no treinamento para:

- Refatorar
- Modularizar
- Garantir segurança
- Documentar
- Estimar custos

---

## O que este projeto faz

- Cria um Resource Group
- Cria uma VNet (`10.0.0.0/16`)
- Cria **4 subnets públicas** (`10.0.1.0/24` a `10.0.4.0/24`)
- Cria uma Route Table com rota para a internet
- Cria um único Network Security Group permitindo **ICMP (ping)**
- Associa a mesma Route Table e NSG às 4 subnets

---

## Desafios propostos

Sua missão é refatorar este código para aplicar as boas práticas discutidas em aula. Algumas sugestões:

- [ ] Remover repetições com `for_each` e `count`
- [ ] Criar um módulo para rede, NSG e rota
- [ ] Usar `variables.tf` e `terraform.tfvars` para parametrizar
- [ ] Criar outputs úteis (subnet_ids, vnet_id, etc.)
- [ ] Adicionar `terraform-docs` para gerar documentação
- [ ] Rodar `checkov` e corrigir os alertas de segurança
- [ ] Rodar `infracost` para estimar os custos da infraestrutura
- [ ] Validar o código com `terraform validate` e `fmt`

---

## Como usar

```bash
terraform init
terraform plan
terraform apply
```