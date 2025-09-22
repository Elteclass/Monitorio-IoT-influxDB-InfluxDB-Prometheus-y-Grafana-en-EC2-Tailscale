<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/af2c21b5-58cf-4233-91d5-11b4c2e6fc0c" />

# ⚙️ 2. Instalación de Prometheus y Node Exporter
Para el monitoreo de la infraestructura de nuestro servidor EC2, se implementó Prometheus junto con Node Exporter. Prometheus se encarga de recolectar y almacenar las métricas como una base de datos de series temporales, mientras que Node Exporter expone las métricas del hardware y del sistema operativo del host.

## 2.1 Instalación
Se optó por el método de instalación a través del gestor de paquetes apt de Ubuntu 20.04, ya que proporciona una configuración inicial robusta y simplifica la gestión del servicio.

- Primero, se actualizaron los repositorios de paquetes del sistema.

<img width="956" height="593" alt="image" src="https://github.com/user-attachments/assets/6006c4eb-cd92-4cc3-8dec-0a971b4fa744" />

- A continuación, se instalaron ambos paquetes con un solo comando.

<img width="800" height="173" alt="image" src="https://github.com/user-attachments/assets/fea2ce9c-e700-4e0f-9fc7-7f037c95d569" />

- Este proceso instala los binarios, crea los archivos de configuración por defecto y configura los servicios systemd para que se ejecuten automáticamente al iniciar el sistema.

## 2.2 Verificación de los Servicios
Una vez finalizada la instalación, se verificó que ambos servicios estuvieran activos y funcionando correctamente utilizando systemctl.

<img width="829" height="207" alt="image" src="https://github.com/user-attachments/assets/9762ba5b-b14a-486c-b21f-cfb1598cf7a5" />
<img width="937" height="190" alt="image" src="https://github.com/user-attachments/assets/35de8496-4ae9-47ee-9725-9cea51f9fccb" />

## 2.3 Configuración y Targets
La instalación a través de apt genera automáticamente un archivo de configuración en /etc/prometheus/prometheus.yml. Este archivo ya viene pre-configurado para que Prometheus se monitoree a sí mismo y para que recolecte las métricas expuestas por Node Exporter en el localhost:9100.

<img width="1586" height="588" alt="image" src="https://github.com/user-attachments/assets/c01cd6f1-3f4a-4a4d-a49c-a0d85a44ed78" />

## 2.4 Acceso a la Interfaz Web y Consulta
Para la prueba final, se accedió a la interfaz web de Prometheus a través de la IP pública de la instancia EC2.

<img width="347" height="34" alt="image" src="https://github.com/user-attachments/assets/0969c32b-9b74-4d19-ad59-a904768f6186" />
<img width="1212" height="492" alt="image" src="https://github.com/user-attachments/assets/e9fa3ffa-4d9d-4fb5-bdac-b871f560c4c0" />

- Dentro de la interfaz, en la sección Status → Targets, se pudo verificar que tanto el endpoint de prometheus como el de node_exporter estaban en estado UP, indicando que la recolección de métricas estaba funcionando.

- Como parte de la actividad, se ejecutó una consulta simple con la métrica up en la pestaña Graph. El resultado mostró un valor de 1 para ambos jobs, confirmando que los servicios están activos y son accesibles para Prometheus.

<img width="1593" height="493" alt="image" src="https://github.com/user-attachments/assets/70a6a567-e8d3-4478-bf33-2ebd88f1956a" />

---

**Autor**: Jaime Antonio Alvarez Crisostomo  
**Institución**: TECNM / Instituto Tecnológico de Tijuana  
**Materia**: Sistemas Programables  
**Año**: 2025
