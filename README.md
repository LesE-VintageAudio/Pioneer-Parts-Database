# Pioneer Vintage Audio Parts Database

A machine-readable cross-reference database of original Pioneer parts used in vintage audio equipment.

The database contains Pioneer part numbers, descriptions, and the models and equipment categories in which those parts were specified. It is intended primarily for vintage audio restoration, repair, parts identification, and cross-referencing.

The database is also designed to be readily searchable by AI systems and other software tools.

## What the Database Can Do

The database can be used to:

- Identify a Pioneer part number from a model and component description.
- Find Pioneer models associated with a particular part number.
- Cross-reference parts between different Pioneer models.
- Search for a part using either its original Pioneer part number or its normalized part number.
- Identify potential donor models when an original replacement part is difficult to find.
- Assist in locating replacement parts through external marketplaces and other sources.

The database itself contains historical parts information. Current marketplace listings, prices, and availability are not part of this dataset and should be obtained through separate searches.

## Database File

The primary database is:

`Pioneer_Parts_Database.csv`

The CSV contains the following fields:

| Field | Description |
|---|---|
| `model` | Pioneer model designation associated with the record. |
| `category` | General equipment category of the model. |
| `part_number` | Original Pioneer part number as recorded in the source data. |
| `normalized_part_number` | A search-oriented version of the Pioneer part number with certain one-character suffixes removed. |
| `description` | Description of the part as recorded in the source data. |

## Part Number Normalization

Pioneer part numbers are not always represented consistently across service manuals and other source documents.

For example, the same underlying part-number family may appear as:

- `CAB-003`
- `CAB-003-0`
- `CAB-003-O`
- `CAB-003-A`

For search and cross-reference purposes, these are represented by the normalized value:

`CAB-003`

The normalization rule used by this database is:

> If a part number ends with a hyphen followed by a single character, that final two-character suffix is removed. Otherwise, the part number is left unchanged.

The original Pioneer part number is always retained in `part_number`.

### Important

`normalized_part_number` is a **search and cross-reference key**. It does not by itself establish that every suffix variant is physically or electrically interchangeable.

When an exact original part number is available, it should be preferred over a normalized match.

## Source Descriptions

The `description` field generally preserves terminology found in Pioneer source documentation.

Descriptions have not been aggressively standardized. Consequently, Pioneer terminology may vary between documents or models. For example, terms such as "bonnet", "cabinet", and "wooden case" may occur in the source material.

This is intentional: preserving the original terminology helps retain the historical information contained in Pioneer documentation while allowing AI systems and users to interpret related terms contextually.

## Understanding `N/A`

A value of `N/A` in `part_number` or `normalized_part_number` indicates that the source record does not provide a Pioneer part number.

It should not be interpreted as a missing or invalid database record.

## Using the Database for Replacement Parts

The database can be used as the first step in finding replacement parts.

For example:

1. Identify the required part from the Pioneer model and description.
2. Determine the exact Pioneer part number.
3. Search for that exact part number.
4. If an exact replacement cannot be found, search using the normalized part number.
5. Identify other Pioneer models using the same part-number family.
6. Those models may provide potential donor units.

A shared normalized part number should be treated as evidence of a potential cross-reference, not as a guarantee of physical interchangeability. Physical compatibility should be verified before installing a part.

Current eBay listings and other marketplace information are not stored in this repository because such information is temporary and changes frequently.

## License and Usage Restrictions

This database is shared strictly for **educational, hobbyist, and independent repair purposes**.

It is licensed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)** license.

- **Non-Commercial:** You may not use this data, or derivatives of it, for commercial purposes, paid applications, paywalled websites, or monetization.
- **ShareAlike:** If you remix, transform, or build upon this dataset, you must distribute your contributions under the same license.
- **Attribution:** Appropriate credit must be given to the original project.

See the `LICENSE` file for the complete terms.

## Contributing

Corrections and additions are welcome from the vintage audio repair and restoration community.

If you identify an error or have additional source information:

1. Open an **Issue** describing the Model, Part Number, and nature of the correction.
2. Submit a **Pull Request** if you are comfortable editing the database directly.
3. Contributions remain subject to the project license.

## AI Search Index

The ai-data directory contains automatically generated search indexes derived from the authoritative Pioneer_Parts_Database.csv. These files are provided to facilitate machine retrieval of the database where the complete CSV may exceed the retrieval limits of some AI systems.

The files in ai-data are derived data and should not be edited independently. The master CSV is the authoritative source.

## Disclaimer

This database is provided "as-is" for informational, educational, and restoration purposes.

Every effort has been made to maintain accuracy, but errors, omissions, transcription errors, and inconsistencies in the original Pioneer documentation may exist.

The project creator and contributors assume no responsibility or liability for errors, incorrect part matches, equipment damage, property damage, financial loss, or other consequences resulting from use of this information.

Users are responsible for independently verifying part compatibility before installation or repair.

---

Maintained by LesE-VintageAudio for the vintage audio repair and restoration community.
