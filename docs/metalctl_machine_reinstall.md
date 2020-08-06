## metalctl machine reinstall

reinstalls an already allocated machine

### Synopsis

reinstalls an already allocated machine. If it is not yet allocated, nothing happens, otherwise only the machine's primary disk
is wiped and the new image will subsequently be installed on that device

```
metalctl machine reinstall <machine ID> [flags]
```

### Options

```
  -d, --description string   description of the reinstallation. [optional]
  -h, --help                 help for reinstall
      --image string         id of the image to get installed. [required]
```

### Options inherited from parent commands

```
      --apitoken string        api token to authenticate. Can be specified with METALCTL_APITOKEN environment variable.
  -c, --config string          alternative config file path, (default is ~/.metalctl/config.yaml).
                               Example config.yaml:
                               
                               ---
                               apitoken: "alongtoken"
                               ...
                               
                               
      --debug                  debug output
  -f, --file string            filename of the create or update request in yaml format, or - for stdin.
                               Example image update:
                               
                               # metalctl image describe ubuntu-19.04 > ubuntu.yaml
                               # vi ubuntu.yaml
                               ## either via stdin
                               # cat ubuntu.yaml | metalctl image update -f -
                               ## or via file
                               # metalctl image update -f ubuntu.yaml
                               
      --kubeconfig string      Path to the kube-config to use for authentication and authorization. Is updated by login.
      --no-headers             do not print headers of table output format (default print headers)
      --order string           order by (comma separated) column(s), possible values: size|id|status|event|when|partition|project
  -o, --output-format string   output format (table|wide|markdown|json|yaml|template), wide is a table with more columns. (default "table")
      --template string        output template for template output-format, go template format.
                               For property names inspect the output of -o json or -o yaml for reference.
                               Example for machines:
                               
                               metalctl machine list -o template --template "{{ .id }}:{{ .size.id  }}"
                               
                               
  -u, --url string             api server address. Can be specified with METALCTL_URL environment variable.
```

### SEE ALSO

* [metalctl machine](metalctl_machine.md)	 - manage machines

###### Auto generated by spf13/cobra on 21-Jul-2020