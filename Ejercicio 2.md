# Almacenamiento en caché

El almacenamiento en caché es una técnica que tiene como objetivo mejorar el rendimiento y la escalabilidad de un sistema. Para ello, se copian temporalmente los 
datos a los que se accede con mayor frecuencia en almacenamiento rápido ubicado cerca de la aplicación. Si este almacenamiento de datos rápido se encuentra más cerca 
de la aplicación que el primer origen, el almacenamiento en caché puede mejorar considerablemente los tiempos de respuesta de las aplicaciones cliente dado que los 
datos se sirven con mayor rapidez.

El almacenamiento en caché es más eficaz cuando una instancia de cliente lee de forma repetida los mismos datos, en especial si todas las condiciones siguientes se 
aplican al almacén de datos original: <br />
- Permanece relativamente estático.
- Es lento en comparación con la velocidad de la caché.
- Está sujeto a un alto nivel de contención.
- Está lejos cuando la latencia de red puede provocar que el acceso sea lento.

El almacenamiento en caché puede mejorar considerablemente el rendimiento, la escalabilidad y la disponibilidad. Cuantos más datos tenga y mayor sea el número de 
usuarios que necesitan tener acceso a ellos, mayores son cada vez las ventajas del almacenamiento en caché. El motivo es que el almacenamiento en caché reduce la 
latencia y la contención asociadas con el tratamiento de grandes volúmenes de solicitudes simultáneas en el almacén de datos original.

Por ejemplo, una base de datos puede admitir un número limitado de conexiones simultáneas. La recuperación de datos de una caché compartida, sin embargo, en lugar 
de la base de datos subyacente, permite que una aplicación cliente acceda a estos datos incluso si el número de conexiones disponibles está actualmente agotado. 
Además, si la base de datos deja de estar disponible, es posible que las aplicaciones cliente continúen usando los datos contenidos en la caché.


# Almacenamiento en caché privado
El tipo más básico de caché es un almacén en memoria. Está contenido en el espacio de direcciones de un solo proceso y se accede directamente a él mediante el código
 que se ejecuta en ese proceso. Este tipo de memoria caché es de acceso rápido. También puede proporcionar un medio efectivo de almacenar cantidades modestas de datos
 estáticos, dado que el tamaño de una memoria caché suele estar restringido por la cantidad de memoria disponible en la máquina que hospeda el proceso.
 
Si necesita almacenar en caché más información de lo que es posible físicamente en la memoria, puede escribir datos en caché en el sistema de archivos local. El acceso 
será más lento que cuando los datos están contenidos en memoria, pero aún así debería ser más rápido y confiable que recuperar los datos desde una red.

Si tiene varias instancias de una aplicación que usa este modelo de ejecución simultánea, cada instancia de la aplicación tendrá su propia caché independiente con su propia
copia de los datos.

Una caché se puede considerar como una instantánea de los datos originales en algún momento del pasado. Si estos datos no son estáticos, es probable que las diferentes 
instancias de aplicación contengan versiones diferentes de los datos en sus cachés. Por lo tanto, la misma consulta realizada por estas instancias podría devolver 
resultados diferentes.
