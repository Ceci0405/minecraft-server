# Minecraft Hybrid Auth

Servidor de Minecraft con mods, desplegado con Docker, con autenticación
híbrida: jugadores premium validados por Mojang y jugadores offline con
contraseña. Incluye modelo de amenazas, hardening y pentest documentado.

## Contexto
Servidor real para una comunidad de Discord de ~15 personas.

## Stack
- Docker + Docker Compose
- itzg/minecraft-server
- NeoForge 1.21.1
- Mods descargados desde Modrinth

## Arquitectura
(diagrama: jugador → servidor → Mojang / mod de auth)

## Cómo levantarlo
1. Copia `.env.example` a `.env` y rellénalo
2. `docker compose up -d`

## Decisiones de seguridad
- Secretos fuera del repo (`.env` en `.gitignore`)
- RCON no expuesto a internet
- Whitelist activa
- (en progreso) Autenticación híbrida — ver `docs/`

## Documentación
- [Evaluación de componentes](docs/component-review.md)
- [Modelo de amenazas](docs/threat-model.md)
- [Hardening](docs/hardening.md)
- [Pentest](docs/pentest-report.md)

## Roadmap
- [x] Servidor base en Docker
- [ ] Autenticación híbrida
- [ ] Modelo de amenazas
- [ ] Pentest
- [ ] Alertas en Discord
