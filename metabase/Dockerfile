FROM eclipse-temurin:21-jre

# Директория для плагинов (стандарт Metabase)
ENV MB_PLUGINS_DIR=/plugins

# Создаём рабочую директорию
WORKDIR /app

# Скачиваем актуальный JAR Metabase (v0.57.2.x на ноябрь 2025)
ADD https://downloads.metabase.com/v0.57.2.x/metabase.jar /app/metabase.jar

# Скачиваем актуальный DuckDB-драйвер (v0.4.0 для Metabase 55+ и DuckDB 1.1.3+)
ADD https://github.com/MotherDuck-Open-Source/metabase_duckdb_driver/releases/download/0.4.0/duckdb.metabase-driver.jar /plugins/

# Создаём директорию plugins, если не существует, и устанавливаем права
RUN mkdir -p /plugins && chmod 644 /plugins/duckdb.metabase-driver.jar

# Порт по умолчанию для Metabase
EXPOSE 3000

# Запуск Metabase
CMD ["java", "-jar", "/app/metabase.jar"]
