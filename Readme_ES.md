# Example Data Packages ´Ejemplos de Paquetes de Información´

[![goodtables.io](https://goodtables.io/badge/github/frictionlessdata/example-data-packages.svg)](https://goodtables.io/github/frictionlessdata/example-data-packages)


Este repositorio contiene ejemplo de paquetes de datos para ayudarte a entender [Frictionless Data](https://frictionlessdata.io/).Los ejemplos de paquetes de información:

- ilustrar la información actualizada de Frictionless [Especificaciones](https://frictionlessdata.io/specs/)
- ayuda sobre la información de Frictionless [Guías](https://frictionlessdata.io/guides/)
- demostraciones de información sobre Frictionless [Muestras](https://frictionlessdata.io/specs/patterns/) - maneras de resolver problemas comunes que no están (aún) en las especificaciones

Las guías son el mejor lugar donde [empieza a aprender](https://frictionlessdata.io/guides/). O en su lugar, abra el directorio de paquetes de datos, lea el `README.md`, luego fíjese en el `datapackage.json` para entender más sobre la información.

*Warning: some data packages are out-of-date. (See [Issue #4](https://github.com/frictionlessdata/example-data-packages/issues/4))*

## Paquetes de Información

Los `datapackage.json` describirá el [dpaquete de información](https://frictionlessdata.io/specs/data-package/) como un todo, y uno o mas [recursos de información](https://frictionlessdata.io/specs/data-resource/) (cada uno traerá opcionalmente un [esquema](https://frictionlessdata.io/specs/data-resource/#resource-schemas) o una [visualización](https://frictionlessdata.io/specs/views/)).

Si toda la información es tabular (es decir [archivos CVS](https://frictionlessdata.io/guides/csv/)), entonces será describido como un [paquete de información tabular](https://frictionlessdata.io/specs/tabular-data-package/) con uno o más [recursos de información tabular](https://frictionlessdata.io/specs/tabular-data-package/) todos con una [esquema de indicaciones](https://frictionlessdata.io/specs/table-schema/) y, si es necesario, un [dialecto en CSV](https://frictionlessdata.io/specs/csv-dialect/).

Hay otras especializaciones en los [perfiles](https://frictionlessdata.io/specs/profiles/) que describen diferentes tipos de información, tales como [Información fiscal](https://frictionlessdata.io/specs/fiscal-data-package/).

Cada paquete es almacenado en su propio directorio:

```
|- data-package-name-1
   |- README.md
   |- datapackage.json
   |- data
      |- data.csv
      |- ...
```

Y este contendrá un:

- `README.md` para explicar de donde proviene la información
- `datapackage.json` una máquina lectora de archivos que explique la estructura y el significado del contenido
- uno o más archivos con contenido, normalmente se agruparán en un directorio de ´data´

El directorio del paquete de contenido puede contener también [otros archivos o subdirectorios](https://frictionlessdata.io/specs/data-package/#illustrative-structure). estos archivos pueden tener scripts utilizados para preparar el paquete de contenido o otros recursos relacionados.

## Validación

### Validación del Repositorio

Con cada ajuste al repositorio, el paquete de contenido se validará usando [goodtables.io](http://goodtables.io/). El resultado de la validación del paquete de contenido se especificará en [goodtables.yml](goodtables.yml) e indicará con una insignia: ![goodtables.io](https://goodtables.io/badge/github/frictionlessdata/example-data-packages.svg)

*Idealmente, una insignia podrá validar cada paquete de contenido y mostrarlo en su archivos `README.md` pero esto aún no es posible. puedes ver el porqué (aquí: goodtables.io [issue #285](https://github.com/frictionlessdata/goodtables.io/issues/285))*

La aprobación es controlada por el archivo [goodtables.yaml](https://github.com/frictionlessdata/example-data-packages/blob/master/goodtables.yml). Debe ser configurado para probar todos los paquetes de contenido en el repositorio. Esto puede ser cambiado si trabajas localmente para [aprobar especificos paquetes de contenido](https://github.com/frictionlessdata/goodtables.io/blob/master/docs/goodtables_yml.md).

### Validación local

Queremos implementar la [validación local](https://github.com/frictionlessdata/example-data-packages/issues/6) para que los paquetes de contenido puedan ser aprobados antes de contribuir en el repositorio.

## Comprimir los paquetes de contenido

Con cada ajuste realizado en el repositorio, el paquete de contenido sera convertido en un archivo .zip para que pueda ser utilizado con un [software que maneje Frictionless Data ](https://frictionlessdata.io/software/) tal como el [Curador de Contenido](http://data-curator.io) app o en la libreria de los [DataPackage.js](https://github.com/frictionlessdata/datapackage-js). Los archivos comprimidos _`zip`_ serán almacenados en el directorio `zip`.

Mientras que [el proceso para comprimir los paquetes de contenidos no haya sido finalizado](https://github.com/frictionlessdata/specs/issues/132) un número de [software para contenido Frictionless](https://frictionlessdata.io/software/) implementará ayuda para comprimor los archivos.

*Para realizarlo: necesitara el script*

## Formateo de JSON

Con cada ajuste, El archivo `datapackage.json` será [formateado para que sea más fácil de procesar](https://frictionlessdata.io/guides/publish-faq/#alignment). Aunque formatearlo no sea necesario en los programas de computador, Vuelve más facil de procesar el contenido del archivo.

*Para realizarlo: necesitará de un script (o un linting)*

## Resoursos

El recurso del directorio contiene una plantilla con fragmentos del `README.md` y un ejemplo del `datapackage.json`.

### Plantilla del `README.md`

En este repositorio, cada paquete de contenido debe tener un archivo `README.md`. El archivo `README.md` deberá mantener [buena legibilidad](https://frictionlessdata.io/guides/publish-faq/#readme).

### Fragmentos `datapackage.json`

Los fragmentos JSON proveen un archivo `datapackage.json` para ayudarte a aprender sobre una propiedad especifica o a copiar y pegar en tu propio paquete de contenido. P.ej. `licenses.json` puede uncluir un JSON por cada [licencia de conformidad con Open Definition recomendada](http://opendefinition.org/licenses/#conformant-licenses).

## Estructura del Repositorio

```
|
|- data-package-name-1
|  |- README.md
|   |- datapackage.json
|   |- data
|     |- data.csv
|     |- data.geojson
|     |- ...
|     
|- data-package-name-2
|  |- etc.
|
|- resources
|  |- README-template.md
|  |- licenses.json
|  |- contributors.json
|  |- dialect.json
|  |- ...
|
|- zip
|  |- data-package-name-1.zip
|  |- data-package-name-2.zip
|
|
|- goodtables.yaml
|- README.md   

```

## Contribuciones

Valoramos todo tipo de contribuciones:
- documentació
- Paquetes de contenido
- [_`issues`_](https://github.com/frictionlessdata/example-data-packages/issues) y [solicitudes](https://github.com/frictionlessdata/example-data-packages/issues)
- códigos

Agradecemos a nuestros generosos [contribuidores](https://github.com/frictionlessdata/example-data-packages/graphs/contributors) de este proyecto.

Para unirse, porfavor lea el [`CONTRIBUTING.md`](.github/CONTRIBUTING.md) para detalles sobre nuestro código de conducta y como pedir un _`pull request`_. Cada paquete con contenido contribuido deberá tener una licencia tan permisiva como sea posible.

## Licenses

En este proyecto los _`Data Packages`_ tienen licencias especificas en cada archivo `datapackage.json` individualmente. Si una licencia no es especificada, se le proveera bajo una dedicación [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) de dominio público.

El código de este proyecto, a menos de que se indique lo contrario, tendrá la licencia como se describe en [`LICENSE.md`](LICENSE.md).
