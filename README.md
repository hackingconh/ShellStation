# ShellStation
Hackeando un ordenador con mando de PS5

# Introducción
Buenas hackers hoy vengo a compartiros como hice este pequeño proyecto que lo publique en mi instagram. La verdad que me gusta crear movidas tan locas como esta, el arte del hacking es camuflar tus armas de una forma que sea efectiva. 

# ⚠ Aviso importante ⚠ 
Todo lo mostrado es con fines educativos para demostrar que hay que proteger nuestras ranuras USB, no me hago responsable del mal uso. 
Este método solo funciona si el autorun está activado, en tu caso si no esta activado puedes usar un Robber ducky o crea uno tu directamente.

# Materiales 
- Mando de PS4 o en mi caso PS5
  
![image](https://github.com/user-attachments/assets/e348eaee-318b-4377-901b-48893bf7e4cc)


- Cableado de 4 hilos:
  
![image](https://github.com/user-attachments/assets/47210e91-c28b-44d9-bc35-11e8571e1b57)
  
   - Rojo (🔴) → VCC (+5V) → Es el cable de alimentación positiva.
   - Negro (⚫) → GND (Tierra) → Es el cable de tierra o negativo.
   - Blanco (⚪) → D- (Datos -) → Es uno de los cables de datos.
   - Verde (🟢) → D+ (Datos +) → Es el otro cable de datos.
     
- USB
  
![image](https://github.com/user-attachments/assets/25f3957b-ff72-40b8-a195-abe8fdd431f8)

- Toma de USB Hembra

![image](https://github.com/user-attachments/assets/c3d4e377-f794-4f23-8a97-567f73e9cd38)

# Creación del USB escondido 

1. Primero lo que tenemos que hacer es empalmar el cableado macho a el cable hembra ya que en mi caso no disponia de un calbe macho y hembra si no hembra y tipo B :(

![image](https://github.com/user-attachments/assets/659c7efb-8473-4dcb-a9f0-d22f8fecaa32)

2. Una vez emplamados, abrirmos el mando lo apegamos al mando (con silicona, pegamento fuerte o modo gitamo "en mi caso" con cinta)

![image](https://github.com/user-attachments/assets/6ef44604-2d1c-422f-ab37-cedf5a3980d2)

3. Ahora preparamos el USB para crear el autorun.
   - Pimero formatea el usb
   - Crea un archivo llamado autorun.inf en la raiz del USB

![image](https://github.com/user-attachments/assets/29d216a5-c32e-4d2b-ae8a-8a2a353eb341)

4. Crea el script de ejecución automática
  - Como autorun.inf no ejecuta scripts directamente en versiones modernas, usamos un archivo .bat para llamar a PowerShell.
  - En la raíz del USB, crea un archivo llamado launcher.bat y añade:

![image](https://github.com/user-attachments/assets/b9f181bd-1407-4273-831c-3fe27ee6009c)

5. Crea la reverse shell en powershell (En mi caso cree una tool para crearla automaticámente) | NO voy a enseñar como se hace, te lo dejo como tarea para qque aprendas :)
6. Ofuscar la Reverse Shell con Invoke-Obfuscation
  - git clone https://github.com/danielbohannon/Invoke-Obfuscation.git
  - cd Invoke-Obfuscation
  - Import-Module .\Invoke-Obfuscation.ps1
  - Invoke-Obfuscation
1️⃣ En el menú de Invoke-Obfuscation, selecciona
  - STRING
2️⃣ Introduce la reverse shell y aplica varias capas de ofuscación:
  - TOKEN
  - ENCODING
  - LAUNCHER
3️⃣ Copia el código y reemplázalo en usb_payload.ps1.
7. Agregar Bypass de AMSI para Evitar Detección
  - Agrega esto al inicio de usb_payload.ps1
    
![image](https://github.com/user-attachments/assets/921f366b-5d84-41d2-b50e-7f8b8ff1e909)

# Resultado final 

![image](https://github.com/user-attachments/assets/54b8f870-6382-4593-9bc2-e88b87a84165)

![image](https://github.com/user-attachments/assets/a7adb38c-961a-4736-8025-15b2beda96e1)






