## Author 

Pavel Constantin-Beniamin 4LF342

# APD – Laborator 

Proiect de laborator pentru disciplina Achiziția și prelucrarea datelor. Nod de achiziție a temperaturii bazat pe Arduino Uno.

# Hardware

Arduino Uno R3, senzor de temperatură TMP36Platformă: Arduino Uno R3 (ATmega328P)
Autor laborator: <numele vostru>

## Parametri
- `SENSOR_PIN`: intrarea analogică a senzorului (A0)
- `SAMPLE_PERIOD_MS`: perioada de eșantionare în milisecunde (1000 ms)
- `SERIAL_BAUD`: viteza de transmisie a portului serial (9600 baud)
- `LED_PIN`: pinul digital pentru LED-ul de stare (13)
- `BUTTON_PIN`: pinul digital pentru butonul de control (2)

Comunicație serială: suportă 115200 baud pentru viteză mare de transfer sau 19200 baud pentru compatibilitate cu echipamente vechi.
