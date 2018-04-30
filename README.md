# Example Kafka On-Demand Tile for PCF

This project relies on the Pivotal Cloud Foundry Services SDK, available to customers and partners for download from the [Pivotal Network](https://network.pivotal.io/products/pivotal-cloud-foundry-services-sdk).

---

This is an example tile that allows Pivotal Cloud Foundry users to create dedicated Kafka clusters on-demand from the marketplace.

## Documentation

Documentation for this example can be found [here](https://docs.pivotal.io/svc-sdk/odb/tile.html)

## Pre-requisites

- Pivotal Cloud Foundry Operations Manager [v1.11](https://network.pivotal.io/products/ops-manager), or later
- Pivotal Application Service (PAS) [v1.11](https://network.pivotal.io/products/elastic-runtime), or later
- [Kiln](https://github.com/pivotal-cf/kiln)

> NB: PAS must be deployed before the Kafka on-demand tile is installed.

## Building the tile

- Clone this repository:
  ```sh
  $ git clone git@github.com:pivotal-cf-experimental/example-kafka-on-demand-tile.git
  $ cd example-kafka-on-demand-tile
  ```
- Download the latest on-demand service broker from [Pivnet](https://network.pivotal.io/products/on-demand-services-sdk/)
- Download the latest Consul release from [GitHub](https://github.com/cloudfoundry-incubator/consul-release/releases)
- Download the latest [Kafka Service Adapter Release](https://s3.amazonaws.com/cf-services-internal-builds/kafka-example-service-adapter/kafka-example-service-adapter-0.18.0.tgz)
 and [Kafka Service Release](https://s3.amazonaws.com/cf-services-internal-builds/kafka-service/kafka-example-service-0.18.0.tgz)
   - Note: ensure to download all releases to the same directory
- Build the tile
  ```sh
  $ ./bake \
    --releases-directory /path/to/releases/dir \
    --stemcell-version <target_stemcell> \
    --tile-version 1.0.0
  ```
 
## Use tile

- Upload `example-kafka-on-demand-1.0.0.pivotal` to Pivotal Cloud Foundry Operations Manager.
- Configure the tile.
- Apply changes.

## Compatibility

This example tile has been successfully tested against PCF versions 1.10, 1.11 and 2.0

## Disclaimer

The Kafka service instances created with this tile may not behave correctly. However, the tile and its errands should work with Operations Manager, and it should be possible to create, update, bind, unbind and delete on-demand Kafka service instances in Pivotal Cloud Foundry.

## Releases used to make this tile:

- [Kafka Example Sevice Adapter Release](https://github.com/pivotal-cf-experimental/kafka-example-service-adapter-release)
- [Kafka Example Service Release](https://github.com/pivotal-cf-experimental/kafka-example-service-release)
- [On Demand Service Broker Release](https://network.pivotal.io/products/on-demand-services-sdk/)
- [Consul Release](https://github.com/cloudfoundry-incubator/consul-release/releases)

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
