
# Desafio 03 - Sintaxe e Semântica

## Linguagem Fictícia: ExType

A **ExType** é uma linguagem de programação fictícia criada para fins didáticos, com o objetivo de ilustrar conceitos de sintaxe e semântica. Ela possui uma estrutura simples, inspirada em linguagens imperativas como Python e C, com algumas ideias de tipagem explícita e sintaxe leve.

---

## 1. Características da Linguagem

- Paradigma: Imperativa, procedural
- Tipagem: Estática e explícita
- Estrutura de blocos definida por indentação
- Sintaxe minimalista e orientada à clareza

---

## 2. Análise Léxica

### Tokens da Linguagem

| Categoria       | Exemplos                  |
|----------------|---------------------------|
| Palavras-chave | `func`, `ret`, `if`, `else`, `loop`, `break`, `int`, `str`, `bool` |
| Operadores     | `+`, `-`, `*`, `/`, `=`, `==`, `!=`, `<`, `>`, `<=`, `>=` |
| Delimitadores  | `:`, `,`, `(`, `)` |
| Identificadores| `nome`, `idade`, `x`, `somaTotal` |
| Literais       | `42`, `"texto"`, `true`, `false` |
| Comentários    | `# Comentário de linha` |

---

## 3. Gramática Formal (BNF Simplificada)

```bnf
<programa> ::= <decl_func>* <decl_var>* <comando>*

<decl_func> ::= "func" <id> "(" [<parametros>] ")" ":" <bloco>

<parametros> ::= <id> ":" <tipo> ("," <id> ":" <tipo>)*

<tipo> ::= "int" | "str" | "bool"

<decl_var> ::= <id> ":" <tipo> "=" <expressao>

<comando> ::= <atribuicao> | <se> | <loop> | <chamada_func> | <retorno>

<atribuicao> ::= <id> "=" <expressao>

<se> ::= "if" <expressao> ":" <bloco> ["else:" <bloco>]

<loop> ::= "loop" ":" <bloco>

<retorno> ::= "ret" <expressao>

<chamada_func> ::= <id> "(" [<args>] ")"

<args> ::= <expressao> ("," <expressao>)*

<bloco> ::= <comando>+

<expressao> ::= <literal> 
              | <id> 
              | <expressao> <op_bin> <expressao>
              | "(" <expressao> ")"

<op_bin> ::= "+" | "-" | "*" | "/" | "==" | "!=" | "<" | ">" | "<=" | ">="

<literal> ::= <int> | <str> | <bool>

<int> ::= [0-9]+
<str> ::= '"' .* '"'
<bool> ::= "true" | "false"

<id> ::= letra (letra | digito)*
```

---

## 4. Exemplos de Código em ExType

### Exemplo 1: Função de Soma

```extype
func soma(a: int, b: int):
    ret a + b
```

### Exemplo 2: Verificação de Número Positivo

```extype
num: int = 7

if num > 0:
    ret true
else:
    ret false
```

### Exemplo 3: Loop Contador

```extype
i: int = 0

loop:
    if i == 5:
        break
    i = i + 1
```

---

## 5. Semântica da Linguagem

### Regras Semânticas:

- **Declaração Obrigatória**: Toda variável deve ser declarada com tipo antes do uso.
- **Escopo**: Variáveis seguem escopo local por função.
- **Tipo Estático**: Tipos são verificados em tempo de compilação.
- **Retorno**: Toda função que retorna um valor deve usar `ret`.

### Exemplo de Erro Semântico

```extype
x: int = "texto"  # Erro: tentativa de atribuir string a uma variável do tipo int
```

---

## 6. Conclusão

A linguagem **ExType** foi desenvolvida como exercício prático para reforçar os conceitos de análise léxica, estrutura gramatical e semântica de linguagens de programação. A clareza da estrutura BNF e dos exemplos ajuda a ilustrar a importância da definição formal de uma linguagem, bem como seus impactos na implementação e análise de código.
