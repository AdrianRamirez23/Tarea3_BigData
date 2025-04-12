

```markdown
# Tarea 3 – Procesamiento de Datos con Apache Spark

Este repositorio contiene el desarrollo de la **Tarea 3** del curso **Procesamiento de Datos con Apache Spark**, en la que se implementa una solución completa de análisis de datos en **modo batch y streaming** utilizando **Apache Spark** y **Apache Kafka**.

## 📁 Estructura del repositorio

```
/codigo/
  ├── tarea3.py                   # Script para procesamiento batch de datos históricos
  ├── spark_streaming_consumer.py # Script de consumo en tiempo real desde Kafka usando Spark Structured Streaming
  └── README.md                   # Documento actual
```

---

## 🧠 Objetivo general

Implementar una solución distribuida de procesamiento de datos que permita analizar información en batch y en tiempo real, integrando Apache Spark con Apache Kafka.

---

## 🚀 Tecnologías utilizadas

- Apache Spark 3.4.4
- Apache Kafka 3.7.2
- Python 3.10
- Spark Structured Streaming
- Kafka-python
- Virtualización: UTM en macOS (Ubuntu 22.04)
- Herramientas: Spark Web UI, CLI, SSH, SCP

---

## 📄 Descripción de scripts

### `tarea3.py`  
Procesamiento batch de un archivo CSV con datos de la Tasa de Cambio Representativa del Mercado (TRM).  
✔️ Limpieza de datos  
✔️ Visualización de estadísticas  
✔️ Transformaciones básicas con DataFrame API

### `spark_streaming_consumer.py`  
Procesamiento de datos en tiempo real desde Kafka.  
✔️ Consumo desde topic `sensor_data`  
✔️ Lectura de JSON y deserialización  
✔️ Ventanas de agregación por sensor  
✔️ Visualización por consola con `writeStream`

---

## 🧪 Cómo ejecutar

### 🔹 Procesamiento batch

```bash
spark-submit tarea3.py
```

### 🔹 Streaming desde Kafka

1. Iniciar Zookeeper y Kafka Broker:
```bash
$KAFKA_HOME/bin/zookeeper-server-start.sh config/zookeeper.properties &
$KAFKA_HOME/bin/kafka-server-start.sh config/server.properties &
```

2. Ejecutar el consumidor:
```bash
spark-submit \
  --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.5.3 \
  spark_streaming_consumer.py
```

3. Visualizar en: [http://localhost:4040](http://localhost:4040)

---

## 📸 Evidencias del proceso

Capturas disponibles en el informe y presentación:

- Jobs y Stages ejecutados
- Panel de ejecución en Structured Streaming
- Consola de resultados por ventana temporal
- Métricas en tiempo real

---

## 📚 Referencias

Consulta las referencias formales en el [informe académico PDF](../Informe_Tarea3_Spark.pdf).

---

## 👨‍💻 Autor

**Adrian Ramirez** – Estudiante de Ingeniería de Sistemas  
UNAD – Abril 2025

---


