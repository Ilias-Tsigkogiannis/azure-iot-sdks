# Microsoft Azure IoT device SDK for C

This folder contains the Microsoft Azure IoT device client SDK to easily and securely connect devices to the Microsoft Azure IoT Hub service.
It also contains samples that show how to use its various features.
To meet the wide range of device requirements in the Internet of Things space, the C libraries are provided in source code form to support multiple form factors, operating systems, tools sets, protocols and communications patterns widely in use today.

## Features

 * Sends event data to Azure IoT based services.
 * Maps server commands to device functions.
 * Buffers data when the network connection is down.
 * Batches messages to improve communication efficiency.
 * Supports pluggable transport protocols. HTTPS, AMQP and MQTT are the protocols currently available now.
 * Supports pluggable serialization methods. JSON serialization is available now.

The library code:

* Is written in ANSI C (C99) to maximize code portability and broad platform compatibility.
* Avoids compiler extensions.
* Exposes a platform abstraction layer to isolate OS dependencies (threading and mutual exclusion mechanisms, communications protocol e.g. HTTP). Refer to [porting guide](doc/porting_guide.md) for more information.

Azure IoT device SDK for C can be used with a broad range of OS platforms and devices. For a list of tested configurations [click here](https://catalog.azureiotsuite.com/).

<a name="nugetpackage"/>
## How to use the NuGet packages on Windows devices

<a name="aptgetpackage"/>
## How to use the apt-get packages on Linux devices

<a name="compile"/>
## How to compile the C SDKs
[Prepare your development environment to use the Azure IoT device SDK for C](doc/devbox_setup.md)


## Reference documentation
For information on how to use this library refer to the documents below:

- [Setup IoT Hub](../doc/setup_iothub.md)
- [Provision and manage devices](../doc/manage_iot_hub.md)
- [Azure IoT device SDK for C  tutorial](https://azure.microsoft.com/documentation/articles/iot-hub-device-sdk-c-intro/)
- [Setup a Protocol Gateway - (i.e. MQTT)](https://github.com/Azure/azure-iot-protocol-gateway/blob/master/README.md)
- [How to port the C libraries to other OS platforms](doc/porting_guide.md)
- [Cross compilation example](doc/SDK_cross_compile_example.md)
- [C API reference](http://azure.github.io/azure-iot-sdks/c/api_reference/index.html)

For guides on how to run the sample applications on supported platforms, check out in this [folder](../../doc/get_started/).