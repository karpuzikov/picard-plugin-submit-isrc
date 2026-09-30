# Submit ISRC

This fork extends the Submit ISRC plugin so the action works with **multiple selected releases at once**.

Select any number of releases in Picard (including Select All), right-click the selection, and choose **Plugins -> Submit ISRCs**. The plugin scans all selected releases, collects the missing ISRCs, deduplicates recordings that appear on more than one selected release, and submits the missing ISRCs to MusicBrainz in one operation.

To use this function, you must first match your files to the appropriate tracks for the releases. Do this before saving your files if Picard is configured to overwrite the `isrc` tag in your files.

For each file that has a single valid ISRC in its metadata, the ISRC will be added to the MusicBrainz recording if it does not already exist.

If the same ISRC appears in multiple selected releases for the **same MusicBrainz recording**, it is submitted only once. If the same ISRC points to **different recordings**, submission is aborted to prevent an unsafe bulk edit.

If a file contains multiple ISRCs, that file is skipped and listed in the notice. Selected releases with no tracks are also skipped.

If one of the files contains an invalid ISRC, submission is aborted.

After submission, one result dialog reports the number of ISRCs submitted and the number of selected releases processed.

Upstream plugin documentation: [Submit ISRC User Guide](https://picard-plugins-user-guides.readthedocs.io/en/latest/submit_isrc/user_guide.html).
