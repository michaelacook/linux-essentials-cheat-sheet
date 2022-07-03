## Permissions

### Octal File Permissions
|    | Read (4) | Write (2) | Execute (1) | Result |
| -- | -- | ----- | ------- |  ------  |
| User | r | w | x |  7  |
| Group | r | - | x | 5 |
| Others | r | - | - | 4 |

### Octal Values
| Octal Value | Mode | Octal Value | Mode |
| ----------- | ---- | ----------- | ---- |
| 0 | - - - | 4 | r - - |
| 1 | - - x | 5 | r - x |
| 2 | - w - | 6 | r w - |
| 3 | - w x | 7 | r w x |

### Symbolic File Permissions
|    | Read (r) | Write (w) | Execute (x) | Result |
| -- | -- | ----- | ------- |  ------  |
| User (u) | + | + | + |  u+rwx  |
| Group (g) | = | - | - | g=r |
| Others (o) | - | - | - | o-rwx |
| All (a) |  |  |  |  |

- Change file mode (permissions):

    ```chmod [permission] [file]```
- Recursively change file mode (for directories): 

    ```chmod -R [permission] [file]```
- Change file user and group owner: 

    ```chown [user:group] [file]```
- Recursively change user and group owner:

    ```chown -R [user:group] [file]```
- Change group only: 

    ```chgrp [group] [file]```
- Change group only: 

    ```chown [:group] file```
- Change user only: 

    ```chown [user] [file]```

