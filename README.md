# Sicobra Soporte · App Android de tickets de TI

Trabajo parcial (TB1) del curso **Plataformas Móviles y Análisis Cloud (1FIS0276)** · UPC EPE · Ciclo 2026-2 · Grupo 5.

Aplicación nativa Android para que los colaboradores de Sicobra reporten incidencias de TI desde el celular y el área de soporte las atienda y les haga seguimiento en tiempo real.

## Equipo

| Integrante | Rol en el Sprint 1 |
| --- | --- |
| Efraín Rodríguez | Bandeja de tickets (HU02), búsqueda (HU09), dashboard (HU10) |
| Albert Vargas | Registro de ticket (HU03), atención del ticket (HU07) |
| Diego Villaran | Foto (HU04), confirmación (HU05), notificaciones (HU06) |
| Nicoleanggie Ysique | Inicio de sesión (HU01), detalle e historial (HU08), asignación (HU14) |

## Tecnología

- Kotlin, Jetpack Compose y Material 3
- Arquitectura MVVM con Clean Architecture (capas `data`, `domain`, `presentation`)
- Paquete: `com.example.sicobra` · minSdk 25 · targetSdk 37
- Release 2: API REST en AWS (API Gateway, Cognito, S3), Retrofit, Room y WorkManager

## Estructura del proyecto

```
app/src/main/java/com/example/sicobra/
├── MainActivity.kt            # NavHost con las rutas
├── data/
│   ├── model/                 # Ticket, Usuario, UserRole, HistorialItem, ArticuloSolucion
│   ├── repository/            # TicketDataSource (datos simulados, Release 1)
│   ├── remote/                # Retrofit (Release 2)
│   └── local/                 # Room (Release 2)
├── domain/                    # Repositorios y casos de uso
├── presentation/
│   ├── navigation/            # RutasNav, BottomNavItem
│   ├── common/                # Componentes reutilizables
│   └── screens/               # auth, dashboard (por rol), detalle, form, inicio, buscar
├── ui/theme/                  # Color, Theme, Type
└── di/                        # Módulos de Hilt
```

## Historias de usuario y estado (fase 0, 06/11/2026)

| HU | Historia | Prioridad | Sprint | Cobertura de escenarios |
| --- | --- | --- | --- | --- |
| HU01 | Inicio de sesión seguro | Must | 1 | 25 % |
| HU02 | Bandeja de tickets móvil | Must | 1 | 13 % |
| HU03 | Registro de ticket desde el celular | Must | 1 | 25 % |
| HU04 | Foto como evidencia | Should | 3 | 0 % |
| HU05 | Confirmación visual de acciones | Must | 1 | 17 % |
| HU06 | Notificación de ticket asignado | Should | 3 | 0 % |
| HU07 | Atención del ticket desde el móvil | Must | 2 | 50 % |
| HU08 | Detalle e historial del ticket | Should | 2 | 50 % |
| HU09 | Búsqueda y filtros rápidos | Should | 2 | 17 % |
| HU10 | Dashboard móvil de indicadores | Should | 3 | 50 % |
| HU11 | Autoayuda sugerida | Could | 3 | 25 % |
| HU12 | Encuesta de satisfacción | Could | 3 | 25 % |
| HU13 | Registro sin conexión | Could | 3 | 0 % |
| HU14 | Asignación de tickets por el Jefe de TI | Must | 2 | 33 % |

Cobertura global: 23 % de 41 escenarios (26 % en las historias Must). Detalle en `docs/fase0_cobertura.png` y en el Anexo 6.14 del informe.

## Cómo ejecutar

1. Clonar el repositorio y abrirlo en Android Studio.
2. Esperar la sincronización de Gradle.
3. Ejecutar en un emulador (API 25 o superior) o en un celular conectado por USB.
4. Las cuentas de prueba de cada rol están en el documento interno del equipo (no se publican aquí).

## Flujo de trabajo con Git

- `main`: versión estable de cada entrega.
- `develop`: integración del sprint en curso.
- `feature/HU##-descripcion`: una rama por historia, integrada a `develop` con pull request revisado por otro integrante.
- Commits con Conventional Commits y el código de la historia, por ejemplo `feat(HU03): valida campos obligatorios`.

Más detalle en [CONTRIBUTING.md](CONTRIBUTING.md).

## Documentación

| Archivo | Contenido |
| --- | --- |
| `docs/prototipo/` | Pantallas del prototipo v2 generadas en Google Stitch |
| `docs/fase0_cobertura.png` | Resultado de la fase 0 del experimento |
| `docs/Kit_Fase1_Prueba_Usabilidad_Sicobra.xlsx` | Registro y análisis de la prueba con usuarios (SUS y Wilcoxon) |

## Próximos pasos

- **Sprint 1 (hasta el 15/11):** reglas de interfaz pendientes y prueba con 6 usuarios.
- **Sprint 2:** ViewModels y Hilt, cámara, huella digital y pruebas automatizadas.
- **Sprint 3:** API en AWS, Retrofit, Room, WorkManager y notificaciones push.
