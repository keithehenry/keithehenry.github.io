---
categories:
  - Electronics
---
This is *actually* a test of using [StackEdit.io](https://stackedit.io) to create blog posts directly.

Here is a photo of my Arduino Uno R3 with a DHT22 temperature and humidity sensor.
![Arduino UNO R3 with DHT22](https://lh3.googleusercontent.com/pw/ACtC-3fQxF82h3h0wkUZ0GbPpplJ9yohmTqoafmO2oP9P5JyKT61vkbR-D8t_D2dTvuMvtIYkzKkeUyiE7WyE2B3bSCaIGiimnMIsgLAeHmnmJAB6hXxDUf2Y6WM6RzV_YHPHTchR0tnSd-fdVzQInh_TBbiHg=w800-no-tmp.jpg)

As it is not WiFi enabled, it uses USB serial (emulation) to output the temperature and humidity with standard print statements. Then, with Node-Red running on Debian Buster (via crouton on a Chromebook), it uses MQTT to send the data to [io.adafruit.com](https://io.adafruit.com). Here is the flow:
![Node-Red flow](https://lh3.googleusercontent.com/yqZv4pVYtyqEtDhJScfomL82zgGS7fKfIeiE02Lya9ygY6iB3SQ3Q1kQnpmfyUpEigBzM6CQOzcRALx7orYfjN0JCtMuKt7sIO7y2w67thhfaETzl3aBR_tMl17dAW0Ml_iXBvYn8VEAWjF02KJSjnvei-b4xRikzBXSKdCa8c4zt8cVu1E-ksrwdfqNgDCzRtUksVQkReQ1sy2LfUK9SuFbRF3gSOaiepAzztzQrTTCSEEYlAHJj9tkR5_V8RVSVfzqYBYos9Cj-0LQR0FCEXi7Qsm49ZkMyqyi4CQy0hn4KWIoD73Ah24tebFDVnWlS6KQ_UWMJ92vIVZx2eoYCHpWDhyQA1CL5FI9u4Npddc1gWGTG0HO0cUCiFYP_PMXW_bnAWypAaQlqkmx6OW4XL1RKPehRyx6I-Z_LiE-XbTapI1IBlBJ25GblZTDyi3TSuDzEoMg65Pq061gT85gyRDGxculIgTlD119BVfkL959Wq9BDYU0VJpV7aVzz-Xm6VQRMA6IlRmQc386iKIGLz5rm7XtsQj3fHAmwFiSYS9RZsw9FuDnn1dE29T2xguQTYtUCiqtsIJisZEh-BLj2RQOFb4p1zKXVjQuvnvunUbSHrajDM4q1W8MX3We1rkA7BI4BwWm99ap8R0VhGWNiqnK50WVVUsO7gwhFWP7NSdkmnbywOvaNEsmIR9FXAI=w1000-no-tmp.jpg)

At Adafruit IO I created a "dashboard" to display the data: [https://io.adafruit.com/keithehenry/dashboards/humidity-and-temperature](https://io.adafruit.com/keithehenry/dashboards/humidity-and-temperature)

Credit to [Andreas Spiess](https://www.youtube.com/channel/UCu7_D0o48KbfhpEohoP7YSQ) for the inspiration. "Cool."

> Written with [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgzODgyNTYxOCwtMTEwNzIwMTgyLC0xMz
Q5NjM1NDk3LDIwMTc5Mjk5MSwxNzA2NzA3ODgsMTg3MTkwOTEw
OCwyODEyMDM3ODYsMjI2NDQ1MTA0LC0xMTEzMzkwMzI1XX0=
-->