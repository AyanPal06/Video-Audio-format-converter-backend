# Audio Converter API - Documentation

## How the API works
- Built with Flask.
- Uses `ffmpeg` (must be installed on the host machine) to perform audio format conversions.
- Endpoints:
  - `POST /convert` - accepts `multipart/form-data` with a file and `target_format`. Returns the converted file.
  - `GET /formats` - returns JSON lists of supported input and output formats.

## Supported formats (20+)
### Input (20)
mp3, wav, aac, flac, ogg, wma, m4a, aiff, alac, amr, opus, ac3, au, pcm, tta, wv, ra, voc, mid, midi

### Output (20)
mp3, wav, aac, flac, ogg, wma, m4a, aiff, alac, amr, opus, ac3, au, pcm, tta, wv, ra, voc, ogg, mp3

## Endpoints and usage
1. Convert:
```bash
curl -X POST "http://localhost:5002/convert" \
  -F "file=@path/to/input.wav" \
  -F "target_format=mp3" \
  -F "filename=outname"
```

2. List supported formats:
```bash
curl http://localhost:5002/formats
```

## Notes
- ffmpeg must be installed and available in PATH.
- For best results with lossless/lossy choices, choose appropriate target format (e.g., flac for lossless).