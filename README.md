# findImport() bug related to .gitignore files outside of the current repo

## Setup
- Select an appropriate node version, e.g. 18.19.1
- Execute `npm ci`

## Expected behavior
- Executing `npm run build` succeeds.
- Executing `npm run graph` shows that lib1 depends on lib2.

## Steps to reproduce the bug

- Add a `.gitignore` file with the line `classes` to the parent folder of this repository with `echo 'classes' >> ../.gitignore`.
- Executing `npm run build` fails.
- Executing `npm run graph` does not show that lib1 depends on lib2.
