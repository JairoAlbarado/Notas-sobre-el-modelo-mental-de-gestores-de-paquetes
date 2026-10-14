# Notas-sobre-el-modelo-mental-de-gestores-de-paquetes
Los módulos

Son componentes lógicos del código, como partes de un programa.

La modularidad

Organiza un programa en partes identificables (módulos). Pero para que sean fáciles de modificar, reparar, depurar y mantener, generalmente conviene que estén lo más desacoplados posible. En pocas palabras, deben ser componentes lo más independientes posible para que, si se llega a modificar uno, tenga menos probabilidades de afectar a otro.

En el código

Para hacer que los componentes sean lo más independientes posible, debemos realizar una clara separación de sus funciones. Generalmente, esto se hace a través de lo que llamamos interfaces. Debemos hacer que entre los componentes solo se comparta la información necesaria para su funcionalidad. Cuanto menos dependa uno del otro, más fácil será modificar sus detalles internos.

En resumen

La modularidad consiste en organizar un programa en partes identificables llamadas módulos. Los módulos son componentes lógicos que contienen código y forman parte del programa. Para facilitar su modificación, depuración y mantenimiento, conviene que estén lo menos acoplados posible, es decir, que dependan lo menos posible de los detalles internos de otros módulos. Para lograrlo, se utilizan interfaces que exponen los elementos necesarios para que otros componentes puedan utilizar un módulo sin conocer cómo funciona internamente.

Dependencias

Son componentes o recursos de los que tu código necesita depender para realizar determinadas tareas. Pueden ser módulos propios o código externo.

Paquetes

Son unidades de código que se agrupan y distribuyen para reutilizar funcionalidades en diferentes proyectos.

Dependencias transitivas

También se conocen como dependencias de una dependencia. Son los paquetes que nuestro proyecto necesita indirectamente porque alguna de sus dependencias directas los utiliza. Las dependencias forman un gráfico de relaciones en lugar de una simple lista de paquetes.

Paquetes como dependencias

Son paquetes que contienen código reutilizable y que un proyecto puede incorporar como dependencias para aprovechar funcionalidades ya desarrolladas.

Gestor de paquetes

Son programas que proporcionan herramientas y comandos para administrar las dependencias de un proyecto, como instalarlas, actualizarlas, inspeccionarlas y eliminarlas. Algunos gestores también permiten publicar paquetes.

Versiones de paquetes

Son las diferentes versiones de un mismo paquete. Permiten introducir nuevas funcionalidades, corregir errores o realizar cambios incompatibles sin tener que reemplazar necesariamente las versiones anteriores. Así, los proyectos pueden utilizar la versión que necesitan según su compatibilidad.

Versión SemVer

SemVer utiliza el formato MAJOR.MINOR.PATCH.

Tipo

¿Cuándo se usa?

Ejemplo

Major

Se usa cuando el contrato público presenta cambios incompatibles.

2.3.4 -> 3.0.0

Minor

Puede añadir funcionalidades compatibles con versiones anteriores.

2.3.4 -> 2.4.0

Patch

Contiene correcciones de errores compatibles con versiones anteriores.

2.3.4 -> 2.3.5

Compatibilidad entre versiones

Aunque SemVer establece reglas para identificar cambios incompatibles, los autores no siempre las siguen correctamente. Además, algunas bibliotecas mantienen la compatibilidad con versiones anteriores o proporcionan versiones intermedias para que los desarrolladores puedan adaptar su código progresivamente.

IMPORTANTE: Dependencias transitivas

Una dependencia directa puede depender de otros paquetes que no sean compatibles con versiones más recientes. Esto puede impedir actualizar una dependencia transitiva. Puede haber muchos casos; por ejemplo, una vulnerabilidad de seguridad que se soluciona en una versión más reciente.

En estos casos, puede ser necesario adaptar el código de la dependencia directa y publicar una nueva versión compatible.

Mientras más dependencias y relaciones existan entre paquetes, más difícil será gestionar sus versiones, resolver problemas de compatibilidad y mantener la seguridad del proyecto.

q wbd :v
