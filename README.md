# StationFinder v1.1

StationFinder is a self-contained radio station database application. It runs entirely in any modern browser with no installation or dependencies. Load a station schedule file and search by frequency. Then filter by station name, mode, language, source, or on-air status. Optionally link to SDRconnect via WebSocket to track and tune stations in real time.  CAT control over a virtual COM port connection is also possible and works with SDRconnect, SDRuno, SDR Console and HDSDR.

## Features

- **Schedule file import**

  - Loads station frequency schedules in multiple formats (auto-detected on import):

    - **Aoki** — text based schedule format.  Frequently updated.

    - **EiBi** — semicolon-delimited schedule format.  Regular updates.

    - **HFCC** —  a retrieval and conversion program is included.

    - **swskeds** — combined EiBi/Aoki/HFCC format.  Semi-annual updates.

    - **s1b** — SDRplay format for memory files.

    - **SDR Console**  — frequency database converted to CSV format.

  - All formats normalized to a common multiple column internal schema.

  - Columns that are empty in the loaded format are automatically hidden.

- **Frequency search**

  - Three search modes selectable via buttons:

    - **Exact** — matches frequencies within ±2 kHz of the entered value.

    - **Prefix** — shows all stations whose frequency starts with the typed digits.

    - **Range** — enter a range of interest in kHz (i.e. 9000-10000)

  - Smart pre-filling when switching modes:

    - Exact → Range pre-fills a ±150 kHz window around the current value.

    - Range → Exact uses the midpoint of the range.

  - Search timing displayed in a status indicator.

- **Filtering**

  - **On Now** — filters to stations currently on air based on UTC time.

  - **Language filter** — dynamic drop-down built from the loaded data. Includes grouping shortcuts i.e. "English (all)" for swskeds format.

  - **Source filter** — filter by schedule source (EiBi, Aoki, HFCC).

  - **Station name search** — substring search on the station name column.

- **Sortable table**

  - First 6 columns (Frequency, Mode, Station, On, Off, Language) are sortable by clicking the column header.

  - Sort state persists across searches.

  - Column headers show ↑, ↓, or ↑↓ arrows to indicate sort state.

- **SDR WebSocket integration**

  - Connects to SDRplay program SDRconnect via WebSocket.

  - Default connection: 127.0.0.1 port 5454 (both configurable).

- **SDR CAT Control**

  - Connects to SDR programs using virtual COM port connection

  - Works with SDRconnect, SDRuno, SDR Console and HDSDR

- **Flexible Search Capability**

  - **Manual** — type a frequency to search manually.

  - **Fetch** — one-shot read of the SDR VFO frequency into the search box.

  - **Track** — continuously follows the SDR VFO frequency and updates results.

  - **Double-click a row** — tunes the SDR to that station's frequency and mode.

  - **Web Search 1** — opens shortwave.live at the current VFO frequency.

  - **Web Search 2** — opens short-wave.info at the current VFO frequency.

- **Keyboard shortcuts**

  - **F or f** — jump to frequency search box.

  - **S or s** — jump to station search box.

  - **Enter** — run search and release focus.

  - **Escape** — release focus from search box, or close help modal.

- **User Interface details**

  - Live UTC and local clock updated every second.

  - Status indicators showing loaded row count and search result count.

  - Batched rendering (150 rows per animation frame) for large datasets.

  - All controls disabled until a file is loaded, then enabled progressively.

  - Built-in help with button descriptions, keyboard shortcuts, and download links for station frequency schedules.

## Requirements

- Any modern browser (Chrome, Firefox, Edge, Safari) works in WebSocket mode.

- Only Chromium-based browsers like MS Edge, Chrome and Opera work with CAT control

- No installation, no server, no internet connection required.

- Will connect to SDRconnect running on the same machine or local network.

- Will connect over the WAN if router has port 5454 forwarding enabled.

- Virtual COM port pair required if using CAT mode (Com0Com or VSPE)

## Typical Workflow

1. **Open StationFinder** in your browser.  Just double-click on file.

2. Click **Import File** and load a frequency schedule (Aoki, EiBi, HFCC, swskeds, s1b or SDR Console format). Help file contains URL links to download station frequency schedule files.

3. Type a frequency in the **Search (Frequency)** box and press **Enter**.

4. Use **Range** mode to browse a range of frequencies.

5. Use **On Now** to filter to stations currently broadcasting.

6. Use the **Language** and **Source** drop-downs to narrow results further.

7. Optionally link to SDRconnect, SDRuno, SDR Console or HDSDR via **Connect**, then use **Fetch** or **Track** to follow the SDR VFO frequency automatically.  Enable WebSocket in SDRconnect first if using that mode.  If using CAT enable in the SDR program prior to making connection.

8. **Double-click** any row to tune the SDR program to that station.

## License

This program is free software: you can redistribute it and/or modify it under the terms of the **GNU General Public License** as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

You must:

- Keep the copyright and license header.

- Release any modifications or derivative works under GPLv3 (or later).

See [https://www.gnu.org/licenses/gpl-3.0.html](https://www.gnu.org/licenses/gpl-3.0.html) for the full license text.

