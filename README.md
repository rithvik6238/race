# race - Wasm binding for llama.cpp

![](./race_banner.png)

Another WebAssembly binding for [llama.cpp](https://github.com/ggerganov/llama.cpp). Inspired by [tangledgroup/llama-cpp-wasm](https://github.com/tangledgroup/llama-cpp-wasm), but unlike it, **Race** aims to support **low-level API** like (de)tokenization, embeddings,...

## Recent changes

- Version 1.5.0
  - Support split model using [gguf-split tool](https://github.com/ggerganov/llama.cpp/tree/master/examples/gguf-split)
- Version 1.4.0
  - Add `single-thread/race.js` and `multi-thread/race.js` to the list of `CONFIG_PATHS`
  - `createEmbedding` is now adding BOS and EOS token by default

## Features

- Typescript support
- Can run inference directly on browser (using [WebAssembly SIMD](https://emscripten.org/docs/porting/simd.html)), no backend or GPU is needed!
- No runtime dependency (see [package.json](./package.json))
- High-level API: completions, embeddings
- Low-level API: (de)tokenize, KV cache control, sampling control,...
- Ability to split the model into smaller files and load them in parallel (same as `split` and `cat`)
- Auto switch between single-thread and multi-thread build based on browser support
- Inference is done inside a worker, does not block UI render
- Pre-built npm package [@race/race](https://www.npmjs.com/package/@race/race)

Limitations:
- To enable multi-thread, you must add `Cross-Origin-Embedder-Policy` and `Cross-Origin-Opener-Policy` headers. See [this discussion](https://github.com/ffmpegwasm/ffmpeg.wasm/issues/106#issuecomment-913450724) for more details.
- No WebGL support, but maybe possible in the future
- Max file size is 2GB, due to [size restriction of ArrayBuffer](https://stackoverflow.com/questions/17823225/do-arraybuffers-have-a-maximum-length). If your model is bigger than 2GB, please follow the **Split model** section below.

## Demo and documentations

**Documentation:** https://ngxson.github.io/race/docs/

Demo:
- Basic usages with completions and embeddings: https://ngxson.github.io/race/examples/basic/
- Advanced example using low-level API: https://ngxson.github.io/race/examples/advanced/
- Embedding and cosine distance: https://ngxson.github.io/race/examples/embeddings/

## How to use

### Use Race inside React Typescript project

Install it:

```bash
npm i @race/race
