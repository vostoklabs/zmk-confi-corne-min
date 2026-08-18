# Corne Min ZMK Firmware Builds

This repository produces firmware for two different Corne Min configurations:

* **Standard Split** — The left half acts as the central device and communicates directly with your computer over USB or Bluetooth.
* **Prospector Dongle** — A Prospector USB dongle acts as the central device, while both keyboard halves operate as BLE peripherals.

---

## Sleep Behaviour

Deep sleep is enabled by the `corne_min` board module, and ZMK's default is to
power the halves down after **15 minutes** of inactivity. Waking from deep sleep
is a full boot plus a BLE reconnect, which is the delay before you can type
again after a break.

[`config/corne_min_left.conf`](config/corne_min_left.conf) and
[`config/corne_min_right.conf`](config/corne_min_right.conf) raise that timeout
to **12 hours**, so the keyboard stays instantly ready through the day and only
sleeps if it is left untouched overnight. Both files carry the same setting —
each half runs its own sleep timer, so edit them together.


<br>


---

<details open>
<summary><strong>Standard Firmware</strong></summary>


### `corne_min_left_with_studio.uf2`

Firmware for the **left (central)** half of the Corne Min.

**Features**

* [ZMK Studio support](https://zmk.studio/)
* Experimental BLE connection

Use this build if you want to configure your keyboard with ZMK Studio.

---

### `corne_min_left_with_studio_and_peripheral_battery_reporting.uf2`

Firmware for the **left (central)** half with battery reporting from the peripheral half.

**Features**

* [ZMK Studio support](https://zmk.studio/)
* Experimental BLE connection
* Peripheral battery level reporting

---

### `corne_min_right.uf2`

Firmware for the **right (peripheral)** half.

**Features**

* Experimental BLE connection

Flash this alongside one of the left-half firmware variants above.

</details>

---

<details>
<summary><strong>Prospector Dongle Firmware</strong></summary>


### `prospector_for_corne_min.uf2`

Firmware for the Prospector USB dongle.

**Features**

* [ZMK Studio support](https://zmk.studio/)

---

### `corne_min_left_for_prospector.uf2`

Firmware for the **left** keyboard half.

---

### `corne_min_right_for_prospector.uf2`

Firmware for the **right** keyboard half.

</details>

---

<details>
<summary><strong>Settings Reset Firmware</strong></summary>


### `prospector_settings_reset.uf2`

Clears all stored settings and Bluetooth bonds on the Prospector dongle.

---

### `corne_min_settings_reset.uf2`

Clears all stored settings and Bluetooth bonds on a Corne Min half.

After flashing a reset image, flash the desired firmware again before using the device.

</details>
