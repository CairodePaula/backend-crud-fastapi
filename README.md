# API de Gerenciamento de Produtos

API REST com CRUD completo feita com FastAPI + SQLAlchemy + PostgreSQL, containerizada com Docker e com testes automatizados via Pytest.

---

## Como rodar a aplicação

Sobe tudo (banco + app) com um comando:

```bash
docker-compose up -d
```

A API fica disponível em `http://localhost:8000`. Documentação interativa em `http://localhost:8000/docs`.

---

## Como rodar os testes

Primeiro sobe o banco de testes:

```bash
docker-compose up -d db_test
```

Depois executa os testes:

```bash
pytest --cov=main -v
```

---

## Endpoints

| Método | Rota | Status | Descrição |
|--------|------|--------|-----------|
| GET | `/produtos` | 200 | Lista todos os produtos |
| POST | `/produtos` | 201 | Cria um novo produto |
| GET | `/produtos/{id}` | 200 / 404 | Busca produto por ID |
| PUT | `/produtos/{id}` | 200 / 404 | Atualiza produto por ID |
| DELETE | `/produtos/{id}` | 204 / 404 | Remove produto por ID |

---

## Variáveis de ambiente

| Variável | Padrão | Descrição |
|----------|--------|-----------|
| `DATABASE_URL` | `postgresql://postgres:postgres@localhost:5432/produtos_db` | URL de conexão com o banco |
| `TEST_DATABASE_URL` | `postgresql://postgres:postgres@localhost:5433/produtos_test` | URL do banco de testes |

```
## Projeto Acadêmico

Projeto desenvolvido para a disciplina **Laboratório de Programação Back End (Eng.Soft05_B_N_M_991532_20261)** do curso de Engenharia de Software.

A atividade teve como objetivo aplicar conceitos de desenvolvimento backend por meio da construção de uma API REST utilizando FastAPI, 
integração com banco de dados PostgreSQL, containerização com Docker e implementação de testes automatizados com Pytest, seguindo boas práticas de desenvolvimento e qualidade de software.
```
