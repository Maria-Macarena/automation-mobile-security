# Casos de Prueba Manuales - Transferencias Bancarias

## CP-001 - Transferencia exitosa

- Funcionalidad**: Transferencias entre cuentas
- Precondición: Usuario logueado con saldo suficiente
- Datos de entrada:
    - CBU destino: 2220000111222333445566
    - Monto: $5000
    - Motivo: "Alquiler"
- Pasos:
    1. Ir a "Transferencias"
    2. Completar los datos
    3. Confirmar
- Resultado esperado:
    - Transferencia confirmada
    - Nuevo saldo reflejado


---


## CP-002 - Rechazo por saldo insuficiente

- Objetivo: Validar que el sistema no permita transferencias sin saldo suficiente.
- Precondición: Usuario autenticado con saldo insuficiente.
- Pasos:
    1. Ingresar a Transferencias.
    2. Completar con monto mayor al disponible.
    3. Confirmar operación.
- Resultado esperado: Mensaje de error por saldo insuficiente.


---


## CP-003 - CBU inválido

- Objetivo: Verificar que el sistema detecte CBU inválido.
- Precondición: Usuario autenticado.
- Pasos:
    1. Ingresar a Transferencias.
    2. Ingresar un CBU de menos de 22 dígitos.
    3. Ingresar un monto válido.
    4. Confirmar.
- Resultado esperado: Se muestra error de validación para el campo CBU.


---


## CP-004 - Visualización del historial de transferencias

- Funcionalidad**: Historial de Transferencias
- Precondición: Usuario ha realizado al menos una transferencia
- Pasos:
    1. Iniciar sesión
    2. Ir a “Transferencias” > “Historial”
- Resultado esperado:
    - Se muestra lista de operaciones con fecha, hora, monto, destino
    - Debe coincidir con la operación anterior


---


## CP-005 - Transferencia con monto mínimo permitido

- Funcionalidad: Transferencias
- Precondición: Usuario autenticado
- Datos de entrada:
    - Cuenta origen: ****1234
    - Cuenta destino: ****5678
    - Monto: $100 (mínimo permitido)
- Pasos:
    1. Iniciar sesión
    2. Ingresar a “Transferencias”
    3. Seleccionar cuentas y monto mínimo
    4. Confirmar
- Resultado esperado:
    - Transferencia procesada correctamente
    - Se refleja el nuevo saldo
    - Se genera número de operación


---


## CP-006 - Transferencia con monto máximo permitido


- Funcionalidad: Transferencias
- Precondición: Usuario autenticado con saldo suficiente
- Datos de entrada:
    - Monto: $500.000 (máximo diario permitido)
- Pasos:
    1. Ingresar al módulo de transferencias
    2. Completar datos y monto máximo
    3. Confirmar operación
- Resultado esperado:
    - Transferencia aceptada
    - Mensaje: “Transferencia realizada con éxito”
    - Validación de límites diarios


---


## CP-007 - Transferencia sin completar campos obligatorios


- Funcionalidad: Transferencias
- Precondición: Usuario autenticado
- Pasos:
    1. Ir a “Transferencias”
    2. No completar campos (cuenta, monto, etc.)
    3. Intentar confirmar
- Resultado esperado:
    - Mensaje de error en cada campo vacío
    - Botón “Confirmar” deshabilitado o bloqueado
    - Validación UI correcta


---


## CP-008 - Desconexión en medio de la transferencia


- Funcionalidad**: Transferencias
- Precondición: Usuario autenticado e iniciando una transferencia
- Pasos:
    1. Iniciar transferencia
    2. Durante la confirmación, simular pérdida de conexión o cerrar sesión
- Resultado esperado:
    - Transferencia no procesada
    - Se requiere nuevo inicio de sesión
    - Historial no muestra operación fallida


---


## CP-009 - Validación del tiempo de sesión inactiva


- Funcionalidad: Seguridad / Sesión
- Precondición: Usuario autenticado
- Pasos:
    1. Iniciar sesión en la app
    2. No realizar ninguna acción por 10 minutos (o el tiempo configurado de timeout)
    3. Intentar realizar una transferencia
- Resultado esperado:
    - Redirección automática al login
    - Mensaje: “Sesión expirada por inactividad”
    - No se ejecuta ninguna operación


---


## CP-010 - Transferencia con CBU/CVU o alias inexistente


### 

- Funcionalidad: Transferencias
- Precondición: Usuario autenticado
- Datos de entrada:
    - Cuenta origen: ****1234
    - Cuenta destino: alias mal escrito o CBU inexistente (ej.: `pepito..banco` o `0123456789999999999999`)
    - Monto: $5.000
- Pasos:
    1. Iniciar sesión en la aplicación
    2. Ingresar al módulo de transferencias
    3. Completar los campos solicitados con un alias o CBU/CVU inválido
    4. Intentar confirmar la operación
- Resultado esperado:
    - Aparece un mensaje de error: “El alias o CBU ingresado no es válido”
    - La transferencia **no se procesa**
    - El botón "Confirmar" queda deshabilitado o aparece en rojo
    - El usuario puede corregir el dato sin reiniciar el formulario






