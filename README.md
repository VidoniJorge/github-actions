# github-actions
Proyecto para probar las capacidades de github-actions

## Operadores

| Operador  | Descripción         |
| --------- |:-------------:|
| ()        | Agrupacion lógica   |
| []        | Índice              |
| .         | Feferencia de propiedad |
| !         | Not                 |
| <         | Menor que           |
| <=        | Menor o igual que   |
| >         | Mayor que           |
| =>        | Mayor o igual que   |
| ==        | Igual               |
| !=        | No igual a          |
| &&        | Y                   |
| \|\|       | Or                 |

## Funciones

### if
```
if:${{<expresión>}}
```
### contains
```
contains(github.event.issue.labels.*.name, 'bug')
```

### toJson
```
toJSON(value)
```

### fromJson
```
fromJSON(value)
```

## Contextos

Es una manara de acceder a información acerca de las ejecuciones de workflows, variables de entorno de runner, jubs y steps.

[doc oficial](https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/accessing-contextual-information-about-workflow-runs)

| Operador  | Descripción |
| --------- |:-------------:|
| github | Información hacerca de la ejecución de workflow |
| env | Contiene variables del workflow, job o steps |
| vars | Contiene variables guardadas en el nivel de abiente, reposirotio u organización |
| job | Información sobre el job que está ejecutándose en ese momento |
| steps | información sobre los steps que se están ejecutando en ese momento |
| runner | Información sobre el runner ejecutando el actual jobs |
| secrets | Contiene nombres y valores de secretos disponibles en la ejecución del workflow |
| inputs | Contiene las entradas con información reutilizable de un workflow lanzado manualmente |


### variables
Son una manera de almacenar y reutilizar información no confidencial.
https://docs.github.com/en/actions/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables

**Uso de variable**
* Se pueden configurar para un workflow con la palabra reservada ENV.
* Se puede configurar a nivel entorno, repositorio u organización.

```yml
name: Saludo usando variables
on:
  workflow_dispatch
env:
  DIA_DE_SEMANA: Lunes
jobs:
  saludo-variables:
    runs-on: ubunto-lastest
    env:
      SALUDO: Hola
    steps:
      - name: Saludar
        run: echo "$SALUDO, $NOMBRE, Hoy es $DIA_DE_SEMANA!"
      env:
        NOMBRE: Pepe
```










