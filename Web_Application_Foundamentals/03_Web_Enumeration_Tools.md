# 🛠️ Web Enumeration & Directory Brute-Forcing

Il primo passo di un attacco web è scoprire cosa non è visibile nei menu della home page.

## 1. Robot.txt e Sitemap
- **/robots.txt**: File che dice ai motori di ricerca cosa non indicizzare. Spesso contiene cartelle sensibili (es. `/admin`, `/backup`).
- **/sitemap.xml**: Mappa completa del sito.

## 2. Directory Brute-Forcing
Si utilizzano wordlist per "indovinare" i nomi di file e cartelle.

### Tool: GoBuster
```bash
gobuster dir -u http://[TARGET_IP] -w /usr/share/wordlists/dirb/common.txt

dir: Modalità enumerazione cartelle.

-u: Target URL.

-w: Wordlist di riferimento.

Tool: Nikto
Vulnerability scanner specializzato per web server.
nikto -h http://[TARGET_IP]
Rileva configurazioni errate, versioni di server obsolete e file pericolosi.
