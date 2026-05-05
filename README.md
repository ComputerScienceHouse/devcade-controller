
## Pin-out
For the pin out of a Raspberry Pi Pico see: https://pip-assets.raspberrypi.com/categories/610-raspberry-pi-pico/documents/RP-008309-DS-1-Pico-R3-A4-Pinout.pdf?disposition=inline
```Rust
//             Name           Color
// Player one  
pins.gpio10 // A4             White
pins.gpio11 // A3             Green
pins.gpio17 // B1             Purple
pins.gpio16 // B2             Purple
pins.gpio13 // A1             Red
pins.gpio12 // A2             Blue
pins.gpio9  // Start button   Black
pins.gpio27 // Joystick North 
pins.gpio26 // Joystick West
pins.gpio22 // Joystick East
pins.gpio28 // Joystick South
pins.gpio15 // B3             Purple
pins.gpio14 // B4             Purple
// Player two
pins.gpio3  // A4             White
pins.gpio2  // A3             Green
pins.gpio4  // B1             Yellow
pins.gpio5  // B2             Yellow
pins.gpio6  // A1             Red
pins.gpio7  // A2             Blue
pins.gpio8  // Start button   Black
pins.gpio20 // Joystick North
pins.gpio19 // Joystick West
pins.gpio18 // Joystick East
pins.gpio21 // Joystick South
pins.gpio0  // B3             Yellow
pins.gpio1  // B4             Yellow

```
## Installation to a Pi Pico
### Software requirements:
- picotool
- `rustup target add thumbv6m-none-eabi`
- `cargo install flip-link`
### Building:
```bash
cargo build --release
```
### Loading into the controller:
Hold `bootsel` while plugging in the Pi Pico and then run:
```bash
cd target/thumbv6m-none-eabi/release
mv devcade-controller devcade-controller.elf
picotool load -v devcade-controller.elf
```