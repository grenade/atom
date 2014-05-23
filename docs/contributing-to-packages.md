# Contributing to Official Atom Packages

If you think you know which package is causing the issue you are reporting, feel
free to open up the issue in that specific repository instead. When in doubt
just open the issue here but be aware that it may get closed here and reopened
in the proper package's repository.

## Hacking on Packages

### Cloning

The first step is creating your own clone. You can of course do this manually
with git, or you can use the `apm develop` command to create a clone based on
the package's `repository` field in the `package.json`.

For example, if you want to make changes to the `tree-view` package, run the
following command:

```
> apm develop tree-view
Cloning https://github.com/atom/tree-view ✓
Installing modules ✓
~/.atom/dev/packages/tree-view -> ~/github/tree-view
```

This clones the `tree-view` repository to `~/github`. If you prefer a different
path, specify it via the `ATOM_REPOS_HOME` environment variable.

### Running in Development Mode

Editing a package in Atom is a bit of a circular experience: you're using Atom
to modify itself. What happens if you temporarily break something? You don't
want the version of Atom you're using to edit to become useless in the process.
For this reason, you'll only want to load packages in **development mode** while
you are working on them. You'll perform your editing in **stable mode**, only
switching to development mode to test your changes.

To open a development mode window, use the "Application: Open Dev" command,
which is normally bound to `cmd-shift-o`. You can also run dev mode from the
command line with `atom --dev`.

To load your package in development mode, create a symlink to it in
`~/.atom/dev/packages`. This occurs automatically when you clone the package
with `apm develop`. You can also run `apm link --dev` and `apm unlink --dev`
from the package directory to create and remove dev-mode symlinks.

### Installing Dependencies

Finally, you need to install the cloned package's dependencies by running
`apm install` within the package directory. This step is also performed
automatically the first time you run `apm develop`, but you'll want to keep
dependencies up to date by running `apm update` after pulling upstream changes.