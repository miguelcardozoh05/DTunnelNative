# 📘 Documentación de la API JavaScript – DTunnel

Esta API te permite interactuar con funciones nativas del sistema **DTunnel** desde un entorno WebView. Todas las funciones están disponibles mediante el objeto `window.Dt*`.  
**Asegúrate de que `window.Dt*` esté disponible antes de llamarlas.**

---

## 🔧 Configuración

### Obtener configuración completa
```js
const configs = window.DtGetConfigs.execute();
```

### Seleccionar una configuración por ID
```js
window.DtSetConfig.execute(1000);
```

### Obtener configuración activa
```js
const current = window.DtGetDefaultConfig.execute();
if (current) console.log(current.name);
```

---

## 🌐 Estado de Red

### IP local
```js
const ip = window.DtGetLocalIP.execute();
```

### Tipo de red actual
```js
const red = window.DtGetNetworkName.execute(); // 'WIFI' o 'MOBILE'
```

### Ping (ms)
```js
const ping = window.DtGetPingResult.execute();
```

### Datos detallados de red
```js
const data = window.DtGetNetworkData.execute();
// { type_name: 'MOBILE', type: 0, extra_info: '', detailed_state: '', reason: '' }
```

---

## 🔒 VPN

### Estado de la VPN
```js
const estado = window.DtGetVpnState.execute();
// 'CONNECTED' | 'DISCONNECTED' | 'CONNECTING' | etc.
```

### Conectar VPN
```js
window.DtExecuteVpnStart.execute();
```

### Desconectar VPN
```js
window.DtExecuteVpnStop.execute();
```

---

## 🧩 Interfaz Nativa

### Abrir diálogo de configuración
```js
window.DtExecuteDialogConfig.execute();
```

### Abrir logs
```js
window.DtShowLoggerDialog.execute();
```

### Abrir menú de herramientas
```js
window.DtShowMenuDialog.execute();
```

---

## 📱 Información del Dispositivo

### Altura de la barra de estado
```js
const hStatus = window.DtGetStatusBarHeight.execute();
```

### Altura de la barra de navegación
```js
const hNav = window.DtGetNavigationBarHeight.execute();
```

### ID del dispositivo
```js
const id = window.DtGetDeviceID.execute();
```

### Versión de la app
```js
const version = window.DtAppVersion.execute();
```

---

## 👤 Usuario y Autenticación

### Obtener / establecer nombre de usuario
```js
window.DtUsername.get();
window.DtUsername.set("miUsuario");
```

### Obtener / establecer contraseña
```js
window.DtPassword.get();
window.DtPassword.set("miClave");
```

### Obtener / establecer UUID (V2Ray)
```js
window.DtUuid.get();
window.DtUuid.set("uuid123");
```

---

## 📄 Logs

### Obtener logs
```js
const logs = window.DtGetLogs.execute();
```

### Limpiar logs
```js
window.DtClearLogs.execute();
```

---

## 🌍 Traducción

### Traducir una etiqueta
```js
const texto = window.DtTranslateText.execute("LBL_START");
```

---

## 🔔 Notificaciones

### Enviar notificación local
```js
window.DtSendNotification.execute("Título", "Mensaje", "URL_Imagen");
```

---

## 🌐 WebView y URLs

### Abrir URL en WebView interna
```js
window.DtStartWebViewActivity.execute("https://ejemplo.com");
```

### Abrir URL en navegador externo
```js
window.DtOpenExternalUrl.execute("https://ejemplo.com");
```

---

## 📶 HotSpot

### Estado del HotSpot
```js
const estado = window.DtGetStatusHotSpotService.execute(); // 'STOPPED' | 'RUNNING'
```

### Iniciar / detener HotSpot
```js
window.DtStartHotSpotService.execute();
window.DtStopHotSpotService.execute();
```

### Bytes descargados / subidos
```js
const down = window.DtGetNetworkDownloadBytes.execute();
const up = window.DtGetNetworkUploadBytes.execute();
```

---

## ✈️ Modo Avión

### Estado del modo avión
```js
const estado = window.DtAirplaneState.execute(); // 'ACTIVE' | 'INACTIVE'
```

### Activar / desactivar
```js
window.DtAirplaneActivate.execute();
window.DtAirplaneDeactivate.execute();
```

---

## ⚙️ Otros

### Versión de configuración local
```js
const version = window.DtGetLocalConfigVersion.execute();
```

### Iniciar actualización de app
```js
window.DtStartAppUpdate.execute();
```

### Verificar usuario
```js
window.DtStartCheckUser.execute();
```

### ¿Es asistente de voz actual?
```js
const esAsistente = window.DtAppIsCurrentAssistant.execute();
```

### Abrir ajustes del asistente de voz
```js
window.DtGoToVoiceInputSettings.execute();
```

---

> **Nota:** Todas estas funciones deben usarse en un entorno donde `window.Dt*` esté correctamente expuesto, normalmente dentro de una WebView en el sistema DTunnel.
