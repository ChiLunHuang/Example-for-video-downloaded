# Example for video download

## Import two packages

You can use `requests` to get the web content and use `shutil` to download video, and you can see more detail in [doucument](https://docs.python.org/3/library/shutil.html) provided by [The Python Standard Library](https://docs.python.org/3/library/).

```python
import requests,shutil
```

## Just two steps, you can get the video

### Get web Content

You have to find the real url of videos by using `F12` and `Network` to filter the `Media` information.

After that, we can easily to get the video by requests.

```python
res=requests.get(url)
```

### Download the video by shutil

```python
with open('D://myVideo.mp4','wb') as f:
    shutil.copyfileobj(res.raw,f)

f.close()
```

Note:
>On Windows, `'b'` appended to the mode opens the file in binary mode, so there are also modes like `'rb'`, `'wb'`, and `'r+b'`

