### PPS over GPIO patch for linux kernel 3.4

This is a patch for pps-gpio module to enable GPIO pin config during module
loading.

It is based on the [PPS patch for Raspberry Pi][RPI_PPS].

The patched pps-gpio module accept three parameters:

- gpio_pin: the GPIO pin number, default to use pin 18.
- falling_edge: rising / falling edge of PPS signal, default to 0, meaning
  rising edge.
- capture_clear: PPS capture clear, default to 0.

## Usage

Add a line
```
pps-gpio
```
to /etc/modules

and specify the pin number by create a new file, /etc/modprobe.d/pps-gpio.conf,
with following content:
```
options pps-gpio gpio_pin=Your_PPS_GPIO_PIN
```



[RPI_PPS]: https://github.com/lampeh/rpi-misc
