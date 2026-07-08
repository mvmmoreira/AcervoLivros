# Regras de Negócio — AcervoLivros

## 1. Entidades

- **Livro**
- **Autor**
- **Categoria**

## 2. Relacionamentos

- Livro **N:N** Autor — um livro pode ter um ou mais autores; um autor pode ter vários livros.
- Livro **N:N** Categoria — um livro pode pertencer a uma ou mais categorias; uma categoria agrupa vários livros.

## 3. Campos por Entidade

### Livro
| Campo | Obrigatório | Observações |
|---|---|---|
| Título | Sim | |
| ISBN | Sim | Único no acervo; formato ISBN-10 ou ISBN-13 (apenas dígitos) |
| Editora | Não | |
| Ano de publicação | Não | |
| Número de páginas | Não | |
| Disponibilidade | Definido pelo sistema | Não é preenchido pelo usuário no cadastro |

### Autor
| Campo | Obrigatório | Observações |
|---|---|---|
| Nome | Sim | |
| Nacionalidade | Não | |

### Categoria
| Campo | Obrigatório | Observações |
|---|---|---|
| Nome | Sim | |

## 4. Regras de Negócio

- **RN01** — O ISBN é único: não é permitido cadastrar dois livros com o mesmo ISBN.
- **RN02** — Todo livro deve ter pelo menos 1 autor vinculado no momento do cadastro.
- **RN03** — Ao cadastrar um livro, o campo de disponibilidade é automaticamente definido como "disponível" (`true`); o usuário não define esse valor manualmente.
- **RN04** — Um livro pode ser excluído do acervo independente do seu status de disponibilidade.
- **RN05** — O ISBN deve seguir o formato ISBN-10 (10 dígitos) ou ISBN-13 (13 dígitos), contendo apenas números.

## 5. Fora do Escopo do MVP (Backlog — Fase 2)

- Módulo de empréstimo (registro de pessoa, data de retirada e devolução).
- Regra futura: só será possível emprestar um livro com status "disponível"; não haverá lista de espera.
