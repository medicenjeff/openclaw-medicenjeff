# Registro de interacción con OpenClaw

Este archivo sirve para documentar de forma breve y reproducible las interacciones con OpenClaw. No incluyas tokens, contraseñas, claves privadas, URLs con secretos ni datos personales innecesarios.


## Interaccion inicial con OpenClaw chat

Inicialmente, OpenClaw chat me reconocio a traves de mi token usando mi nombre completo y actualizo mi progreso en el curso.

Al pedirle a OpenClaw chat que me conectara a la API de 4Geeks con mi token, primero solicito aclarar el tipo de conexion necesaria:

> Que tipo de conexion necesitas exactamente?
>
> 1. Usar la API de 4Geeks como modelo LLM (chat/completions) — ya tienes LiteLLM configurado con `llm.4geeks.ai`
> 2. Acceder a otros endpoints de 4Geeks — courses, exercises, projects, etc.
> 3. Algo mas especifico?

Despues pedi ayuda para construir las siguientes skills:

- Autenticar
- Obtener mis proyectos
- Obtener trabajo pendiente
- Obtener resumen de progreso

Tambien quise agregar estas funcionalidades:

- Sugerencias de proyectos en los que debo mejorar
- Notas importantes de cada proyecto

### Redaccion narrativa

Describe brevemente que intentabas conseguir, como interactuaste con OpenClaw, que decisiones tomaste y cual fue el resultado final.

### Creacion de las skills

Inicialmente tuve muchos problemas porque OpenClaw creaba y reconocia un par de skills, pero con otras no lo hacia y decia que no era posible.

Cerré VS Code y lo abri nuevamente. Despues inicie un nuevo chat y OpenClaw reconocio que habia huecos en el archivo, porque en la sesion anterior habiamos creado varias skills que no se habian cargado correctamente.

Automaticamente me pregunto si queria hacer una revision y actualizar todo. Continuamos de esta forma hasta que me confirmo el uso de dos skills: la 1 (Autenticacion) y la 4 (Resumen de progreso). El detalle estaba correcto.

Luego le pedi que aplicara cada skill para asegurarme de que todo estuviera correcto. Efectivamente, fue asi.
