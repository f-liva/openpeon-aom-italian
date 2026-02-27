# Age of Mythology - Italian Voice Pack

Italian voice pack for [peon-ping](https://openpeon.com), featuring dialogue from the Italian localization of the Age of Mythology campaign.

## Characters

- **Arkantos** - Main hero of the campaign
- **Ajax** - Greek warrior
- **Amanra** - Egyptian warrior
- **Kastor** - Son of Arkantos
- **Chirone** - Centaur hero
- **Odisseo** - Odysseus
- **Skult** - Norse trickster
- **Kemsyt** - Egyptian antagonist
- Multiplayer taunts (Italian)

## Categories

| Category | Sounds | Examples |
|---|---|---|
| session.start | 8 | "Si, signore!", "Seguimi!", "Ai tuoi ordini" |
| task.acknowledge | 9 | "Si!", "Perfetto!", "Bene cosi!", "E sia!" |
| task.complete | 8 | "Era ora!", "Siamo liberi!", "La porta e' abbattuta!" |
| task.error | 8 | "Cosa e' successo?", "Non mi suona bene!", "Attenzione!" |
| input.required | 8 | "Cosa facciamo ora?", "Quale missione?", "Cosa?" |
| resource.limit | 6 | "Scarsita' di oro/legname/cibo", "Aiuto!" |
| task.progress | 7 | "Sono in posizione!", "Sto esplorando" |
| user.spam | 8 | "Non mi piaci!", "Vattene!", "Sei proprio uno sciocco!" |
| session.end | 5 | "Grazie, amico mio!", "Che gli Dei ci proteggano!" |

**64 sound files (WAV)** | **67 category entries** | **~5.5 MB total**

## Install

```bash
peon install aom-italian
```

Or with Claude Code:

```
/peon-ping-use aom-italian
```

## How this pack was built

This pack was created with the help of [Claude Code](https://claude.com/claude-code) (Claude Opus) through the following process:

1. **Audio extraction** - 1099 Italian voice files were extracted from the Age of Mythology game data (campaign dialogue and multiplayer taunts)

2. **Automated transcription** - [OpenAI Whisper](https://github.com/openai/whisper) (model `small`, language `it`) was used to transcribe all 882 unlabeled audio files locally. The labeled multiplayer taunts (files 001-044) already had Italian text in their filenames

3. **Duration filtering** - Files were filtered to keep only short clips (under 6 seconds), ideal for notification sounds

4. **Curated selection** - From 882 transcribed clips, 64 were hand-picked based on:
   - Clarity of the voice line
   - Relevance to the peon-ping event category (e.g. "Cosa facciamo ora?" for `input.required`)
   - Variety of characters (Arkantos, Ajax, Amanra, etc.)
   - Appropriate tone and duration (0.5s - 2.5s)

5. **Format conversion** - All files were converted from MP3 to WAV (PCM 16-bit, 44.1kHz, mono) for maximum compatibility with audio backends (paplay on WSL/PulseAudio does not reliably play MP3)

6. **Pack assembly** - Files were renamed with descriptive names (`ajax-era-ora.wav`), SHA256 checksums computed, and the `openpeon.json` manifest generated following the CESP v1.0 format

## License

CC-BY-NC-4.0

Audio content belongs to Xbox Game Studios / Ensemble Studios. This pack is a fan project for non-commercial use.
