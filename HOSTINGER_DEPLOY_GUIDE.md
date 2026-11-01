# Guía de Despliegue CI/CD en Hostinger: publicaciones.privacidad.ec

Esta guía explica la configuración para conectar el repositorio de GitHub con el Shared Hosting de Hostinger y publicar automáticamente el blog con Grav CMS bajo el dominio **`publicaciones.privacidad.ec`**.

---

## 1. Configuración del Subdominio en Hostinger (hPanel)

1. Ingresa a tu panel de control de Hostinger (**hPanel**).
2. Dirígete a **Sitios Web** > Selecciona tu cuenta de hosting > **Dominios** > **Subdominios**.
3. En el campo de subdominio:
   - Nombre: `publicaciones`
   - Dominio principal: `privacidad.ec`
   - Carpeta raíz personalizada (Custom folder): Marca la casilla y define la ruta:
     ```
     public_html/publicaciones
     ```
4. Haz clic en **Crear**.
5. Ve a **Seguridad** > **SSL** y asegúrate de que el certificado Let's Encrypt gratuito esté emitido y activo para `publicaciones.privacidad.ec`.

---

## 2. Configuración de PHP en Hostinger

Grav CMS requiere PHP 8.1 o superior (se recomienda **PHP 8.2 o 8.3**):

1. En hPanel, ve a **Avanzado** > **Configuración de PHP**.
2. Selecciona **PHP 8.2** o **PHP 8.3**.
3. En la pestaña **Extensiones de PHP**, verifica que estén activadas:
   - `curl`
   - `gd`
   - `mbstring`
   - `openssl`
   - `xml`
   - `zip`
   - `opcache`
   - `yaml` (si está disponible)

---

## 3. Credenciales FTP para GitHub Actions

1. En hPanel, ve a **Archivos** > **Cuentas FTP**.
2. Puedes usar la cuenta principal o crear una cuenta específica apuntando a `/public_html/publicaciones`:
   - **Host FTP / Servidor:** Suele ser la IP del hosting o `ftp.privacidad.ec`
   - **Usuario FTP:** Tu usuario de Hostinger (ej: `u123456789` o `deployer@privacidad.ec`)
   - **Contraseña FTP:** La clave asignada a la cuenta
   - **Directorio:** `public_html/publicaciones`

---

## 4. Configurar Secrets en GitHub

En tu repositorio de GitHub (ej. `github.com/tu-organizacion/privacidad-blog`):

1. Ve a **Settings** > **Secrets and variables** > **Actions**.
2. Agrega los siguientes **Repository Secrets**:

| Secret | Descripción | Ejemplo |
| :--- | :--- | :--- |
| `HOSTINGER_FTP_SERVER` | Dirección IP o host FTP de Hostinger | `ftp.privacidad.ec` o `185.xxx.xxx.xxx` |
| `HOSTINGER_FTP_USERNAME` | Usuario FTP de Hostinger | `u123456789` |
| `HOSTINGER_FTP_PASSWORD` | Contraseña de la cuenta FTP | `••••••••••••` |
| `HOSTINGER_TARGET_DIR` | Directorio destino en el servidor | `public_html/publicaciones/` |

---

## 5. Primer Commit y Push a GitHub

Para vincular este directorio local con tu repositorio remoto de GitHub:

```bash
# 1. Inicializar git
git init
git branch -M main

# 2. Agregar archivos y hacer primer commit
git add .
git commit -m "feat: setup Grav CMS blog and Hostinger CI/CD pipeline"

# 3. Vincular con tu repositorio remoto de GitHub
git remote add origin https://github.com/<TU_USUARIO_O_ORG>/<TU_REPOSITORIO>.git

# 4. Enviar a GitHub (disparará el workflow de despliegue)
git push -u origin main
```

---

## 6. Primer Acceso al Panel de Administración en Hostinger

Una vez completado el despliegue automático:
1. Abre tu navegador y dirígete a:
   ```
   https://publicaciones.privacidad.ec/admin
   ```
2. Grav te solicitará crear el primer **Usuario Administrador** (nombre de usuario, email y contraseña segura).
3. ¡Listo! Desde allí puedes redactar publicaciones, instalar plugins y gestionar el blog.
