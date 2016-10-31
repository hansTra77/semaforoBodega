# semaforoBodega
###Tarea de Sistemas Operacionales.
####Juan Pablo Medina Mora

**Solucion:** 

Para dar solucion al problema de la bodega haciendo uso de semaforos se necesita de dos semaforos, uno para el servicio de descargar y otro para el servicio de empaquetar. Ademas de lo anterior se hace uso de un objeto lock que sirva para bloquear los recursos una vez assignado un servicio, de forma que en el momento de agregar un producto a la bodega no se este creando un paquete, lo que podria llevar a errores.
La solucion consiste en una clase principal encargada de crear e inicializar los objetos Bodega, Descargador y Empacador. Las dos clases que prestan los servicios (Descargador y Empacador) pasan de extender de Thread a tener un hilo interno que es el encargado de ejecutar el servicio. Las clases anteriormente mencionadas hacen uso de Random para generar un producto tipo 1 o tipo 2, y llaman internamente metodos de la clase Bodega, que es quien realmente se encarga de realizar las operaciones, por lo tanto es en esta clase que se crean e inicializan los semaforos que permiten la sincronizacion de los hilos. Dentro de los metodos de la clase Bodega se debe adquirir inicialmente el recurso a utilizar, y al final del metodo siempre se deben de soltar los recursos para que los otros metodos puedan cumplir su trabajo, lo anterior se realiza por medio de los metodos acquire, synchronized y release().

**Resultado:**  
![alt text](https://github.com/hansTra77/semaforoBodega/blob/master/imagenSemaforoResult.JPG)  
