# Evaluación de componentes

## Mod de autenticación

### Candidatos evaluados
| Criterio | MixAuth | DirectAuth |
|---|---|---|
| Código fuente | GitHub, LGPLv3 | GitHub, MIT |
| Hash de contraseñas | BCrypt, coste 12 | PBKDF2-SHA256 |
| Detección premium | Automática | Manual (`/online`) |
| Protección robo de nick | Sí | No hasta `/online` |
| Madurez | Muy nuevo | Algo más usado |

### Decisión: MixAuth
Protege por diseño contra el robo de nicks premium y usa BCrypt.
Riesgo aceptado: proyecto reciente con poca adopción → mitigado con
revisión de código propia y fijación de versión + hash.

### Integridad
| Campo | Valor |
|---|---|
| Archivo | mixauth-1.21.1-x.x.x.jar |
| Versión | x.x.x |
| Origen | https://www.curseforge.com/minecraft/mc-mods/mixauth |
| SHA-256 | PEGA_AQUÍ_EL_HASH |
| Fecha de revisión | 2026-10-11 |

### Valores por defecto inseguros detectados
- `min_password_length = 1` → se cambiará a ≥ 8
- `trusted_login_window_hours = 24` → se reducirá o desactivará