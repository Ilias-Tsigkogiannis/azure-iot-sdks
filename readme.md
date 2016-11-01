# Microsoft Azure IoT SDKs

This repository contains Azure IoT SDKs for devices, for service applications as well as samples and developer tools.

## Table of contents:

- [Developing applications for Azure IoT](#developing-applications-for-azure-iot)
- [How to clone the repository](#how-to-clone-the-repository)
- [How to use the Azure IoT SDKs](#how-to-use-the-azure-iot-sdks)
- [OS platforms and hardware compatibility](#os-platforms-and-hardware-compatibility)
- [Contribution, feedback and issues](#contribution-feedback-and-issues)
- [Support](#support)
- [Additional resources](#additional-resources)

## Developing applications for Azure IoT

Visit [http://azure.com/iotdev](http://azure.com/iotdev) to learn more about developing applications for Azure IoT.

## How to clone the repository

The repository is using [GitHub Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for its dependencies. In order to automatically clone these submodules, you need to use the --recursive options as described here:

```
git clone --recursive https://github.com/Azure/azure-iot-sdks.git 
```

## How to use the Azure IoT SDKs

- **Using packages**: the simplest way to use our SDKs is to use the packages when available. The following packages are available:
  - **npm** for Node v0.10+: 
    - Device client: [azure-iot-device](https://www.npmjs.com/package/azure-iot-device),
    - Service client: [azure-iothub](https://www.npmjs.com/package/azure-iothub)
  - **NuGet** for C (on Windows):
    - Device client: [Microsoft.Azure.IoTHub.IoTHubClient](c/iothub_client/readme.md#nugetpackage)
  - **Nuget** for .Net (.Net 4.5+, UWP, PCL, Xamarin): 
    - Device client: [Microsoft.Azure.Devices.Client](https://www.nuget.org/packages/Microsoft.Azure.Devices.Client/)
    - Service client: [Microsoft.Azure.Devices](https://www.nuget.org/packages/Microsoft.Azure.Devices)
  - **apt-get** for C (on Ubuntu 14.04, 15.04, 15.10, 16.04)
    - Device client: [ppa-azureiot](c/iothub_client/readme.md#aptgetpackage)
  - **maven** for Java 1.7+
    - Service client: [iothub-jave-service-client](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.microsoft.azure.iothub-java-client%22%20AND%20a%3A%22iothub-java-service-client%22)
    - Device client: [iothub-java-device-client](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.microsoft.azure.iothub-java-client%22%20AND%20a%3A%22iothub-java-device-client%22)
  - **PyPI** for Python (2.7.x, 3.4.x and 3.5.x)
    - Device client: [iothub-client](https://pypi.python.org/pypi/iothub-client/)
 
- **Compiling the source**: when no package is available for your platform or if you want to modify the SDKs code, or port the SDKs to a new platform, then you can leverage the build environement provided in the repository.
    - **C**
        - Device client: [Azure IoT device SDK for C](c/iothub_client/readme.md#compile)
        - Service client: [Azure IoT device SDK for C](c/iothub_service_client/readme.md#compile)
    - **JavaScript** for Node
        - Device client: [Azure IoT device SDK for Node.js](node/device/core/readme.md)
        - Service client: [Azure IoT service SDK for Node.js](node/service/README.md)
    - **Java**
        - Device client: [Azure IoT device SDK for Java](java/device/readme.md)
        - Service client: [Azure IoT service SDK for Java](java/service/readme.md)
    - **JavaWrapper**
    - **C#** for .Net
        - Device client: [Azure IoT device SDK for .NET](csharp/device/readme.md)
        - Service client: [Azure IoT service SDK for .NET](csharp/service/README.md)
    - **Python**
        - Device client: [Azure IoT device SDK for Python](python/device/readme.md)

## OS platforms and hardware compatibility

Azure IoT device SDKs can be used with a broad range of OS platforms and devices. The minimum requirements are for the device platform to support the following:

- **Being capable of establishing an IP connection**: only IP-capable devices can communicate directly with Azure IoT Hub.
- **Support TLS**: required to establish a secure communication channel with Azure IoT Hub.
- **Support SHA-256**: necessary to generate the secure token for authenticating the device with the service.
- **Have a Real Time Clock or implement code to connect to an NTP server**: necessary for both establishing the TLS connection and generating the secure token for authentication.
- **Having at least 64KB of RAM**: the memory footprint of the SDK depends on the SDK and protocol used as well as the platform targeted. The smallest footprint is achieved using the C SDK targeting microcontrollers.

You can find an exhaustive list of the OS platforms the various SDKs have been tested against in the [Azure Certified for IoT device catalog](https://catalog.azureiotsuite.com/).

Note that you might still be able to use the SDKs on OS and hardware platforms that are not listed on this page: all the SDKs are open sourced and designed to be portable. If you have suggestions, feedback or issues to report, refer to the Contribution and Support sections below.

## Contribution, feedback and issues

If you encounter any bugs, have suggestions for new features or if you would like to become an active contributor to this project please follow the instructions provided in the [contribution guidelines](CONTRIBUTING.md).

## Support

If you are having issues using one of the packages or using the Azure IoT Hub service that go beyond simple bug fixes or help requests that would be dealt within the [issues section](https://github.com/Azure/azure-iot-sdks/issues) of this project, the Microsoft Customer Support team will try and help out on a best effort basis.
To engage Microsoft support, you can create a support ticket directly from the [Azure portal](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade).
Escalated support requests for Azure IoT Hub SDKs development questions will only be available Monday thru Friday during normal coverage hours of 6 a.m. to 6 p.m. PST.
Here is what you can expect Microsoft Support to be able to help with:
* **Client SDKs issues**: If you are trying to compile and run the libraries on a supported platform, the Support team will be able to assist with troubleshooting or questions related to compiler issues and communications to and from the IoT Hub.  They will also try to assist with questions related to porting to an unsupported platform, but will be limited in how much assistance can be provided.  The team will be limited with trouble-shooting the hardware device itself or drivers and or specific properties on that device. 
* **IoT Hub / Connectivity Issues**: Communication from the device client to the Azure IoT Hub service and communication from the Azure IoT Hub service to the client.  Or any other issues specifically related to the Azure IoT Hub.
* **Portal Issues**: Issues related to the portal, that includes access, security, dashboard, devices, Alarms, Usage, Settings and Actions.
* **REST/API Issues**: Using the IoT Hub REST/APIs that are documented in the [documentation]( https://msdn.microsoft.com/library/mt548492.aspx).

## Additional resources

In addition to the language SDKs, this repository ([azure-iot-sdks](https://github.com/Azure/azure-iot-sdks)) contains the following folders:

### /build

This folder contains various build scripts to build the libraries.

### /doc

This folder contains the following documents that are relevant to all the language SDKs:

- [Set up IoT Hub](doc/setup_iothub.md) describes how to configure your Azure IoT Hub service.
- [Manage IoT Hub](doc/manage_iot_hub.md) describes how to provision devices in your Azure IoT Hub service.
- [FAQ](doc/faq.md) contains frequently asked questions about the SDKs and libraries.
- [Azure Certified for IoT device catalog](https://catalog.azureiotsuite.com/).

### /tools

This folder contains tools you will find useful when you are working with IoT Hub and the device SDKs.
- [iothub-explorer](tools/iothub-explorer/readme.md): describes how to use the iothub-explorer node.js tool to provision a device for use in IoT Hub, monitor the messages from the device, and send commands to the device.
- [Device Explorer](tools/DeviceExplorer/readme.md): this tool enables you to perform operations such as manage the devices registered to an IoT hub, view device-to-cloud messages sent to an IoT hub, and send cloud-to-device messages from an IoT hub. Note this tool only runs on Windows.
- [iothub-diagnostics](tools/iothub-diagnostics/readme.md): this tool is provided to help diagnose issues with a device connecting to Azure IoT Hubs.

---
This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
