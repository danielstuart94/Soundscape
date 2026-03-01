A Rapid Soundscape Assessment Tool for Real-Time Environmental Characterisation
1. Introduction
Traditional acoustic assessment relies on sound pressure level metrics (e.g. LAeq), which do not capture how environments are perceived. Recent research in soundscape (ISO 12913 series) demonstrates that human response is driven by sound composition and context, not level alone.
This tool has been developed as a rapid, field-deployable soundscape logger, combining acoustic signal processing with perceptual indicators.
2. Methodology
2.1 Signal Acquisition
Audio is captured via device microphones using the Web Audio API. Automatic gain control and noise suppression are disabled where possible.
2.2 Level Estimation
Sound pressure is approximated via RMS:
Calibration is applied via field reference:
Where:
� is derived from comparison with a reference meter
2.3 Spectral Descriptors
The following real-time descriptors are derived from FFT analysis:
Spectral Centroid
Indicates perceived “brightness”
Spectral Flatness
Differentiates tonal vs broadband signals
Band Energy Ratios
Low frequency (<200 Hz) → traffic / mechanical
High frequency (>2 kHz) → birds / speech / alerts
2.4 Sound Source Approximation
Sound types are inferred using heuristic mapping:
Descriptor Pattern
Likely Source
High low-frequency energy
Traffic
High centroid + high-frequency
Birds
Mid centroid + variability
Speech
High flatness
Wind / rain
This approach provides indicative composition, not classification certainty.
2.5 Perceptual Metrics
Based on ISO soundscape models:
Pleasantness
Where:
�: natural sound proportion
�: mechanical sound proportion
�: alarms/sirens
Eventfulness
Where:
�: active sources (speech, music)
�: variability
2.6 Quadrant Mapping
Quadrant
Description
Calm
High P, Low E
Vibrant
High P, High E
Chaotic
Low P, High E
Monotonous
Low P, Low E
3. Output
The system logs:
LAeq (proxy)
Spectral descriptors
Estimated sound composition
Pleasantness & Eventfulness
Manual source tagging
4. Applications
Urban public realm assessment
Pre/post intervention evaluation
Workplace acoustic optimisation
Planning and design narratives
5. Limitations
Not compliant with IEC sound level meter standards
Source identification is heuristic (non-ML)
Device microphones introduce variability
6. Conclusion
This tool demonstrates a practical bridge between acoustic measurement and human perception, enabling rapid, scalable soundscape assessment suitable for early-stage design and decision-making.
