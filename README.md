# IoT26-HW05 - Home Assistant on Raspberry Pi

## 1. Objective

This assignment is to set up Home Assistant on Raspberry Pi and control LEDs using GPIO pins.

## 2. Hardware

- Raspberry Pi
- Breadboard
- 2 LEDs
- 2 resistors
- Jumper wires
- PC or laptop

## 3. Software

- Home Assistant OS
- Samba share add-on
- rpi_gpio custom integration

## 4. Setup Process

Home Assistant OS was installed on Raspberry Pi.  
After the initial setup, I accessed Home Assistant through a web browser and created a user account.

Samba share was installed to access the `configuration.yaml` file from Windows.

<img width="1439" height="853" alt="01_dashboard_switches" src="https://github.com/user-attachments/assets/0baa1d97-4556-4cee-80a6-52ef30d17b41" />

### 4.2 Samba Share Setup

The Samba share add-on was installed to access the Home Assistant configuration files from Windows.

Using Samba share, I accessed the `config` folder from my PC and edited the `configuration.yaml` file.

<img width="829" height="480" alt="02_samba_config_folder" src="https://github.com/user-attachments/assets/3f474115-5796-4547-ade3-0019103e6502" />


## 5. rpi_gpio Setup

The original tutorial used the `rpi_gpio` integration, but the current Home Assistant version did not support it by default.

So I installed the `ha-rpi_gpio` custom integration and copied the `rpi_gpio` folder to:

`/config/custom_components/rpi_gpio`

<img width="842" height="469" alt="03_rpi_gpio_custom_component" src="https://github.com/user-attachments/assets/84a82365-74cb-45f8-baf0-9fedeea15057" />


## 6. configuration.yaml

The following code was added to `configuration.yaml`.

```yaml
switch:
  - platform: rpi_gpio
    switches:
      - port: 11
        name: "Fan Office"
      - port: 12
        name: "Light Desk"

```
<img width="815" height="640" alt="04_configuration_yaml" src="https://github.com/user-attachments/assets/e132cd85-2d1e-4d87-b650-f627dcddd93f" />

## 7. result
<img width="3024" height="4032" alt="HW5" src="https://github.com/user-attachments/assets/2969a156-42fa-4703-8e2c-7eee7d4d864d" />


https://github.com/user-attachments/assets/ca34967c-e6ee-4c62-b510-8b4424b81bb4


