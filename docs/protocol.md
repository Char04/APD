# Protocol de comunicație serială

## 1. Diagramă de secvență

```mermaid
sequenceDiagram
    autonumber
    actor PC as PC / Host
    participant Arduino as Arduino Uno

    PC->>Arduino: START
    Arduino-->>PC: ACK
    loop Eșantionare periodică
        Arduino->>PC: timestamp_ms, raw_adc, voltage_v, temp_c
    end
```

## 2. Comenzi suportate

| Comandă | Cod / Format | Efect produs |
| :--- | :---: | :--- |
| `START` | `START` / `0x01` | Inițiază achiziția periodică și transmiterea eșantioanelor pe interfața serială |
| `STOP` | `STOP` / `0x02` | Oprește procesul de achiziție și transmitere a datelor |
| `STATUS` | `STATUS` / `0x03` | Răspunde cu starea curentă a modulului de achiziție și configurarea activă |

## 3. Diagramă de stări (Automat de achiziție)

```mermaid
stateDiagram-v2
    [*] --> IDLE
    IDLE --> SAMPLING : Comandă START / Buton
    SAMPLING --> IDLE : Comandă STOP / Buton
    SAMPLING --> ALARM : T_masurata > T_prag
    ALARM --> SAMPLING : T_masurata <= T_prag
    ALARM --> IDLE : Comandă STOP
```

