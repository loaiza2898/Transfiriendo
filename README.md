# Proyecto Transfiriendo

Aplicación en NODE.JS para validar modificar y crear transacciones.


## 📌 Características
Este proyecto es una aplicación backend que gestiona transacciones financieras, almacenando los datos en **MongoDB** y registrando logs en **SQL Server**. La aplicación está desarrollada en **Node.js** y utiliza **Express.js** como framework.


## 🗂️ Estructura de archivos
```bash
Transfiriendo/
src/
├── index.ts               # Punto de entrada de la aplicación
├── application/                  # Lógica de la aplicación
│   └── TS TransactionAppService.ts  # Servicio de aplicación para transacciones
│
├── domain/                       # Lógica del dominio
│   ├── entities/
│   │   └── TS Transaction.ts     # Entidad de transacción
│   └── interfaces/
│       ├── TS TransactionRepository.ts  # Interfaz del repositorio de transacciones
│       └── TS TransactionService.ts     # Interfaz del servicio de transacciones
│
├── infrastructure/               # Infraestructura y conexiones externas
│   ├── database/
│   │   ├── connections/
│   │   │   ├── TS mongoConnection.ts  # Conexión a MongoDB
│   │   │   └── TS sqlConnection.ts    # Conexión a SQL Server
│   │   ├── models/
│   │   │   ├── TS LogModel.ts         # Modelo de log para SQL Server
│   │   │   └── TS TransactionModel.ts # Modelo de transacción para MongoDB
│   │   └── repositories/
│   │       ├── TS MongoTransactionRepository.ts  # Repositorio de transacciones (MongoDB)
│   │       └── TS SqlLogRepository.ts           # Repositorio de logs (SQL Server)
│
└── webapi/                       # Capa de presentación (API)
    ├── config/
    │   └── TS swagger.ts         # Configuración de Swagger para la documentación de la API
    ├── controllers/
    │   ├── TS AuthController.ts  # Controlador para autenticación
    │   └── TS TransactionController.ts  # Controlador para transacciones
    ├── middlewares/
    │   └── TS authMiddleware.ts  # Middleware para autenticación
    ├── routes/
    │   ├── TS authRoutes.ts      # Rutas para autenticación
    │   └── TS transactionRoutes.ts  # Rutas para transacciones
   

```
## 🚀 Instalación
Sigue estos pasos para configurar y ejecutar el proyecto:

### **1. Clonar el repositorio**
```bash
https://github.com/loaiza2898/Transfiriendo.git
```

### **2. Abrir el proyecto en Visual Studio Code**
```bash
Transfiriendo .
```

### **3. Instalar dependencias **
Este proyecto utiliza bastantes dependencias que estan especificadas en el archivo package.json
Abre la terminal y coloca `npm install`

### **4. Ejecutar la aplicación**
1. Una vez instaladas las dependencias colocamos `npm start`
2. Nos dirigimos a el Swagger por medio de la URL `http://localhost:3000/api-docs/#/`.
3. Generamos un token y lo pondremos donde dice Authorize.
4. Procedemos a realizar las pruebas de los endPoints.
5. Dentro del mismo Swagger hay algunos json que pueden funcionar a modo de prueba para cada endpoint.

## 🛠️ Configuración Adicional
### **Crear el archivo .env**
Para que la aplicacion funcione es necesario que crear un archivo de variables de entorno llamado `.env` con los siguientes componentes:

```.env

MONGO_URI=mongodb+srv://root:f3vTpUZ8kaSGWZan@transfiriendo.nlyyq.mongodb.net/transfiriendo
JWT_SECRET=clave_secreta_super_segura
PORT=3000
SQL_SERVER=localhost
SQL_USER=sa
SQL_PASSWORD=123456
SQL_DATABASE=TransaccionesDB

```



