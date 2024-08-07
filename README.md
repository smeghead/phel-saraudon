# Saraudon

A command to Visualize result of `git log --stat`

## Description

It takes as input the commit history of the git repository (`git log --stat`) and outputs HTML content to visualize the information.
D3(https://d3js.org/) is used to display the graphs.

The tool uses `phel-lang`. There are no restrictions on target repositories.

This tool is experimental. So, what can be gained from what is visualized by this tool is a subject for future work.

## Install (composer)

```bash
$ composer require --dev smeghead/phel-saraudon
```

https://packagist.org/packages/smeghead/phel-saraudon

## Execute

Output analysis results for the last 20 commits.

```bash
$ git log --stat -n 20 | vendor/bin/saraudon -- src > output.html
```

Run the `git log` command which outputs the last 50 commit logs against the git repository in another directory, parse the results and save the html content in `output.html`.

```bash
$ $(vendor/bin/saraudon-git-log /usr/target-project) -n 50 | vendor/bin/saraudon -- src > output.html
```

`$(vendor/bin/saraudon-git-log /usr/target-project)`: `saraudon-git-log` generates a `git` command by specifying the target git directory. This can be followed by additional options for `git log`.

Run the `git log` command to output the commit log for tags v0.14.0 through v0.15.0 for the git repository in another directory, parse the results and save the html content in `output.html`.

```bash
$ $(vendor/bin/saraudon-git-log /usr/target-project) v0.14.0..v0.15.0 | vendor/bin/saraudon -- src > output.html
```

## Example

Visualization of the history of the last 50 commits of `php-class-diagram`.

[example-output-page](https://smeghead.github.io/phel-saraudon/example/output.html)

![example](example/output.jpg)

## Development

### docker

```bash
$ docker compose build 
$ docker compose run --rm php_cli bash
# composer install
```



