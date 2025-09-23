# 📡 Práctica 3: Monitoreo IoT con InfluxDB, Prometheus y Grafana  

Este repositorio documenta el despliegue de un stack completo de monitoreo para un caso de uso de **Internet de las Cosas (IoT)**.  
El proyecto integra:  

- **InfluxDB** → para datos de series temporales.  
- **Prometheus** → para métricas de infraestructura.  
- **Grafana** → para la visualización unificada.  

Todo se despliega en una instancia de **Amazon EC2**, asegurada mediante una **VPN con Tailscale**.  

---

## 🏗️ Arquitectura de la Solución  

La arquitectura implementada consiste en un servidor central en EC2 que aloja todo el stack de observabilidad.  

- Los datos simulados de sensores IoT se inyectan en **InfluxDB**.  
- **Prometheus** recolecta métricas del estado del servidor vía **Node Exporter**.  
- **Grafana** se conecta a ambas fuentes para centralizar la visualización en un dashboard único y seguro.  
- El acceso se restringe mediante la red privada de **Tailscale**, evitando exponer puertos públicos.  

---

## 📂 Estructura del Repositorio  

La documentación se organiza en carpetas para facilitar la lectura y seguimiento de cada etapa:  

---

## 🛠️ Desarrollo de la Práctica (Según Rúbrica)  

### 1. Configuración de Tailscale (20%)  
Se configuró una **VPN con Tailscale** para interconectar de forma segura la instancia EC2 y los dispositivos personales.  
Esto eliminó la necesidad de exponer puertos públicos, aumentando la seguridad.  

📎 Evidencia: *Captura del panel de administración de Tailscale*.  

---

### 2. Instalación de InfluxDB (15%)  
- Instalación desde repositorio oficial.  
- Creación de **organización**, **bucket** y **token** de autenticación.  

📄 [Ver Pasos de Instalación de InfluxDB](./InfluxDB/README.md)  

---

### 3. Instalación de Prometheus + Node Exporter (15%)  
- Servicios configurados con **systemd**.  
- Archivo `prometheus.yml` actualizado para monitoreo de endpoints.  

📄 [Ver Pasos de Instalación de Prometheus](./Prometheus/README.md)  

---

### 4. Instalación de Grafana (15%)  
- Instalación y habilitación del servicio.  
- Configuración de **data sources**: InfluxDB y Prometheus.  

📄 [Ver Pasos de Instalación de Grafana](./Grafana/README.md)  

---

### 5. Simulación de Datos IoT (15%)  
Se desarrolló un script en **Python** que simula un sensor de **temperatura y humedad**, enviando datos a InfluxDB cada 5 segundos.  

🐍 [Ver Script de Simulación](./simulador/simulador.py)  

---

### 6. Dashboard en Grafana (15%)  
Dashboard unificado que integra:  

- **Métricas IoT** desde InfluxDB.  
- **Métricas de sistema** desde Prometheus/Node Exporter.  

📊 Resultado Final: *Captura del dashboard en Grafana*.  

---

### 7. Informe Escrito y Reflexiones (5%)  

**¿Por qué es útil Tailscale en este escenario?**  
Tailscale permite crear una VPN de malla entre dispositivos y el servidor EC2, evitando la exposición de puertos públicos como **3000 (Grafana)** o **9090 (Prometheus)**.  
Esto reduce la superficie de ataque y garantiza acceso seguro únicamente a los dispositivos autorizados en la *Tailnet*.  

**Diferencia entre métricas de IoT e infraestructura:**  

- **Métricas IoT (InfluxDB):** datos de sensores (ej. temperatura, humedad). Responden al *qué* ocurre en el proceso o ambiente.  
- **Métricas de sistema (Prometheus/Node Exporter):** datos del servidor (CPU, memoria, red). Responden al *cómo* funciona la infraestructura que soporta la aplicación.  

---

## 👤 Autor y Agradecimientos  

- **Autor:** Jaime Antonio Alvarez Crisostomo  
- **Institución:** TECNM / Instituto Tecnológico de Tijuana  
- **Materia:** Sistemas Programables  
- **Año:** 2025  

📝 Documento elaborado con la asistencia del modelo de lenguaje **Gemini (pro2.5)** para la redacción y estructuración de la documentación.  

---
