# Kelo third-party notices and corresponding source

Kelo includes separately licensed open-source components. Their original
copyright and license texts are retained in the application and accompanying
notice archive. No upstream publisher endorses Kelo. The notices are available
in `Kelo.app/Contents/Resources/ThirdPartyNotices`, the Python package license
directories, and the npm packages' own license files.

## FFmpeg and native dependency sources

The included FFmpeg 8.1.1 build is GPL-3.0-or-later and is invoked as a separate
executable. Kelo's native host does not link against the FFmpeg libraries.
The accompanying `kelo-third-party-source-2026-10-14.tar.gz` contains the exact
13 previously identified native source versions, build recipes, applicable
source patch, license texts, FFmpeg configure flags and relocation instructions.
Its source manifest records archive SHA-256 values and x264's exact Git revision.

The independently licensed FFmpeg dependencies include x264/x265 under GPL,
LAME under LGPL, and other library-specific permissive terms. Consult their
actual license files rather than applying one license to the entire application.

## SoundFile's LGPL audio library

SoundFile 0.14.0 is BSD licensed and dynamically loads the separately replaceable
`libsndfile_arm64.dylib`. That library contains libsndfile 1.2.2, Ogg 1.3.5,
Vorbis 1.3.7, FLAC 1.4.3, Opus 1.4, mpg123 1.32.3 and LAME 3.100. The LGPL
components and codecs are combined inside this shared library, rather than
statically linked into the Kelo native host.

`Kelo-audio-corresponding-source-2026-10-15.tar.gz` provides all seven exact
versioned source archives, the publisher's pinned build script/CMake file, its
source adaptation patch and `REBUILD-AND-REPLACE.md`. That document explains
rebuilding/relinking the shared library, replacing it in a separate app copy,
and re-signing a user-modified copy without Kelo's private signing key.

Kelo imposes no prohibition on modifying these LGPL components or reverse
engineering for debugging those modifications. Preserve those permissions
when distributing additional application terms. Original LGPL texts and codec
attribution accompany these sources and the installed SoundFile package.

## Python packages, runtime and speech models

Python retains the PSF and historical notices. The bundled Python dependencies
retain their own MIT, BSD, Apache and other permissive license texts. PyTorch's
omnibus license also includes a GPL notice for an upstream CPR test directory;
that test program is not an identified shipped runtime component.

Certifi and tqdm include MPL-2.0-covered material. Their readable Python/PEM
source and original license notices are included in the application and the
audio source supplement. MPL permissions remain available for those files.

Node, Ollama/llama.cpp/MLX, Whisper.cpp/OpenAI Whisper, MioCodec, WavLM and their
vendors retain the original licenses in this notice set and their packages.
This distribution does not include downloaded conversational model weights.

BgTTS V2 and its exact three stock reference WAV files have an Apache-2.0
publisher declaration. Kelo's BgTTS `model.py` contains application integration
modifications and must carry a prominent Kelo modification notice. The renamed
stock WAV files have unchanged contents. The `wake-model` directory preserves
the model author's Apache-2.0 declaration and exact hash correspondence for
the four bundled wake files. The wake runtime and ONNX Runtime retain their
separate Apache/MIT notices.

The updater and other bundled components retain their own included notices.
Antigravity's optional `agy` client is recipient-installed and is not included
in this distribution.

## Accompanying artifacts

Provide the following with the binary download through the same release page:

- `kelo-third-party-source-2026-10-14.tar.gz`
- `Kelo-audio-corresponding-source-2026-10-15.tar.gz`
- `Kelo-third-party-notices-2026-10-15.tar.gz`

Checksums, exact scope and evidence are recorded in the release review receipt.
Keep these sources/notices available with the corresponding binary releases.
