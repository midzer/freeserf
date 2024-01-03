# Emscripten

## Build

```
mkdir build && cd build
emcmake cmake ..
emmake make
```

## Link

```
emcc -flto -O3 ../../libdata.a ../../libgame.a ../../libplatform.a ../../libtools.a *.o -o index.html -sUSE_SDL=2 -sUSE_SDL_IMAGE=2 -sUSE_SDL_MIXER=2 -sSDL2_MIXER_FORMATS='["pcm","mod","mid","wav"]' -sASYNCIFY -sASYNCIFY_ONLY=@funcs.txt -sASYNCIFY_IGNORE_INDIRECT -sENVIRONMENT=web --preload-file gfxchip --preload-file gfxfast --preload-file gfxheader --preload-file gfxpics --preload-file music --preload-file sounds -Wl,-u,fileno --closure 1
```
