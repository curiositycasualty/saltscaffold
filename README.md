# saltscaffold

This python module creates a new directory structure for salt formulas with the following features:

* README.md with sample content
* state files that mimic the package / file / service pattern.
* .kitchen.yml with content to drive test-kitchen
* custom-pillar content to show pillar overrides
* defaults.yml content with default values
* map.jinja show how to have grains based overrides and merge defaults with custom pillars
* example of toggle feature
* The resulting formula will be testable with test-kitchen

## Folder and File Structure
Each salt formula you scaffold will create the following folder structure:
```
[formula_name]/
[formula_name]/README.md
[formula_name]/pillar-custom.sls
[formula_name]/[formula_name]
[formula_name]/[formula_name]/defaults.yaml
[formula_name]/[formula_name]/map.jinja
[formula_name]/[formula_name]/init.sls
[formula_name]/[formula_name]/install.sls
[formula_name]/[formula_name]/config.sls
[formula_name]/[formula_name]/service.sls
[formula_name]/[formula_name]/files/
[formula_name]/[formula_name]/files/[formula_name]_options.conf.j2
```

## Installing saltscaffold

You can view the source code on the [Bits Project Page](https://bits.linode.com/cmarzullo/saltscaffold)

### Install from source

  1. clone the repo `git clone https://bits.linode.com/cmarzullo/saltscaffold`
  2. make the packages `cd saltscaffold && python setup.py sdist`
  3. install the package `sudo pip install dist/Saltscaffold-<version>.tar.gz`

### Install from release

  1. Visit the [Bits Project Page](https://bits.linode.com/cmarzullo/saltscaffold)
  2. Click on Releases
  3. Download the latest release
  4. install the package `sudo pip install Saltscaffold-<version>.tar.gz`

## Running saltscaffold

The module gets installed as an executable python script. There aren't many options. You can only choose the name of the formula and an optional directory to create the formula in.
`saltscaffold -p myformula [-d {base directory} ]`

If you don't supply a base directory the formula will be created in your current directory.

## Contribution

Pull requests are welcome! The code is pretty ugly for generating the templates and could certainly use better reuse.
