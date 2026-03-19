# MultiClickButton_DavidLastra

# Thresholds del proyecto

- Long press timer de 0.4s
- Double click timer de 0.3s

# Functionalidades del proyecto

El botón empieza en un Idle state y una vez clicado entra en la funcion OnPointerDown

# OnPointerDown

OnPointerDown chequea si el boton está en estado Idle, lo cambia a estado WaitingForRelease y empieza a hacer la Task para comprobar si el usuario quiere hacer un long press.Si supera el threshold, automáticamente printeará que el usuario esta haciendo un long press y reseteará el estado del botón a Idle.

Si ya había clicado antes, y está en el estado WaitingForDoubleClick, activa el cancelation token del timer del double click y vuelve a chequear si se está haciendo un long press después de un short click. Si eso pasa, printeará en la consola un short click y un long press y resetará a Idle el estado del botón.

Una vez el usuario levanta el clic, entra en la funcion OnPointerUp

# OnPointerUp

OnPointerUp primero activa el cancelation token del timer del long press y chequea si el usuario ya había pulsado antes. Si lo había hecho anteriormente, printeará en la consola que el usuario está haciendo un double click y reseteará el estado del botón a Idle.

Si es la primera vez que el usuario había clicado el botón, el botón cambiará de estado a WaitingForDoubleClick y chequará si detecta algún otro click antes de que se acabe el timer, sino printerá un short click y reseteará el estado del botón a Idle.



