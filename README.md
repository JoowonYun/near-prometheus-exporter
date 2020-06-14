# Near Prometheus Exporter

This service exports various metrics from Near node for consumption by [Prometheus](https://prometheus.io). It uses [JSON-RPC](https://docs.near.org/docs/interaction/rpc) interface to collect the metrics. Inspired by [Ethereum Prometheus Exporter](https://github.com/31z4/ethereum-prometheus-exporter)

## Usage

    git clone https://github.com/masknetgoal634/near-prometheus-exporter

    cd near-prometheus-exporter

    sudo docker build -t near-prometheus-exporter .

```
sudo docker run -dit \
    --restart always \
    --name near-exporter \
    --network=host \
    -p 9333:9333 \
    near-prometheus-exporter:latest /dist/main -accountId <YOUR_POOL_ID>
```

By default the exporter serves on `:9333` at `/metrics`.

## Exported Metrics

| Name | Description |
| ---- | ----------- |
| near_block_number | The number of most recent block |
| near_epoch_block_produced_number | The number of blocks produced in epoch |
| near_epoch_block_expected_number | The number of block expected in epoch |
| near_seat_price | The current seat price |
| near_current_stake | The current stake of a given account id |
| near_sync_state | The current sync state of node |
| near_epoch_start_height | The epoch start height |
| near_version_number | The version number of the near node (float value) |
| near_version_build | The version build of the near node (float value) |
| near_dev_version_number | The dev node version number of the public rpc node (float value) |
| near_dev_version_build | The version build of of the public rpc node (float value) |

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
