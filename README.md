# Trabajo Práctico Final - Sistemas Operativos y Redes

## Integrantes
- Bruno Berini
- Valentín Máximo Flores

## Descripción
Este proyecto consiste en el diseño de una red que contempla tanto las necesidades actuales como la expansión futura de una empresa.

La red fue planificada considerando:
- Un mínimo de 25 hosts y un máximo de 150 hosts por subred.
- Una previsión a futuro duplicando el máximo estimado de hosts (300 hosts).
- Subneteo de la IP 172.16.0.0/16, utilizando una máscara /23 para adaptarse a los requerimientos.

---

## Configuración de la Red

Se utilizaron **9 bits** para hosts y **23 bits** para red.

- **Máscara de subred:** 255.255.254.0 (/23)
- **Máscara de subred en binario:** 11111111.11111111.11111110.00000000

---

## División de Sedes y Departamentos

### Casa Matriz - Buenos Aires
- Desarrollo Tecnológico → 172.16.2.0/23
- Diseño Gráfico → 172.16.4.0/23
- Contabilidad → 172.16.6.0/23
- Gerencia → 172.16.8.0/23
- Servidor WEB y DNS → 172.16.10.0/23

### Sucursal Córdoba
- Administración → 172.16.12.0/23
- Ventas → 172.16.14.0/23
- Servidor DNS → 172.16.16.0/23

### Sucursal La Rioja
- Administración → 172.16.18.0/23
- Ventas → 172.16.20.0/23
- Marketing → 172.16.22.0/23

---

## Conexiones entre Sucursales

Para las conexiones entre routers se reservaron subredes específicas, mejorando el aislamiento de problemas y la seguridad:

- Enlace Buenos Aires A - Buenos Aires B → 172.16.24.0/23
- Enlace Buenos Aires A - Córdoba → 172.16.26.0/23
- Enlace Buenos Aires A - La Rioja → 172.16.28.0/23
- Enlace Buenos Aires B - Córdoba → 172.16.30.0/23
- Enlace Buenos Aires B – La Rioja → 172.16.32.0/23
- Enlace Cordoba – La Rioja → 172.16.34.0/23

---

## Beneficios del Diseño
- **Escalabilidad:** Red preparada para duplicar el número de hosts.
- **Seguridad y control:** Subredes dedicadas para los enlaces entre sedes.
- **Organización eficiente:** Cada departamento y sucursal posee su propio segmento de red.
