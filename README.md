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
* **Significant Current Handling:** Built around a heavy-duty industrial photorelay capable of routing up to **5.0 Amps of continuous current** and absorbing up to **15.0 Amp startup surges** from stalling electric motors.
* **Complete Optical Isolation:** The switch loop and the toy loop are separated by a physical beam of light inside the chip. Electrical faults or short circuits inside a malfunctioning toy can never travel backward down the cable to damage a user's custom switch hardware.
* **Ultra-Low Voltage Drop:** The external switch loop is reduced to drawing a microscopic 5mA trigger pulse. Voltage drop across a 6-foot wire is mitigated, significantly restoring the toy's factory performance.
* **Keyfob Form Factor:** Designed to run autonomously on a single CR2032 coin cell battery, keeping the entire footprint smaller than a standard car key remote.

---

## 🛠️ How It Works
Classic adaptive setups force the thin switch wire to carry the heavy electrical load of the toy's motor. The T.U.R.B.O. Adapter splits the system into two entirely independent electrical environments:

1. **The Control Loop (Safe & Light):** When a user presses their accessibility switch, a tiny 5mA pulse flows from the internal CR2032 battery through the long cable. This pulse does not power the motor; it only illuminates a microscopic internal LED inside the adapter's chip.
2. **The Power Loop (Local & Strong):** The light from that LED instantly closes a high-power solid-state switch right at the toy's port. The toy's motor draws its heavy current locally from its own internal batteries over a distance of millimeters instead of feet, operating at maximum power.

```
[INPUT CONTROL LOOP - Low Current]             [OUTPUT POWER LOOP - High Current][Interact Switch]                      ┌──► [Any Toy Jack Contact A]│                               │(6ft Cable)     (Optical Isolation)  ││                ░░░░           │  (Handles up to 5A continuous)▼                 █             │  (Polarity free / Bidirectional)[Internal LED] ───────► █ ────────────┴──► [Any Toy Jack Contact B](Requires ~5mA)         ██ (PhotoMOSFET Switch)
```

---

## 📦 Bill of Materials (BOM)

Total cost per unit is approximately **$11.00 – $14.00** for prototypes, dropping to **~$8.00** when components are batch-purchased in quantities of 50+.


| Component | Description | Suggested Part Number | Quantity |
| :--- | :--- | :--- | :--- |
| **High-Current Photorelay** | 8-Pin DIP Optocoupler (5A DC, 40V) | Toshiba TLP3547(F) | 1 |
| **DIP Socket** | 8-Pin IC Socket (Protects chip from soldering heat) | Standard Through-Hole | 1 |
| **Current Limiting Resistor** | 150 $\Omega$ $\pm$5% Resistor (1/4 Watt) | Standard Carbon Film | 1 |
| **Coin Cell Battery Holder** | 20mm Through-Hole CR2032 Retainer | Linx Technologies BAT-HLD-001 | 1 |
| **Lithium Coin Cell** | CR2032 3V Battery | Standard | 1 |
| **Input Switch Jack** | 3.5mm Female Mono Phone Jack | CUI Devices SJ1-3523N | 1 |
| **Output Toy Tail** | 3.5mm Male Mono Plug with 18 AWG Cable | Standard Heavy-Duty Repair Pigtail | 1 |
| **Circuit Base** | Solderable Perfboard | Standard FR4 Slices (approx 1x2") | 1 |

---

## 🛠️ Step-by-Step Assembly & Soldering Sequence

To ensure successful builds across volunteer assembly lines, follow this layout sequence:

1. **Mount the Socket First:** Solder the 8-pin DIP IC socket to the center of your perfboard. *Do not solder the TLP3547 chip directly to the board* to prevent thermal damage from the soldering iron.
2. **Bridge the Output Pins:** Flip the board over. Use small solder bridges or short solid-core wire pieces to permanently connect **Pin 5 to Pin 8**, and **Pin 6 to Pin 7**. This bridges the internal output MOSFETs into a parallel configuration for maximum 5A current handling.
3. **Attach the Power Loop:** Solder the positive (+) leg of the CR2032 battery retainer to the **Tip pin** of the 3.5mm female audio jack.
4. **Wire the Trigger Resistor:** Connect the **Sleeve pin** of the female audio jack to one side of the 150-ohm resistor. Run the other side of the resistor directly to **Pin 1 (Anode)** of the IC socket.
5. **Complete the Ground Loop:** Route **Pin 2 (Cathode)** of the IC socket straight back to the negative (-) terminal of the CR2032 battery retainer.
6. **Connect the Toy Tail:** Solder the positive wire (Tip) of your thick 18 AWG male pigtail to the joined **Pins 5/8** node. Solder the ground wire (Sleeve) of that same tail to the joined **Pins 6/7** node.
7. **Final Quality Check:** Ensure no stray solder tracks bridge the input side (Pins 1–4) over to the output side (Pins 5–8) to keep the optical isolation 100% pure. Pop the TLP3547 chip into the socket, slide a battery in, and begin testing.

---

## ⚖️ License

This project is open-source and built for the community. We use a split license to protect both the hardware and the documentation:

* **Hardware & Electronics:** The 3D design files, circuit schematics, and PCB layouts are licensed under the **CERN Open Hardware Licence v2 - Weakly Reciprocal (CERN-OHL-W-2.0)**.
* **Documentation & Guides:** All assembly manuals, written documentation, and text are licensed under the **MIT License**.

By keeping this project open, we ensure that families, schools, and organizations worldwide can continue to fabricate, modify, and improve the T.U.R.B.O. Switch Adapter without financial barriers.
