# CAS_fork_DSW_DT_chcecklist
Changes for CAS fork document templates for DSW.
The document temlated is based on Horizon Europe DMP Template for DSW.
CAS fork adds integration to ASEP for questions:
- Contributor - Name
- Project - Name
## Contributors
**Tereza Kolmačková** <[kolmackova@knav.cz](mailto:kolmackova@knav.cz)>
 * ORCID: [0000-0003-0829-0770](https://orcid.org/0000-0003-0829-0770)
 * GitHub: [@TerezaKolmackova](https://github.com/TerezaKolmackova)

## Changelog

### Version 3
- Based on Horizon Europe DMP 3.1.2:
- Since 3.0.0 the replies are read through `x` (`src/data/model.j2`, `extract_replies` v2) instead of `repliesMap` and UUIDs. An integration question is an object `{_value, _raw}` (`_raw` only when an item from the integration was selected; a reply typed as plain text has just `_value`). `macros.integrationCAS` therefore takes this object, not the reply.
- **Prerequisite in the CAS fork of the KM:** the integration questions Contributor-Name and Project-Name must keep their `json.key` annotation (`name`), otherwise `x...name._value` is empty.
- `src/word/contributors.html.j2` and `src/word/projects.html.j2` no longer exist, MS Word uses the shared `src/contributors.html.j2` and `src/projects.html.j2` -> one change instead of two.
- The macro strips the `<p>` wrapper of the markdown, so the name can be used inline (`<strong>`, `<h3>`, sentences in section 4). The `<br>` / `</p> <br>` workarounds are not needed any more.
- **Not carried over:** the custom layout of the contributor list (old lines 34-53), the old `integrationROR` / `formatOrcid` calls (replaced upstream by `macros.ror` / `macros.orcid`) and the typo fixes in `02-2-accessible` (already fixed in 3.1.2).
- 2026-11-18

### Version 2
- Based on Horizon Europe DMP 1.20.0 - some typos already solved in the original DT 
- Corrected typos
- 2026-01-14


### Version 1
- Based on Horizon Europe DMP 1.19.0
- usable with: *CAS Common DSW Knowledge Model 3.0.8* and *CAS Life Sciences DSW Knowledge Model 3.0.13*
- 2026-01-09