# dirty-laundry-iot-gateway


## Disclaimer
This project is a private hobby project and is not affiliated with, endorsed, or supported by Miele & Cie. KG. No proprietary protocols are reverse-engineered intentionally.
All observations are based on user-visible network behaviour.

"Miele" is a registered trademark of Miele & Cie. KG and Miele Beteiligungs GmbH.
This project uses the official Miele 3rd Party API to access Miele Cloud. It is required to register for a Miele developer account (https://developer.miele.com/).

**This project is experimental and provided “as is”, without any warranty or guarantee.
Use at your own risk.**

## AI Usage Disclaimer

Parts of this project’s documentation, structure, and design rationale were created
with the assistance of an AI language model (ChatGPT by OpenAI).

The AI was used as a **support tool** for:
- Structuring documentation
- Summarizing experiments and observations
- Brainstorming design options and risks
- Drafting non-code explanatory text

All technical decisions, experiments, validations, and interpretations were
performed, reviewed, and are owned by the project author.

The AI:
- Did **not** access proprietary Miele documentation
- Did **not** reverse-engineer encrypted protocols
- Did **not** provide guarantees of correctness, completeness, or suitability
- Did **not** perform live network analysis or testing

Any errors, omissions, or incorrect assumptions remain the responsibility of
the human project maintainer.

This project is for educational and private hobby purposes only.

---

### Background

The motivation for this project originates from the purchase of two Miele appliances:

- **Miele WWD380 WPS** (washing machine) (https://www.miele.de/product/12703620/w1-waschmaschine-frontlader-wwd380-wps-pwashundsteamund9kg-lotosweiss)
- **Miele TWD640 WP** (heat pump dryer)(https://www.miele.de/product/12703870/t1-warmepumpentrockner-twd640wp-ecospeedund9kg)

Both appliances support Miele’s smart connectivity features, including 
cloud-based status reporting and coordinated programs (e.g. Wash2Dry). 
The complete and direct appliance control by MobileStart feels like technical play and is of lesser importance.

Due to the physical location of the appliances in a cellar environment with
limited power availability and severe wireless signal attenuation, the
intended smart functionality could not be used with the existing home network.

This project was started to explore **practical and low-impact ways** to regain
these smart features under real-world constraints, without permanent
installation or modification of the building infrastructure.

---

## Motivation

This project explores how to provide stable and reliable internet connectivity for
Miele washing machines and dryers located in a cellar with no usable (owned) Wi-Fi coverage.

The goal is to restore **Smart Home Features**, such as:
- Program status visibility
- End-of-cycle notifications
- Cloud-based functions (e.g. Wash2Dry coordination)
- EcoFeedback visibility

… without installing permanent infrastructure or relying on neighbor networks.

My personal interest is to learn from the project in different fields (design, communication, hardware, software, mechanical) 
and gain deeper insight to my usage behaviour. Water and power prices are constantly demanding and likely continue increasing.  


## Problem Summary

- Cellar location blocks Wi-Fi due to **concrete, metal, and geometry**.
- Power outlet availability is very **limited** and occupied by the appliances. Running always-on solutions is to expensive.
- Internet access must be provided via **cellular (5G, 4G, 3G)** or other means.
- Connectivity interruptions appear to **break smart features per cycle** since appliances seem to fallback to standalone mode and stop reporting to Miele cloud during this particular cycle. 
- Data volume, protocol behaviour, and buffering tolerance are **undocumented**. It doesnt appear to be hardened against harsh communication environments.
- The Miele cloud service provision and certain design decisions are proprietary and inherently unknown.


## Core Idea

Use a **small, battery-powered gateway** that:
- Acts as a **Wi-Fi Access Point** for the appliances.
- Uses **cellular (5G or LTE)** as upstream internet.
- Provides **stable, always-on connectivity during a wash cycle**.
- Allows **packet capture and analysis** to understand cloud behaviour and infer valuable informations for later optimizations.

