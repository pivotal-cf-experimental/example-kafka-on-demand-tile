# Example Kafka On-Demand Tile for PCF

This project relies on the Pivotal Cloud Foundry Services SDK, available to customers and partners for download from the [Pivotal Network](https://network.pivotal.io/products/pivotal-cloud-foundry-services-sdk).

---

This is an example tile that allows Pivotal Cloud Foundry users to create dedicated Kafka clusters on-demand from the marketplace.

## Pre-requisites

- Pivotal Cloud Foundry Operations Manager [v1.8-RC4](https://network.pivotal.io/products/elastic-runtime#/releases/2184), or later
- Pivotal Cloud Foundry Elastic Runtime [v1.8.0-rc5](https://network.pivotal.io/products/ops-manager#/releases/2203), or later
- Ruby [v2.2](https://www.ruby-lang.org/en/downloads/), or later
- Vara [v0.22.0](https://rubygems.org/gems/vara/versions/0.22.0)

> NB: Elastic Runtime must be deployed before the Kafka on-demand tile is installed.

## Build tile

Clone the repository:

```sh
git clone git@github.com:pivotal-cf-experimental/example-kafka-on-demand-tile.git
cd example-kafka-on-demand-tile
```

Download the on-demand service broker from the Pivotal Network:

- Browse to https://network.pivotal.io/products/pivotal-cloud-foundry-services-sdk
- Download on-demand service broker v0.9.0
- Save `on-demand-service-broker-0.9.0.tgz` in `example-kafka-on-demand-tile/releases`

Build a tile:

```
bundle
bundle exec vara build-pivotal .
```

## Use tile

- Upload `example-kafka-on-demand-0.9.0.pivotal` to Pivotal Cloud Foundry Operations Manager.
- Configure the tile.
- Apply changes.

## Disclaimer

The Kafka service instances created with this tile may not behave correctly. However, the tile and its errands should work with Operations Manager, and it should be possible to create, update, bind, unbind and delete on-demand Kafka service instances in Pivotal Cloud Foundry.

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
