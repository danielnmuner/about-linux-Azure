## Curso Introduccion a la Nube 🌍☁️💻

- **Introduccion al computo en la nube**
   - [Niveles de Servicio de Azure](#niveles-de-servicio-de-azure-y-certificaciones)
   - [Qué es la nube: ventajas y características](#qué-es-la-nube-:-ventajas-y-características)
   - [Modelos de servicio: IaaS, PaaS, SaaS y serverless](#modelos-de-servicio-:-iaas-,-paas-,-saas-y-serverless)
   - [Tipos de nube: pública, privada e híbrida](#tipos-de-nube-:-pública-,-privada-e-híbrida)

- **Componentes de Azure**
   - [Qué es Azure](#qué-es-azure)
   - [Cuentas de Azure](#cuentas-de-azure)

### Niveles de Servicio de Azure y Certificaiones
---
1. Fundamentals
2. Associate
3. Expert
4. Specialty and Certifications
   > - Developer [Azure Developer, Dymamics 365, Power Platform, IoT Developer]
   > - Administrator [Azure Administrator, Teams Admin, Security Admin]
   > - Solutions Architec [Power Platforms]
   > - Data Engineer [Azure Data Engineer Associate]
   > - Data Scientist [Azure Data Scientist Associate]
   > - AI Engineer [Azure AI Engineer Associate]
   > - DevOps

### Qué es la nube: ventajas y características
---
**¿Qué es la nube?**  

La nube son instalaciones en las cuales cada una tiene de forma independiente energia electrica, refrigeración y seguridad, son llamados Centro de Datos.

**¿Para qué o Por qué?**
- Cómputo
- Servidores
- Almacenamiento y bases de datos
- Redes
- Inteligencia Artificial
- Reduce costos operativos
- Optimiza la infraestructura
- Escala según las necesidades

####  **CapEx vs OpEx**
- Gastos de capital **`CapEx`**: Inversión en infraestructura física, deducible a **largo plazo**.
- Gastos operativos **`OpEx`**: Inversión en servicios o productos facturados al momento de consumo.

** Tipo de Escalabilidad**
- **Vertical**: aumentando RAM | CPU a una VM
- **Horizontal**: aumentado instancias de recursos

### Modelos de servicio: IaaS, PaaS, SaaS y Serverless
---
- **On-Premise** Local-MiPC-Hardware
- **Infraestructura como servicio-IaaS**
- **Plataforma como servicio-PaaS**
- **Software como Servicio-SaaS**
- **`aaS`** As a Service, significa una instalación, generalmente relacionada con TI, computación o telecomunicaciones, que está disponible para sus usuarios como un servicio, en lugar de algo que ellos instalan y operan a través de su propio hardware. Se accede a estos servicios a través de internet.

**¿Qué es IaaS?**
1. IaaS les da a las empresas la opción de tener un proveedor que proporcione y administre estos elementos. Este servicio permite a las empresas deshacerse de la responsabilidad de tener que operar su propia infraestructura y hardware.

2. A través de IaaS, las empresas pueden acceder a lo que necesitan en cada momento, a nivel de infraestructura, almacenamiento y capacidad de red a través de Internet, un entorno de TI que se adapte a sus necesidades y se puede ampliar o reducir según sea necesario. Los proveedores de IaaS pueden administrar servicios como firewalls, conexiones de red, balanceadores de carga, almacenamiento de datos y administración de identidades. Con estos recursos atendidos, las empresas acceden a esta infraestructura y desarrollarla, instalar sistemas operativos, crear bases de datos y almacenar archivos.

**¿Qué es PaaS?**
1. Los clientes pueden usar PaaS para anclar las capacidades de la nube en su propia red existente. El modelo PaaS proporciona a las empresas componentes de nube para cierto software, ofreciendo un marco basado en la nube en el que los desarrolladores pueden crear e implementar aplicaciones personalizadas.

2. Al igual que IaaS proporciona a las empresas los marcos para construir un entorno informático que se adapte a sus necesidades, PaaS les brinda a las empresas la plataforma digital para desarrollar e implementar sus propias aplicaciones y servicios, sin la necesidad de mantener el espacio del servidor, el software de programación y los protocolos de seguridad internamente. La principal diferencia entre IaaS y PaaS es que con PaaS, el cliente consume el servicio central necesario para las aplicaciones propias, y la administración interna se deja al proveedor de la nube.

3. Con PaaS, las empresas pueden crear y desarrollar sus propios servicios en una plataforma existente, utilizando herramientas que pueden obtener de un proveedor externo que se hará cargo de todas las actualizaciones y la administración de esa plataforma. PaaS hace que las empresas construyan sus productos y servicios más rápido, más barato y más sencillo, y aumente sus recursos según sea necesario sin un desembolso financiero significativo.

**¿Qué es SaaS?**
1. SaaS, o software como servicio, es un modelo a través del cual el software se entrega a través de Internet, en lugar de descargarse en dispositivos individuales. El software es administrado por un proveedor externo y, por lo general, se accede a él a través de una aplicación o un navegador web.

2. Con SaaS, todos los aspectos del alojamiento, la configuración y el mantenimiento del software están a cargo de su proveedor. Todo lo que necesita hacer para acceder es iniciar sesión en una aplicación o navegador y usar el software de la misma manera que lo haría con una aplicación de escritorio tradicional instalada en su propia computadora.

**¿Algo más que necesitas saber?**
La infraestructura, la plataforma y el software son los tres pilares de la computación en la nube; sin embargo, a medida que la tecnología ha avanzado, han surgido más usos para la nube, lo que significa que hay muchos otros modelos como servicio. Y es probable que sigan viniendo más. En el lado positivo, ahora hay tantos tipos de servicios que muchos en la comunidad de TI han empezado a usar el término general XaaS; Significando cualquier cosa como un servicio.

> Estos son algunos de los modelos de servicios complementarios más comunes que puede encontrar:

**DbaaS (base de datos como servicio)**
> Este se explica por sí mismo. Las DbaaS son bases de datos alojadas en los servidores de un proveedor, donde puede almacenar y acceder a datos estructurados. Una de las grandes ventajas que ofrece DbaaS es que sus datos gozan de alta disponibilidad, seguridad estricta y están protegidos contra pérdidas. Emplear DbaaS también significa que no tiene que ejecutar sus propios servidores para alojar todos sus datos.

**FaaS (Funciones como un Servicio)**
FaaS es esencialmente una versión más simple de PaaS. Conocida como una arquitectura sin servidor, FaaS es autoescalable y utiliza eventos de activación para ejecutar funciones sin tener que preocuparse por la implementación o los recursos del servidor.

**AaaS (Analytics como servicio)**
> También conocida como Insights as a Service, AaaS es cualquier plataforma que se ofrece en la web y proporciona capacidades analíticas, incluida la gestión y visualización de big data. Las plataformas AaaS brindan a las empresas acceso a herramientas como aprendizaje automático e inteligencia artificial a pedido, para que puedan disfrutar de tecnología analítica de vanguardia y evitar el trabajo pesado de desarrollar estas herramientas.

**SECaaS (Seguridad como Servicio)**
> A medida que aumenta el uso de la tecnología de la nube, la seguridad se convierte en una preocupación cada vez más apremiante, y los ciberdelincuentes atacan a las organizaciones grandes y pequeñas todos los días. La seguridad como servicio está permitiendo que incluso las empresas que no tienen el recurso puedan ejecutar los procesos de seguridad necesarios en la empresa para utilizar protocolos de nivel empresarial mediante la externalización de su gestión y supervisión de la seguridad.

**VaaS (virtualización como servicio)**
> La virtualización es un componente clave de la computación en nube moderna. VaaS ofrece máquinas virtuales aisladas (VM), alojadas por el proveedor, que pueden personalizarse para satisfacer las necesidades de los clientes.

### Tipos de nube: pública, privada e híbrida
---
**Nube pública**  

- Accesible a todo el mundo
- Son propiedad de un proveedor
- Se distribuye a través de internet  

**Nube privada**  

- Accesible para miembros de una organización
- Puede estar on-premise u hospedada  

**Nube híbrida**  

- Combinación de on-premise, nube pública y privada

**Escenarios on-premises**:  

- Banca (por ahora).
- Milicia o agencias de integliencia.
- Casos de uso donde se requiera un contar delay hyper bajo

**Escenarios hibridos**:  

- Entiendo que es el paso natural cuando se quiere migrar de on premise a la nube.
- Que mi app corra on premise y si la demanda sube por encima de lo que soporto fisicamente, desborde en la nube.
- Proveer Diaster Recovery a mi app (no estoy 100% seguro de esto).

**Escenarios Publicos**  

- Que mi app requiera elasticidad, digamos pueda soportar temporalidades como Black Friday.
- Validar ideas de negocio rapidamente, digamos quiero lanzar mi app y necesito contar con un servidor que no tengo.
- Lanzar mi app globalmente, digamos que quiero que mi app corra tan bien en Brazil como en Australia, con las distintas regiones podría hacerlo.

### Qué es Azure
---
Microsoft Azure es una creciente colección de servicios en la nube integrados que los desarrolladores y los profesionales de TI utilizan para crear, implementar y administrar aplicaciones a través de nuestra red global de centros de datos. Con Azure, obtiene la libertad de crear e implementar donde quiera, utilizando las herramientas, las aplicaciones y los marcos que prefiera.

- Herramientas [Azure Portal, Azure Marketplace]

![Qué-es-Azure](https://user-images.githubusercontent.com/60556632/162094209-01b393cf-14b2-4827-8270-04c70740553c.png)

### Cuentas de Azure
---
**Estructura de una cuenta de Azure**
![Recursos](https://user-images.githubusercontent.com/60556632/162201105-63449a07-9a10-434b-a192-b46df4bbcf71.png)


- **Recursos**  

Instancias de los servicios disponibles: Máquinas virtuales, discos duros y bases de datos. Los recursos solo pueden pertenecer a un único grupo de recursos, pero los recursos de un grupo se pueden comunicar con los recursos de otro.

- **Grupos de recursos**  

Contenedor lógico donde se implementan y administran recursos de Azure. Un recurso puede pertenecer a un solo GR pero puede comunicarse con recursos de otro GR.

- **Suscripciones**  

Agrupación de cuentas de usuario y recursos creados por estas cuentas. Puede tener límites o cuotas definidas.

**Grupos de administración**  

Administran el acceso, las directivas y cumplimiento de las suscripciones. Las suscripciones heredan las condiciones de su grupo.

### [Suscripciones y grupos de administración](https://docs.microsoft.com/es-mx/learn/modules/azure-architecture-fundamentals/overview)
---
Se necesita de una suscripción de Azure para utilizar sus servicios:

- **Desarrollador**: Pagas por los servicios a medida que los utilices.
- **Prueba**: experimentar de manera gratuita.
- **Suscripción**: a través de un partner compras servicios de Azure.
- **Estudiante**: a través de un email autorizado (.edu)

**Limites**  

- **Facturación**: forma de facturarse. Cada suscripción tiene su factura.
- **Control de acceso**: cada suscripción tiene directivas de acceso.

**¿Cuándo se necesita más suscripciones?**  

- **Entorno**: separación de entornos de trabajos como desarrollo, pruebas, aislamiento de datos, entre otros.
- **Estructura Organizacional**: limitaciones según presupuesto, tiempo, por equipos o acceso a recursos.
- **Facturación**: para facilitar el seguimiento de costos según entornos como producción, desarrollo o pruebas.
- **Límites por suscripción**: Pueden haber algunas limitaciones de hardware por suscripción, entonces es necesario crear nuevas.

**Grupos de Administración**

Hasta 10 000 grupos de administración en un único directorio.
El árbol de grupo de administración puede admitir hasta seis niveles de profundidad. Cada grupo de administración y suscripción solo puede admitir un elemento primario. Cada grupo de administración puede tener muchos elementos secundarios. Todas las suscripciones y grupos de administración están dentro de una única jerarquía en cada directorio.


