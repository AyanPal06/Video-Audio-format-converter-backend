# Video Converter API - Documentation

## How the API works
- Built with Flask.
- Uses `ffmpeg` (must be installed on the host machine) to perform all format conversions.
- Exposes two endpoints:
  - `POST /convert` - accepts `multipart/form-data` with a file and `target_format` form field. Returns the converted file as attachment.
  - `GET /formats` - returns JSON lists of supported input and output formats.

## Supported formats (20+)
### Input (20)
mp4, mkv, mov, avi, flv, wmv, webm, mpeg, mpg, 3gp, m4v, ts, mts, vob, ogv, qt, rm, rmvb, ivf, f4v

### Output (20)
mp4, mkv, avi, flv, wmv, webm, mpeg, mpg, 3gp, mov, m4v, ts, ogg, mp3, wav, aac, flac, opus, amr, wma

## Endpoints and usage
1. Convert:
```bash
curl -X POST "http://localhost:5001/convert" \
  -F "file=@path/to/input.mp4" \
  -F "target_format=mp3" \
  -F "filename=output_name"
```
This will convert input.mp4 -> output_name.mp3 and return the converted file.

2. List supported formats:
```bash
curl http://localhost:5001/formats
```

## Notes
- ffmpeg must be installed and available in PATH.
- For large files, increase server timeout and be mindful of disk space (uploads saved to `uploads/`).
- The project uses a very small wrapper around ffmpeg — you can extend it to add specific codec flags for quality control.