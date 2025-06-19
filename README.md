# Avaliador de ExpressÃµes NumÃ©ricas em C

Este projeto implementa um avaliador de expressÃµes numÃ©ricas em linguagem C. Ele Ã© capaz de converter expressÃµes da notaÃ§Ã£o infixa para pÃ³s-fixa (NotaÃ§Ã£o Polonesa Reversa - RPN) e calcular o valor numÃ©rico dessas expressÃµes. O projeto faz uso extensivo da estrutura de dados Pilha para gerenciar operadores e operandos durante os processos de conversÃ£o e avaliaÃ§Ã£o.

## Funcionalidades

*   **ConversÃ£o Infixa para PÃ³s-fixa**: Transforma expressÃµes matemÃ¡ticas da forma usual (infixa) para a notaÃ§Ã£o pÃ³s-fixa.
*   **ConversÃ£o PÃ³s-fixa para Infixa**: ReconstrÃ³i a expressÃ£o infixa a partir de sua forma pÃ³s-fixa, adicionando parÃªnteses quando necessÃ¡rio para manter a precedÃªncia correta.
*   **AvaliaÃ§Ã£o de ExpressÃµes PÃ³s-fixas**: Calcula o valor numÃ©rico de expressÃµes em notaÃ§Ã£o pÃ³s-fixa.
*   **AvaliaÃ§Ã£o de ExpressÃµes Infixas**: Calcula o valor numÃ©rico de expressÃµes em notaÃ§Ã£o infixa, utilizando a conversÃ£o interna para pÃ³s-fixa.
*   **Suporte a Operadores BÃ¡sicos**: AdiÃ§Ã£o (`+`), SubtraÃ§Ã£o (`-`), MultiplicaÃ§Ã£o (`*`), DivisÃ£o (`/`), MÃ³dulo (`%`), PotenciaÃ§Ã£o (`^`).
*   **Suporte a FunÃ§Ãµes MatemÃ¡ticas**: Raiz quadrada (`raiz`), Seno (`sen`), Cosseno (`cos`), Tangente (`tg`), Logaritmo na base 10 (`log`).

## Estrutura do Projeto

O projeto Ã© composto pelos seguintes arquivos:

*   `expressao.h`: ContÃ©m as definiÃ§Ãµes da estrutura `Expressao` e os protÃ³tipos das funÃ§Ãµes de conversÃ£o e avaliaÃ§Ã£o.
*   `expressao.c`: Implementa as funÃ§Ãµes declaradas em `expressao.h`, incluindo as lÃ³gicas para manipulaÃ§Ã£o de pilhas, conversÃ£o de notaÃ§Ã£o e avaliaÃ§Ã£o de expressÃµes.
*   `main.c`: ContÃ©m a funÃ§Ã£o principal (`main`) que demonstra o uso das funcionalidades do avaliador atravÃ©s de uma sÃ©rie de testes com diferentes expressÃµes.

## Como Compilar

Para compilar o projeto, vocÃª precisarÃ¡ de um compilador C (como o GCC). Navegue atÃ© o diretÃ³rio raiz do projeto no seu terminal e execute o seguinte comando:

```bash
gcc main.c expressao.c -o avaliador -lm
```

*   `gcc`: O compilador C.
*   `main.c expressao.c`: Os arquivos fonte a serem compilados.
*   `-o avaliador`: Define o nome do executÃ¡vel de saÃ­da como `avaliador`.
*   `-lm`: Linka a biblioteca matemÃ¡tica (necessÃ¡ria para funÃ§Ãµes como `sqrt`, `sin`, `cos`, `tan`, `log10`, `pow`, `fmod`).

## Como Executar

ApÃ³s a compilaÃ§Ã£o bem-sucedida, vocÃª pode executar o programa a partir do terminal:

```bash
./avaliador
```

O programa irÃ¡ exibir os resultados dos testes prÃ©-definidos no arquivo `main.c`, mostrando as expressÃµes infixas, suas conversÃµes para pÃ³s-fixa, a reconstruÃ§Ã£o para infixa e os valores calculados.

## Exemplo de Uso (do `main.c`)

```c
#include <stdio.h>
#include <string.h>
#include <math.h>
#include "expressao.h"

int main() {
    Expressao exp;
    printf("=== Avaliador de Expressoes ===\n\n");

    // Teste 1
    strcpy(exp.inFixa, "(3 + 4) * 5");
    strcpy(exp.posFixa, getFormaPosFixa(exp.inFixa));
    printf("Infixa: %s\n", exp.inFixa);
    printf("Posfixa: %s\n", exp.posFixa);
    printf("Infixa convertida: %s\n", getFormaInFixa(exp.posFixa));
    printf("Valor na posfixa: %.5f\n", getValorPosFixa(exp.posFixa));
    printf("Valor na infixa: %.5f\n", getValorInFixa(exp.inFixa));
    printf("------------------------------------------------------------\n");

    // Outros testes...

    printf("=== Fim dos testes ===\n");
    return 0;
}
```

## ContribuiÃ§Ã£o

ContribuiÃ§Ãµes sÃ£o bem-vindas! Sinta-se Ã  vontade para abrir issues ou enviar pull requests para melhorias, correÃ§Ãµes de bugs ou novas funcionalidades.

## LicenÃ§a

Este projeto estÃ¡ licenciado sob a [LicenÃ§a MIT](https://opensource.org/licenses/MIT).

