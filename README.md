# Example Kafka On-Demand Tile for PCF

This project relies on the Pivotal Cloud Foundry Services SDK, available to customers and partners for download from the [Pivotal Network](https://network.pivotal.io/products/pivotal-cloud-foundry-services-sdk).

---

This is an example tile that allows Pivotal Cloud Foundry users to create dedicated Kafka clusters on-demand from the marketplace.

## Pre-requisites

- Pivotal Cloud Foundry Operations Manager [v1.8.10](https://network.pivotal.io/products/ops-manager), or later
- Pivotal Cloud Foundry Elastic Runtime [v1.8.13](https://network.pivotal.io/products/elastic-runtime), or later
- One of:
  - Tile Generator [v9.0.2](http://docs.pivotal.io/tiledev/tile-generator.html), or later
  - Ruby [v2.2](https://www.ruby-lang.org/en/downloads/), or later and Vara [v0.22.0](https://rubygems.org/gems/vara), or later

> NB: Elastic Runtime must be deployed before the Kafka on-demand tile is installed.

## Build tile

Clone the repository:

```sh
git clone git@github.com:pivotal-cf-experimental/example-kafka-on-demand-tile.git
cd example-kafka-on-demand-tile
```

Download the on-demand service broker from the Pivotal Network:

- Browse to https://network.pivotal.io/products/on-demand-services-sdk/
- Download on-demand service broker v0.17.0
- Save `on-demand-service-broker-0.17.0.tgz` in `example-kafka-on-demand-tile/releases`

Build the tile:

### Using Tile Generator
```
tile build
```

### Using Vara
```
bundle
bundle exec vara build-pivotal .
```

## Use tile

- Upload `example-kafka-on-demand-0.17.0.pivotal` to Pivotal Cloud Foundry Operations Manager.
- Configure the tile.
- Apply changes.

## Compatibility

This example tile has been successfully tested against PCF versions 1.10 & 1.11

## Disclaimer

The Kafka service instances created with this tile may not behave correctly. However, the tile and its errands should work with Operations Manager, and it should be possible to create, update, bind, unbind and delete on-demand Kafka service instances in Pivotal Cloud Foundry.

## Releases used to make this tile:

- [Kafka Example Sevice Adapter Release](https://github.com/pivotal-cf-experimental/kafka-example-service-adapter-release)
- [Kafka Example Service Release](https://github.com/pivotal-cf-experimental/kafka-example-service-release)
- [On Demand Service Broker Release](https://network.pivotal.io/products/on-demand-services-sdk/)

---

README - PIVOTAL SDK - MODIFIABLE CODE NOTICE

The contents of this GitHub repository available at https://github.com/pivotal-cf-experimental/example-kafka-on-demand-tile are licensed to you
under the terms of the Pivotal Software Development Kit License Agreement ("SDK EULA")
and are designated by Pivotal Software, Inc. as "Modifiable Code."

Your rights to distribute, modify or create derivative works of all or portions of this
Modifiable Code are described in the Pivotal Software Development Kit License Agreement
("SDK EULA") and this Modifiable Code may only be used in accordance with the terms and
conditions of the SDK EULA.

Unless required by applicable law or agreed to in writing, this Modifiable Code is
provided on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either
express or implied. See the SDK EULA for the specific language governing permissions and
limitations for this Modifiable Code under the SDK EULA.
