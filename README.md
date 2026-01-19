# Education Lakehouse Pipeline

## Objetivo
Construir um pipeline de dados **end-to-end** para um cenário educacional (empresa fictícia), incluindo:
- Geração de dados sintéticos (`CSV`) para alunos, escolas e notas;
- ETL com **PySpark** (simulando um job de Glue);
- Armazenamento em formato analítico (**Parquet**) em um “data lake” local;
- Carga e consulta em banco relacional (**Postgres**, simulando Aurora);
- Infraestrutura como código (**Terraform**) preparada para AWS (não aplicada para manter custo zero).

## Stack 
- **Python** (scripts e utilitários)
- **PySpark** (ETL)
- **Postgres** (banco relacional local, “Aurora-like”)
- **MinIO** (S3 local)
- **Docker + Docker Compose** (subir MinIO/Postgres localmente)
- **Terraform** (representação de infraestrutura AWS — apenas código)

## Estrutura do Projeto
data/
raw/ # dados brutos (CSVs gerados)
transformed/ # dados tratados (Parquet)
src/
generate_data.py
etl_spark.py
sql/
01_create_tables.sql
02_queries.sql
docker/
docker-compose.yml
terraform/
aws/ # IaC AWS (não aplicada)
docs/ # diagramas e documentação auxiliar

markdown
Copiar código

## Como rodar (WIP)
1. Subir MinIO e Postgres via Docker Compose
2. Gerar dados sintéticos (CSVs) em `data/raw`
3. Rodar ETL com PySpark e gerar Parquet em `data/transformed`
4. Carregar dados no Postgres e executar queries em `sql/`