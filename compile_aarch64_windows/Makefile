.PHONY: all build run compile-only clean help

all: run

# Construye la imagen de Docker
build:
	@echo Construyendo imagen Docker ARM64...
	@docker-compose build

# Compila y ejecuta (sin reconstruir imagen)
run:
	@echo Compilando y ejecutando codigo.s...
	@docker-compose run --rm arm64-compiler
	@echo ******* Ejecucion completada *******

# Solo compila sin ejecutar
compile-only:
	@echo Solo compilando codigo.s...
	@docker-compose run --rm arm64-compiler /bin/bash -c "aarch64-linux-gnu-as -o codigo.o codigo.s && aarch64-linux-gnu-gcc -static -o codigo codigo.o && echo 'Compilacion exitosa'"

# Limpia archivos generados
clean:
	@echo Limpiando archivos generados...
	-@docker-compose down --rmi local --volumes --remove-orphans 2>nul
	-@del /f codigo.o 2>nul
	-@del /f codigo 2>nul
	@echo ******* Limpieza completada *******
