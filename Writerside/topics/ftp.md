# ftp

<b>delfer/alpine-ftp-server</b> alpine docker ftp server image. This service is used to store files locally.
The volume of the ftp service is mapped to the host machine, so disk usage and maintenance are facilitated.

Here is the structure of the mapped ftp_data directory:

<code-block>
ftp_data
├── avatars
├── groups
├── justifications
└── userribs
</code-block>