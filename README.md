# ExamenArqDePC_SarahJulio# Examen Final - Arquitectura de Computadores

## 1. Objetivo del Proyecto
El objetivo principal es diseñar, estructurar y desplegar un servidor web automatizado en una instancia EC2 dentro de AWS mediante flujos de Integración y Despliegue Continuo (CI/CD).

## 2. Tecnologías Utilizadas
* **AWS CloudFormation:** Para la Infraestructura como Código (IaC).
* **GitHub Actions:** Para la automatización del despliegue (CI/CD).
* **Git / Git Flow:** Para el control de versiones estructurado.
* **Apache (HTTPD):** Servidor web para alojar el sitio interactivo (HTML/CSS/JS).

## 3. Funcionalidad de Deploy
El archivo `deploy.yml` valida de forma automática el template de CloudFormation y realiza el aprovisionamiento de la instancia EC2 y sus grupos de seguridad cada vez que se genera un cambio confirmado en la rama principal.

## 4. Funcionalidad de Destroy
El archivo `destroy.yml` se ejecuta de forma manual mediante `workflow_dispatch`, eliminando el Stack completo de CloudFormation y asegurando el borrado limpio de todos los recursos para evitar costos residuales.

## 5. Objetivo del Template EC2 creado
El archivo `ec2.yaml` define de manera declarativa una instancia `t2.micro` y un Security Group con el puerto 80 abierto. Además, automatiza la instalación del servidor Apache y monta la solución web interactiva del estudiante.