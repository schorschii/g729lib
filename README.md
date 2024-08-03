# G729lib
Python bindings for the libbcg729 audio codec C library.

Make sure you have the Ubuntu/Debian package `libbcg729-0` installed.

# Examples
This library was created for [Jabber4Linux](https://github.com/schorschii/Jabber4Linux). You can have a look at the code for an example implementation.

**Decode:**
```
import g729lib
decoder = g729lib.Decoder()

# returns 16-bit pcm_data
pcm_data = decoder.decode(g729_data)
```

**Encode:**
```
import g729lib

# 1. parameter: 0 = VAD (voice activity detection) disabled
encoder = g729lib.Encoder(0)

# expects 16-bit pcm_data, at least 160 bytes (80 samples; 2 byte per sample)
# returns 10 byte G729 data per 80 samples
g729_data = encoder.encode(pcm_data)
```
