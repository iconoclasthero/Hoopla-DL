.SYNOPSIS
    Downloads, decrypts and repackages content from Hoopla

.DESCRIPTION
    Uses a HooplaDigital.com account to download DRM-free copies of ebooks, comics,
    and/or audiobooks available on the platform. Content that is not already borrowed
    on the account will be borrowed if slots are available. Content that is not borrowed
    cannot be downloaded.

    * E-Books are downloaded to epub files (most) or cbz (rare, picture books).
    * Comic books are downloaded to cbz files.
    * Audiobooks are downloaded to m4a files. (single file, and very little metadata available
      from Hoopla, such as chapters)

.PARAMETER Credential
    Credential to use for logging into Hoopla site.
    (Cannot be used with Username and Password parameters)

.PARAMETER Username
    Username to use for logging into Hoopla site.
    (Cannot be used with Credential parameter)

.PARAMETER Password
    Password to use for logging into Hoopla site.
    (Cannot be used with Credential parameter)

.PARAMETER TitleId
    Specifies one or more title IDs of content to download.

.PARAMETER OutputFolder
    Sets the output folder for downloaded content. Defaults to current directory.

.PARAMETER PatronId
    Override default patron id for Hoopla. (This is rarely required as most user accounts are only tied
    to a single patron).

.PARAMETER EpubZipBin
    Specifies path to epubzip binary. Else look for one beside script, or in system path.

.PARAMETER FfmpegBin
    Specifies path to ffmpeg binary. Else look for one beside script, or in system path.

.PARAMETER KeepDecryptedData
    If set, don't delete the intermediary data after decryption, before final output file.
    For ebooks, this is xml, images, and the manifest. For comics, it is images. For audiobooks,
    it is mp4 ts files. This is typically only useful for development or troubleshooting.

.PARAMETER KeepEncryptedData
    If set, don't delete the encrypted data as downloaded from Hoopla's servers. This is typically
    only useful for development or troubleshooting.

.PARAMETER AllBorrowed
    This parameter is deprecated. If TitleId is not set, it is implied that all borrowed titles will
    be downloaded.

.PARAMETER AudioBookForceSingleFile
    If set, leave audiobook as single file, as if chapter data is not present.

.EXAMPLE
    .\hoopla-dl.ps1 123456
    Downloads Hoopla content with title id 123456

.NOTES
    Author: kabutops728 - My Anonamouse
    Version: 2.9
