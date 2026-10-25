# Despliegue de la Aplicación PokeDex en Azure

Este documento detalla el paso a paso del despliegue del código fuente de la aplicación Angular "PokeDex" hacia la nube pública de Microsoft Azure utilizando el servicio **Azure Static Web Apps**.

## 1. Configuración de Seguridad Previa

Antes de desplegar, se implementaron las directivas de seguridad para cumplir con los estándares de calificación A+. Se creó el archivo `staticwebapp.config.json` en la raíz del repositorio de GitHub con la configuración de encabezados HTTP (CSP, HSTS, X-Frame-Options, X-XSS-Protection, Referrer-Policy).

> **Captura del archivo staticwebapp.config.json en GitHub**[staticwebapp.config.json](https://drive.google.com/file/d/10UnZxc8XXPXqK3HQv06sby9vJbUxHGx2/view?usp=drive_link) 

## 2. Creación del Recurso en Azure

1.  Desde el Portal de Azure, bajo la suscripción "Azure subscription 1", se buscó el servicio **Static Web Apps**.
    
2.  Se configuraron los detalles básicos:
    
    -   **Grupo de recursos:** pokedex-rg
        
    -   **Plan de hospedaje:** Gratuito (Free)
        
3.  Se vinculó la cuenta de GitHub autorizando el acceso al repositorio `pokedex` en la rama `main`.
    
> Captura de la configuración en Azure  
> 
> [creacion de recursos Azure](https://drive.google.com/drive/folders/1Nyn_aNA5eGpaY8p6RnLz97cuaKRbSPOR?usp=drive_link)

## 3. Detalles de Compilación (Build Details)

Al ser una aplicación basada en Angular, se configuraron los parámetros de construcción automatizada (CI/CD) de GitHub Actions:

-   **Framework:** Angular
    
-   **Ubicación de la aplicación:**  `/`
    
-   **Directorio de salida (Output location):**  `dist/pokedex`
    

> Captura de pantalla de la implementación exitosa en Azure

>[detalles de compilación](https://drive.google.com/file/d/1vO8gEOMAoGXFPmc5IWD1xEvnZ_5y_zY8/view?usp=drive_link)

## 4. Resultado del Despliegue y Pruebas de Seguridad

Una vez finalizada la acción de compilación en GitHub, la aplicación quedó expuesta públicamente a través del dominio proporcionado por Azure.

> Captura de la PokeDex funcionando en el navegador
> 
> [captura de pokedex navegador](https://drive.google.com/file/d/127hA7qoP2T28VcEe5Uf-Q580cQRZTtrC/view?usp=drive_link)

Para verificar la eficacia de los encabezados HTTP implementados en el paso 1, se sometió la URL pública a un escaneo en **securityheaders.com**, logrando la calificación máxima de seguridad.

> Captura del escaneo en SecurityHeaders con calificación 
> [captura de escaneo de seguridad](https://drive.google.com/file/d/1WVYrgJjoGiGpakuHquG_Abp7oQVe5k8I/view?usp=drive_link)

> Written with [StackEdit](https://stackedit.io/).
