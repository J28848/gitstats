# GITSTATS

This version was forked from [hoxu](https://github.com/hoxu/gitstats) and rewrite line calculate logic ref [ShawnMilo](https://github.com/ShawnMilo/gitstats)

## Features

### Support extensions filters, collect data since some date.

* __include extensions__
* __exclude extensions__
* __since date__
* 

## Usage Examples

### help

```
./gitstats --help

```

```
Usage: gitstats [options] <gitpath..> <outputpath>

Options:
-c key=value     Override configuration value

Default config values:
{'project_name': '', 'processes': 8, 'max_domains': 10, 'commit_begin': '', 'max_ext_length': 10, 'commit_end': 'HEAD', 'include_extensions': (), 'linear_linestats': 0, 'style': 'gitstats.css', 'max_authors': 20, 'exclude_extensions': ('png', 'gif', 'pdf', 'json', 'csv', 'jpg', 'sh', 'txt', 'lock', 'svg',  'md', 'woff2', 'hbm', 'gif'), 'authors_top': 5, 'exclude_directories': (), 'start_date': ''}

Please see the manual page for more details.

```

exclude / include extensions `js`, `jsx`, `java`, `php`.

```
./gitstat -c include_extensions='js,jsx,java,php' project_dir report_dir
```

### generate `project` report since `1 January, 2017` , store the report in dir `report_dir`

```
./gitstat -c start_date='1 January, 2017' project_dir report_dir

```

### multiple git repository support.

```

./gitstat project_dir1 project_di2 project_di3 ... report_dir

```

## Notes

- All MR commit will be **Ignored** in the line calculation.
- When include extensions was setted, exclude_extensions will be **Ignored**
- Default exclude extensions was setted. use `--help` to check default configuration.

