# StormGlass
Lightning Animation using CircuitPython and an Adafruit CircuitPlayground Bluefruit

Derived from the [Adafruit Bluetooth Snow Globe guide](https://learn.adafruit.com/snow-globe-bluefruit-cpb/code-the-bluetooth-snow-globe) - follow instructions there for installation of CircuitPython and required libraries.

An STL file is provided as a base for the globe. This is derived from the [NASA 3D model of the Block Island rock](https://nasa3d.arc.nasa.gov/detail/block-island) from Mars.

The relevant lightning code is contained within this block:
`def lightning(config):
    start_time = time.monotonic()
    last_update = start_time
    while time.monotonic() - start_time < config['duration']:
        if time.monotonic() - last_update > config['speed']:
            for _ in range(random.randint(1,8)):
                pixels.fill(0)
                pixels.fill(config['color'])
                time.sleep(0.02+(.001*random.randint(1,70)))
                pixels.fill(0)
                time.sleep(.01)
                #pixels.fill(0)
            time.sleep(5+random.randint(1,5))
            last_update = time.monotonic()`

