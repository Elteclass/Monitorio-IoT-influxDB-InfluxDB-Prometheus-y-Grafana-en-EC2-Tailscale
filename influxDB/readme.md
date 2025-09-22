<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/61d4cbc3-7352-48a0-a8eb-44ab218ed668" />

## 🗃️ 1. Instalación y Configuración de InfluxDB
En esta sección, se detalla el proceso de instalación y configuración de InfluxDB v2 como la base de datos de series temporales para almacenar los datos de nuestros sensores IoT.

### 1.1 Instalación del Paquete
- La instalación se realizó en el servidor Ubuntu 20.04. Primero, se agregó la clave GPG y el repositorio oficial de InfluxData para apt.

![repo_influx](https://github.com/user-attachments/assets/e659a63c-d969-4e5c-ad09-43032f643306)

- Una vez configurado el repositorio, se actualizó la lista de paquetes y se procedió con la instalación.
<img width="770" height="587" alt="image" src="https://github.com/user-attachments/assets/95a42c98-2a12-4e4e-8668-9b0bee9d1001" />

### 1.2 Configuración Inicial (influx setup)
Tras la instalación, se ejecutó el comando influx setup para inicializar la base de datos. Este asistente interactivo nos permitió configurar el primer usuario, organización y bucket.

Los parámetros utilizados fueron:
- Username: JaimeAlvarez
- Organization: SistemasProgramables
- Bucket: datos
- Retention: infinite (0)

![config_Influx](https://github.com/user-attachments/assets/00931aab-276a-48aa-a0d7-bd5addd815d1)

### 1.3 Obtención del API Token
- El token de administrador es esencial para interactuar con la API de InfluxDB. Se generó durante el setup y se recuperó usando el comando **influx auth list**.
<img width="1595" height="451" alt="image" src="https://github.com/user-attachments/assets/b30b023e-04bd-4ab3-9db5-20b063b3c523" />

### 1.4 Verificación del Servicio
- Para asegurar que InfluxDB se estuviera ejecutando correctamente después de la instalación y configuración, se verificó el estado del servicio con systemctl.
<img width="1372" height="216" alt="image" src="https://github.com/user-attachments/assets/fe555133-6ed8-4290-8aee-341bd56ccaa6" />

- El servicio se mostró active (running), confirmando que la base de datos está operativa.

### 1.5 Consulta Simple desde la CLI
- Para validar la correcta creación de nuestros recursos, realizamos una consulta simple para listar los buckets existentes.
<img width="1056" height="116" alt="image" src="https://github.com/user-attachments/assets/d4a0fa00-1e53-4366-9346-d55bd8a833eb" />

- El resultado muestra el bucket datos que creamos, junto a los buckets internos del sistema.

### 1.6 Acceso a la Interfaz Web (UI)
- Finalmente, se confirmó el acceso a la interfaz gráfica de InfluxDB a través del navegador, utilizando la IP de la instancia EC2 y el puerto 8086.
<img width="582" height="113" alt="image" src="https://github.com/user-attachments/assets/5b689434-fb3d-4e26-8675-f89735edd58e" />
<img width="1407" height="738" alt="image" src="https://github.com/user-attachments/assets/1ce82363-d62c-42b5-983e-25d84c94b2d7" />
<img width="1594" height="772" alt="image" src="https://github.com/user-attachments/assets/c901a44e-a103-4173-8111-ad4579c26cac" />

- La interfaz web cargó correctamente, mostrando la página de inicio de sesión donde se puede acceder con el usuario y contraseña creados.

---

**Autor**: Jaime Antonio Alvarez Crisostomo  
**Institución**: TECNM / Instituto Tecnológico de Tijuana  
**Materia**: Sistemas Programables  
**Año**: 2025
