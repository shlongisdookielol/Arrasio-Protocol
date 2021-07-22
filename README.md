# Arrasio Protocol (shlong#2873 and Cesnad#0803)
### Outgoing Packets
| Header  | What It Is        | Explanation                           |
|---------|-------------------|---------------------------------------|
| `C`     | Camera Packet     | Contains Camera X & Y, FoV, and more. |
| `d`     | Ticks Camera      | Ticks your camera.                    |
| `p`     | Ping              | Obtains your ping.                    |
| `x`     | Upgrade Stats     | Sends what stats you want.            |
| `U`     | Upgrade Tank      | Send what tank you want to upgrade as.|
| `s`     | Spawn Packet      | Contains your name and party id.      |
| `L`     | Leveling Up       | Levels you up                         |

### Incoming Packets
| Header  | Information       |
|---------|-------------------|
| `u`     | update            |
| `b`     | Broadcast         |

![Bots](pictures/bots.PNG)
![FOV](pictures/fov.PNG)
