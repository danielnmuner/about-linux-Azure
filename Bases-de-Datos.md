## Bases de Datos en Azure

- [x] [Introduccion](#Introduccion)
- [x] [Azure con MySQL y MariaDB](#azure-con-mysql-y-mariadb)

### Introduccion
- **¿Por qué Azure es la mejor plataforma para tus bases de datos?**
Azure informa a la comunidad que Microsoft🧡Linux por con el objetivo de hacer notar que con Azure todos los servidores Linux serian mas facil de migrar a servidores en la nube. 

- **Actualidad de Bases de Datos Open Source**
> **Bases de datos relacionales**: Al menos el 85 % de las nuevas aplicaciones y proyectos usarán esquema relacional.

> **Open Source**: Más del 70% de las nuevas aplicaciones internas se desarrollaran en OSDBMS

> **Cloud**:DBass(Relational) es el mejor servicio de nube pública utilizado.

> **Casos de uso**:CMS,Gaming,e-commerce donde se contara con infraestructura escalables en momentos muy alta demanda.

** Proceso de Migracion de Bases de Datos **END-TO-END**
![image](https://user-images.githubusercontent.com/60556632/168206770-804105af-3d1d-4c32-ad2c-cfdc4fdb1fd8.png)

### Azure con MySQL y MariaDB
MariaDB es un Fork de MySQL en la medida que MySQL se comienza a privatizar con Oracle. Ambas son ampliamente utilizadas en el mercado y se encuentran en Azure. 

![image](https://user-images.githubusercontent.com/60556632/168207507-720d85fe-2a93-487b-ae0a-051bbb81149c.png)

- **¿Cómo crear bases de datos MariaDB y MySQL en Azure utilizando la interface gráfica?**
---
- Creamos un servidor de MySQL
  - Creamos un recurso de **Bases de Datos** `Azure DataBase for MySql` y en este caso `Un solo servidor`
  ![image](https://user-images.githubusercontent.com/60556632/168404097-11af4f67-c7a4-407f-966f-c449ecb1d256.png)
  - Creamos un `grupo de recurso` si no lo tenemos (server-mysql)
  - Colocamos el `nombre del servidor` debe ser unico. 
  - Seleccionamos la version de la base de datos
  - **Importante** configurar `nivel de servicio` el cual depende la necesidad de la empresa. **Proposito General**: Equilibrio entre computo y almacenamiento(Permite escalar la base de datos en almacenamiento). La redundancia local y geografica se refiere a la recuperacion de datos de forma local o de cualquier parte del mundo. **Memoria Optimizada**: Procesamiento de datos en tiempo real. 
    ![image](https://user-images.githubusercontent.com/60556632/168404643-266f127b-4da7-47b9-b516-99210cea4d76.png)
    ![image](https://user-images.githubusercontent.com/60556632/168404737-2dab9715-efb8-4728-93e1-ebce80e0da70.png)
  - Indicamos la informacion del usuario y su password luego `Revisar y Crear`. 
  - Luego abrimos nuestro recurso
  ![image](https://user-images.githubusercontent.com/60556632/168407360-98209822-70d8-4d5f-8465-754091f118f0.png)
  - Configuramos la direccion IP desde `Seguridad de Conexion`.
    ![image](https://user-images.githubusercontent.com/60556632/168408016-11cb0af7-af31-4d68-9754-02ed6c0ab28c.png)
  - Finalmente antes de guardar **desabilitamos** SSL por praticidad para este proyecto pero esto no se debe realizar en produccion y se deberia configurar `SSL`
- **Desplegar la misma base de datos desde CLI para eso abrimos bash de azure**
---
  ```sh
  #Indicamos la suscripcion que usaremos
  az account set --subscription id-suscripcion (id-subscripcion)
  #Creamos un grupo de recursos
	az group create --name (nombre) --location (region-westus)
	
  #Creamos el recurso
  az (mariadb) server create 
	--resource-group (nombre_grupo)
	--name (mydemosqlservestest) --location westus 
	--admin-user (usuario)
	--admin-password (contraseña)
  
  #Indicamos el nivel de servicio
	--sku-name GP_Gen5_2 
	--version 10.2
  ```
  
- **¿Cómo conectarme a una base de datos MariaDB en Azure?**
---
  - Para conectarme a una base de Datos necesitamos la siguiente informacion.
    ![image](https://user-images.githubusercontent.com/60556632/168407899-d09e6fbd-aa01-42de-a52f-de6d49186d3f.png)
  - Abrimos `Workbench` y configuramos la conexion 
  ![image](https://user-images.githubusercontent.com/60556632/168408077-f5e0b32f-263c-44cf-9e5b-91f1a1862b17.png)
  ![image](https://user-images.githubusercontent.com/60556632/168408121-7d1e0ffc-3bae-4e1b-8515-01d8de7c66f5.png)
  - Luego de habernos enlazado a la base datos podemos empezar a crear nuestra base de datos.
```sql
create database rrhdb;
use rrhdb;
create table empleados(
	id serial primary key,
    nombre varchar(50),
    salario decimal,
    fecha_nacimiento date
);
insert into empleados (id, nombre, salario, fecha_nacimiento)
values
(1,'Maria Perez',1500,'1993-11-11'),
(2,'Daniel Lopez',5600,'1975-01-17'),
(3,'Juliana Dominguez',3500,'1999-09-02'),
(4,'Maria Perez',1500,'1993-11-11'),
(5,'Carolina Herrera',2500,'1981-12-23'),
(6,'Roger Federer',3400,'1962-10-01'),
(7,'Maria Sharapova',7200,'1986-05-15'),
(8,'Diana Random',1500,'1993-11-11'),
(9,'Cristina Watss',2100,'2001-02-01'),
(10,'Camila Osorio',5100,'1996-03-11');
commit;
select * from empleados;
```
- **Desarrollar aplicacion VSCode que consumira los datos de la BD**
    - Creamos un proyecto de **tipo consola** desde VSCode `New Terminal` y en a terminal colocamos `dotnet new nombre-consola`.
    - Agregamos los siguiente **pluggins** para soportar la conexion con MySql: 1. `C#`, 2. `MySQL Syntax` 3. `MySQL` 4. ``NuGet Package Manager`.
    - Abrimos archivo Program.cs` -> `Ctlr + Shit + P` -> `MySqlConnector` -> `Cualquier version que no sea Beta` -> `MySqlData` y luego agregamos las librerias a nuestro archivo `Program.cs`

```sh
#Insetar librerias
using MySql.Data.MySqlClient;
using System.Threading.Tasks;
```
  - Colocamos este codigo despues de la funcion `static async Task Main(string[] args)`
```sh
var builder = new MySqlConnectionStringBuilder
{
    Server = "mysqlrdbms-server.mysql.database.azure.com",
    Database = "rrhdb",
    UserID = "myadmin@mysqlrdbms-server",
    Password = "CEdndm1246",
    #Indica que no tendremos SSl
    SslMode = MySqlSslMode.None
};

#Abrimos la conexion como una tarea asincrona
using (var conn = new MySqlConnection(builder.ConnectionString)) {
    Console.WriteLine("Opening connection");
    await conn.OpenAsync();
    using (var command = conn.CreateCommand()) {
    #Insertar datos
        command.CommandText = @"INSERT INTO empleados(id,nombre,salario,fecha_nacimiento)
                                VALUES(@id1, @nombre1, @salario1, @fecha_nacimiento1);";
        command.Parameters.AddWithValue("@id1", "32");
        command.Parameters.AddWithValue("@nombre1", "Roberto Antonio Alferes Gomez");
        command.Parameters.AddWithValue("@salario1", "400");
        command.Parameters.AddWithValue("@fecha_nacimiento1", "1994-09-24");
        int rowCount = await command.ExecuteNonQueryAsync();
        Console.WriteLine(String.Format("Number of rows inserted={0} ", rowCount));
    }
}

    Console.WriteLine("Hello, World!");
```
  
    - Ejecutamos la applicacion con `dotnet run` y basicamente lo que sucede es que se insertan:
    ```sh
     	command.Parameters.AddWithValue("@id1", "32");
        command.Parameters.AddWithValue("@nombre1", "Roberto Antonio Alferes Gomez");
        command.Parameters.AddWithValue("@salario1", "400");
        command.Parameters.AddWithValue("@fecha_nacimiento1", "1994-09-24");
    ```
    - Y ahora consultar el id=32 desde workbech.
    
    
