# ESP-AWS-IoT

> **IMPORTANT**: Please choose the branch of this repo, based on the [FreeRTOS-LTS release](https://github.com/FreeRTOS/FreeRTOS-LTS/releases) that you would like to base your application on.

If you are using the older (3.x.x) `aws-iot-device-sdk-embedded-C` release, please checkout the [`release/v3.1.x`](https://github.com/espressif/esp-aws-iot/tree/release/v3.1.x) branch.

This SDK enables AWS IoT cloud connectivity with ESP32-based platforms using the libraries provided as a part of the [AWS IoT Device Embedded C SDK](https://github.com/aws/aws-iot-device-sdk-embedded-C).

## Getting Started

- Please clone this branch of the repository using
    ```
    git clone -b "<name_of_the_release_branch>" --recursive https://github.com/espressif/esp-aws-iot
    ```
  For example: To clone just `release/202406.03-LTS`, you may run:
  ```
  git clone -b "release/202406.03-LTS" --recursive https://github.com/espressif/esp-aws-iot
  ```
- Please refer to https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html for setting up ESP-IDF
  - ESP-IDF can be downloaded from https://github.com/espressif/esp-idf/
  - This SDK supports `release/v5.5`, `release/v5.4`, `release/v5.3`, `release/v5.2`, `release/v5.1`, `release/v5.0` (expired), and `release/v4.4` (expired) of ESP-IDF.
  - Please set your branch to the IDF release that you would like to use, and pull in the latest changes.
  > **Note**: Please read [Support Policy](#support-policy) below for more details.
- Please refer to the [example README](examples/README.md) for more information on setting up examples.
- For a production-ready starting point for making applications that connect to AWS IoT Core using `esp-aws-iot`, refer to the [reference example](https://github.com/FreeRTOS/iot-reference-esp32).
- Please refer to the [Security Guide](https://github.com/espressif/esp-aws-iot/blob/release/202210.01-LTS/examples/ota/SecurityGuide.md) for steps to enable Security Features on your Espressif chip.
  - This SDK supports multiple ways to securely store the PKI credentials.
  - The default method is to use PKI credentials which are embedded in the binary, using the certs from the `certs/` in every example. 
  - For using Secure Element (ATECC608A), you will need to use [esp-cryptoauthlib](https://github.com/espressif/esp-cryptoauthlib#how-to-use-esp-cryptoauthlib-with-esp-idf).
  - The Security Guide includes detailed steps and pointers to configure and use the Digital Signature Peripheral on supported chips, using [esp_secure_cert_mgr](https://components.espressif.com/components/espressif/esp_secure_cert_mgr).

## Supported SoCs

The following table shows esp-aws-iot support with the ESP-IDF support of Espressif SoCs:  
Cell marked as ![supported][supported] denotes supported combination.  
Cell marked as ![expired][expired] denotes expired combination.

<table>
    <thead>
        <tr align="center">
            <th rowspan="2">SoC</th>
            <th rowspan="2">Supported IDF Version</th>
            <th colspan="2">esp-aws-iot Release</th>
        </tr>
        <tr align="center">
            <th><a href="https://github.com/espressif/esp-aws-iot/tree/master">master</a></th>
            <th><a href="https://github.com/espressif/esp-aws-iot/tree/release/202406.03-LTS">202406.03-LTS<br/><a href="https://github.com/espressif/esp-aws-iot/tree/release/202406.01-LTS">202406.01-LTS</a></th>
        </tr>
    </thead>
    <tbody>
        <tr align="center">
            <td rowspan="7">ESP32</td>
            <td>IDF v4.4</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.0</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.1</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.2</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.3</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.4</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td rowspan="7">ESP32-S2</td>
            <td>IDF v4.4</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.0</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.1</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.2</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.3</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.4</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td rowspan="7">ESP32-C3</td>
            <td>IDF v4.4</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.0</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.1</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.2</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.3</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.4</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td rowspan="7">ESP32-S3</td>
            <td>IDF v4.4</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.0</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.1</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.2</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.3</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.4</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td rowspan="6">ESP32-C2</td>
            <td>IDF v5.0</td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
            <td><img src="https://img.shields.io/badge/-expired-grey" alt="expired" width="50" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.1</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.2</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.3</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.4</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td rowspan="5">ESP32-C6</td>
            <td>IDF v5.1</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.2</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.3</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.4</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
        <tr align="center">
            <td rowspan="1">ESP32-C5</td>
            <td>IDF v5.5</td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
            <td><img src="https://img.shields.io/badge/-supported-green" alt="supported" width="65" height="20"></td>
        </tr>
    </tbody>
</table>

[supported]: https://img.shields.io/badge/-supported-green "supported"
[expired]: https://img.shields.io/badge/-expired-grey "expired"

## Support Policy


Support for `esp-aws-iot` release branches is based on a combination of the [IDF Release Support Schedule](https://github.com/espressif/esp-idf#esp-idf-release-support-schedule) and the FreeRTOS Long Term Support [Maintenance Period](https://github.com/FreeRTOS/FreeRTOS-LTS#freertosfreertos-long-term-support).


**Examples:**

1) IDF v5.1 in esp-aws-iot 202406.03-LTS → expires 30 December 2025, when IDF v5.1 reaches End-of-Life.

2) IDF v4.4 in esp-aws-iot 202406.03-LTS → expired July 2024, when IDF v4.4 [reached End-of-Life](https://www.espressif.com/sites/default/files/advisory_downloads/AR2024-008%20End-of-Life%20Advisory%20for%20ESP-IDF%20v4.4%20Release%20Branch%20EN.pdf).

3) Complete support for esp-aws-iot 202210.01-LTS → expired 31st October 2024, when FreeRTOS-LTS 202210.01-LTS [reached End-of-Life](https://github.com/FreeRTOS/FreeRTOS-LTS/tree/202210.01-LTS#freertosfreertos-long-term-support).
