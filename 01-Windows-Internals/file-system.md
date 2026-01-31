# NTFS File System

Has the following features:

## Journaling
Changes done to the metadata in the volume are logged. 

Helps the system recover from a crash or data movement due to defragmentation.

log location: `$LOGFILE in the volume's root directory`


## Access Control
Defines the owner of a file/directory and permissions for each user. 


## Volume Shadow Copy
Keeps track of changes made to a file. Using this feature, a user can restore previous file versions for recovery or system restore. 

## Alternate Data Streams (ADS)
Allows files to have multiple streams of data stored in a single file.


## Master File Table (MFT)
Structured database that tracks the objects stored in a volume. NTFS file system data is organized in the MFT.

Critical Files in MFT:

- **$MFT**: First record in the volume.
  Stores information about the clusters where all other objects present on the volume are located. Contains a directory of all the files present on the volume.

- **$LOGFILE**: stores the transactional logging of the file system
   It helps maintain the integrity of the file system in the event of a crash.

- **$UsnJrnl**: Contain info about  all the files that were changed in the file system and the reason for the change

## Tools to parse
- mftExplorer - quick GUI viewing
- MFTECmd - scripting and csv export

Command for MFTECmd: 
`MFTECmd.exe -f <path-to-$MFT-file> --csv <path-to-save-results-in-csv>`






