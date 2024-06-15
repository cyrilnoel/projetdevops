# Simple calculator

This is a simple calculator made in go !

It supports :

- division
- multiplication
- addition
- subtraction

## Usage example

```text
This is a simple calculator application.
It supports Addition, Subtraction, Division, Multiplication.
Specify the numbers to use with --x or --y.
Default values for x and y are 0.

Usage:
  calculator [command]

Available Commands:
  add         Addition of x and y
  completion  Generate the autocompletion script for the specified shell
  div         Division of x and y
  help        Help about any command
  mul         Multiplication of x and y
  sub         Subtraction of x and y

Flags:
  -h, --help     help for calculator
  -t, --toggle   Help message for toggle

Use "calculator [command] --help" for more information about a command.
```

## Example usage

### Addition

```bash
./calculator add --x 5 4
4.000000 + 5.000000 = 9.000000
```

### Subtraction

```bash
./calculator sub --x 5 4
4.000000 - 5.000000 = -1.000000
```

### Multiplication

```bash
./calculator mul --x 5 4
4.000000 * 5.000000 = 20.000000
```

### Division

```bash
./calculator div --x 5 4
4.000000 / 5.000000 = 0.800000
```

## Test execution

This application uses the default go test integration.

```text
> go test ./...
?       calculator                  [no test files]
?       calculator/cmd              [no test files]
ok      calculator/internals/math   0.002s
```

Ce document technique décrit la configuration et l'implémentation des workflows GitHub Actions pour le projet SuperCalculator

Dependabot.yml

Pour assurer la gestion des dépendances, Dependabot sera configuré pour vérifier quotidiennement les mises à jour des dépendances Go et Docker.

release.yml

Ce fichier est un workflow GitHub Actions qui automatise le processus de publication d'une nouvelle version de notre projet. 

lint.yml

Ce workflow effectue les actions suivantes sur le dépôt :

    Exécute Semgrep pour l'analyse statique et le linting du code.
    Exécute Hadolint pour vérifier les Dockerfiles.
    Exécute Super-Linter pour effectuer le linting sur différents types de fichiers dans le dépôt.


test.yml

Ce workflow "Test" effectue les actions suivantes :

    Se déclenche lorsqu'un push est effectué sur la branche main.
    Vérifie le contenu du dépôt.
    Configure l'environnement Go pour trois versions différentes (1.17, 1.18, 1.19).
    Exécute les tests unitaires en utilisant la commande go test ./....

La stratégie de matrice permet d'exécuter les tests pour chaque version de Go spécifiée, ce qui aide à s'assurer que le projet est compatible avec plusieurs versions de Go.




