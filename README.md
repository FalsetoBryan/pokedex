# Creación del Repositorio y Subida del Código Fuente a GitHub

Para gestionar el control de versiones y permitir el despliegue automático hacia Azure, el código fuente de la PokeDex se alojó en un repositorio de GitHub. A continuación, se detallan los pasos realizados.

## Paso 1: Creación del Repositorio en GitHub

1.  Se ingresó a la cuenta de GitHub y se creó un nuevo repositorio público.
    
2.  El repositorio fue nombrado exactamente **`pokedex`** para cumplir con los lineamientos del proyecto.
    
3.  Se dejó el repositorio completamente vacío (sin archivo README ni .gitignore inicial) para evitar conflictos al vincularlo con el código local.
    

> **Captura de la creación del repositorio vacío en GitHub** 
> 
> [Creacion  de repositorio](https://drive.google.com/drive/folders/1RM2CivftWTa4jIDuoEcdIZ8flP8ojjG-?usp=drive_link)

## Paso 2: Preparación del Entorno Local

1.  Se descargó y extrajo el código fuente original de la aplicación Angular (PokeDex) en una carpeta local (`C:\Users\RYZEN\Downloads\pokedex-angular`).
    
2.  Se abrió la consola de comandos (CMD/Terminal) y se navegó hasta la ruta del proyecto.
    
3.  Se configuraron las credenciales de Git globales para enlazar los cambios a la cuenta de GitHub correspondiente, solucionando el error de "Author identity unknown":
    
  CMD
    
    ```
    git config --global user.email "bryanmorelos98@gmail.com"
    git config --global user.name "FalsetoBryan"
    
    ```
  
> Captura de la terminal con la configuración inicial

>[captura autorizacion](https://drive.google.com/file/d/1NKG3d0-FgGefNztYLDfwe-pmGuxL55OO/view?usp=drive_link)


## Paso 3: Inicialización y Subida del Código

Una vez dentro de la carpeta del proyecto, se ejecutaron los comandos secuenciales de Git para inicializar el repositorio local, preparar los archivos y subirlos a la nube:

1.  **`git init`**: Inicializó el control de versiones de Git en la carpeta local.
    
2.  **`git add .`**: Agregó todos los archivos extraídos del proyecto al área de preparación (staging).

>[git init y git add . captura](https://drive.google.com/file/d/1DXBWF3wk6qXLlwgf7mlqWIbOjXXIVsrG/view?usp=sharing)
    
4.  **`git commit -m "Primer commit: subiendo código fuente PokeDex"`**: Creó el primer punto de guardado en el historial con un mensaje descriptivo.
> [primer commit](https://drive.google.com/file/d/1DXBWF3wk6qXLlwgf7mlqWIbOjXXIVsrG/view?usp=drive_link)
    
6.  **`git branch -M main`**: Estableció `main` como la rama principal de trabajo.
    
7.  **`git remote add origin https://github.com/FalsetoBryan/pokedex.git`**: Vinculó la carpeta local con el repositorio vacío alojado en GitHub.
    
8.  **`git push -u origin main`**: Subió finalmente todos los archivos a los servidores de GitHub. (Durante este paso, se completó la autenticación en el navegador mediante el ecosistema de Git).
   >  [captura del paso 6,7 y 8](https://drive.google.com/file/d/1Qq-eSDLN9P9fSTmWUMb5rgnjEY_600E6/view?usp=drive_link)

> Captura de la terminal con los comandos ejecutados y la subida exitosa
> [subida exitosa](https://drive.google.com/file/d/1qUTQ3pWzzUKS963chHPOhNO6jxYMpKE4/view?usp=drive_link)
> 
Al finalizar este proceso, todo el código base de Angular quedó reflejado en la rama `main` del repositorio remoto, dejándolo listo para ser conectado al servicio de Azure Static Web Apps.

>**Captura del repositorio en GitHub con los archivos ya subidos**
[repositorio](https://drive.google.com/file/d/1jphjMlv-fRY3sXOGNQeUHUxCMheSWZTL/view?usp=drive_link)



 # Creación de Cuenta en Microsoft Azure

Para el despliegue de la aplicación PokeDex, se ha seleccionado la plataforma de nube pública **Microsoft Azure**. A continuación, se detalla el proceso paso a paso para la creación de la cuenta y la identificación de la suscripción activa que se utilizará, denominada **"Azure subscription 1"**

## Paso 1: Acceso y Registro en Azure

1.  **Acceso:** Dirígete al portal de Azure en [https://portal.azure.com](https://www.google.com/search?q=https://portal.azure.com/) o a la página de inicio de ofertas gratuitas en [https://azure.microsoft.com/free/](https://azure.microsoft.com/free/).
    
2.  **Inicio de Sesión:** Haz clic en el botón de inicio de sesión. Utiliza una cuenta de Microsoft existente (Outlook, Hotmail) o crea una nueva si aún no la tienes.
    

> Captura de pantalla del portal de Azure solicitando inicio de sesión
>[imagen de paguina de inicio de azure
>](https://drive.google.com/file/d/1bceExTXK5Sx6GdUEss9n2JRdvons4BdD/view?usp=drive_link)
[imagen Login azure](https://drive.google.com/file/d/1M3V9dv335OlfOdJ02Deh51C_pCoS6-hi/view?usp=drive_link)

## Paso 2: Validación de Identidad y Suscripción

1.  **Datos Personales y de Contacto:** Tras iniciar sesión, Azure solicitará completar un perfil con información básica (nombre, dirección, correo electrónico).
    
2.  **Verificación Telefónica:** Deberás verificar tu identidad mediante un código enviado a tu número de celular.
    
3.  **Método de Pago:** Para completar el registro, es necesario ingresar una tarjeta de crédito o débito (incluso para la cuenta gratuita).  **Nota importante:** Esto es solo una medida de seguridad y no se realizarán cobros sin tu consentimiento expreso al actualizar a un plan de pago superior.
    

> Captura de pantalla de la sección de verificación de identidad
> [envió de peticion](https://drive.google.com/file/d/1uc7Wh3FwU3WZCQmk8csGsn79OTismzCE/view?usp=drive_link)

>[comprobar por mensaje](https://drive.google.com/file/d/1w6fpdg3nWHbDUqab7DzAxU4l_LSTD-5V/view?usp=drive_link)

>en este caso no me pide método de pago porque la cuenta ya estaba creada con anterioridad
## Paso 3: Confirmación y Acceso al Portal

1.  Una vez completados los pasos de validación y aceptados los términos del acuerdo de suscripción, tu cuenta será creada.
    
2.  Serás redirigido automáticamente al **Portal de Azure** principal (`portal.azure.com`).
    

> [Portal  Azure](https://drive.google.com/file/d/19DXLZvyeakrvK3-wr89CvQT2UxndFC_O/view?usp=drive_link)

## Paso 4: Identificación de la Suscripción Activa ("Azure subscription 1")

1.  Para asegurar que el despliegue se realice en el entorno correcto, es fundamental verificar la suscripción asignada.
    
2.  En la barra de búsqueda superior del Portal de Azure, escribe **"Suscripciones"** y haz clic en el primer resultado (icono de llave).
    
3.  Se mostrará una lista de suscripciones activas. Deberás confirmar que aparece listada y seleccionada la suscripción denominada **"Azure subscription 1"**. Esta será la cuenta sobre la cual se crearán y facturarán (si superas los límites gratuitos) los recursos de la PokeDex.
    

> [suscripcion](https://drive.google.com/file/d/1WodpuzLUxfXr3bUPFNonQ8itzwO0pf85/view?usp=drive_link)
>
> Written with [StackEdit](https://stackedit.io/).
