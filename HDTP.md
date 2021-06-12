# HDTP (HYDIN Document Transfer Protocol)

## HYDIN addresses

HYDIN addresses consist of a location part and a document path part, separated by a colon.

Location part generally starts with a hostname or address of a HYDIN server.

```
<SERVER>[/<LOCATION>]:/<DOCUMENT>
```

`example.edu:/departments/cs/faculty/jrandomhacker/projects/megalisp`

```
(Document /departments/cs/faculty/jrandomhacker/projects/megalisp
       on server example.edu)
```

`192.0.2.45:/test/page` (Document `/test/page` on server 192.0.2.45)

### Sub-locations

A server address MAY be followed by a location path, to indicate a sub-location on a server.

HYDIN servers may host multiple independent sites. In this case sites can be separated by a "location path"
(this is distinct from a document path that is placed after the colon).

`example.edu/users/jrandomhacker:/projects/megalisp`

```
(Document /projects/megalisp
 of the site /users/jrandomhacker
 on server example.edu)
```

### Foreign transports

Foreign protocol address is placed in square brackets, in place of the location part.

Degenerate foreign transport: HYDIN listening on a non-standard port: `[example.net:9090]:/about`

HYDIN over HTTP: `[http://example.net/~jrandomhacker]:/projects/megalisp`

Foreign protocol addresses may contain nested square brackets. This is required for IPv6 addresses,
so this monstrosity is, sadly, valid—it has to be:

```
[http://[2001:db8::1]:9090]:/about
```

## Protocol operations

* GET (retrieves a document)
* LIST (lists all child nodes under a path)
* MAP (retrieves a machine-readable map of a path)
* INFO (retrieves resource information)

### GET

The GET method retrieves a document.


### LIST

`LIST /projects`

```
["megalisp"]
```

### MAP

`MAP /`

```
{"projects": [
    {"megalisp": ["about", "downloads", "docs"]}
  ]
}
```

### INFO

```
INFO /

Description: jrandomhacker's website
Contact: J. Random Hacker <jrandomhacker@example.net>
```

```
INFO /files/cat.png

Type: image/png
Size: 45k
```
