# HTB · Enigma — PoC

Proof-of-concept per la macchina **Enigma** (Hack The Box, Season 11).
Writeup completo: https://blog.ldsec.it/enigma/

**Catena:** share NFS esposta → PDF con credenziali → riuso password su Roundcube →
RCE su OpenSTAManager (**CVE-2025-69212**, command injection via file `.p7m`) →
crack bcrypt (lateral movement) → privesc via OliveTin (guest-exec come root).

| File | Ruolo |
|------|-------|
| `exploit.py` | Command injection su OpenSTAManager (CVE-2025-69212) via `.p7m` → RCE |
| `backupScript.sh` | Script di supporto usato nella fase di privesc |

> ⚠️ Solo a scopo educativo e per testing autorizzato.

## Licenza e uso autorizzato

Distribuito sotto licenza [MIT](LICENSE).

Codice proof-of-concept pubblicato a scopo educativo e di ricerca, come
companion dei writeup su <https://blog.ldsec.it>. Sviluppato ed eseguito
esclusivamente contro una macchina di laboratorio volutamente vulnerabile, in
un contesto isolato e autorizzato. Usalo solo su sistemi di cui sei proprietario
o per i quali hai un'autorizzazione esplicita a eseguire test di sicurezza.
