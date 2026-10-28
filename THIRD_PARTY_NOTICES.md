# Third-party notices and data licences

This app is a prototype for learning the Buryat language. Its own code and original artwork are under the MIT licence
(see `LICENSE`). Everything below is included under its own terms. Nothing here has been reviewed by a native speaker.
If you reuse any of it, follow the licence of that part, not only the MIT licence of the code.

## Language data

| What | Where in this repository | Source | Licence | Changes made |
|---|---|---|---|---|
| Recordings of single Buryat words (74 of them are used) | `assets/clips/`, `src/content/clips.ts` | UCLA Phonetics Lab Archive, Buryat word list ([archive](https://archive.phonetics.ucla.edu/Language/BXM/bxm.html)); speaker Ms. Darima Sanzhina, fieldworker Vadim Kasevich, recorded in the Republic of Buryatia in 1991. | [CC BY-NC 2.0](https://creativecommons.org/licenses/by-nc/2.0/): attribution required, **non-commercial use only** | Cut into word clips and matched to our words by `scripts/build-ucla-clips.py`; only high-confidence alignments are used. |
| Buryat sentences and their translations (Russian, and a few English, French, German) | `src/content/sentences.json`, `src/content/cloze.json` | [Tatoeba](https://tatoeba.org) contributors. Usernames of authors: mari_marie, zorrig, AqQoyriq_1, Balamax, BW; 460 sentences have no author recorded. Each sentence keeps its Tatoeba id. | [CC BY 2.0 FR](https://creativecommons.org/licenses/by/2.0/fr/) | Letters typed in Latin or Greek look-alikes were repaired, sentences filtered and grouped by difficulty (`scripts/build-sentences.py`). The earlier 50-sentence set came through the Sarana corpus below. |
| English lines for the sentences that have only Russian (marked `mt` in the data) | `src/content/sentences.json` | Machine-translated from the Russian offline with Helsinki-NLP opus-mt-ru-en ([Hugging Face](https://huggingface.co/Helsinki-NLP/opus-mt-ru-en)), run through `scripts/translate-sentences.mjs`. | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) for the model | Unreviewed; the app says on each such line that the English is machine-translated. |
| Buryat-Russian word pairs and sentence pairs, used for word meanings (glosses, the word list of the word and picture games) and the first sentence set | `src/content/glosses.json`, `src/content/vocab.json`, `src/content/cloze.json` | Buryat-Russian parallel corpus by Sarana Abidueva and Dari Baturova ([Hugging Face](https://huggingface.co/datasets/SaranaAbidueva/buryat-russian_parallel_corpus)). Its dictionary part is used for meanings and its sentence pairs only to count which words go together; no sentences from its books, Bible, poems or plays are shown. | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) for the dataset | Filtered; meanings checked against sentence alignment and by hand (`scripts/build-vocab.py`); English glosses and English sentence translations are machine-written (or hand-written for the checked words) and unreviewed. |
| Traditional Mongolian script letters, forms, transcriptions, IPA, example words and their Buryat descendants | `src/content/script.json`, `src/content/script-words.json`, `data/script-words.csv` | [Wiktionary](https://en.wiktionary.org) contributors | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Selected and re-organised. These files, and anything derived from them, must stay under CC BY-SA 4.0. |
| Cyrillic-to-script letter correspondences | `src/content/cyrillic-script.json` | The "Buryat scripts" table of the Wikipedia article [Buryat language](https://en.wikipedia.org/wiki/Buryat_language) (which cites the Institute of the Estonian Language) | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Extracted and annotated. Stays under CC BY-SA 4.0. |
| Unicode code points and names of the Mongolian block | `src/content/script.json` | [Unicode Character Database](https://www.unicode.org/ucd/) | [Unicode licence](https://www.unicode.org/license.txt) | None |
| The 36-letter Buryat Cyrillic alphabet and a short word list | `src/content/alphabet.json`, `src/content/words.json` | Chart attributed to Burlang.Nom, as cited by the [buryat.global](https://buryat.global) guide | The alphabet is a fact and is not claimed as anyone's text. **Licence of the buryat.global guide itself: not confirmed.** | Re-typed. Confirm before wide release. |
| Letter sound hints, respellings, comprehension tiers | `src/content/sounds.json`, `src/engine/` | Written for this project (drafted with an AI assistant) | MIT, with the rest of the code | Unreviewed approximations. |

## Fonts

| Font | Licence | Notes |
|---|---|---|
| Nunito (via the `@expo-google-fonts/nunito` package), copyright 2014 The Nunito Project Authors | [SIL Open Font License 1.1](https://openfontlicense.org) | Not modified. |
| Noto Sans Mongolian, copyright 2022 The Noto Project Authors | [SIL Open Font License 1.1](https://openfontlicense.org); text in `assets/fonts/OFL-NotoSansMongolian.txt` | Not modified. |

## Sound

| File | Source | Licence |
|---|---|---|
| `assets/sounds/correct.wav` | Freesound [29813](https://freesound.org/people/stomachache/sounds/29813/) by stomachache | [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) (trimmed, volume changed) |
| `assets/sounds/wrong.wav` | Freesound [82545](https://freesound.org/people/CaptainSiberia/sounds/82545/) by CaptainSiberia | [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) (trimmed, volume changed) |
| `assets/sounds/finish.wav` | Composed in code for this project (`scripts/make-finish.py`) | MIT, with the code |

The spoken voice in the app is the user's own device voice (text to speech). No voice recordings are included.

## Speech recognition model (web build)

| Part | Licence |
|---|---|
| Whisper tiny, by OpenAI, ONNX export from the [transformers.js](https://github.com/huggingface/transformers.js) project (`onnx-community/whisper-tiny`), loaded in the browser from the site's own folder | [Apache-2.0](https://huggingface.co/openai/whisper-tiny) |
| `@huggingface/transformers` (transformers.js) | Apache-2.0 |
| ONNX Runtime Web (`onnxruntime-web`) | MIT |

Audio never leaves the device: recognition runs in the browser.

## Images

| What | Source | Licence |
|---|---|---|
| App logo emblem (flame, sun and moon) | Flag of Buryatia on [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Flag_of_Buryatia.svg), own work by Elvonudinium | Public domain. Redrawn here in other colours. |
| Outline of Lake Baikal and Olkhon Island | `Lake_Baikal.svg`, supplied by the project owner; recoloured and turned | **Origin and licence to be confirmed by the owner.** The Selenga river and Ulan-Ude on the map are drawn schematically; they are not in that file. |
| Pictures in the picture games (dog, cat, house, and about thirty more) | [Icons8](https://icons8.com/icons/arcade), Arcade style, 96 px PNG | Icons8 free licence: use in an app or website with a link to Icons8 (shown in the picture games and on the Credits screen). They are downloaded by `scripts/fetch-icons.sh` and kept out of the source repository, since the licence does not allow redistributing them as standalone files. **Please re-read Icons8's current licence before release.** |
| About 550 more Arcade icons shown only on the experimental icon-check page (web) | [Icons8](https://icons8.com/icons/arcade), 96 px PNG, `public/icon-check/icons/` | Same terms as above; the page links to Icons8. Not in the source repository. |
| Character, scenery drawings (pine, ger, nerpa, ice) | Original artwork for this project | MIT, with the code |

## Software

The app is built with Expo, React Native, React, React Native Web, react-native-svg, expo-audio, expo-speech, expo-font and
AsyncStorage, all under the MIT licence, plus their own dependencies. A check of the production dependency tree found
permissive licences only (MIT, ISC, BSD, Apache-2.0, 0BSD, BlueOak, CC0, MPL-2.0 for two packages, and one dual-licensed
BSD-3-Clause OR GPL-2.0, used under BSD-3-Clause). Run `npx license-checker --production` for the full list.

## Not included

- The Buryat children's plays, Bible, books and poems that are part of the Sarana corpus. Their rights are unknown and they are not used.
- Any machine translation of them (`docs/childrens-plays-en.md` is for private study and is not part of the public repository).
- Raw downloaded datasets (`scripts/cache/`).

## Privacy

The app makes no network requests while you use it, collects no analytics and sends no audio anywhere. Progress is kept on
your device only.
