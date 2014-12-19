# Novels Project Library

This repository contains all data relevant to the Novels Project. It is under
version control so all changes are recorded.

- `works.csv` contains records of *works* identified by `id`.
- Each directory in `volumes/` corresponds to a *volume*. The directory name is
  unimportant, the file `metadata.json` in each directory describes the
  relationship between the volume and a *work*.

## Works

The vast majority of records in `works.csv` are from the two volumes edited by
Garside, Raven, and Schöwerling. There are a handful of additions as well as
some placeholders where data has only been partially entered.

The following fields shall uniquely identify a record:

- `id`
- `source` and `source_identifier`

## Volumes

Each directory shall contain two files:

- `metadata.json`
- a text file with the extension `.txt`

The SHA1 of the text file is stored in `metadata.json`.

## Volume metadata

`metadata.json` contains a JSON-encoded dictionary which shall conform to the
following schema:

- `work_id` the work with which this volume is associated
- `internet_archive_identifier` Internet Archive id (e.g., `glenarvon01lambc`)
- `volume` integer
- `volume_count` integer (`volume_count` must be greater than or equal to `volume`)
- `date_entered` `%Y-%m-%d` of metadata creation
- `sha1` hex-encoded SHA1 of the text file in the directory
- `extra_info` (optionally empty) dictionary of non-essential information

The following fields uniquely identify a record: `work_id` and `volume`
