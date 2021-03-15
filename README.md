# dedupedirs

A script to search the contents of two or more identically structured directories and replace duplicates with hardlinks.

This may be useful for backup snapshots where some files are present as exact copies across different snapshots.

Usage:

```
dedupedirs [-n|--dry-run] [-v|--verbose] DIR1 DIR2 [...]
```

This hardlinks `DIR1/path` and `DIR2/path` for every `path` that is a regular file present in both directories and with the same content.

Additional arguments are also compared to `DIR1`, but not to any other specified directories. Thus, running `dedupedirs a b c` is equivalent to running `dedupedirs a b` and then `dedupedirs a c`.
