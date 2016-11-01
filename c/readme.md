# Microsoft Azure IoT SDKs and libraries for C

This folder contains the following:
- Microsoft Azure IoT Hub device client SDK for C to connect devices running C code to Azure IoT Hub
- Microsoft Azure IoT Hub service client SDK for C to manage an Azure IoT Hub service instance from a C application
- Serializer library for C to help you serialize and deserialize data on your device.

The SDKs and library code:

* Is written in ANSI C (C99) to maximize code portability and broad platform compatibility.
* Avoids compiler extensions.
* In the device client SDK, the library exposes a platform abstraction layer to isolate OS dependencies (threading and mutual exclusion mechanisms, communications protocol e.g. HTTP). Refer to [porting guide](doc/porting_guide.md) for more information.

## Developing applications for Azure IoT

Visit [http://azure.com/iotdev](http://azure.com/iotdev) to learn more about developing applications for Azure IoT.

## How to use the Azure IoT SDKs for C

- **Using packages**: the simplest way to use our SDKs is to use the packages when available. The following packages are available:
  - **NuGet** for C (on Windows):
    - Device client: [Microsoft.Azure.IoTHub.IoTHubClient](https://www.nuget.org/packages/Microsoft.Azure.IoTHub.IoTHubClient)
  - **apt-get** for C (on Ubuntu 14.04, 15.04, 15.10, 16.04)
    - Device client: [ppa-azureiot](https://launchpad.net/~aziotsdklinux/+archive/ubuntu/ppa-azureiot)
- **Compiling the source**: when no package is available for your platform or if you want to modify the SDKs code, or port the SDKs to a new platform, then you can leverage the build environement provided in the repository.
    - Device client: [Azure IoT device SDK for C](c/readme.md)
    - Service client: [Azure IoT device SDK for C](c/readme.md)

--- 

## SDK folder structure

All C specific resources are located in the **azure-iot-sdks\c** folder. A description of the key directories follows:

### /c-utility, /uamqp, and /umqtt

These are git submodules that contain code, such as adapters and protocol implementations, shared with other projects. Note that some of them contain nested submodules.

### /blob

This folder contains client components that enable access to Azure blob storage.

### /certs

Contains certificates needed to communicate with Azure IoT Hub.

### /doc

This folder contains application development guides and device setup instructions.

### /build_all

This folder contains platform-specific build scripts for the client libraries and dependent components.

### /iothub_client

Contains Azure IoT Hub client components that provide the raw messaging capabilities of the library. Refer to the API documentation and samples for information on how to use it.

   * build: has one subfolder for each platform (e.g. Windows, Linux, Mbed). Contains makefiles, batch files, and solutions that are used to generate the library binaries.
   * devdoc: contains requirements, designs notes, manuals.
   * inc: public include files.
   * src: client libraries source files.
   * samples: contains the send event and receive message samples (with ports for the supported platforms).
   * tests: unit and end-to-end tests for source code.

### /serializer

Contains libraries that provide modeling and JSON serialization capabilities on top of the raw messaging library. These libraries facilitate uploading structured data and command and control for use with Azure IoT services. Refer to the API documentation and samples for information on how to use it.

   * build: has one subfolder for each platform (e.g. Windows, Linux, Mbed). Contains makefiles, batch files, and solutions that are used to generate the library binaries.
   * devdoc: contains requirements, designs notes, manuals.
   * inc: public include files.
   * src: client libraries source files.
   * samples: contains the send event and receive message samples (with ports for the supported platforms).
   * tests: unit tests and end-to-end tests for source code.

### /iothub_service_client

Contains libraries that enable interactions with the IoT Hub service to perform operations such as sending messages to devices and managing the device identity registry.

### /testtools

Contains tools that are currently used in testing the client libraries: Mocking Framework (micromock), Generic Test Runner (CTest), Unit Test Project Template, etc.

### /tools

Miscellaneous tools: compilembed, mbed_build, traceabilitytool (checks spec requirements vs code implementation).
