# PS5 Relapse Exploit - Remix
Supported firmware: 7.00 through 13.60.

## Usage
- In the network settings, set Primary DNS to `45.56.67.85` (Recommended)
- Run `python serve.py` locally, or open https://ntfargo.github.io/Relapse-Exploit/ on the PS5.
- The default payloads are stored in `payloads/` after a successful run, the ELF loader listens on port `9021`.
- After elfldr starts on port `9021`, you can press R2 to send `kstuff.elf`, `pldmgr.elf`, `shadowmountplus.elf`, then `onionHEN.elf`.
- Alternatively, after elfldr starts you can exit the page without pressing R2 and use [NetCat Gui](https://gbatemp.net/download/netcat-gui-by-modded-warfare.37016/) to send payloads on port 9021.
- After Payload Manager loads you can use it to load other payloads if needed.

## Stability notes
On my 12.70 firmware kstuff lite v1.11 would crash everytime.  This loads kstuff lite v1.10 instead
Webkit may need several attempts, reload the page if the browser stalls. The kernel exploit may hang or panic the console, so reboot before trying again if that happens.

## Exploit chain
Browser stage uses JSC info leaks and a structured clone object pool mismatch to corrupt a typedarray. The kernel stage combines a address leak with an `aio_multi_wait` uaf race to establish kernel r/w.

## Credits
ntfargo, ufm42, Sonic-Iso, Jordy, Dr. Yenyen, TheFlow, SlidyBat,  Flatz, cow, nhk, bollarz, Sleirsgoevy, EchoStretch, EarthOnion.

## Disclaimer
This project is intended for **educational and security research purposes only**. It does not endorse piracy, unauthorized access, or misuse of commercial devices. Use it only on devices you own or are authorized to test, and comply with applicable laws and regulations.

The software is provided as-is, without warranty. You assume the risks of using it, including system instability, data loss, and account bans. The maintainers accept no liability for resulting damage. 
