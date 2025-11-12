#  User CRUD Monitoring – FastAPI + PostgreSQL + Prometheus + Grafana

Este proyecto implementa un sistema de gestión de usuarios (CRUD)utilizando FastAPI como backend, PostgreSQL como base de datos y Prometheus + Grafana para el monitoreo de métricas.  
Toda la aplicación se orquesta mediante Docker Compose, lo que facilita su despliegue y portabilidad.

---

##  Tecnologías utilizadas

- **FastAPI** → Framework web para el backend en Python.  
- **PostgreSQL** → Base de datos relacional.  
- **SQLAlchemy** → ORM para manejar las consultas.  
- **Prometheus** → Recolección y almacenamiento de métricas.  
- **Grafana** → Visualización y monitoreo de métricas.  
- **Docker Compose** → Orquestación de servicios.

###  Clonar el repositorio


git clone https://github.com/JuanJose123488/Gesti-n-de-Usuarios-con-FastAPI-PostgreSQL-Prometheus-y-Grafana.git
cd user-crud-monitori

###  Construir y levantar los contenedores
docker compose up --build

### Endpoints principales

Una vez el servicio esté corriendo, puedes explorar la documentación interactiva de FastAPI:

Aplicación : http://localhost:8000/

Documentación : http://localhost:8000/docs
---

## 📈 Monitoreo de métricas con Prometheus y Grafana

El sistema incluye una integración completa de **monitoreo en tiempo real** gracias a **Prometheus** y **Grafana**.  
Estas herramientas permiten visualizar métricas clave del comportamiento de la aplicación FastAPI.

---

### 🧩 Métricas expuestas por FastAPI

La aplicación expone un endpoint `/metrics` compatible con **Prometheus**, que permite recolectar información sobre:

- Cantidad total de usuarios creados (`user_created_total`)
- Tasa de creación de usuarios
- Usuarios creados en la última hora 

Prometheus se encarga de recolectar periódicamente estos datos definidos en `prometheus/prometheus.yml`.

###  Visualización en Grafana

Grafana consume los datos recolectados por Prometheus y los presenta en paneles dinámicos.  
A continuación se muestra un ejemplo de las métricas visualizadas:

#### **Panel de Monitoreo de Usuarios**

**Descripción de los paneles:**

1. **Usuarios creados :**  
   - Muestra el número total de usuarios registrados en la aplicación.
   - Se actualiza automáticamente a medida que se realizan nuevas inserciones.

2. **Usuarios creados en la última hora :**  
   - Representa el número acumulado de usuarios creados en los últimos 60 minutos.  
   - Útil para observar tendencias recientes de actividad del sistema.

3. **Tasa de creación de usuarios :**  
   - Mide la frecuencia con que se crean nuevos usuarios en el tiempo

### Licencia

Este proyecto se distribuye bajo la licencia MIT, lo que permite su uso, modificación y distribución libre.
