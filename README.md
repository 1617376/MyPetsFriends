# MyPetsFriends - Sistema Veterinario

## Descripción general del proyecto

MyPetsFriends es una solución ERP orientada a la administración de una clínica veterinaria, cuyo propósito es integrar y facilitar el control de sus actividades operativas. El sistema está implementado con Odoo Community, PostgreSQL y Docker, permitiendo organizar desde una misma plataforma la información de clientes, proveedores, productos, servicios, inventario, ventas y facturación.

## Herramientas y tecnologías empleadas

- **Odoo Community 19.0:** plataforma utilizada para administrar los procesos empresariales.
- **PostgreSQL 16:** base de datos encargada de almacenar la información del sistema.
- **Docker:** herramienta para ejecutar los servicios mediante contenedores.
- **Docker Compose:** permite configurar y gestionar los diferentes contenedores.
- **Git y GitHub:** utilizados para administrar las versiones y mantener el código fuente del proyecto.

## Módulos implementados

Para cubrir las necesidades administrativas de la clínica, se habilitaron los siguientes módulos:

- Contactos.
- Ventas.
- Inventario.
- Facturación.
- Calendario.

## Registro y carga de información

Se incorporaron los datos iniciales al sistema mediante archivos CSV, organizados de la siguiente manera:

| Archivo | Cantidad de registros |
|---|---:|
| propietarios.csv | 15 |
| proveedores.csv | 5 |
| productos.csv | 30 |
| **Total** | **50** |

Adicionalmente, se crearon y configuraron cinco servicios relacionados con la atención veterinaria:

- Atención mediante consulta veterinaria.
- Aplicación de vacunas.
- Servicio de baño para mascotas.
- Tratamientos de desparasitación.
- Procedimientos de cirugía veterinaria.

## Validación del proceso de venta

Se efectuó una operación de prueba para verificar el funcionamiento del módulo de ventas y su integración con los demás componentes del ERP.

Los datos utilizados fueron los siguientes:

- **Cliente:** Carlos Mendoza.
- **Artículo vendido:** Alimento para perro adulto de 3 kg.
- **Cantidad solicitada:** 2 unidades.
- **Valor por unidad:** S/ 45.00.
- **Subtotal:** S/ 90.00.
- **IGV (18 %):** S/ 16.20.
- **Importe total:** S/ 106.20.

Durante esta prueba se verificó el proceso completo, desde la confirmación de la venta hasta la entrega del artículo. Asimismo, se comprobó la modificación de las existencias, la emisión de la factura y el registro del pago de prueba.

## Control de inventario

Se ingresaron existencias iniciales correspondientes a cinco productos para comprobar el funcionamiento del módulo de inventario.

Como parte de la validación, se realizó la salida de dos unidades de alimento para perro adulto de 3 kg. En consecuencia, la cantidad disponible se redujo de 20 a 18 unidades, confirmando que el sistema actualiza las existencias después de completar una entrega.

## Guía de instalación y ejecución

### Requisitos previos

Para poner en funcionamiento el proyecto se necesitan las siguientes herramientas:

- Sistema operativo Windows.
- Docker Desktop.
- Docker Compose.
- Git.
- Visual Studio Code.

### Pasos para ejecutar el sistema

**1. Descargar el repositorio**

```bash
git clone https://github.com/nikoTM02/MyPetsFriends-ERP.git
```

**2. Acceder al directorio del proyecto**

```bash
cd MyPetsFriends-ERP
```

**3. Preparar las variables de entorno**

Crear y configurar el archivo `.env` con los valores necesarios que solicita el archivo `docker-compose.yml`.

**4. Obtener las imágenes de los servicios**

```bash
docker compose pull
```

**5. Levantar los contenedores**

```bash
docker compose up -d
```

**6. Revisar el estado de ejecución**

```bash
docker compose ps
```

**7. Ingresar a la plataforma**

Abrir el navegador y acceder a la siguiente dirección:

http://localhost:8069

## Gestión de copias de seguridad

Para proteger la información almacenada en el sistema, se generó un respaldo de PostgreSQL mediante la herramienta `pg_dump`, utilizando el formato personalizado.

Posteriormente, se comprobó que el archivo de respaldo pudiera leerse correctamente y se efectuó una restauración en una base de datos temporal. Esta prueba permitió verificar que los registros podían recuperarse adecuadamente.

Los archivos generados se conservan localmente dentro del directorio `backups/`.

## Organización de los archivos del proyecto

La estructura de directorios y archivos se encuentra distribuida de la siguiente manera:

```text
MyPetsFriends/
│
├── addons/
├── backups/
├── config/
├── csv/
├── screenshots/
│
├── .env
├── .gitignore
├── docker-compose.yml
└── README.md
```

## Evidencias del desarrollo

Dentro de la carpeta `screenshots/` se encuentran las imágenes que documentan las principales pruebas y configuraciones realizadas en el sistema:

- Registro y administración de contactos.
- Catálogo de productos.
- Configuración de servicios veterinarios.
- Gestión de existencias.
- Creación de órdenes de venta.
- Validación de entregas.
- Generación de facturas.
- Registro de pagos.
- Informes de ventas.
- Informes de inventario.

## Alcances y limitaciones

La implementación se desarrolló utilizando las funcionalidades estándar de Odoo Community, adaptándolas a los procesos administrativos de una clínica veterinaria.

Sin embargo, algunas características propias de la gestión veterinaria, como las historias clínicas de los animales, el seguimiento de tratamientos y el historial de vacunación, necesitan complementarse mediante módulos especializados o funcionalidades desarrolladas a medida.

## Autoría

**Proyecto académico: MyPetsFriends - Sistema Veterinario.**
