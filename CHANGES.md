# CHANGES

This file lists changes made to monit_exporter. It follows semantic versioning
guidelines. The content is sorted in reverse chronological order and formatted
to allow easy grepping by scripts.

The headers are:
- bugs
- changes
- enhancements
- features

## 0.2.3 (2025-02-01)

### Enhancements

- Build monit_exporter with Go version 1.23.5

## 0.2.2 (2023-10-22)

### Enhancements

- Build monit_exporter with Go version 1.21.3

## 0.2.1 (2023-07-27)

### Enhancements

- Build monit_exporter with Go version 1.20.6

## 0.2.0 (2023-04-11)

### Changes

- Rebuild monit_exporter for OpenBSD 7.3

### Enhancements

- Build monit_exporter with Go version 1.20.3
- Resolve GoReleaser deprecation notices \
  `--rm-dist` has been deprecated in favor of `--clean` \
  `replacements` will be removed from the `archives` section

## 0.1.0 (2020-11-29)

### Bugs

- Add promhttp dependency (prometheus.Handler deprecated by promhttp.Handler)
- Improve error handling if close body is not nil

### Enhancements

- Return descriptive error message with HTTP response status codes
- Remove white spaces from service types

## 0.0.2 (2017-10-16)

### Features

- Change deploy key

## 0.0.1 (2017-09-22)

### Features

- First working release
