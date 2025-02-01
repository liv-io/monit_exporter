# monit_exporter

<!-- shields.io -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

## Index

* [About](#about)
  * [Features](#features)
  * [Support](#support)
  * [Dependencies](#dependencies)
* [Setup](#setup)
  * [Requirements](#requirements)
  * [Installation](#installation)
  * [Update](#update)
* [Usage](#usage)
* [License](#license)
* [Credits](#credits)
* [Appendix](#appendix)

## About

monit_exporter periodically scrapes the monit status and provides its data via HTTP to Prometheus.

### Features

### Support

### Dependencies

This application is written in Go and has the following dependencies:
* [client_golang](github.com/prometheus/client_golang/prometheus)
* [logrus](github.com/sirupsen/logrus)
* [viper](github.com/spf13/viper)
* [charset](golang.org/x/net/html/charset)

## Setup

### Requirements

This application has the following build requirements:
* Git
* Go

### Installation

To build the application from source, simply run the following commands:
```
git clone https://github.com/liv-io/monit_exporter.git
cd monit_exporter
go build
```

### Update

To rebuild the application with the latest Go release, execute the following commands:
```
export GO_VERSION="1.23.5"
cd ~
curl --location https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gz --output ~/go${GO_VERSION}.linux-amd64.tar.gz
tar xzvf ~/go${GO_VERSION}.linux-amd64.tar.gz
sudo rm -rf /usr/local/src/go
sudo mv ~/go /usr/local/src
echo 'PATH=$PATH:/usr/local/src/go/bin:$GOPATH/bin' | sudo tee /etc/profile.d/go.sh
source /etc/profile.d/go.sh
go version

git clone https://github.com/liv-io/monit_exporter.git
cd ./monit_exporter/
rm -f go\.mod  go\.sum
sed -i "s@go-version: .*@go-version: ${GO_VERSION}@g" .github/workflows/release.yml
go mod init github.com/liv-io/monit_exporter
go mod tidy
```

## Usage

The application will load the `config.toml` file located in the same directory if present. Use the `-conf` flag to override the default configuration file name and location.

To run the application, simply execute the Go binary.

### Parameters ###

Parameter | Description | Type | Default
--- | --- | --- | ---
`listen_address` | address and port to bind | String | localhost:9388
`metrics_path` | relative path to expose metrics | String | /metrics
`ignore_ssl` | whether of not to ignore ssl errors | Boolean | false
`monit_scrape_uri` | uri to get monit status | String | http://localhost:2812/_status?format=xml&level=full
`monit_user` | user for monit basic auth, if needed | String | none
`monit_password` | password for monit status, if needed | String | none

## License

Distributed under the MIT License.

See `LICENSE` file for more information.

## Contact

Project: [monit_exporter](https://github.com/liv-io/monit_exporter)

## Credits

Acknowledgements:
* [commercetools](https://github.com/commercetools/monit_exporter)
* [delucks](https://github.com/delucks/monit_exporter)

<!-- shields.io -->
[contributors-shield]: https://img.shields.io/github/contributors/liv-io/monit_exporter.svg?style=flat
[contributors-url]: https://github.com/liv-io/monit_exporter/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/liv-io/monit_exporter.svg?style=flat
[forks-url]: https://github.com/liv-io/monit_exporter/network/members
[stars-shield]: https://img.shields.io/github/stars/liv-io/monit_exporter.svg?style=flat
[stars-url]: https://github.com/liv-io/monit_exporter/stargazers
[issues-shield]: https://img.shields.io/github/issues/liv-io/monit_exporter.svg?style=flat
[issues-url]: https://github.com/liv-io/monit_exporter/issues
[license-shield]: https://img.shields.io/github/license/liv-io/monit_exporter.svg?style=flat
[license-url]: https://github.com/liv-io/monit_exporter/blob/master/LICENSE
