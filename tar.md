Tar
===


Options
--------------------------------------------------
c – create new archive  
x – extract from archive  
v – verbose mode  
f – archive file name  
z – archive through gzip
j – archive through bzip2


Creating an archive
--------------------------------------------------

### tar archive
`tar cvf myarchive.tar dirname/`

### tar gzipped archive
`tar cvfz myarchive.tar.gz dirname/`

### tar bzipped archive
`tar cvfj myarchive.tar.bz2 dirname/`


Extracting an archive
--------------------------------------------------

### Extracting all files

#### tar archive
`tar xvf myarchive.tar`

#### tar gzipped archive
`tar xvfz myarchive.tar.gz`

#### tar bzipped archive
`tar xvfj myarchive.tar.bz2`

### Extracting a single file

#### tar archive
`tar xvf myarchive.tar /path/to/file`

#### tar gzipped archive
`tar xvfz myarchive.tar.gz /path/to/file`

#### tar bzipped archive
`tar xvfj myarchive.tar.bz2 /path/to/file`

### Extracting a single directory

#### tar archive
`tar xvf myarchive.tar /path/to/dir/`

#### tar gzipped archive
`tar xvfz myarchive.tar.gz /path/to/dir/`

#### tar bzipped archive
`tar xvfj myarchive.tar.bz2 /path/to/dir/`


Listing an archive
--------------------------------------------------

### tar archive
`tar tvf myarchive.tar`

### tar gzipped archive
`tar tvfz myarchive.tar.gz`

### tar bzipped archive
`tar tvfj myarchive.tar.bz2`