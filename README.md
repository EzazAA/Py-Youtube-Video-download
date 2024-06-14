
---

# YouTube Video Downloader

This Python script allows you to easily download YouTube videos using the `pytube` library. It provides a simple command-line interface for users to input the URL of the YouTube video they want to download.

## Prerequisites

Before using this script, ensure you have Python installed on your system. You also need to install the `pytube` library. You can install it via pip:

```bash
pip install pytube
```

## Usage

1. Clone the repository or copy the script `youtube_downloader.py` to your local machine.
2. Open a terminal or command prompt.
3. Navigate to the directory where `youtube_downloader.py` is located.
4. Run the script by executing the following command:

```bash
python youtube_downloader.py
```

5. Enter the URL of the YouTube video you want to download when prompted.
6. The script will download the highest resolution MP4 video available and save it to the current directory.

You can also specify a download path by editing the `download_video` function in the script and passing the desired output path as an argument.

```python
def download_video(url, path=''):
    try:
        yt = YouTube(url)
        video = yt.streams.filter(progressive=True, file_extension='mp4').order_by('resolution').desc().first()
        if path:
            video.download(output_path=path)
        else:
            video.download()
        print("Download completed successfully.")
    except Exception as e:
        print("An error occurred:", str(e))
```
## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- This script uses the `pytube` library, developed by Nick Ficano. You can find the library [here](https://github.com/nficano/pytube).
- Special thanks to the open-source community for their contributions and support.

## Contributing

Contributions are welcome! If you find any bugs or have suggestions for improvements, please open an issue or create a pull request.

---
