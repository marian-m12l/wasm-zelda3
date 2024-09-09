# Emscripten

## Build

```
mkdir build && cd build
emcmake cmake ..
emmake make -j$(nproc)
```

## Build assets file

TODO: must be provided by the user (extracted from US rom file)
```
make zelda3_assets.dat
```

## Add configuration file

`zelda3.ini` must be copied to `build` directory.

## Link

```
emcc -flto -O3 **/*.o libgl.a libopus.a -o index.html --shell-file ../shell.html -sUSE_SDL=2 -sENVIRONMENT=web -sINVOKE_RUN=0 --preload-file zelda3.ini -Wl,-u,fileno -lidbfs.js
```


# Run locally

```
emrun index.html
```

Then open in browser: http://localhost:6931/ and upload `zelda3_assets.dat`.


