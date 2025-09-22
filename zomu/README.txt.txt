1️⃣ Descripción del Proyecto


Este paquete contiene:


- Proyecto completo de Android Studio para la app ZOMU
- AAB de versión release firmado listo para subir a Google Play
- Archivo de keystore y credenciales para firmar futuras actualizaciones

---

2️⃣ Estructura de Carpetas

	zomu/
	│
	├── source_code/           # Proyecto completo de Android Studio
	│
	├── signing_key/
	│   ├── zomu-release-key.jks          # Archivo de keystore
	│   └── keystore_credentials.txt      # Contraseñas y alias
	│
	├── release_aab/
	│   └── app-release.aab                # Bundle listo para Play Store
	│
	└── README.txt                         # Este archivo


---

3️⃣ Información del Keystore (CRÍTICO)


El keystore es necesario para firmar las actualizaciones de la app.
No pierdas este archivo ni las credenciales.
Si se pierde, no será posible actualizar la app en Google Play.

Archivo keystore: signing_key/zomu-release-key.jks
Contraseña del keystore: ********
Alias de la clave: ********
Contraseña de la clave: ********

(Las contraseñas están en signing_key/keystore_credentials.txt — guárdalo en un lugar seguro.)


---

4️⃣ Cómo Abrir el Proyecto

1. Instalar Android Studio.
2. En Android Studio, ir a Archivo → Abrir.
3. Seleccionar la carpeta source_code/.
4. Esperar a que finalice la sincronización de Gradle.

---

5️⃣ Cómo Generar un AAB de Release Firmado

1. En Android Studio, ir a:

	Build → Generate Signed Bundle / APK…



2. Seleccionar Android App Bundle → Next.
3. En Key store path, seleccionar:

	signing_key/zomu-release-key.jks



4. Ingresar:
	- Contraseña del keystore
	- Alias de la clave
	- Contraseña de la clave
5. Seleccionar el tipo de compilación release.
6. Hacer clic en Finish.
7. El .aab firmado se generará en:

	app/build/outputs/bundle/release/app-release.aab




---

6️⃣ Cómo Subir a Google Play

1. Ir a Google Play Console.
2. Seleccionar la app ZOMU (o crear una nueva ficha si aún no está publicada).
3. Ir a Producción (o Pruebas internas) → Crear nueva versión.
4. Subir el archivo app-release.aab.
5. Completar las notas de la versión y enviar para revisión.

---

7️⃣ Notas Importantes

- Siempre usar el mismo keystore para todas las actualizaciones futuras.
- Guardar el archivo keystore y las credenciales en un lugar seguro y con copia de respaldo.
- Si cambias el nombre del paquete en build.gradle, Google Play lo tratará como una nueva app.

---

8️⃣ Soporte


Si tienes problemas al compilar:


- Asegúrate de que la sincronización de Gradle finalice sin errores.
- Verifica que la ruta del keystore en el diálogo de firmado sea correcta.
- Comprueba que las contraseñas coincidan con las de keystore_credentials.txt.