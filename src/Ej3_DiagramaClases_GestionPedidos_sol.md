# Solución: Ejercicio 5 - Juego del NIM

## Análisis del Problema

### Identificación de Clases

Del análisis de las especificaciones, identificamos las siguientes clases:

1. **JuegoNIM**
   - Clase principal que coordina toda la partida
   - Atributos: palillos, jugadores, turnoActual, juegoTerminado
   - Métodos: iniciarJuego(), jugarTurno(), verificarFinJuego()

2. **Jugador**
   - Representa a un participante del juego
   - Atributos: nombre, esHumano
   - Métodos: decidirMovimiento()

3. **JugadorInteligente** (Especialización de Jugador)
   - Jugador con estrategia ganadora
   - Métodos: calcularMovimientoOptimo()

## Análisis de Relaciones

### 1. Composición (JuegoNIM - Jugador)
- **Nombre**: "tiene" / "participa en"
- **Tipo**: Agregación (no composición, porque los jugadores pueden existir independientemente)
- **Cardinalidad**: 
  - Un JuegoNIM tiene 2..* Jugadores (mínimo 2, sin máximo)
  - Un Jugador participa en 1 JuegoNIM (en este contexto)
- **Justificación**: El juego necesita múltiples jugadores para funcionar, pero los jugadores son entidades independientes

### 2. Herencia (Jugador - JugadorInteligente)
- **Tipo**: Especialización
- **Justificación**: Un JugadorInteligente "es un" Jugador con algoritmo de estrategia mejorado


## Diagrama de Clases

![Diagrama de Clases](../assets/ej1_captura.png)

## Código PlantUML

```plantuml

```

## Conceptos Clave de UML Aplicados

1. **Agregación**
   - JuegoNIM tiene Jugadores pero no los posee
   - Los jugadores pueden existir independientemente del juego

2. **Herencia**
   - JugadorInteligente especializa Jugador
   - Sobrescribe el método decidirMovimiento()

3. **Encapsulación**
   - Atributos privados (palillosRestantes, turnoActual)
   - Métodos públicos para interactuar con el estado

4. **Responsabilidad Única**
   - JuegoNIM: gestiona reglas y flujo
   - Jugador: toma decisiones de movimiento
   - JugadorInteligente: implementa estrategia

5. **Cardinalidades**
   - 2..* jugadores (mínimo 2, sin límite superior)
   - Validadas en tiempo de ejecución