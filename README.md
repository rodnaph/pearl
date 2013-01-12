# Pearl - Easy Portfile Updates

Pearl is a super-simple script to make it a little bit easier to update your [Macports](https://macports.org) Portfile for your project.  It just automates the diffing of your current Portfile with the release version from the [Macports SVN](https://svn.macports.org) repository.

## Installation

You can install Pearl through Macports…

```bash
sudo port install pearl
```

If you're installing from source just clone the repository and put it in your $PATH.

## Usage

Just change to your project folder and run Pearl.

```bash
pearl
```

By default this assumes you have your Portfile in your repository root, and it will create a diff'd version named _Portfile-yourproject.diff_ (where the name of the project is guessed from the current directory).

You can then submit this file via the [Macports Trac](https://trac.macports.org) for an update.

## Configuration

This is handled by a small [YAML](http://yaml.org/) file in your project root named _.pearl.yml_.  Here are the options...

```yaml
# required
project_type:       devel

# optional
portfile:           path/to/Portfile
project_name:       my-project
```

## Other Options

Pearl support a few other options for helping you out updating your Portfile.
To get these options at any time just use the _help_ switch.

```
pearl --help
```

### Diff to Stdout

If you'd like to write the Portfile diff to STDOUT (useful to easily see it when
making changes) use the _stdout_ switch.

```
pearl --stdout
```

### Sync with Macports

Sometimes when submitting new Portfiles, or update patches, your Portfile will
be changed by one of the Macports admins before they commit it.  So it can be
useful to re-sync your Portfile with the master version in their repository.

```
pearl --sync
```

Be warned though - this will overwrite your local Portfile with no prompt.

Issues/Suggestions
------------------

Any bugs/features please submit them via [Github issues](https://github.com/rodnaph/pearl/issues).

