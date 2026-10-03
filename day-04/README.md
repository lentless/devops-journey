# Day-04 (YAML)

## What I learned

- YAML = human-readable data format, same category as JSON and
  XML (not HTML — that's for structuring web pages, different
  category entirely, not really comparable)
- File extension: .yaml or .yml
- Core structure: key-value pairs (dictionaries/hashmaps).
  Case-sensitive. Indentation (spaces only, never tabs) defines
  structure
- Lists use `-` prefix; nested objects via indentation
- `---` separates multiple documents in one file; `...` marks a
  document as ended
- Explicit data-type tags exist: !!int, !!float, !!str, !!bool,
  !!null, !!map, !!seq, !!set, !!pairs, !!omap (maps/seqs are the
  common ones in real use; rest are good to recognize, not memorize)
- Numbers support binary (0b..), octal, hex (0x..), exponential
  (6.023E56), and comma-separated large numbers
- Null can be written as null / Null / NULL / ~
- CAUTION - the "Norway Problem": unquoted `NO` can be silently
  read as boolean false by some parsers (real production bug
  source). Always quote ambiguous strings like "NO", "yes"
- Block scalars: `|` preserves line breaks exactly, `>` folds
  multiple lines into one with spaces
- Serialization = converting a complex object into a byte stream
  that can be saved/sent and later reconstructed (deserialization
  reverses it)
- Anchors (&name) mark a reusable block, aliases (\*name) reference
  it, <<: merges it into another map — used constantly in real
  CI/CD YAML to avoid repeating config
- Can convert YAML <-> JSON <-> XML with online tools
- Used in: Docker, Kubernetes, Ansible, CI/CD pipeline configs

## Commands/syntax practiced

- Basic key-value, nested maps, block-style lists
- Multi-line strings: `>` (folds to one line) vs `|` (preserves
  line breaks)
- Anchors: &base / \*base / <<:

## What confused me

- Initially grouped HTML with YAML/JSON/XML — corrected: HTML is
  a different category (web pages, not data)
- Said XML is "non-readable" — corrected: XML IS human-readable,
  just more verbose than YAML
- Anchors/aliases syntax still new, needs more hands-on practice

## Tomorrow

- Back to shell scripting backlog
