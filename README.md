# Resources

Currently moncheis' list of handy programs.

This list assumes you're using Windows, but most (if not all) programs listed
below are available in most OSs.

The text I've copied and pasted from my terminal is formatted as code. The
PowerShell prompt `PS C:\> ` is only included to distinguish my input from the
output of the programs.

## Windows

### winget - Windows Package Manager

[Check its documentation.](https://learn.microsoft.com/en-us/windows/package-manager/)

#### Help text

```
PS C:\> winget
Windows Package Manager v1.4.10173
Copyright (c) Microsoft Corporation. All rights reserved.

The winget command line utility enables installing applications and other packages from the command line.

usage: winget  [<command>] [<options>]
```

#### Example

#### Install Python 3.11

```
PS C:\> winget install Python.Python.3.11
```

#### Upgrade all packages

```
PS C:\> winget upgrade --all
```

### Chocolatey - The Package Manager for Windows

Chocolatey is an alternative to winget with a bigger software repository.

[Check its website.](https://chocolatey.org/)

#### Example

##### Install Rclone

```
PS C:\> choco install licecap
```

##### Upgrade all packages

```
PS C:\> choco upgrade all
```

##### Rescale a video while preserving aspect ratio

```
PS C:\> ffmpeg -i original.mp4 -vf scale=-1:720 scaled.mp4
```

##### Reencode a video with default settings

```
PS C:\> ffmpeg -i original.mp4 reencoded.mp4
```

##### Convert a video format

```
PS C:\> ffmpeg -i original.mp4 converted.webm
```

## Media

### ImageMagick

[Check its website.](https://imagemagick.org/index.php)

#### Install

```
PS C:\> winget install ImageMagick.ImageMagick
```

#### Help text

```
PS C:\> magick --help
Help text: magick.exe tool [ {option} | {image} ... ] {output_image}
Help text: magick.exe [ {option} | {image} ... ] {output_image}
       magick.exe [ {option} | {image} ... ] -script {filename} [ {script_args} ...]
       magick.exe -help | -version | -usage | -list {option}
```

#### Example

```
PS C:\> magick some-gif.gif -scale 50% some-gif-scaled.gif
```

### youtube-dl

[Check its website.](https://youtube-dl.org/)

#### Install

```
PS C:\> winget install youtube-dl.youtube-dl
```

#### Help text

```
PS C:\> youtube-dl --help
Help text: youtube-dl [OPTIONS] URL [URL...]
```

#### Example

```
PS C:\> youtube-dl https://twitter.com/melchizedek420/status/1602505751079145473
```

## File management

### Rclone

[Check its website.](https://rclone.org/)

#### Install

```
PS C:\>Rclone.Rclone
```

#### Help text

```
PS C:\> rclone
Usage:
  rclone [flags]
  rclone [command]

Available Commands:
  [..]
  copy            Copy files from source to dest, skipping identical files.
  [..]
  sync            Make source and dest identical, modifying destination only.
  [..]

Use "rclone [command] --help" for more information about a command.
Use "rclone help flags" for to see the global flags.
Use "rclone help backends" for a list of supported services.
```

#### Example

```
PS C:\> rclone sync Pictures gdrive:Pictures --progress
```

## Terminal

### tldr

[Check its website.](https://tldr.sh/)

#### Install

```
PS C:\> choco install tldr
```

#### Example

```
PS C:\> tldr 7z

  7z

  File archiver with a high compression ratio.
  More information: https://www.7-zip.org.

  - [a]dd a file or directory to a new or existing archive:
    7z a path/to/archive.7z path/to/file_or_directory

  - Encrypt an existing archive (including filenames):
    7z a path/to/encrypted.7z -ppassword -mhe=on path/to/archive.7z

  - E[x]tract an archive preserving the original directory structure:
    7z x path/to/archive.7z

  - E[x]tract an archive to a specific directory:
    7z x path/to/archive.7z -opath/to/output

  - E[x]tract an archive to `stdout`:
    7z x path/to/archive.7z -so

  - [a]rchive using a specific archive type:
    7z a -t7z|bzip2|gzip|lzip|tar|zip path/to/archive.7z path/to/file_or_directory

  - [l]ist the contents of an archive:
    7z l path/to/archive.7z

  - List available archive types:
    7z i
```

### jq

A command-line JSON processor.

[Check its website.](https://stedolan.github.io/jq/)

#### Install

```
PS C:\> winget install stedolan.jq
```

#### Help text

```
PS C:\> jq --help
jq - commandline JSON processor [version 1.6]

[..]

jq is a tool for processing JSON inputs, applying the given filter to
its JSON text inputs and producing the filter's results as JSON on
standard output.

[..]

Example:

        $ echo '{"foo": 0}' | jq .
        {
                "foo": 0
        }
```

## Coding

### git-filter-repo

[Check its repository.](https://github.com/newren/git-filter-repo#how-do-i-install-it)

#### Install

```
PS C:\> pipx install git-filter-repo
```

#### Example

##### Attribute all commits to the given person

```
git filter-repo --name-callback "return b'moncheis'" --email-callback "return b'127621840+moncheis@users.noreply.github.com'"
```
