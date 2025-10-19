FROM ubuntu:22.04

# Instalamos las herramientas necesarias para cross-compilation y emulación
RUN apt-get update && apt-get install -y \
    binutils-aarch64-linux-gnu \
    gcc-aarch64-linux-gnu \
    qemu-user \
    make \
    && rm -rf /var/lib/apt/lists/*

# Creamos un directorio de trabajo
WORKDIR /app

# Copiamos los archivos
COPY . .

# El contenedor ejecutará el comando que le pasemos
CMD ["/bin/bash"]
