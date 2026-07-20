[![CC BY 4.0][cc-by-shield]][cc-by]

# IEM MultiEncoder & AllRADecoder presets

A collection of loudspeaker layout presets for the [IEM MultiEncoder](https://plugins.iem.at/docs/plugindescriptions/#multiencoder) and [AllRADecoder](https://plugins.iem.at/docs/plugindescriptions/#allradecoder) plug-ins from the [IEM Plug-in Suite](https://plugins.iem.at/). Both plug-ins read the same loudspeaker layout format, so every preset here works with either. Covers industry-standard multichannel formats, mathematical spherical distributions, and special loudspeaker arrays.

## Included presets

### Industry standards

| Preset | Format |
|---|---|
| `Dolby_Atmos_5.1.2` | Dolby Atmos 5.1.2 |
| `Dolby_Atmos_5.1.4` | Dolby Atmos 5.1.4 |
| `Dolby_Atmos_7.1.2_A/B` | Dolby Atmos 7.1.2 (two variants) |
| `Dolby_Atmos_7.1.4_A/B` | Dolby Atmos 7.1.4 (two variants) |
| `Dolby_Atmos_9.1.6_A/B` | Dolby Atmos 9.1.6 (two variants) |
| `Auro-3D_9.1/11.1/13.1` | Auro-3D 9.1, 11.1, 13.1 |
| `ITU-R_5.1_Film/SMPTE` | ITU-R BS.2051 5.1 (Film and SMPTE panning) |
| `ITU-R_7.1_A/B_Film/SMPTE` | ITU-R BS.2051 7.1 A/B (Film and SMPTE) |
| `ISO_IEC_MPEG-H_5.1+2H` … `7.1+4H` | ISO/IEC 23008-3 MPEG-H layouts |
| `Sony_360RA_13ch_5.0.5+3B` | Sony 360 Reality Audio recommended 13-speaker layout |
| `Sony_360RA_13.1` | As above, plus an LFE object as channel 14 |

### Spherical distributions

| Preset | Type |
|---|---|
| `t-design_04p/12p/24p/48p/60p` | Spherical t-designs |
| `Lebedev_14p/26p` | Lebedev quadrature grids |
| `SphCov_09p/16p/25p/49p/64p` | Spherical coverage designs |

### Special arrays & stereo

| Preset | Description |
|---|---|
| `IKO_42` | IKO icosahedral loudspeaker |
| `stereo` / `stereo_narrow` / `stereo_wide` | Stereo variants |

## Sources

- Most loudspeaker positions follow the APL [Virtuoso](https://apl-hud.com/product/virtuoso/) loudspeaker layouts [specification](https://apl-hud.com/wp-content/uploads/2023/03/APL-Virtuoso-Loudspeaker-Layouts.pdf).
- The Sony 360 Reality Audio layouts follow the [360 Reality Audio content creation guideline](https://www.sony.co.jp/en/Products/create360RA/assets/360_Reality_Audio_content_creation_guideline.pdf) (v2.1, 30 September 2025), section *Recommended Speaker Layout 13 Speakers (5.0.5+3B)*.

### LFE placement

Formats with an LFE channel need it to occupy its position in the channel order, even though LFE has no defined direction. In these presets it is given a nominal position of azimuth −45°, elevation −30°, placed at whatever index the format's channel order requires — channel 4 in SMPTE ordering, channel 6 or 8 in Film ordering, which is the only difference between the `_Film` and `_SMPTE` variants.

`Sony_360RA_13.1` is the one exception. Sony's guideline defines no LFE loudspeaker and instead recommends importing LFE content as an object at azimuth 0°, elevation −50°, gain +6 dB, so that preset follows its own source rather than the convention above: the 13 guideline positions stay in their original order as channels 1–13, with LFE appended as channel 14. If you already compensate the LFE level in your DAW, set that speaker's gain back to `1.0` to avoid applying +6 dB twice.

## Usage

These are loudspeaker **layout** files — they contain positions only, with no precomputed decoding matrix, so any decoder is derived on your side from your own choice of order, weighting and normalisation.

1. Install the [IEM Plug-in Suite](https://plugins.iem.at/)
2. Open **MultiEncoder** or **AllRADecoder** in your DAW
3. Click **Import** and select the desired `.json` preset file
4. To decode rather than encode, press **Calculate Decoder** in AllRADecoder, then export the result as a configuration file for use in **SimpleDecoder**

![IEM MultiEncoder VST plug-in](https://i.ibb.co/gVFZKMx/SCR-20241201-pmgi-2.png)

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: https://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

## Contact

Bartłomiej Mróz · bartlomiej.mroz@pg.edu.pl · Department of Multimedia Systems, Gdańsk University of Technology · [bmroz.eu](https://bmroz.eu)
