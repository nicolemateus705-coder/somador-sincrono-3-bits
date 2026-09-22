# Somador Síncrono de 3 Bits

Projeto desenvolvido no **Logisim Evolution** com o objetivo de implementar um circuito capaz de realizar a soma de dois números binários de 3 bits, armazenar o resultado e exibi-lo em um display de 7 segmentos.

## Sobre o projeto

O circuito recebe duas entradas de 3 bits, **A** e **B**, e realiza a soma utilizando somadores construídos a partir de portas lógicas.

O resultado é armazenado em um registrador controlado por clock e, em seguida, enviado para um conversor responsável por controlar o display de 7 segmentos.

O circuito é composto por:

- 1 Half Adder para o bit menos significativo;
- 2 Full Adders para os demais bits;
- Portas lógicas XOR, AND e OR;
- Registrador de 3 bits;
- Clock;
- Conversor de 3 bits para 7 segmentos;
- Display de 7 segmentos.

## Funcionamento

O fluxo principal do circuito é:

A + B → Somador → Registrador → Conversor 3 para 7 segmentos → Display

O somador gera um resultado de 3 bits. Esse resultado é armazenado pelo registrador na borda de subida do clock (`0 → 1`).

Depois, o valor armazenado é enviado ao conversor, que determina quais segmentos do display devem ser ativados para representar os números de **0 a 7**.

Como o resultado possui apenas 3 bits, o carry final da soma é ignorado.

### Exemplos

| A | B | Resultado exibido |
|---|---|-------------------|
| 1 | 1 | 2 |
| 3 | 1 | 4 |
| 3 | 3 | 6 |
| 3 | 4 | 7 |
| 5 | 3 | 0* |

\* `5 + 3 = 8` (`1000` em binário). Como o circuito utiliza apenas 3 bits, o carry final é descartado e o resultado armazenado é `000`.

## Conversor para 7 segmentos

Foi desenvolvido um subcircuito chamado `Conversor3para7`, responsável por receber um valor binário de 3 bits e gerar as sete saídas (`a`, `b`, `c`, `d`, `e`, `f` e `g`) utilizadas pelo display.

## Ferramenta utilizada

- Logisim Evolution 5.0.0

## Arquivo do projeto

O circuito completo está disponível no arquivo `.circ` deste repositório.

## Contexto

Projeto desenvolvido como atividade acadêmica na disciplina de arquitetura de computadores.
