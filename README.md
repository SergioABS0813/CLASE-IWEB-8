# CLASE9-IWEB-JDBC

## Driver JDBC
Ahora crearemos proyecto con Maeven

Maeven es un gestor de librerías.

<img width="368" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/1d87e2d9-ef59-453c-b402-9d578b4eab07">

Creación de Proyecto con Maeven

<img width="353" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/95b9e9d7-bc9e-418b-9583-76873e2d5d14">

Main Creación de Proyecto en Maeven

    package org.example;
    
    public class Main {
        public static void main(String[] args) {
    
            
        }
    }
    
OJO: XML es un lenguaje de etiqueta, (HTML se basa en XML)

Las dependencias son las librerías

Posteriormente buscamos en google el Driver que queramos usar

<img width="710" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/d089a5bb-05c7-4bbf-82be-68e4be2f2eef">

Copiamos y pegamos en el archivo .xml 

<img width="691" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/e76162fe-d9b0-4fec-886d-b0711beeaeb4">

<img width="358" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/63ac16c4-c067-4be9-bd91-7e10b5668470">

Si bien tenemos el driver (que contiene todas las librerías), nos falta poder declarar la libreria que queremos utilizar en el proyecto

## Registrar Driver

Se coloca un try-catch por la excepción que tiene:

<img width="452" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/90e19530-2bdf-4bed-9315-9aeb6e5ae196">

Registramos el Driver en el Main con la sentencia "Class.forName":

<img width="864" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/0d3d48b4-0ba5-4399-b307-70417e3e75c4">

## Parámetros de Conexión a MYSQL

Parámetros necesarios para poder trabajar en una base de datos. Se colocan en el Main

El username = "123456" (para los del lab)

El password = "123456"

OJO: El puerto usado por MYSQL es: 3306

<img width="343" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/63360940-76bb-45d5-b03f-22d327b16b81">

Resultado en mi PC:

<img width="569" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/3eaa1204-002f-48ca-8d7e-6e9cc429ca5d">

## Conexión MySQL
Inicializamos la conexión a MYSQL

<img width="369" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/9765e7e3-8fbe-4053-9b6b-a70d463434c6">

Resultado en mi PC:

<img width="629" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/9c37e214-178c-472d-8558-9a9727fdce27">

Se tiene que colocar el connection "conn" (puente de conexión entre JAVA y MYSQL)

Colocar statement "stmt" (transporte de lo que deseo enviar a MYSQL)

Colocar Resultset "rs" (respuesta de MYSQL)

RECORDAR: TENEMOS QUE CERRAR TODA CONEXIÓN ESTABLECIDA (rs, stmt y conn):

Lo cerramos colocandolos dentro del try y el sql lo colocamos antes :D

<img width="736" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/cce6360a-cc59-497b-bcbc-5510a6fb9cc6">


## Uso del rs en Tablas

El rs es un puntero. Va a apuntar a una fila antes de la tabla, pero con "rs.next()" podremos verificar si hay info (TRUE es tabla con info y FALSE es tabla sin info o es una fila vacía). Cada vez que usemos "rs.next()", el rs se mueve a una fila de abajo.

![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/135c5eef-b515-4a47-ac1d-51c3618c97d8)

Ahora validamos que tenga info la siguiente línea. El rs está en la primera fila con info y con "getInt" podemos obtener el valor (entero) de la fila a la que indica, mismo caso con "getString"

<img width="464" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/89e57e4d-10a8-42b1-b56f-0202e6834c2a">

Resultado para tener info de ambos:

<img width="667" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/3f69f34b-c15b-4477-8aea-98b9e4e1e267">

Otro resultado: (también se puede hacer así)

<img width="651" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/6a979a02-786e-4984-9bb1-7cf714f6a703">

También en vez de número podemos colocar el nombre de la columna de la cual extraemos info:

<img width="682" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/adf2e69a-fa00-4e9b-8694-93255d491786">

## PRACTICA: FILTRO EMPLEADOS

Hecho con un Query:

<img width="632" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/a8a35b48-09cb-4dce-ae79-f2fa75686a87">

Hecho con Java:

<img width="766" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/ca2e29d2-a364-432c-85a2-bf5dd0a97c45">

## Problemas ZONA HORARIA

<img width="384" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/944b9081-c9bf-49b8-b20a-28ec0152e3e9">

.

<img width="438" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/17c29ff7-bba4-4ea6-b0c0-009e58a49fc2">

## Data Source

<img width="505" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/b3e8bc4b-82b7-4fbc-8eff-7a6f654e7485">

## Daos

Data Access Object (DAO). En los Dao podemos crear los métodos que emplearemos para cada tabla. Lo que estaba en el main, lo pasamos a los DAO

EmployeeDao

<img width="724" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/140939da-13ba-41cc-97ba-b0e3d83d9c65">

JobDao 

Metodo para insertar una fila en la tabla JOB

<img width="713" alt="image" src="https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/0a1b359f-7e9d-48b7-bf43-5dcbe18d6ffe">

"executeUpdate" nos servirá para hacer un update a la tabla con los valores que insertemos desde JAVA. Además, retorna un entero.
