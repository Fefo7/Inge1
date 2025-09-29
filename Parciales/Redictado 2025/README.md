!<img width="770" height="525" alt="image" src="https://github.com/user-attachments/assets/0bb697b2-f70f-418c-9ae3-ec456cbcf11c" />


- **Solicitar un turno**
    
    > **ID: Solicitar un turno**
    > 
    > 
    > **Titulo: Como** paciente **quiero** solicitar un turno **para** ser atendido
    > 
    > **Reglas de negocio:**
    > 
    > - Solo un turno por especialidad por semana
    > - El paciente debe ser mayor de edad
    
    ### **Criterios de aceptación**
    
    **Escenario: Solicitar un turno exitoso**
    
    - **Dado**: que existe una sesión activa, la edad es de “20” años y  la especialidad “Oftalmología” la cual no ha solicito un turno esta semana
    - **Cuando**: se ingrese  la especialidad “Oftalmología”, medico “Federico isla”, día “Lunes 29 a las 19:00” y se presione “Solicitar turno”
    - **Entonces**:  El sistema efectuara el registro del turno, se deshabilitara la posibilidad de pedir otro turno de esa especialidad en esa semana y se informara “Turno solicitado con éxito”
    
    **Escenarios**: **Solicitar un turno sea fallido por no tener una sesión activa**
    
    - Dado: que no existe una sesión activa
    - Cuando: se presione “solicitar turno”
    - Entonces: el sistema informara “debe iniciar sesión previamente” y redireccionara al inicio de sesión.
    
    **Escenario: Solicitar un turno sea fallido es menor de edad**
    
    - **Dado**: que existe una sesión activa, la edad es de “15” años y la especialidad es “Kinesiología” la cual no ha solicito un turno esta semana
    - **Cuando**: se ingrese la especialidad “Kinesiología”, medico “Pablo cabe”, día “Miércoles 1 a las 10:00” y se presione “Solicitar turno”
    - **Entonces**: El sistema informara “No puedes  solicitar un turno siendo menor de edad”
    
    **Escenario: Solicitar un turno sea fallido por misma especialidad en la semana**
    
    - Dado: que existe una sesión activa, la edad es de “20” años y  la especialidad “Oftalmología” la cual ya ha solicito un turno esta semana
    - Cuando: se ingrese especialidad “Oftalmología”, medico “Federico isla”, día “Lunes 3 a las 14:00” y se presione “Solicitar turno”
    - Entonces: El sistema informara “No puedes solicitar un turno en esta semana”
- **Ver turnos**
    
    > **ID: Ver turnos**
    > 
    > 
    > **Titulo: Como medico quiero ingresar a un panel para ver mis turnos activos** 
    > 
    > **Reglas de negocio:**
    > 
    > - Solo fechas del año actual
    
    ### **Criterios de aceptación**
    
    **Escenario: Ver turnos exitoso**
    
    - **Dado**: que se encuentra una sesión activa ,“29/09/2025” la cual pertenece al año actual y existen al menos un turno activo.
    - **Cuando**: se ingresa “29/09/2025” y se presione ”Ver turnos”
    - **Entonces**: el sistema mostrara los turnos activos de esa fecha.
    
    **Escenario: Ver turnos exitoso sin turnos**
    
    - **Dado**: que se encuentra una sesión activa ,  “1/09/2025” la cual pertenece al año actual y no existen turnos activos
    - **Cuando**: se ingresa “1/09/2025” y se presione ”Ver turnos”
    - **Entonces**: el sistema informara “No hay turnos activos para la fecha “1/09/2025””.
    
    **Escenario: Ver turnos fallido por ingresar un año incorrecto**
    
    - **Dado**: que se encuentra una sesión activa,  “1/09/2023” la cual no pertenece al año actual
    - **Cuando**: se ingrese “1/09/2023” y se presione “Ver turnos”
    - **Entonces**: el sistema informara “La fecha no pertenece al año actual”.
    
    **Escenario: Ver turnos fallido por no estar autenticado**
    
    - **Dado**: que no se encuentra una sesión activa
    - **Cuando**: cuando ingrese al panel para ver los turno pendientes y presione “ver turnos”
    - **Entonces**:  el sistema informara “Debe iniciar sesión” y lo redirigirá al inicio de sesión.

## 2. Realice el diagrama completo y los escenarios de los casos de usos relacionados al estudiante. (CU y extensiones o usos).

Se desea modelar un **sistema de préstamo de bicicletas para estudiantes de la Universidad Nacional de La Plata**. Las bicicletas se encuentran disponibles en estaciones distribuidas dentro del campus, y el **préstamo debe gestionarse a través de una aplicación web o móvil.**

Para realizar un **préstamo**, los **estudiantes** deben ingresar su número de **legajo**, seleccionar una **estación de origen** y una **bicicleta disponible**. El sistema verifica si el usuario tiene un **préstamo activo**; si no lo tiene, asigna la **bicicleta seleccionada** y registra la hora de inicio del **préstamo**. Si ya tiene un **préstamo activo**, el sistema le **impide realizar uno nuevo** y muestra un **mensaje informativo**.

Para que un **estudiante** pueda realizar un **préstamo**, debe figurar como **alumno activo** en alguna de las carreras de la **UNLP**. Para verificar esto, el sistema se conecta a un **servidor de la Universidad**, le envía el **legajo** del alumno, el **servidor verifica** si es **alumno activo** de alguna carrera y retorna un resultado.

Cuando finaliza el recorrido, el **estudiante** debe **devolver la bicicleta** en **cualquier estación disponible**. Para la **devolución** el alumno ingresa su **legajo** y la **bicicleta** y el sistema registra la **devolución**.

Los **administradores del sistema**, además de hacer todo lo que puede hacer un alumno, también pueden **consultar el historial de préstamos** de cualquier alumno y **cargar nuevas bicicletas a una estación**.
[Casos de uso](https://github.com/fedeisla/Inge1/blob/main/Parciales/Redictado%202025/Escenarios.png)
<img width="650" height="561" alt="Diagrama" src="https://github.com/user-attachments/assets/bfd07c07-ca47-4d95-aae6-7088dcb48b5a" />



