<img width="1920" height="1081" alt="image" src="https://github.com/user-attachments/assets/2314841b-3722-4f05-aebe-b693f0d3fd47" />

# 3. 🚀 Instalación y Configuración de Grafana
En esta fase se despliega Grafana, la plataforma de visualización que unificará las métricas de InfluxDB y Prometheus en dashboards interactivos.

## 3.1 Preparación del Sistema
Se instalan las dependencias necesarias para gestionar los repositorios de software de forma segura.

<img width="1155" height="256" alt="image" src="https://github.com/user-attachments/assets/f84fcf4a-b23d-4ba4-bcbe-85897b1dab7a" />

## 3.2 Agregar el Repositorio de Grafana
A continuación, se importa la clave GPG de Grafana y se agrega su repositorio oficial al sistema. Este método utiliza signed-by para mayor seguridad, que es la práctica recomendada actualmente.

<img width="867" height="132" alt="image" src="https://github.com/user-attachments/assets/4492c78f-a674-4292-b3cf-33a0bfba186f" />

## 3.3 Instalar Grafana
Con el repositorio ya configurado, se actualiza la lista de paquetes una vez más para incluir los de Grafana y se procede con la instalación.

<img width="966" height="305" alt="image" src="https://github.com/user-attachments/assets/a7a89170-0d6c-473c-8975-867f57ccfedd" />

## 3.4 Iniciar y Verificar el Servicio
El siguiente paso es iniciar el servicio de Grafana y habilitarlo para que se ejecute automáticamente cada vez que el servidor se reinicie.

<img width="1224" height="106" alt="image" src="https://github.com/user-attachments/assets/1aefb01f-c58d-4998-8be2-df2fab969f31" />
<img width="898" height="190" alt="image" src="https://github.com/user-attachments/assets/ac766165-dd32-46a1-8979-40e7121d4214" />

Se debe observar un estado de active (running) en color verde, lo que confirma que Grafana está funcionando correctamente.

# 3.5 Acceso a la Interfaz Web
Finalmente, se accede a la interfaz de Grafana a través de un navegador.

- URL: http://<IP_PUBLICA_EC2>:3000
- Usuario por defecto: admin
- Contraseña por defecto: admin

Al iniciar sesión por primera vez, Grafana solicitará de inmediato el cambio de la contraseña por defecto por una nueva y segura.

<img width="1599" height="701" alt="image" src="https://github.com/user-attachments/assets/7710eb40-8ebd-4da2-a227-a2228e4d15e7" />
<img width="500" height="585" alt="image" src="https://github.com/user-attachments/assets/093dceed-5cb5-4984-a912-c3434f6e8990" />
<img width="1589" height="771" alt="image" src="https://github.com/user-attachments/assets/68e32265-f41f-4d22-89aa-0e1882e2b988" />

## Grafana - Data Sources
<img width="1280" height="408" alt="image" src="https://github.com/user-attachments/assets/e48be4cd-18f4-4c6a-a03b-3806c85013f1" />

---

**Autor**: Jaime Antonio Alvarez Crisostomo  
**Institución**: TECNM / Instituto Tecnológico de Tijuana  
**Materia**: Sistemas Programables  
**Año**: 2025
