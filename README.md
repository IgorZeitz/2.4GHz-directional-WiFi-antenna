<h1 align="center">
 2.4GHz-directional-WiFi-antenna
</h1>
  
  The project aims to create a directional antenna for 2.4GHz WiFi. The device can be used to maximize network range in one direction (e.g., along a long hallway) while minimizing radiation in the opposite direction, which is not accessible to users. 

<div align="center">
  <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Model%203D%20anteny%20helikalnej.png" alt="Logo" width="450" height="250">
  <br />

  </div>
  <br>

<details open="open">
<summary>Table of Contents</summary>

- [About](#about)
- [Simulations](#simulations-antennadesigner)
- [Feed Design](#Feed-Design)
- [Impedance Matching](#Impedance-Matching)

</details>

## About
The device was built as a helical antenna, which offers good directivity, gain, and interference protection due to its elliptical polarization.
To reduce the physical size, a thick wire with only 3 turns was used. This provides good parameters while keeping the helix compact. An additional ground plane was included to reflect waves coming from the opposite direction.

The antenna final design:
<div align="center">
  <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Antena-GOTOWA_2.webp" alt="Logo" width="250" height="250">
</div>

## Simulations (AntennaDesigner)
Before beginning the build process, simulations were carried out to estimate the antenna gain, directivity and impedance for different dimensional variants.

The simulation model consists of:
- 3 conductor turns
- 4 mm helix copper width
- 4 cm spacings
- 8 cm ground plane radius
- 2.5 cm PVC core radius
  
<div align="center">
<img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Ko%C5%84cowy%20model%20anteny%20-%20symulacje%20(z%20PVC).png" alt="Logo" width="650" height="487">
</div>

**Radiation Pattern**

The simulation results show that the antenna can achieve approximately 11 dB of forward gain. In the opposite direction, a loss of about 3 dB is observed.
The azimuth radiation pattern and 3D visualization illustrate how the antenna distributes gain in space.

| Azimuth | 3D visualization|
|:------------------:|:-----:|
| <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Charakterystyka%20promieniowania%20elewacyjna.png" alt="Logo" width="540" height="352"> | <img src="https://github.com/IgorZeitz/test/blob/test2/images/model%203D%20promieniowania.png" alt="Logo" width="540" height="352"> |

A typical helical antena in end-fire mode has an impedace between 100 Ω and 200 Ω. In this design, the simulated impedance in the WiFi band is approximately 84 Ω, consisting almost entirely of resistive values.
Such a desing requires the use of an impedance-matching stub.

<h1 align="center"> 
  <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Impedancja%20anteny%20-%20symulacja.png" alt="Logo" width="650" height="487">
</h1>

## Feed Design
For impedance matching, a strip-line stub was used. The first design was created according to calculated dimensions, however, this approach did not provide sufficient matching. Further attempts were based on a trial-and-error method, with continuous monitoring of the S11 parameter using a network analyzer. The tested variants are shown below:

| calculated desing | trial-and-error method | final desing |
|:------------------:|:-----:|:---:|
| <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Nowy%20spos%C3%B3b%20dopasowania%20anteny%20-%20pr%C3%B3ba%201.jpg" alt="Logo" width="407" height="338"> | <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Nowy%20spos%C3%B3b%20dopasowania%20anteny%20-%20pr%C3%B3ba%203.jpg" alt="Logo" width="407" height="338"> | <img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Nowy%20spos%C3%B3b%20dopasowania%20anteny%20-%20pr%C3%B3ba%202.jpg" width="407" height="338"> |

**Impedance Matching**

The measured values of S11 parameter for each strip-stub design are presented in the chart. The final antenna achieved a reflection coefficient of -27.8 dB.

<div align="center">
<img src="https://github.com/IgorZeitz/2.4GHz-directional-WiFi-antenna/blob/main/images/Zestawienie%20charakterystyk%20dopasowania.png" alt="Logo">
</div>

<br>
To fully test the device, measurements were performed in a hallway using an external program to save received signal strength. Measured values for both the helical and dipole antennas are summarized in the table below.

*Antenna Range:*
<div align="center">
 
| Distance | Dipole Antenna Gain | Helical Antenna Front Gain | Helical Antenna Rear Gain |
|:--------:|:-------------------:|:--------------------------:|:-------------------------:|
| 1 | -43.7 | -41.9 | -48.25 |
| 5 | -48.7 | -47 | -59 |
| 8.5 | -52.7 | -47.8 | -66 |
| 13.5 | -57.3 | -50.7 | -66
| 20.5 | -63 | -54.5 | -65.25 |
| 24.5 | -68 | -54.3 | -67 |
| 30 | -62.7 | -57 | -69.5 |

</div>
