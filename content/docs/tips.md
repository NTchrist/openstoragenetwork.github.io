---
title: Tools, Tips & Tricks
prev: transfer-data
weight: 100
---

## Tools

These are some (but not all!) of the libraries and packages you can use with OSN.
If you have a tool to add to the list, please let the OSN team know at {{< help-email >}}.

### S3 command-line clients

| **Tool** | **Platform** |
|----------|--------------|
| rclone | all |

### S3 libraries

| **Tool** | **Language** | **Platform** |
|----------|--------------|--------------|
| [Boto3](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)    | Python       | All          |
| [aws.s3](https://cloud.r-project.org/web/packages/aws.s3/index.html) | R | All |

## Best Practices

### Naming Conventions

For broad compatibility with tools, libraries, and filesystems: use lower-case letters, numbers, spaces, hyphens (`-`), underscores (`_`), and periods (`.`) in file and folder names.  Avoid unnecessary special characters, names that differ only by capitalization, and leading or trailing spaces or periods.  Deviating from this may result in data that is unreadable in certain circumstances.

S3 permits many special characters in object names, but some tools and libraries may interpret them differently.  For example, a name containing a plus sign (`+`) may conflict with an otherwise identical name containing a space:

```text
test file.txt
test+file.txt
```

Names that differ only by capitalization may also conflict when used with some tools or filesystems:

```text
test file.txt
Test File.txt
```

Forward slashes (`/`) may be used to separate "folders" or "directories" in a path, such as:

```text
project/data/test file.txt
```

However, a forward slash should not be used within the name of an individual file or directory.
