# Notas sobre el modelo mental de gestores de paquetes

## 1. Módulos, modularidad y desacoplamiento

### Los módulos
Son componentes lógicos del código, como partes de un programa.

### La modularidad
Organiza un programa en partes identificables (**módulos**). Pero para que sean fáciles de modificar, reparar, depurar y mantener, generalmente conviene que estén lo más **desacoplados** posible (reducir el acoplamiento). En pocas palabras, deben ser componentes lo más independientes posibles para que, en caso de que se llegue a modificar un componente, este tenga menor probabilidad de afectar a otro.

### En el código
Para hacer que los componentes sean lo más independientes posibles, debemos realizar una clara separación de sus funciones; generalmente se hace a través de lo que llamamos **interfaces**. Debemos hacer que entre componentes solo tengan la información necesaria para su funcionalidad. Cuanto menos dependan unos módulos de otros, más fácil será modificar sus detalles internos., más fácil se hará modificar los detalles internos.

### En resumen
La modularidad consiste en organizar un programa en partes identificables llamadas módulos. Los módulos son componentes lógicos que contienen código y forman parte del programa. Para facilitar su modificación, depuración y mantenimiento, conviene que estén lo menos acoplados posible, es decir, que dependan lo menos posible de los detalles internos de otros módulos. Para lograrlo, se utilizan interfaces que exponen los elementos necesarios para que otros componentes puedan utilizar un módulo sin conocer cómo funciona internamente.

---

## 2. Dependencias, paquetes y gestores

### Dependencias
Son componentes o recursos de los que tu código necesita depender para realizar determinadas tareas. Pueden ser módulos propios o código externo.

### Paquetes
Son unidades de código que se agrupan y distribuyen para reutilizar funcionalidades en diferentes proyectos.

### Dependencias Transitivas
Tambíén conocida como dependencia de una dependencia. Son los paquetes que nuestro proyecto necesita indirectamente porque alguna de sus dependencias directas los utiliza. Las dependencias forman un gráfico de relaciones en lugar de una simple lista de paquetes.

### Paquete de dependencias
Son dependencias agrupadas y distribuidas en paquetes que contienen código reutilizable. Un proyecto puede incorporar paquetes externos como dependencias para reutilizar funcionalidades ya desarrolladas.

### Gestor de paquetes
Son programas que proporcionan herramientas y comandos para administrar las dependencias de un proyecto: instalarlas, actualizarlas, inspeccionarlas, eliminarlas y publicarlas.

---

## 3. Versiones y compatibilidad

### Versiones de paquetes
Son las diferentes ediciones de un mismo paquete. Permiten introducir nuevas funcionalidades, corregir errores o realizar cambios incompatibles sin tener que reemplazar necesariamente las versiones anteriores. Así, los proyectos pueden utilizar la versión que necesitan según su compatibilidad.

### Versión SemVer

| Nombre | Explicación | Ejemplo |
| :--- | :--- | :--- |
| **Major** | Se usa cuando el contrato público presenta cambios incompatibles | 2.3.4 -> 3.0.0 |
| **Minor** | Puede añadir funcionalidades compatibles con versiones anteriores | 2.3.4 -> 2.4.0 |
| **Patch** | Contiene correcciones de errores compatibles con versiones anteriores | 2.3.4 -> 2.3.5 |

### Compatibilidad entre versiones
Aunque SemVer establece reglas para identificar cambios incompatibles, los autores no siempre las siguen correctamente. Además, algunas bibliotecas mantienen la compatibilidad con versiones anteriores o proporcionan versiones intermedias para que los desarrolladores puedan adaptar su código progresivamente.

### IMPORTANTE: dependencias transitivas
Una dependencia directa puede depender de otros paquetes que no son compatibles con versiones más recientes. Esto puede impedir actualizar una dependencia transitiva (puede haber muchos casos, por ejemplo, una vulnerabilidad de seguridad). En estos casos, puede ser necesario adaptar el código de la dependencia directa y publicar la nueva versión compatible. Mientras más dependencias y relaciones existan entre paquetes, más difícil será gestionar sus versiones, resolver compatibilidades y mantener la seguridad del proyecto. q wbd :v
