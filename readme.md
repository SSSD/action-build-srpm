# Build source rpm from tarball and spec file

You can use this action to build a source rpm of given tarball and spec file.

## Inputs

### `tarball`

Path to the tarball. Required.

### `specfile`

Path to the spec file. Required.

## Outputs

### `path`

Absolute path to the created source rpm.

### `file`

Source rpm file name.

## Example usage

```yaml
- name: Build source rpm
  id: srpm
  uses: next-actions/build-srpm@master
  with:
    tarball: package-n-v-r.tar.gz
    specfile: package.spec

- name: Upload source rpm as an artifact
  uses: actions/upload-artifact@v2
  with:
    name: ${{ steps.srpm.outputs.file }}
    path: ${{ steps.srpm.outputs.path }}
```
