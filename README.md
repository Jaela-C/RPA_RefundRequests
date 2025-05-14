## Solicitud de Reembolsos

* **Entregables**
  * Proyecto cargado en GitHub
  * Capturas de pantalla

* **Acciones que deben ser consideradas antes de mandar la ejecución**

  * Es necesario que el equipo en el que se despliegue el bot tenga configurado el formato **dd/MM/yyyy** para la fecha, caso contrario, el bot va a presentar novedades.
  * La ruta de la carpeta que contiene la información debe terminar con un **(\\)**
  * Es necesario que el equipo cuente con la aplicación **Outlook** para el envío de notificaciones.

* **Instrucciones del ejercicio**
  * El robot debe leer todos los archivos .xlsx que se encuentren en una carpeta de entrada.
  * Para cada fila donde el estado sea "pendiente", debe hacer lo siguiente:
    
      * Verificar que el monto sea mayor a 0.
      * Validar que la fecha no sea posterior al día de hoy.
      * Si ambas validaciones son correctas, marcar el estado como "aprobado"; de lo contrario, marcarlo como "rechazado".
        
  * Generar un archivo de resumen en Excel que contenga:
    
      * Nombre del archivo procesado
      * Número de registros aprobados
      * Número de registros rechazados
      * Fecha y hora de ejecución
        
  * Mover cada archivo procesado a una carpeta de archivo histórico con la fecha en el nombre del subdirectorio (ej. /histórico/2025-04-14/). 

* **Instrucciones de instalación**
  * Clonar repositorio en la carpeta de su preferencia
    ```
    git clone https://github.com/Jaela-C/RPA_RefundRequests.git
    ```
  * Descomprimir el archivo que se encuentra en la carpeta **Proyecto**.
  * Importar el proyecto **BOT_SolicitudesReembolsos.zip** en un Control Room de Automation Anywhere 360.
  * Para ejecutar el proceso se debe desplegar la tarea: **RequestsOrchestrator**.
 
* **Instrucciones de uso**
  * Al ejecutar el proceso el bot pedirá que ingrese un correo electrónico y la ruta en la que se encuentra cargada la lista de archivos que se quieren procesar.
    
      * Ejemplo:
          * **Correo:** jaelacarlosama3c@hotmail.com
          * **Ruta Carpeta:** C:\Users\USER\Desktop\Documentación y Proyectos AA\EY\
            
        ![image](https://github.com/user-attachments/assets/1a005abd-5660-48dd-982d-63d75bca4c88)

* **Capturas de pantalla de la ejecución**
  * El primer paso que realiza el bot, es la creación de los directorios.

     ![image](https://github.com/user-attachments/assets/fbbd5cb6-c873-4204-ab25-5e6d37490d9f)
    
  * Procede a validar los archivos que se encuentran cargados en la carpeta, en caso de que no exista un documento válido el bot envía una alerta.

    ![ValidateFiles](https://github.com/user-attachments/assets/d6d2724d-6c00-4d72-a94d-05d896a030c0)
    ![ValidateFiles1](https://github.com/user-attachments/assets/a3f07546-5977-4d4a-8ddb-5ba0b1bf17c3)
    ![FileNotFound](https://github.com/user-attachments/assets/d711987d-99a7-464d-b75b-318f5072de74)
 
  * Posteriormente el bot, itera en cada registro para realizar las validaciones correspondientes y procede a aprobar o rechazar la solicitud.

    ![ApproFile](https://github.com/user-attachments/assets/9457a139-2bb7-4bb7-b209-bfc21fbee728)
    ![ApproFile2](https://github.com/user-attachments/assets/f5e10b4b-dc4c-4f57-a0f4-8e705ba9dcee)

  * El bot con la información obtenida genera un archivo de reporte con el nombre del archivo, la cantidad de solicitudes aprobadas, la cantidad de solicitudes rechazadas y la hora en la que se procesó el archivo.

    ![Report](https://github.com/user-attachments/assets/5258ebde-d5ff-4d2b-9a2b-5c97aaad0dca)
    ![WriteReport](https://github.com/user-attachments/assets/8886d7f6-fe07-422c-b63d-a7b2f943b3fe)
    
  * Finalmente, el bot envía una alerta con los resultados obtenidos o las novedades presentadas durante la ejecución del proceso y adicionalmente, envía un correo con la lista de archivos que no fueron procesados por temas de validación.

    ![EndExe](https://github.com/user-attachments/assets/119be790-516a-4edf-8604-f78d81011873)
    ![DirFiles](https://github.com/user-attachments/assets/756b947b-a119-4d0d-8319-ea6af0ec8b2f)
    ![SuccExe](https://github.com/user-attachments/assets/16b5a2f2-b505-4dd7-9008-e69bbd8a9923)
    ![EmailSucc](https://github.com/user-attachments/assets/d1bceb3c-c9ce-454f-83c0-4e21541a52bc)
    ![FailFiles](https://github.com/user-attachments/assets/5d0df513-ee07-482d-9c51-41e1f33b8e0a)

  * El proceso también genera un archivo Log, en el que se detallan los errores y las principales acciones a nivel macro que se realizan durante la ejecución del proceso.

    ![image](https://github.com/user-attachments/assets/b1c8ef03-efdc-4ef6-af33-4c6f6cd02458)
    ![LogFile](https://github.com/user-attachments/assets/795e6061-c15e-4a40-84d1-c1274b2a750b)
