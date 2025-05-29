# Automation-Mobile-Security

## Descripción
Este proyecto reúne un conjunto completo de pruebas funcionales y automatizadas aplicadas a una funcionalidad realista: transferencias bancarias en una aplicación web.

Incluye:

- Casos de prueba manuales detallados para asegurar la funcionalidad correcta.
- Scripts y frameworks de automatización para pruebas web y mobile.
- Implementación de pruebas de seguridad básicas, como validación de headers, JWT y análisis con OWASP ZAP.
- Integración con herramientas de CI/CD para garantizar calidad continua.
- Uso de metodologías ágiles con seguimiento en Jira y gestión de casos con Xray/QMetry.

El objetivo es demostrar habilidades prácticas en QA manual, automatización, mobile testing y ciberseguridad, preparando para roles laborales actuales y la transición a seguridad informática.

---

## Casos de prueba manuales

Aquí se listan los casos de prueba manuales desarrollados para la funcionalidad de transferencias bancarias en una app web.

| Caso # | Título                                   | Descripción breve                                          | Resultado esperado                         |
|--------|-----------------------------------------|------------------------------------------------------------|--------------------------------------------|
| 1      | Transferencia exitosa                    | Transferir monto válido a cuenta válida                     | Transferencia completada correctamente     |
| 2      | Transferencia con saldo insuficiente    | Intentar transferir monto mayor que saldo                   | Mensaje de error de saldo insuficiente     |
| 3      | Transferencia a cuenta inválida          | Transferir a cuenta no registrada o inválida                | Mensaje de error de cuenta no válida       |
| 4      | Transferencia sin autenticación          | Intentar transferir sin iniciar sesión                       | Redirección a login                         |
| 5      | Transferencia con campo monto vacío      | Enviar formulario con monto vacío                            | Mensaje de error de campo obligatorio      |
| 6      | Transferencia con caracteres no numéricos en monto | Ingresar letras en monto                                     | Mensaje de error de formato inválido       |
| 7      | Transferencia a cuenta con bloqueo       | Transferir a cuenta bloqueada                                | Mensaje de cuenta bloqueada                 |
| 8      | Verificación de registro de transferencia| Confirmar que la transferencia quede registrada en historial| Transferencia registrada correctamente      |
| 9      | Transferencia a múltiples destinatarios  | Transferir a varias cuentas en una sola operación            | Todas las transferencias completadas        |
| 10     | Transferencia con límite diario excedido| Intentar transferir monto que supera el límite diario        | Mensaje de límite excedido                   |

---

## Estructura del proyecto

- /test-cases/ : Documentos con casos de prueba manuales y automatizados.
- /automation/ : Scripts y código para pruebas automatizadas (Selenium, Appium).
- /security/ : Herramientas y scripts para pruebas de seguridad (OWASP ZAP, validaciones JWT).
- /ci-cd/ : Configuraciones para pipelines de integración continua y despliegue.

---

## Herramientas utilizadas

- Postman
- Selenium WebDriver con TestNG
- Appium para mobile testing
- OWASP ZAP para pruebas de seguridad
- Jenkins / GitHub Actions para CI/CD
- Jira con Xray o QMetry para gestión ágil y casos de prueba

---

## Cómo contribuir

Si querés colaborar o sugerir mejoras, abrí un issue o hacé un pull request.

---

## Contacto

Para consultas o contacto profesional, visitá mi [LinkedIn](https://www.linkedin.com/in/maria-macarena-developer/).

---

*Proyecto desarrollado por María Macarena, Técnica Superior en Desarrollo de Software y QA Manual y Automatización en formación.*

