---
categories:
  - Electronics
---
This is *actually* a test of using [StackEdit.io](https://stackedit.io) to create blog posts directly.

Here is a photo of my Arduino Uno R3 with a DHT22 temperature and humidity sensor.
![Arduino UNO R3 with DHT22](https://lh3.googleusercontent.com/pw/ACtC-3fQxF82h3h0wkUZ0GbPpplJ9yohmTqoafmO2oP9P5JyKT61vkbR-D8t_D2dTvuMvtIYkzKkeUyiE7WyE2B3bSCaIGiimnMIsgLAeHmnmJAB6hXxDUf2Y6WM6RzV_YHPHTchR0tnSd-fdVzQInh_TBbiHg=w800-no-tmp.jpg)

As it is not WiFi enabled, it uses USB serial (emulation) to output the temperature and humidity with standard print statements. Then, with Node-Red running on Debian Buster (via crouton on a Chromebook), it uses MQTT to send the data to [io.adafruit.com](https://io.adafruit.com). Here is the flow:
![Node-Red flow](https://lh3.googleusercontent.com/pw/ACtC-3clHPUcPF8eltIy_acv0trip7yLWBX5IsQlRbZZ7IJx_qdWYFP1mjxo7IMGoaaIj7N3UoLQ8vMuC6ms81oAV-iQixWkd03VzKbUqSbHBisZqgan-wKAzoQsXuf6lJ7DiplO9icSMO5_hljb5FuHzRqxhQ=w800-no-tmp.jpg)

At Adafruit IO I created a "dashboard" to display the data: [https://io.adafruit.com/keithehenry/dashboards/humidity-and-temperature](https://io.adafruit.com/keithehenry/dashboards/humidity-and-temperature)

Credit to [Andreas Spiess](https://www.youtube.com/channel/UCu7_D0o48KbfhpEohoP7YSQ) for the inspiration. "Cool."

> Written with [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3ODQ1MTU1MjksLTE5NDQ1NzE0MTksLT
ExMDcyMDE4MiwtMTM0OTYzNTQ5NywyMDE3OTI5OTEsMTcwNjcw
Nzg4LDE4NzE5MDkxMDgsMjgxMjAzNzg2LDIyNjQ0NTEwNCwtMT
ExMzM5MDMyNV19
-->