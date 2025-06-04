# Progressbar

Dependency for creating progressbars in QB-Core.

Previuw

https://streamable.com/ietpkn



# Usage

## QB-Core Functions

### Client

- QBCore.Functions.Progressbar(**name**: string, **label**: string, **duration**: number, **useWhileDead**: boolean, **canCancel**: boolean, **disableControls**: table, **animation**: table, **prop**: table, **propTwo**: table, **onFinish**: function, **onCancel**: function)
  > Create a new progressbar from the built in qb-core functions.<br>
  > **Example:**
  > ```lua
  >QBCore.Functions.Progressbar("random_task", "Doing something", 5000, false, true, {
  >    disableMovement = false,
  >    disableCarMovement = false,
  >    disableMouse = false,
  >    disableCombat = true,
  >}, {
  >    animDict = "mp_suicide",
  >    anim = "pill",
  >    flags = 49,
  >}, {}, {}, function()
  >    -- Done
  >end, function()
  >    -- Cancel
  >end)
  > ```

## Exports

### Client

- Progress(**data**: string, **handler**: function)
  > Creates a new progress bar directly from the export, always use the built in qb-core function if possible.<br>
  > **Example:**
  > ```lua
  >exports['progressbar']:Progress({
  >    name = "random_task",
  >    duration = 5000,
  >    label = "Doing something",
  >    useWhileDead = false,
  >    canCancel = true,
  >    controlDisables = {
  >        disableMovement = false,
  >        disableCarMovement = false,
  >        disableMouse = false,
  >        disableCombat = true,
  >    },
  >    animation = {
  >        animDict = "mp_suicide",
  >        anim = "pill",
  >        flags = 49,
  >    },
  >    prop = {},
  >    propTwo = {}
  >}, function(cancelled)
  >    if not cancelled then
  >        -- finished
  >    else
  >        -- cancelled
  >    end
  >end)
  > ```
  > **Props Example:**
  > ```lua
  >exports['progressbar']:Progress({
  >    name = "random_task",
  >    duration = 5000,
  >    label = "Doing something",
  >    useWhileDead = false,
  >    canCancel = true,
  >    controlDisables = {
  >        disableMovement = false,
  >        disableCarMovement = false,
  >        disableMouse = false,
  >        disableCombat = true,
  >    },
  >    animation = {
  >        animDict = "missheistdockssetup1clipboard@base",
  >        anim = "pill",
  >        flags = 49,
  >    },
  >    prop = {
  >      model = 'prop_notepad_01',
  >      bone = 18905,
  >      coords = vec3(0.1, 0.02, 0.05),
  >      rotation = vec3(10.0, 0.0, 0.0),
  >    },
  >    propTwo = {
  >      model = 'prop_pencil_01',
  >      bone = 58866,
  >      coords = vec3(0.11, -0.02, 0.001),
  >      rotation = vec3(-120.0, 0.0, 0.0),
  >    }
  >}, function(cancelled)
  >    if not cancelled then
  >        -- finished
  >    else
  >        -- cancelled
  >    end
  >end)
  > ```
    - isDoingSomething()
        > Devuelve un booleano (true/false) dependiendo de si hay una barra de progreso activa.<br>
        > **Ejemplo:**
        > ```lua
        > local ocupado = exports["progressbar"]:isDoingSomething()
        > ```
    
    - ProgressWithStartEvent(**data**: table, **start**: function, **finish**: function)
        > Funciona como una barra de progreso normal, el parámetro data debe ser igual al que se pasa en el export `Progress` de arriba.<br>
        > La función start se ejecuta al iniciar la barra de progreso.<br>
        > El manejador finish es igual al parámetro `handler` en el export `Progress` de arriba.
    
    - ProgressWithTickEvent(**data**: table, **tick**: function, **finish**: function)
        > Funciona como una barra de progreso normal, el parámetro data debe ser igual al que se pasa en el export `Progress` de arriba.<br>
        > La función tick se ejecuta cada frame mientras la barra de progreso está activa.<br>
        > El manejador finish es igual al parámetro `handler` en el export `Progress` de arriba.
    
    - ProgressWithTickEvent(**data**: table, **start**: function, **tick**: function, **finish**: function)
        > Funciona como una barra de progreso normal, el parámetro data debe ser igual al que se pasa en el export `Progress` de arriba.<br>
        > La función start se ejecuta al iniciar la barra de progreso.<br>
        > La función tick se ejecuta cada frame mientras la barra de progreso está activa.<br>
        > El manejador finish es igual al parámetro `handler` en el export `Progress` de arriba.



**Este scirpt esta echo para QBCore no para ESX**
