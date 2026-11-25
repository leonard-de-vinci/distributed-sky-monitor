# Distributed sky monitor with stereo vision

A demonstration of a low-cost, distributed sky observatory: two fisheye camera stations (a Jetson Orin
Nano and a Raspberry Pi) watch the whole sky, and their images are fused with aircraft transponder
signals (ADS-B), airport weather reports and open satellite data.

**Live demo:** <https://leonard-de-vinci.github.io/distributed-sky-monitor/>

## What it shows

- **Aircraft detection and identification** from 4,000 to 39,000 ft: a detector finds the aircraft in the
  fisheye images, a tracker follows it, and each track is matched to the aircraft's own ADS-B broadcast.
- **Contrail attribution:** which aircraft made which trail, drawn only where the camera actually saw it,
  tested against a control on air the aircraft had not reached yet.
- **Self-calibration:** each camera's orientation is fitted from the sun and from known aircraft
  positions, to a median pointing error of about 0.5°.
- **Two-station stereo:** cloud height from two cameras 1.4 km apart, checked against airport reports.
- **3D reconstruction:** five minutes of sky rebuilt in 3D (cloud base from stereo, cloud top from
  Meteosat, aircraft at their true altitudes), for a high cirrus sky and for broken low cloud. Drag to
  rotate; the model follows the camera video's clock.
- **Edge–cloud architecture:** detection runs on the devices; fusion, calibration and 3D reconstruction
  run on the cloud side.

## About this repository

This repository contains only the demonstration page and its media. All images, videos and numbers come
from the stations in November 2026. Station locations are deliberately not shown: ground and buildings
are masked out of the images and all 3D coordinates are relative to the stations.

Satellite products: EUMETSAT (Meteosat Cloud Top Height, MTG FCI imagery) via the EUMETView service.

Contact: Yiru Zhang, permanent teacher-researcher, ESILV.
