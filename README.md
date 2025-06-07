# 🔍 Comparativa de Tráfico Telnet vs SSH con Wireshark – Cisco CyberOps

Este repositorio documenta el laboratorio del módulo **23.4.8 del curso Cisco CyberOps Associate**, enfocado en comparar sesiones Telnet y SSH mediante captura de tráfico con **Wireshark**. Se analizan los riesgos asociados a protocolos no cifrados frente a alternativas seguras para conexiones remotas.

---

## 🎯 Objetivos del laboratorio

- Capturar y analizar tráfico web cifrado (HTTPS).
- Ejecutar una sesión **Telnet** local y observar tráfico en texto plano.
- Ejecutar una sesión **SSH** local y verificar el cifrado de datos.
- Comparar ambos protocolos en términos de exposición de credenciales y seguridad.

---

## 🧰 Requisitos del entorno

- Máquina virtual: `CSE-LABVM` en **VirtualBox**
- Usuario: `cisco` / Contraseña: `password`
- Herramientas:
  - Terminal de Linux
  - **Wireshark** (ejecutado como superusuario)

---

## 🧪 Estructura del laboratorio

### 🔹 Parte 1: Captura de tráfico web

- Acceso a `www.cisco.com` desde Firefox.
- Tráfico TLS capturado en Wireshark → validación de HTTPS activo.

### 🔹 Parte 2: Sesión Telnet (sin cifrado)

- Comando: `telnet localhost`
- Inicio de sesión visible: `labvm login:`, `cisco`, `password`
- Credenciales observables en texto claro dentro del `.pcapng`.

### 🔹 Parte 3: Sesión SSH (cifrada)

- Comando: `ssh localhost`
- Tráfico capturado completamente cifrado → imposibilidad de visualizar datos.

---

## 📊 Comparativa de resultados

| Elemento                  | Telnet (sin cifrado) | SSH (cifrado)           |
|---------------------------|----------------------|--------------------------|
| Visibilidad de login      | ✅ Sí (texto claro)  | ❌ No                    |
| Visibilidad de contraseña | ✅ Sí (letra por letra) | ❌ No                 |
| Seguridad en transmisión  | ❌ Ninguna            | ✅ Alta                  |
| Uso recomendado en producción | ❌ No            | ✅ Sí                    |

---

## 📁 Archivos del proyecto

```
telnet-vs-ssh-wireshark/
├── README.md
├── LICENSE
├── capturas/
│   ├── telnet_session.png
│   ├── ssh_session.png
│   └── comparativa.png
├── sesiones/
│   ├── telnet_session.pcapng
│   └── ssh_session.pcapng
```

---

## 🛡️ Conclusiones

Este laboratorio evidencia de forma visual y técnica la **necesidad de reemplazar Telnet por SSH** en entornos reales. El uso de Telnet representa un riesgo crítico para la confidencialidad de los datos, mientras que SSH proporciona protección efectiva frente a interceptaciones.

---

## 👨‍💻 Autor

- **Nombre:** Lester Alfonso Dávila Escobedo  
- **Curso:** Cisco CyberOps - Módulo 23.4.8  
- **Fecha:** Junio 2025  
- **Licencia:** MIT  
- **LinkedIn:** [linkedin.com/in/lester-alfonso-davila-escobedo-cpa](https://www.linkedin.com/in/lester-alfonso-davila-escobedo-cpa)
