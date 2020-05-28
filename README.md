![Logo del ITCR](https://www.tec.ac.cr/sites/default/files/media/branding/logo-tec.png)

**Instituto Tecnológico de Costa Rica.**

**Área de Ingeniería en Computadores.**

**Algoritmos y Estructuras de Datos II (CE 2103).**

**Primer Semestre 2020.**

**Tarea Extraclase #2**

**Profesor Antonio González Torres.**

**Estudiantes: Tomás Segura.**

A lo largo de los años de la carrera como estudiantes hemos enfrentado diversos retos  de software. La mayoría, si no todos, inspirados en desarrollos antiguos o ya existentes. Esto representa una ventaja ya que hemos podido encontrar ayuda en la web que nos amplía la mente, nos enseña muchísimo y, principalmente, nos orienta a solucionar nuestros retos.

Es muy común que estas soluciones se estandaricen para evitar el mismo dolor de cabeza a nuevas generaciones.

El siguiente consiste en un documento que pretende introducir y resumir el tema de patrones de diseño. A continuación se presentan: un resumen introductorio de dos artículos que tratan el tema y el desarrollo de dos patrones específicos (Adapter y Observer) con descripción de la estructura y una implementación en C++.

# Patrones de Diseño de Software

Un patrón de diseño es la convención para llamar a estas soluciones, del mismo problema, que alguien más ha encontrado. Es decir, **una solución que se puede explicar, extraer y reutilizar en múltiples ámbitos.** 

A pesar de que el concepto existe desde la década de los años 70, se popularizó en los 90s con el lanzamiento del libro [Design Patterns](http://www.uml.org.cn/c++/pdf/DesignPatterns.pdf) escrita por The Gang Of Four, que es el nombre con el que se conoce a los cuatro creadores de esta convención: Erich Gamma, Richard Helm, Ralph Johnson y John Vilssides. En este libro se desarrollan [23 patrones de diseño]([https://sourcemaking.com/design_patterns](https://sourcemaking.com/design_patterns)) y es considerado como un estándar en el tema.

### Ventajas del uso de patrones de diseño.
Los patrones de diseño tienen varias características por las cuales son muy populares pero se nombrarán solamente algunas.

 1. **Economizan tiempo**.
Existen muchísimos problemas que los desarrolladores enfrentan y que muchos otros ya han enfrentado. Siguiendo con el principio básico de los programadores ("no reinventar la rueda") entonces una solución de otra persona, y que puede adecuarse, favorece el tiempo de desarrollo de otros programas.

2. **Homogenizan las soluciones**.
De igual forma que en otras profesiones, la globalización ha permitido que las comunidades de todo el mundo se acerquen para formar una muy grande. Es así que se ha buscado forjar un lenguaje universal que permita entender soluciones en cualquier parte del mundo y los patrones de diseño conforman uno de muchísimos ejemplos sobre este tema. Por este motivo es que el código debe ser bien documentado siempre. Por lo tanto, se vuelve más sencillo explicarle a los compañeros de trabajo sobre la solución que se utilizó y que se entienda fácilmente.

3. **Sirven como una gran herramienta de validez**.
Todos aquellos que disfrutan de solucionar problemas y sienten curiosidad sobre la calidad de dicha solución resulta muy útil encontrar una respuesta que es aceptada por la comunidad. Esto le da validez al código y permite aprender mejores o diferentes formas de modelar problemas.

### Tipos de patrones
Si bien los patrones de diseño conforman una gran herramienta para solucionar problemas, es cierto que puede resultar complicado el decidir cuál utilizar. El libro [Head First Design Patterns]([http://ce.sharif.edu/courses/98-99/2/ce484-1/resources/root/Design%20Patterns/Eric%20Freeman,%20Elisabeth%20Freeman,%20Kathy%20Sierra,%20Bert%20Bates-Head%20First%20Design%20Patterns%20-OReilly%20(2008).pdf](http://ce.sharif.edu/courses/98-99/2/ce484-1/resources/root/Design%20Patterns/Eric%20Freeman,%20Elisabeth%20Freeman,%20Kathy%20Sierra,%20Bert%20Bates-Head%20First%20Design%20Patterns%20-OReilly%20(2008).pdf)) es conocido por tratar de forma amigable este tema. Por esta misma razón es que los patrones son categorizados según el tipo de problema que solventan.

|Tipo |Solución | Ejemplos 
|--|--|---
|Creacionales |Permiten la creación o instanciación de objetos de forma que el proceso se encapsule del resto de procesos.| Factory. Abstract Factory. Singleton. Builder.
|Estructurales | Definen la manera en que los objetos se estructuran entre sí. |Adapter. Decorator. Facade.
|De comportamiento| Definen la forman en que los objetos se comportan entre sí. |Command. Observer. Strategy. Template Method.

### Antipatrones de diseño.
Existen muchos y diversos que solventan algún problema en específico, cada uno. Es por esta razón que también pueden convertirse en un error. Por esto, es bueno conocer los [antipatrones]([https://sourcemaking.com/antipatterns](https://sourcemaking.com/antipatterns)) para evitar fatalismos a futuro.

Un ejemplo es el patrón Singleton cuyo uso en exceso puede ser fatal a corto plazo.

## Adapter
De igual manera que un cable adaptador de VGA a HDMI comunica dos conectores incompatibles, este patrón **tiene el propósito de permitir a clases incompatibles trabajar colectivamente** ¿Cómo? Edita una interfaz que comunica ambas interfaces. Tal cual un adaptador de sonido o video. En este caso, la interfaz editada "adapter" sería el cable y las dos interfaces incompatibles son el emisor y el receptor de la información.

Es importante destacar que **Adapter es un patrón estructural.**

![Adaptador de USB a micro-USB vector](https://images.assetsdelivery.com/compings_v2/amin268/amin2681706/amin268170601171.jpg) 

### Estructura
Lo que diferencia a un puente de un adaptador es que el primero conecta dos partes antes de ser construidas y el segundo después de ser creadas. Este patrón funciona como la modificación  de una interfaz ya existente para que reciba o emita los parámetros necesarios para que otra interfaz ya existente pueda funcionar correctamente. Este patrón busca que **dos interfaces funcionen colectivamente sin crear una adicional**.

Por ejemplo, un teléfono móvil transfiere información a través de un puerto micro-USB y una computadora lo hace con USB. Si se requiere comunicar ambos se debe conseguir un cable que conecte ambas interfaces.

![Diagrama de clases sobre un ejemplo de Adapter](https://user-images.githubusercontent.com/38998436/83078301-821f7800-a036-11ea-9abd-90259bb495df.png)

Los pasos para escribir un Adapter pueden resumirse de la siguiente manera:
- [ ] Identificar los componentes que se requieren conectar entre sí (emisor y receptor).
- [ ] Identificar la interfaz que el receptor requiere.
- [ ] Diseñar una clase Adaptador que pueda transformar los parámetros del emisor a los requeridos por el receptor.
- [ ] El Adaptador "tiene" una instancia de la clase emisora.
- [ ] El Adaptador "mapea" la interfaz del receptor.
- [ ] El receptor usa la nueva interfaz.

En el repositorio se muestra una implentación en C++ tomada de [Source Making](https://sourcemaking.com/design_patterns/adapter/cpp/1) cuyo output es el siguiente.
#### Output
```
LegacyRectangle:  create.  (120,200) => (180,240)
RectangleAdapter: create.  (120,200), width = 60, height = 40
RectangleAdapter: draw.
LegacyRectangle:  oldDraw.  (120,200) => (180,240)
```

## Observer
Este es un patrón comportamental (de comportamiento). Su propósito principal es el de **crear una dependencia uno-varios de objetos de manera que al realizar un cambio en el Observer, los demás son notificados automáticamente**. 

### Estructura

Existe un Sujeto que representa una abstracción parecida a un núcleo (componente independiente, centro o motor). También, un Observer que representa una abstracción variable (componente dependiente, opcional o interfaz de usuario) abstracta. Además, los componentes Observadores que son los que se actualizan en masa. El Sujeto envía una señal al Observer que notifica a todos los Observadores para que realicen sus respectivas tareas. Cada observador puede llamar al sujeto de ser necesario.

El Observer contiene una lista de todos los observadores y cuando recibe la señal entonces recorre la lista para actualizarlos.

![Diagrama de clases sobre un observer](https://user-images.githubusercontent.com/38998436/83078221-543a3380-a036-11ea-9ed2-b00291a0138e.png)

Por ejemplo, un sistema de subastas. Existe un subastador (Sujeto) que recibe todas las ofertas (observadores) y declara la más alta como el precio actual. Así, todos los compradores son notificados del nuevo precio y el ciclo se reinicia cuando se emite una oferta mayor.

Otro ejemplo sería un juego de poker en línea. Cada jugador (observador) debe ser notificado de las actualizaciones de la mesa (Observer). Existe un mediador (sujeto) que aprueba las jugadas y se encarga de actualizar al Observer.

Los pasos para implementar un Observer pueden resumirse de la siguiente manera:

 - [ ] Diferenciar entre el componente dependiente (observador) y el independiente (sujeto).
 - [ ] Modelar ambos con sus respectivas funcionalidades.
 - [ ] Conectar el sujeto únicamente a la clase Observer base.
 - [ ] Los observadores se registran a sí mismos con el Observer.
 - [ ] El sujeto emite señales al Observer.
 - [ ] Se pueden utilizar dos métodos: los observadores "piden" las señales o el sujeto las "envía".

En el repositorio se muestra una implementación en C++ del patrón Observer tomado de [Source Making](https://sourcemaking.com/design_patterns/observer) cuyo output es el siguiente.

#### Output
```
14 div 4 is 3
14 div 3 is 4
14 mod 3 is 2
```
# Bibliografía

- [Sánchez, M. A. (2020, February 27). Patrones de Diseño de Software. Retrieved May 27, 2020](https://medium.com/all-you-need-is-clean-code/patrones-de-dise%C3%B1o-b7a99b8525e)
- [Leiva, A. (2016, March 05). Patrones de diseño de software. Retrieved May 27, 2020](https://devexperto.com/patrones-de-diseno-software/)
- [N.d., N. (2007). Design Patterns and Refactoring. Retrieved May 27, 2020](https://sourcemaking.com/design_patterns/adapter)

[Aquí](https://drive.google.com/file/d/1QdUGDE2Dw7k_31784ExMrkh-W9y4AGII/view?usp=sharing) se puede acceder al PDF de este repositorio.
