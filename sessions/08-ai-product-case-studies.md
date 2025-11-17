# Session 08: AI Product Case Studies

**Week 3 | Duration: 3 hours**

## 🎯 Learning Objectives

- Analyze real-world AI product successes and failures
- Understand AI product patterns across industries
- Extract lessons applicable to your AI PM work

---

## 📱 Case Study 1: Smart Speakers (Alexa, Google Home)

### Product Overview
Voice-activated AI assistants for homes

### AI Components
- **Speech Recognition**: Convert voice to text
- **Natural Language Understanding**: Interpret user intent
- **Dialog Management**: Maintain conversation context
- **Text-to-Speech**: Generate voice responses
- **Skills/Actions Ecosystem**: Third-party integrations

### Key Product Decisions
1. **Always listening** (privacy trade-off)
2. **Wake word** detection (Hey Alexa/OK Google)
3. **Cloud-based** processing (latency vs. accuracy)
4. **Open platform** for third-party skills

### Success Factors
- Continuous improvement from user interactions
- Network effects (more users → more data → better AI)
- Ecosystem approach (hardware + platform + developers)

### Lessons for PMs
- **Start narrow, expand over time** (music → smart home → everything)
- **Data flywheel**: more usage → better AI → more usage
- **Privacy must be designed in**, not bolted on
- **Error recovery**: how system handles failures matters

---

## 🚗 Case Study 2: Self-Driving Cars (Tesla Autopilot, Waymo)

### Product Overview
AI-powered autonomous vehicle systems

### AI Components
- **Computer Vision**: Detect objects, lanes, signs, lights
- **Sensor Fusion**: Combine camera, radar, lidar data
- **Path Planning**: Determine safe route
- **Reinforcement Learning**: Improve from experience
- **Simulation**: Test scenarios virtually

### Product Approaches

**Tesla Approach:**
- Vision-first (cameras over lidar)
- Fleet learning (learn from all Tesla drivers)
- Gradual autonomy (driver assistance → full self-driving)
- Consumer deployment with safety driver

**Waymo Approach:**
- Sensor-rich (lidar + cameras + radar)
- Geo-fenced operation (limited areas)
- Safety-first (extensive testing before deployment)
- Robo-taxi service (no private ownership yet)

### Challenges
- **Safety critical**: Errors can be fatal
- **Edge cases**: Rare scenarios hard to train for
- **Regulatory**: Legal frameworks evolving
- **Liability**: Who's responsible for AI decisions?
- **Trust**: User acceptance and confidence

### Lessons for PMs
- **Define levels clearly** (SAE levels 0-5 for autonomy)
- **Safety is paramount** for high-stakes AI
- **Different strategies can work** (Tesla vs. Waymo)
- **Regulatory engagement** critical for new categories
- **Data strategy** is competitive moat

---

## 📺 Case Study 3: Netflix Recommendations

### AI Impact
- 80% of watched content from recommendations
- Saves $1B+/year in retained subscriptions
- Personalizes entire UX (artwork, rankings, categories)

### Evolution
1. **Ratings-based** (1-5 stars)
2. **Collaborative filtering** (similar users)
3. **Deep learning** (neural networks)
4. **Contextual bandits** (optimize for engagement)
5. **Personalized everything** (thumbnails, rankings, rows)

### Key Insights
- **Multiple algorithms** working together
- **Continuous A/B testing** (hundreds running concurrently)
- **Metrics evolution**: star ratings → watch time
- **Personalized presentation**: same show, different thumbnails per user

### Lessons for PMs
- Start simple, iterate to complex
- The full experience is personalized, not just recommendations
- Invest in experimentation infrastructure
- Metrics should align with business goals (retention)

---

## 🔍 More Quick Cases

### Google Search (RankBrain)
- **What**: AI for understanding search queries
- **Impact**: Better results for ambiguous queries
- **Lesson**: AI can augment existing products powerfully

### Spotify Discover Weekly
- **What**: Personalized weekly playlist
- **Impact**: Massive engagement, differentiation
- **Lesson**: AI can create new product experiences

### Grammarly
- **What**: AI-powered writing assistant
- **Impact**: 30M+ users, clear value prop
- **Lesson**: AI can enhance everyday tasks

---

## 🔗 Next Session

[Session 09: AI Team Structure →](./09-ai-team-structure.md)

---

*Last Updated: 2025*
