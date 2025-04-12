¡Por supuesto, Adrian! Aquí tienes todo el contenido completo del `README.md` listo para **copiar y pegar directamente** dentro de tu archivo `/codigo/README.md`:

---

```markdown
# Tarea 3 – Procesamiento de Datos con Apache Spark

Este repositorio contiene el desarrollo de la **Tarea 3** del curso **Procesamiento de Datos con Apache Spark**, en la que se implementa una solución completa de análisis de datos en **modo batch y streaming** utilizando **Apache Spark** y **Apache Kafka**.

---

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
- kafka-python
- Virtualización: UTM en macOS (Ubuntu 22.04)
- Herramientas: Spark Web UI, CLI, SSH, SCP

---

## 📄 Descripción de scripts

### `tarea3.py`  
Procesamiento batch de un archivo CSV con datos de la Tasa de Cambio Representativa del Mercado (TRM).

**Operaciones realizadas:**
- Lectura del archivo `.csv` con `SparkSession.read.csv`
- Limpieza de columnas y tipos de datos
- Análisis exploratorio: `describe()`, `select()`, `orderBy()`
- Cálculos estadísticos y visualización por consola

---

### `spark_streaming_consumer.py`  
Procesamiento de datos en tiempo real desde Kafka.

**Operaciones realizadas:**
- Lectura del stream de datos desde el topic `sensor_data`
- Definición de esquema JSON para los mensajes
- Conversión de timestamp y creación de ventanas de agregación
- Cálculo de promedios por sensor y ventana
- Impresión continua de resultados usando `writeStream`

---

## 🧪 Cómo ejecutar

### 🔹 1. Procesamiento batch

```bash
spark-submit tarea3.py
```

### 🔹 2. Streaming desde Kafka

1. Iniciar servicios de Kafka:

```bash
# En terminal 1
$KAFKA_HOME/bin/zookeeper-server-start.sh config/zookeeper.properties &

# En terminal 2
$KAFKA_HOME/bin/kafka-server-start.sh config/server.properties &
```

2. Ejecutar el productor simulado (opcional):
```bash
python3 kafka_producer.py
```

3. Ejecutar el consumidor Spark Streaming:

```bash
spark-submit \
  --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.5.3 \
  spark_streaming_consumer.py
```

4. Abrir la consola de monitoreo:  
👉 http://localhost:4040 (o tu IP local)

---

## 📸 Evidencias del proceso

- Jobs, stages y DAGs visualizados desde Spark UI
- Batches y micro-lotes procesados en tiempo real
- Estadísticas de rendimiento desde “Structured Streaming”
- Consola de resultados por ventana y sensor_id

*(Las capturas están documentadas en el informe y presentación adjunta.)*

---

## 📚 Referencias

- Apache Spark documentation: https://spark.apache.org/docs/latest/
- Kafka documentation: https://kafka.apache.org/documentation/
- UNAD – Contenido del curso virtual
- Owen, S. et al. (2017). *Advanced Analytics with Spark: Patterns for Learning from Data at Scale*. O’Reilly Media.

---

## 👨‍💻 Autor

**Adrian Ramirez**  
Estudiante de Ingeniería de Sistemas – UNAD  
Abril 2025

---

