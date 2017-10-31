# parse_yaml

A simple Bash script that parses a YAML file and return the output in `key=value` pair. Also has an option to add prefix to each key. 

# History
The bash source code was [initially provided in Stackoverflow](https://stackoverflow.com/a/21189044/399759) by [Stefan Farestam](https://stackoverflow.com/users/1792684/stefan-farestam). The code was [further modified to support parsing of arrays](https://gist.github.com/epiloque/8cf512c6d64641bde388).  

Finally I changed the bash function into a command. For [Homebrew users](http://brew.sh), you can install it

```
$ brew install hanxue/cmd/parse_yaml
```

# Sample Output
You can use [sample.yml](sample.yml) to test the command. 

```
$ ./parse_yaml sample.yml 
development_adapter=("mysql2")
development_encoding=("utf8")
development_database=("my_database")
development_username=("root")
development_apt+=("somepackage")
development_apt+=("anotherpackage")
```

With prefix

```
$ ./parse_yaml sample.yml "CONF_"
CONF_development_adapter=("mysql2")
CONF_development_encoding=("utf8")
CONF_development_database=("my_database")
CONF_development_username=("root")
CONF_development_apt+=("somepackage")
CONF_development_apt+=("anotherpackage")
```