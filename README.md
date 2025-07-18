# 🏎️ TM-AlgoCrack – Stadium Car Speedslide Analyzer

This project provides a physics-based utility for analyzing and tuning **speedslide mechanics** of Stadium Cars in Trackmania, based on speed and material properties like side friction. It helps modders, developers, or competitive players understand how different speeds and surfaces impact vehicle sliding behavior.

---

## 📌 Features

- Calculates **maximum side friction** from forward speed
- Determines **optimal lateral speed** for controlled sliding
- Computes **slide quality metrics** to evaluate drifting performance
- Adjustable for different surface materials (road, dirt, grass)

---

## 🧠 How It Works

This tool uses predefined speed-friction mappings and mathematical scaling to:
- **Model friction curves** based on velocity
- Evaluate how much sideways drift (SpeedX) the car can maintain before losing grip
- Score "drift quality" from 0 to 1 depending on physical tolerances

---

## 🧪 Functions

| Function | Description |
|---------|-------------|
| `GetFuncAbsoluteSpeedXFromSpeedForStadiumCar()` | Returns function curve of max side friction vs speed |
| `GetPerfectSpeedslideAbsoluteLocalSpeedXForStadiumCar(speed_z)` | Calculates ideal SpeedX for speedslides |
| `GetMinimumSpeedslideAbsoluteLocalSpeedXForStadiumCar(speed_z)` | Calculates minimum viable drift |
| `GetSpeedslideQualityForStadiumCar(speed_x, speed_z)` | Returns a drift quality score (closer to 1 is ideal) |

---

## ⚙️ Example Usage

```python
import sd_quality

quality = sd_quality.GetSpeedslideQualityForStadiumCar(speed_x=15.0, speed_z=120.0)
print("Slide Quality:", quality)
