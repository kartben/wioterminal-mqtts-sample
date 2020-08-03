# Welcome to wioterminal-mqtt-sample 👋
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](/LICENSE)
[![Twitter: kartben](https://img.shields.io/twitter/follow/kartben.svg?style=social)](https://twitter.com/kartben)
[![Build Status](https://travis-ci.org/kartben/wioterminal-mqtts-sample.svg?branch=master)](https://travis-ci.org/kartben/wioterminal-mqtts-sample)

This sample application shows you how to use MQTT over TLS on the [Wio Terminal](https://www.seeedstudio.com/Wio-Terminal-p-4509.html) from Seeed Studio. 

As [PlatformIO](https://platformio.org/) [supports](https://docs.platformio.org/en/latest/boards/atmelsam/seeed_wio_terminal.html) the Wio Terminal, the sample comes in a form a PlatformIO project. This means that you don't have to worry about installing the [multiple Arduino libraries](https://wiki.seeedstudio.com/Wio-Terminal-Network-Overview/) the Wio Terminal requires for Wi-Fi & TLS, and you don't need to manually install the PubSubClient MQTT library either. All dependencies are automatically fetched from Github by the PlatformIO Library Manager.

In order to run the sample, just update the ``ssid`` and ``password`` variables in [``main.cpp``](src/main.cpp) with your Wi-Fi SSID and password.

```cpp
const char *ssid = "<your-ssid>";      // your network SSID
const char *password = "<your-password>"; // your network password
```

Use the [PlatformIO IDE](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide) (VS Code extension) or the [PlatformIO command-line interface](https://platformio.org/install/cli) to deploy the application to your Wio Terminal. 

Once running, the sample will connect to the public MQTT server running at ``mqtt.eclipse.org`` over TLS, publish "Hello from Wio Terminal" on the ``outTopic`` topic, and print on the serial output the contents of any message received on ``inTopic``.

If you'd like to use a different MQTT broker, you will need to update the ``test_root_ca`` variable accordingly (it should be set to the root CA for the server you want to connect to).

IMPORTANT: A mistake that is often done when using the PubSubClient for real-world project, is to not pay attention to the fact that, by default, it's defining a maximum MQTT message size of 256 bytes. Make sure to call ``PubSubClient::setBufferSize(size)`` with the desired message size if 256 bytes is not enough for your application.

## Author

👤 **Benjamin Cabé**

* Website: https://blog.benjamin-cabe.com
* Twitter: [@kartben](https://twitter.com/kartben)
* Github: [@kartben](https://github.com/kartben)
* LinkedIn: [@benjamincabe](https://linkedin.com/in/benjamincabe)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

Feel free to check [issues page](https://github.com/kartben/mxchip-serial-capture/issues).

## Show your support

Give a ⭐️ if this project helped you!


## 📝 License

Copyright &copy; 2020 [Benjamin Cabé](https://github.com/kartben).

This project is [MIT](/LICENSE) licensed.

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
