# pdpark-consulta

Página para consultar en vivo los ingresos de un estacionamiento con PD Park (`consulta.html`).

## Cómo se usa
1. En PD Park › Ajustes › Respaldo en la nube: conecta la cuenta del estacionamiento y activa
   **"Enviar estadísticas en vivo a la página de consulta"**.
2. Toca **"Compartir la página de consulta"** y manda el enlace (WhatsApp o correo).
3. Quien lo abra solo escribe **su correo y contraseña** y ve **únicamente los datos de esa cuenta**.

El enlace tiene la forma `consulta.html#u=<proyecto>&k=<anon key>&d=<teléfono>`. Solo lleva la dirección del
proyecto y la clave pública (anon key), que es pública por diseño: los datos los protege la seguridad por fila de
Supabase (`supabase/configuracion.sql` del repositorio de la app). La página guarda esos datos en el navegador y
los quita de la barra de direcciones.

Opcional: en `consulta.html` se pueden poner `DEF_URL` y `DEF_KEY` para que la página ya traiga el proyecto
aunque se abra sin enlace.

## Varios estacionamientos en un solo proyecto de Supabase
- Crea una cuenta por estacionamiento en Supabase › Authentication › Users › Add user (con "Auto Confirm User").
- Desactiva el registro libre: Authentication › Sign In / Providers › "Allow new users to sign up".
- Cada cuenta solo puede ver y cambiar sus propias filas.
