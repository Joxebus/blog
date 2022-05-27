---
tags:
  - "descripciones"
  - "primero-pasos"
---

## ¿Qué es Groovy?

[![Que es Groovy](/blog/img/2022/que_es_groovy.png "que-es-groovy")](/blog/img/2022/que_es_groovy.png)

Hay algo que es bien cierto y no lo voy a negar, nada cómo la información de primera mano, con esto me refiero a que por lo regular la buena documentación o información en cuestiones de programación es en inglés, en esta ocasión trataré de hacer un tuto al estilo spanglish donde todos y cada uno podamos entender de lo que hablamos con la menor perdida de información y conceptos relevantes. ¡Trataré!

Podríamos decir que Groovy...

- es un **lenguaje dinámico** y ágil para la [JVM](http://es.wikipedia.org/wiki/JVM "Java Virtual Machine") (Maquina Virtual de JAVA)
- tiene las capacidades y fortalezas de Java pero con características adicionales y muy poderosas inspiradas en lenguajes cómo [Python](http://es.wikipedia.org/wiki/Python "Python"), [Ruby](http://es.wikipedia.org/wiki/Ruby "Ruby"), [Smalltalk](http://es.wikipedia.org/wiki/Smalltalk "Smalltalk") entre otros.
- pone a disposición de los desarrolladores JAVA las nuevas características de la programación en la mayoría de los casos sin necesidad de una curva de aprendizaje.
- integra todas las características de JAVA existentes, objetos y librerías.
- y mucho mucho más (click [aquí](http://groovy-lang.org/documentation.html "Documentación de Groovy") para ver la documentación completa).

Podríamos decir que Groovy es JAVA pero con esteroides. Salvo algunas pocas excepciones los códigos JAVA son también códigos válidos para Groovy de hecho al tiempo de programar en Groovy podemos dar por hecho que podemos realizar ciertas tareas sin necesidad de importar clases, al igual que JAVA importa por default el paquete _java.lang_ Groovy hereda este comportamiento para los paquetes:

- java.io
- java.math
- java.net
- java.util
- groovy.lang
- groovy.util

Es decir que estos paquetes no es necesario importarlos para hacer uso de sus clases y funciones. A la hora de realizar scripts esto es muy eficiente, puesto que no necesitamos preocuparnos si por equivocación hemos olvidado importar alguna de estas clases de uso común.

Existen muchos conceptos que deberíamos leer a fondo para comprender mucho de donde nace la idea de Groovy pero la verdad eso se los dejo de tarea, por ahora hay algunas consideraciones que debemos tener en cuenta para poder ejecutar Scripts de Groovy en nuestra PC.

**Instalación**

Consideraciones para empezar a programar con Groovy:

- Groovy corre sobre la JVM por lo que les recomiendo bajarse el JDK antes que nada de la página de Oracle.
- Deben descargar la última versión estable de Groovy, para el día de hoy esta sería la 1.8.0 y la pueden descargar [aquí](https://groovy.apache.org/download.html "Download Groovy").

Una vez instalados abrimos la consola y escribimos el siguiente comando:

```shell
> groovy -v

Groovy Version: 3.0.6 JVM: 16.0.2 Vendor: GraalVM Community OS: Mac OS X
```


[![Groovy Version](/blog/img/2022/groovy_version.png "cmd-groovy-version")](/blog/img/2022/groovy_version.png)

Lo cual representa respectivamente nuestra versión de Groovy y de la JVM que tenemos instalada. Ahora que si al ejecutar el comando nos manda algun error de que el comando no es reconocido probablemente es porque no tenemos bien configuradas las "variables de entorno..." para ello tendremos que seguir los siguientes pasos.

- Abrir las propiedades del sistema
- Configuración avanzada del Sistema
- Variables de entorno...
- Crear una nueva variable de sistema llamada **"GROOVY\_HOME"** y agregarle el path del bin donde quedo instalado, en mi caso fue **"D:\\Program Files\\Groovy\\Groovy-3.0.6"**
- En la variable **"Path"** agregamos la siguiente entrada **"%GROOVY\_HOME%\\bin"**

Reiniciamos la consola y volvemos a ejecutar el comando `groovy -v` y ya tendría que haber quedado configurado para hacer pruebas.

Dudas, comentarios o aportaciones son bien recibidos, en el siguiente post veremos como realizar nuestro primer "¡hola mundo!" y algunos conceptos básicos de Groovy.
