# The T.U.R.B.O. Switch Adapter
**Toy Upgrade for Resistance Bypass Optocoupler**

Developed by **[Faithful Fabricators](https://faithfulfabricators.org)**

---

## 🚀 The Mission
In the assistive technology community, many open-source switches (such as the 3D-printed Interact Switch) and switch-adapted toys (like dice rollers, penguin launchers, spinning bubble blowers, and dancing horses) suffer from a hidden enemy: **Voltage Drop**. 

When a high-current DC motor inside a toy is triggered through a long, thin 24 AWG assistive technology cable, the wire's internal electrical resistance chokes the current. This results in severe performance loss, stalling motors, and compromised play experiences.

The **T.U.R.B.O. Switch Adapter** is a universal, open-source hardware accessory that completely eliminates this bottleneck. By placing a high-current, optically-isolated solid-state buffer directly next to the toy's input jack, it delivers **lossless, maximum-performance play** using *any* standard accessibility switch, regardless of cable length or wire thickness.

---

## 🕹️ Key Features
* **100% Universal Compatibility:** Features a polarity-free, bidirectional solid-state output stage. It functions seamlessly on any switch-adapted toy on the market, whether it switches the positive terminal, the negative ground, or utilizes internal logic loops.
* **Indestructible Current Handling:** Built around a heavy-duty industrial photorelay capable of routing up to **5.0 Amps of continuous current** and absorbing up to **15.0 Amp startup surges** from stalling electric motors.
* **Complete Optical Isolation:** The switch loop and the toy loop are separated by a physical beam of light inside the chip. Electrical faults or short circuits inside a malfunctioning toy can never travel backward down the cable to damage a user's custom switch hardware.
* **Ultra-Low Voltage Drop:** The external switch loop is reduced to drawing a microscopic 5mA trigger pulse. Voltage drop across a 6-foot wire falls to essentially zero, completely restoring the toy's factory performance.
* **Keyfob Form Factor:** Designed to run autonomously on a single CR2032 coin cell battery, keeping the entire footprint smaller than a standard car key remote.

---

## 🛠️ How It Works
Classic adaptive setups force the thin switch wire to carry the heavy electrical load of the toy's motor. The T.U.R.B.O. Adapter splits the system into two entirely independent electrical environments:

1. **The Control Loop (Safe & Light):** When a user presses their accessibility switch, a tiny 5mA pulse flows from the internal CR2032 battery through the long cable. This pulse does not power the motor; it only illuminates a microscopic internal LED inside the adapter's chip.
2. **The Power Loop (Local & Strong):** The light from that LED instantly closes a high-power solid-state switch right at the toy's port. The toy's motor draws its heavy current locally from its own internal batteries over a distance of millimeters instead of feet, operating at maximum power.
