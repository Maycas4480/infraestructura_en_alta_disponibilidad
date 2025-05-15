# Auto Scaling con NGINX en AWS usando CloudFormation

Este proyecto despliega una arquitectura en AWS utilizando CloudFormation que incluye:

- Un **Launch Template** para instancias EC2 con Ubuntu.
- Un **Auto Scaling Group** con mínimo, máximo y capacidad deseada de 2 instancias.
- Un **Application Load Balancer (ALB)** que distribuye tráfico a las instancias.
- Instalación de **NGINX** en las instancias EC2 para servir contenido web.

## 📁 Archivos incluidos

- `template.yaml` – Archivo principal de CloudFormation para desplegar toda la infraestructura.

## 🚀 Cómo usar

### 1. Subir el template a AWS CloudFormation

1. Ve a [CloudFormation en la consola de AWS](https://console.aws.amazon.com/cloudformation).
2. Haz clic en **"Crear pila" → "Con recursos nuevos (estándar)"**.
3. Selecciona **"Subir un archivo de plantilla"**.
4. Carga el archivo `template.yaml`.
5. Continúa con los pasos y crea la pila.

### 2. Espera a que la pila se cree

Esto puede tardar unos minutos. Una vez creada:

- Busca en la **salida (Outputs)** de la pila el **DNS del Load Balancer**.
- Abre ese DNS en tu navegador.

### 3. Verifica el sitio

Deberías ver la página por defecto de NGINX si todo está funcionando correctamente.

---

## 🔧 Requisitos

- Cuenta en AWS.
- Permisos para crear recursos: EC2, Auto Scaling, Load Balancer, VPC, etc.
- Una AMI válida (por ejemplo, Ubuntu 20.04 – `ami-00399ec92321828f5` en us-east-2).

---

## ✅ Verificaciones realizadas

- Las instancias EC2 están en estado "running".
- NGINX está instalado y habilitado.
- El Load Balancer enruta correctamente a las instancias.
- Las instancias están en estado “healthy” dentro del Target Group.

---

## 🧑‍💻 Autor

Este proyecto fue realizado como práctica para la creación de infraestructura automática en AWS usando YAML y CloudFormation.

