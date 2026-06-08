# Uso de IA para geração de cenários de teste

## Função escolhida

`calcular_media(lista)`

```python
def calcular_media(lista):
    if len(lista) == 0:
        raise ValueError

    return sum(lista) / len(lista)
```

## Prompt utilizado

```text
Tenho a seguinte função Python:

def calcular_media(lista):
    if len(lista) == 0:
        raise ValueError

    return sum(lista) / len(lista)

Quero criar testes unitários usando unittest.

Liste cenários de teste para essa função, incluindo:
- lista com números inteiros;
- lista com números decimais;
- lista com apenas um elemento;
- lista vazia gerando ValueError.

Informe entrada, resultado esperado e tipo de cenário.
```

## Cenários sugeridos pela IA

| ID | Cenário | Entrada | Resultado esperado | Tipo |
| :--- | :--- | :--- | :--- | :--- |
| T01 | Média de números inteiros | `calcular_media([10, 8, 6])` | `8` | Caso normal |
| T02 | Média de números decimais | `calcular_media([2.5, 7.5])` | `5.0` | Caso normal |
| T03 | Lista com apenas um número | `calcular_media([10])` | `10` | Caso de borda |
| T04 | Lista vazia | `calcular_media([])` | `ValueError` | Caso de erro |

## Análise dos cenários

Os cenários foram aceitos porque testam os principais comportamentos da função `calcular_media(lista)`.

Os cenários T01 e T02 verificam o cálculo da média com números inteiros e decimais.

O cenário T03 verifica o caso em que a lista possui apenas um elemento.

O cenário T04 verifica o caso de erro, pois uma lista vazia não permite o cálculo da média e deve gerar `ValueError`.

## Código final dos testes

```python
def test_calcular_media(self):
    """Testa se a função calcular_media está funcionando corretamente."""
    self.assertEqual(calcular_media([10, 8, 6]), 8)
    self.assertEqual(calcular_media([2.5, 7.5]), 5.0)
    self.assertEqual(calcular_media([10]), 10)

def test_calcular_media_lista_vazia(self):
    """Testa se a lista vazia gera erro."""
    with self.assertRaises(ValueError):
        calcular_media([])
```

## Resultado da execução

Comando utilizado:

```bash
python -m unittest discover
```

Saída obtida:

```bash
........
----------------------------------------------------------------------
Ran 8 tests in 0.001s

OK
```

## Link do repositório no GitHub

```text
https://github.com/matheuspimenta3/teste-unitario-python
```
