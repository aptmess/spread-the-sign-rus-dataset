# Spread-The-Sign Russian Dataset

This is parsed Sign Language Russian Dataset from the [SpreadTheSign site](https://spreadthesign.com/ru.ru/search/by-category/).

## Downloads

You ara available to download dataset from this [source]() in [ZIP](https://en.wikipedia.org/wiki/ZIP_(file_format)) format (~1.6GB).

## Dataset Information

### Words Annotatations

Annotation file is easy to use and contains some useful columns, see `words.csv` file:

| id   | word        | word\_type        | word\_url                                                                                                                        | video\_link                                             | poster\_link                                            | video\_width | video\_height | word\_category                 | video\_duration    | error\_type | amount\_of\_frames |
|:-----|:------------|:------------------|:---------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------|:--------------------------------------------------------|:-------------|:--------------|:-------------------------------|:-------------------|:------------|:-------------------|
| 6    | юбка        | Существительное   | https://www.spreadthesign.com/ru.ru/word/1493/iubka/0/?q=%D1%8E%D0%B1%D0%BA%D0%B0                                                | https://media.spreadthesign.com/video/mp4/12/14812.mp4  | https://media.spreadthesign.com/video/jpg/12/14812.jpg  | 320.0        | 240.0         | Жестовый язык для начинающих   | 3.48               | 0           | 87.0               |
| 7    | экран       | Существительное   | https://www.spreadthesign.com/ru.ru/word/4502/ekran/0/?q=%D1%8D%D0%BA%D1%80%D0%B0%D0%BD                                          | https://media.spreadthesign.com/video/mp4/12/44584.mp4  | https://media.spreadthesign.com/video/jpg/12/44584.jpg  | 320.0        | 240.0         | Жестовый язык для начинающих   | 3.24               | 0           | 81.0               |
| 8    | шея         | Существительное   | https://www.spreadthesign.com/ru.ru/word/8229/sheia/0/?q=%D1%88%D0%B5%D1%8F                                                      | https://media.spreadthesign.com/video/mp4/12/349187.mp4 | https://media.spreadthesign.com/video/jpg/12/349187.jpg | 320.0        | 240.0         | Жестовый язык для начинающих   | 1.72               | 0           | 43.0               |

where:

- `id` - unique `word_id` | `UInt16`
- `word` - gesture class in Russian Langauge | `String`
- `word_type` - part of the speech | `String`
- `word_url` - link to the word in Russian Language on SpreadTheSign Site | `String`
- `video_link` - download link for the video of sign russian language translator of the `word` | `Nullable(String)`
- `poster_link` - link to the poster from the video (freeze frame from the video) | `Nullable(String)`
- `video_height` - video height | `nullable(UInt8)`
- `video_width` - video width | `nullable(UInt8)`
- `word_category` - the category of `word` in Russian Language from SpreadTheSign Site | `String`
- `video_duration` - video duration in seconds | `UInt16`
- `error_type` - type of error when parsing video | `Enum`:
  - `0` - `OK` - the video was processed correctly
  - `1` - `Not Found` - there is no video for the word on the site
  - `2` - `Requests Error` - processing error on the site
  - `3` - `Unprosessed entity` - the color black in the video, unprosessed entity
- `amount_of_frames` - the number of frames for the video (in increments of `0.04` ms) | `UInt16`

The corresponding video to each `id` is stored in folder `./video/<id>.mp4`

### Letters Annotatations

Annotation file is easy to use and contains some useful columns for letters translation, see `letters.csv` file:

| id   | letter        | letter\_image\_url |  
|:-----|:------------|:------------------|
|1|у|https://media.spreadthesign.com/image/500/alphabet-letter-886-1.jpg|
|2|ф|https://media.spreadthesign.com/image/500/alphabet-letter-887-1.jpg|
|3|х|https://media.spreadthesign.com/image/500/alphabet-letter-888-1.jpg|               

where:

- `id` - unique `letter_id` | `UInt8`
- `letter` - unique letter | `String`
- `letter_image_url` - link to the url of downloaded image from SpreadTheSign Site | `String`

The corresponding letter image representation to each `id` is stored in folder `./letters/<id>.jpg`

### Dataset Statistic

- Number of videos - `14815`
- Duration (h) - `2.26
- Vocabulary size (words) - `12.4K`
- Number of frames - `1.12M`
- Resolution, Fps - `340x360, 30`

## Distibutor

- [Aleksandr Shirokov](https://github.com/)

