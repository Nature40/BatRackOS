# BatRack OS
[![Build Images](https://github.com/Nature40/BatRackOS/actions/workflows/build_images.yml/badge.svg)](https://github.com/Nature40/BatRackOS/actions/workflows/build_images.yml)

BatRack is a multi-sensor device that combines ultrasonic audio recordings, automatic radio telemetry, and video camera recordings in a single modular unit. BatRack facilitates the individual or combined scheduling of sensors and includes a mutual triggering mode. It consists of off-the-shelf hardware and both its hardware blueprints and the required software have been published under an open license to allow scientists and practitioners to replicate the system. 

## Configuration

The system can be configured through different files in the `/boot` partition.

### `boot/cmdline.txt`

`cmdline.txt` holds the kernel boot commandline, which allows to configure the hostname in newer systemd versions. This behavioud is emulated and a hostname can be configured by setting `systemd.hostname=tRackIT-00001`

### [`/boot/radiotracking.ini`](boot/radiotracking.ini)

Hold the configuration of `pyradiotracking`, [see example config](https://github.com/Nature40/pyradiotracking/blob/master/etc/radiotracking.ini).

### [`/boot/mqttutil.conf`](boot/mqttutil.conf)

Mqttutil reports system statistics via MQTT, [see example config](https://github.com/Nature40/pymqttutil/blob/main/etc/mqttutil.conf).


### `/boot/wireguard.conf`

A wireguard configuration can be set using this configuration file. 

### [`/boot/mosquitto.d/`](boot/mosquitto.d/)

Files in this directory are loaded by mosquitto. E.g. mqtt brokers for reporting can be set using files in this folder.

## Scientific Usage & Citation

If you are using BatRack OS in academia, we'd appreciate if you cited our [scientific research paper](https://jonashoechst.de/assets/papers/gottwald2021batrack.pdf). Please cite as "Gottwald & Lampe et al."

> J. Gottwald, P. Lampe, J. Höchst, N. Friess, J. Maier, L. Leister, B. Neumann, T. Richter, B. Freisleben, and T. Nauss, “BatRack: An open-source multi-sensor device for wildlife research,” Methods in Ecology and Evolution, Jul. 2021.

```bibtex
@article{gottwald2021batrack,
  title = {{BatRack: An open-source multi-sensor device for wildlife research}},
  author = {Gottwald, Jannis and Lampe, Patrick and H{\"o}chst, Jonas and Friess, Nicolas and Maier, Julia and Leister, Lea and Neumann, Betty and Richter, Tobias and Freisleben, Bernd and Nauss, Thomas},
  journal = {Methods in Ecology and Evolution},
  publisher = {Wiley Online Library},
  month = jul,
  year = {2021},
  keywords = {Automatic Radio Tracking, Bats, Behavioural Ecology, Camera Traps, Multi-Sensor, Passive Acoustic Monitoring},
  doi = {10.1111/2041-210X.13672}
}
```
