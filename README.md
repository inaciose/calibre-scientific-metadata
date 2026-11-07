# Scientific Metadata for Calibre

A Calibre metadata source plugin for retrieving bibliographic information from scientific publications.

The plugin identifies scientific papers using identifiers found in their filenames and retrieves their metadata from supported academic repositories.

## Supported sources

| Repository | Identifier example |
|---|---|
| [arXiv](https://arxiv.org/) | `2402.00786v5` |
| [ACL Anthology](https://aclanthology.org/) | `2023.acl-long.284v2` |

Additional repositories may be supported in future releases.

## Requirements

- [Calibre](https://calibre-ebook.com/) 9.x or compatible versions.
- Internet connection.

## Installation

1. Download the latest plugin ZIP file from the [Releases](../../releases) page.
2. Open Calibre.
3. Navigate to **Preferences → Plugins**.
4. Select **Load plugin from file**.
5. Choose the downloaded ZIP file.
6. Confirm the security warning and install the plugin.

Restart Calibre if requested.

## Usage

The plugin integrates with Calibre's native metadata retrieval functionality.

1. Add your scientific PDF files to the Calibre library.
2. Select one or more books.
3. Open **Edit metadata → Download metadata**.
4. Calibre will search the available metadata sources, including this plugin.
5. Review the returned results and select the correct publication.
6. Apply the metadata.

### Filename identification

The plugin extracts publication identifiers from filenames.

Examples:

| Filename | Identifier detected |
|---|---|
| `2402.00786v5.pdf` | arXiv: `2402.00786` |
| `1911.02116v2.pdf` | arXiv: `1911.02116` |
| `2023.acl-long.284v2.pdf` | ACL Anthology: `2023.acl-long.284` |
| `E91-1001v2.pdf` | ACL Anthology: `E91-1001` |

Version suffixes (such as `v2` or `v5`) are ignored when identifying the publication.

**Important:** The plugin does not rename or modify the original PDF files.

## Multiple search results

Calibre may return results from several metadata providers, including this plugin and its other configured sources.

When multiple candidates are displayed:

- Check the publication title and authors.
- Prefer the result matching the original repository identifier.
- Review the publication date and other bibliographic details before applying the metadata.

## Metadata and library preservation

The plugin retrieves bibliographic fields such as:

- Title
- Authors
- Abstract / comments
- Publication date
- DOI and repository identifiers
- Publisher and publication series

Existing Calibre tags and library organization are not intentionally modified by the plugin.

## Troubleshooting

If no results are returned:

1. Check that the filename contains a supported publication identifier.
2. Verify that the identifier corresponds to an existing publication.
3. Check your internet connection.
4. Make sure the plugin is installed and enabled.
5. Review Calibre's metadata download log for errors.

## Development

The plugin is designed to support multiple scientific metadata repositories through a single Calibre metadata source.

New repositories can be integrated incrementally without changing the existing user workflow.

Contributions, bug reports and suggestions are welcome.

## License

This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 Sérgio Inácio
