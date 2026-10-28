# ⚽ Match Pulse
Real-time football analytics: live xG, xT and goal probability with and end to end MLOps pipeline

Match Pulse turn raw events into a live visual story of a football match:
Who is creating danger, how the momentum is shifting, and how likely a goal is in the next few minutes.

## Why this project
Most of MLOps projects stop at notebook. I wanted to go further: take away all the way from raw data to a monitored, real-time system, and learn every stage of the MLOps lifecycle along the way. Football analytics felt like the perfect playground: rich open data, clear metrics, and results anyone can see
on the pitch.

> 🚧 **Status** early development. This README describes the target system; see the [roadmap](#roadmap) for progress.

---

## 📊 Metrics
| Metric | What it answers |
|---|---|
| **xG (Expected Goal)** | How likely was *this shot* to become a goal, given its location, angle, body part and the defenders in the way? |
| **xT (Expected Threat)** | How much did *this pass or carry* increase the team's chances of scoring? |
| **Live Goal Probability** | How likely is a goal in the *next few minutes*, given the current momentum of the match? |

## 🎯 Planned Features
- **Interactive 2D Pitch:** very pass and carry drawn as an arrow, colored by threat (vivid for dangerous actions, muted for safe possession).
- **Momentum gauges:** a tachometer per team showing their recent attacking intensity.
- **Cumulative xG chart:** the evolution of each team's xG throughout the match.
- **Shot moments:** when a shot happens, the match pauses to show the shooter, goalkeeper and defenders, the shooting angle and the xG value, then reveals the outcome.

## 🔌 Data modes
The system is designed to be **source-agnostic**: every data source is a pluggable connector producing the same event format.

| Mode | Source | xG | xT | Notes |
|---|---|---|---|---|
| **Replay** | StatsBomb Open Data | ✅ | ✅ | Historical matches streamed in real time |
| **Live (manual)** | Manual shot tagging while watching a match | ✅ | ❌ | Full xT requires every pass location, which is not feasible to tag by hand |

## 🗺️ Roadmap
### v1: Core system
- [ ] Project setup & tooling
- [ ] Data exploration
- [ ] xG model
- [ ] xT model
- [ ] Reproducible training pipeline & experiment tracking
- [ ] Inference API & containerization
- [ ] Match replay streaming
- [ ] Live dashboard
- [ ] Testing & CI/CD
- [ ] Monitoring & data drift detection

### v2: Live Goal Probability model
### v3: Live mode with manual shot tagging
### v4: Computer Vision module (future work)

## 🛠️ Tech stack (planned)

- **Language & tooling:** Python, uv
- **Data & ML:** pandas, scikit-learn, LightGBM
- **MLOps:** MLflow, GitHub Actions
- **Serving:** FastAPI, Docker
- **Streaming:** Redpanda / Kafka
- **Visualization:** Streamlit, Plotly, mplsoccer


## 📚 Data

This project uses [StatsBomb Open Data](https://github.com/statsbomb/open-data) for non-commercial purposes.

## 📄 License

Licensed under the [GNU AGPL-3.0](LICENSE).
