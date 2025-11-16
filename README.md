## 🔧 Projeto Oficina Mecânica — README.md

```markdown
# 🔧 Projeto de Banco de Dados: Oficina Mecânica

Este projeto apresenta a modelagem lógica e relacional de um banco de dados para uma oficina mecânica. O sistema contempla clientes, veículos, funcionários, serviços, peças e ordens de serviço, com suporte a consultas analíticas e controle de estoque.

## 📐 Modelagem

A modelagem ER foi refinada para incluir:
- Clientes com CPF e dados de contato
- Veículos com placa, modelo e ano
- Funcionários com cargo e telefone
- Serviços com descrição e preço
- Peças com preço e estoque
- Ordens de serviço com status e data
- Relações entre OS, serviços e peças

## 🧱 Estrutura do Banco

- `cliente`: Dados dos clientes
- `veiculo`: Veículos vinculados aos clientes
- `funcionario`: Funcionários da oficina
- `servico`: Serviços oferecidos
- `peca`: Peças disponíveis
- `ordem_servico`: Ordens de serviço
- `os_servico`: Serviços realizados por OS
- `os_peca`: Peças utilizadas por OS

## 🛠️ Tecnologias

- MySQL
- MySQL Workbench
- SQL com chaves primárias compostas
- `ON DELETE CASCADE` e `ON UPDATE CASCADE` para integridade

## 📥 População de Dados

Scripts simulam:
- Clientes e veículos reais
- Funcionários e serviços
- Peças com estoque
- Ordens de serviço com serviços e peças vinculadas

## 🔍 Consultas SQL

### Quantos serviços foram realizados por cada funcionário?
```sql
SELECT f.nome, COUNT(*) AS total_servicos
FROM funcionario f
JOIN os_servico os ON f.idFuncionario = os.idFuncionario
GROUP BY f.idFuncionario;# Desafio-de-projeto-oficina
