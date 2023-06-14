# Bitsery ESP-IDF Component

This is a simple wrapper around fraillt's fast and tiny binary serialization library [Bitsery](https://github.com/fraillt/bitsery) so that you can use it with the [ESP-IDF Component Manager](https://github.com/espressif/idf-component-manager).

Due to its small footprint and concise binary representation, Bitsery is a good choice for serialization on the ESP32.

Check out their repository for more information!

## 💫 How to use in your project

1. Make sure you have installed and enabled the IDF Component Manager. If you're using a recent version of ESP-IDF, it is enabled by default. Otherwise, follow the [getting started guide](https://docs.espressif.com/projects/idf-component-manager/en/latest/getting_started/index.html)

2. Add bitsery as a dependency to your component:
   
   1. Create the `idf_component.yml` manifest file (if you haven't already) by running `idf.py create-manifest --component=my_component`
   2. Add a new `dependencies` entry named `bitsery` with `git` url set to `https://github.com/derkalaender/bitsery-esp.git`

Your `idf_component.yml` manifest will look something like this:

```yml
dependencies:
  idf:
    version: ">=5.0.1"
  bitsery:
    git: "https://github.com/derkalaender/bitsery-esp.git"
```

3. Run `idf.py reconfigure` to reconfigure the project and let the component manager discover and download bitsery
4. Add `bitsery` to your `PRIV_REQUIRES` (or `REQUIRES` if you're exposing bitsery in your public include files) in the components `CMakeLists.txt`

Done! You can now use Bitsery! Again, be sure to check out the [Bitsery repository](https://github.com/fraillt/bitsery) for docs and examples.
