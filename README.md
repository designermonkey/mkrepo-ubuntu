# mkvhost for Ubuntu

Create a new git bare repository, connected to a virtualhost on your Ubuntu system.

This script links a bare git repository to a virtualhost on your ubuntu system, and allows you to push to the repo, and automatically deploy the files into your vhost.

## Note About File Location

This script defaults the location of any repository paths to `/data/git/*`. This is a personal preference to allow an easily accessible location to store sites on the server. This is done to also allow easy mounting of a filestore into the server to hold the repositories.

If this isn't to your tastes, you can override it with the `-s` or `--sites` option below, or modify the script.

## Installation

Clone the repo to a suitable location on your server like `/opt/mkrepo`

    git clone git://github.com/designermonkey/mkrepo-ubuntu.git /opt/mkrepo

Run the `install` script to create the correct links on your filesystem. This will make sure the script is callable from your command prompt without having to specify the path.

    /opt/mkrepo/install

## Usage

Once installed, usage couldn't be simpler.

    mkrepo [<options>] <reponame> <vhostname>

## Options
- `-h`, `--help` Shows this help screen.
- `-u`, `--user` Configure the username to give ownership of the repository.
- `-g`, `--group` Configure the group to give ownership of the repository.
- `-r`, `--repos` Configure the location of your repositories.
- `-s`, `--sites` Configure the location of your folder to contain the virtualhost http root.
- `-vv`, `--verbose` Output messages during processing.
- `-v`, `--version` Shows the version number for this script.
- `-t`, `--template` Specify a template file to use for the post-recieve hook


## Template
A custom template can be specified to use instead of the bundled simple template. There are specific values that are needed in the template to be replaced with values from the script.

- `USERNAME` Wherever you want the supplied or default user name to be placed inside the template.
- `GROUPNAME` Wherever you want the supplied or default group name to be placed inside the template.
- `WORKTREE` Wherever you want the supplied or default sites path to be placed inside the template.

## Vhostname
Name of the repository folder.

## Reponame

The name for the virtualhost to autmatically deploy to.

## License

The MIT License (MIT)

Copyright (c) 2013 John Porter

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
