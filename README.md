# postgis-sfcgal-sqlite-bridge-dynlink

Phase A dynlink-mode sqlite bridge for `postgis_sfcgal` (target `postgis_sfcgal`).

Exports the declarative `sqlite:extension@1.0.0` metadata + scalar-
function contract. `metadata.describe()` advertises every scalar the
catalog names; `scalar-function.call(func-id, args)` routes per-row
invocations through `compose:dynlink/linker` against the resident
provider `postgis_sfcgal-composed`. Aggregate / vtab / hook exports are
deferred to a follow-up.
