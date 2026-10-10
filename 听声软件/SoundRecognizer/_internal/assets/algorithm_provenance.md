# Waveform core provenance

The short-pickup waveform backend in pickup_waveform.py adapts the supplied
FieldTrader 0.7.4 executable's decompiled recognition core. The user expressly
requested reuse and stated that the author publicly permits it. No repository
or independently verifiable license document was supplied; no new license is
asserted for the adapted material.

Original components: WaveformRecognitionService, PickupEventDetector,
InterferenceFilter, SoundFeaturesExtractor.Resample. Original author/company
metadata: 取名字真麻烦. Supplied installer SHA-256:
189AD008A63EBD16BDABC5CB7F966E7A642D71ADCB82BE9D5325A9B9ED08710E.

The Python integration retains 16 kHz resampling, 49-tap sinc conversion,
300/1500 Hz high-pass routes, 100/180 ms sliding windows, 30 ms stride,
550 ms reference prefix, 420 ms query prefix, 0.70 correlation threshold,
0.04 inter-group margin, and the original automatic high-frequency detector.
FFT batches and precomputed normalization tables change execution structure,
not the scoring rule. Existing Python legacy recognition is separately selectable.

Development comparison invokes the original DLL's recognition class directly
via PowerShell/.NET, without launching the original app's UI or installing it.
Sixteen clean/quiet/delayed/low-frequency test cases have the same top-two
groups and acceptance decisions; maximum score difference observed 0.001314.
This is port-consistency evidence, not a claim of superior gameplay accuracy.
