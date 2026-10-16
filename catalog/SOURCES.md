# Song-chart reference catalog — v1.1.053

Snapshot prepared October 16, 2026. The user's inclusion rule is a **top-10 song**,
not an album, on Billboard's Hot 100 or a relevant genre/format song chart from
1970 through available 2026 issues. Groups and credited featured performers count.
The 190 previously available editorial references are retained independently of
this expansion's qualification audit.

The app contains 4,347 references: 4,294 entries supported by the imported
song-chart records or chart-achievement summaries, plus 53 retained editorial
references not matched by this import. There are 4,157 newly added names.

## Sources and coverage

- [mhollingshead/billboard-hot-100](https://github.com/mhollingshead/billboard-hot-100),
  `all.json`: weekly Hot 100 rows with positions 1–10, January 3, 1970–October 17,
  2026. The issue date can follow its publication date.
- [pdp2600/chartscraper](https://github.com/pdp2600/chartscraper): archived Country,
  R&B/Hip-Hop, Latin, Dance/Electronic, Rock and Pop song charts, through December
  2018. Imports use actual weekly rank, not a lower-chart row's lifetime peak.
  Some archive dates represent a requested day within a chart week.
- DrTravel's historical Billboard chart transcriptions, shared by kingofskiffle
  in the [UKMIX archive thread](https://www.ukmix.org/forum/chart-discussion/chart-analysis/11535800-updated-billboard-chart-spreadsheets):
  Mainstream Rock, March 21, 1981–August 3, 2024; Alternative, September 10,
  1988–August 3, 2024 (the corrected file restores 2019); R&B/Hip-Hop and its
  Airplay continuation through August 3, 2024; Country and Adult Contemporary/
  Adult Top 40 summaries through June 28, 2025. Country/Adult summary evidence
  uses a documented top-10 peak and its peak date, rather than annual rank.
- [Hot Gospel Songs](https://en.wikipedia.org/wiki/Hot_Gospel_Songs) and
  [Hot Christian Songs](https://en.wikipedia.org/wiki/Hot_Christian_Songs):
  documented top-ten-count and number-one-song summaries supplement the weekly
  imports. Their rank/date cells are blank in the CSV when only the achievement
  summary, rather than a particular weekly placement, was used. Blank does not
  mean a rank of zero or an invented chart date.
- Genre enrichment uses broad tags from
  [kevinschaich/billboard](https://github.com/kevinschaich/billboard),
  [sergeikofman444/music-data-scripts](https://github.com/sergeikofman444/music-data-scripts),
  chart-family context, and editorial crossover assignments. A chart-family tag
  describes that context; it does not establish an artist's exclusive genre.

## Method and limits

`top10-song-evidence.csv` retains one qualifying placement or summary per imported
reference. This is an inclusion audit, not a count of all hits or a full career
chart history. Alternate spellings and common stage-name changes are normalized;
collaborative credits are split while known group names stay together. Ambiguous
components without an independently identifiable name are excluded for review.
Source transcriptions can contain mistakes, and identity normalization is not a
complete music-authority database.

**This is not an exhaustive all-genres-through-2026 catalog.** Remaining gaps
include late genre-chart updates, historical Dance Club coverage, portions of
Christian/Gospel and Smooth Jazz song-chart history, and unresolved artist
credits. No completeness badge is displayed. Future releases can fill gaps using
additional accessible chart records. No album positions were used for eligibility.

Individual vocal descriptions are editorial starting points. Newly listed acts
without an individual profile use a clearly labeled genre template with vocal
register, texture, delivery and accent left on Auto. Chart placement does not
establish vocal characteristics, range, accent, or a voice replica. The artist
name remains in the reference controls and saved settings, not automatically in
the generated Style or lyric direction.

The catalog is embedded in `index.html` for downloaded/offline use. Artist lookup,
genre filtering, and prompt assembly make no network or model requests.
