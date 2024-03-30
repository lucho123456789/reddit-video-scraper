# reddit video scraper
<div align="center">
  
![DescargarBot](https://www.descargarbot.com/v/download-github_02.png)
  
[![Reddit](https://img.shields.io/badge/on-descargarbot?logo=github&label=status&color=green
)](https://github.com/lucho123456789/reddit-video-scraper/issues "Reddit")
</div>

<h2>dependencies</h2>
<code>Python 3.9+</code>
<code>Requests</code>
<code>FFmpeg</code>

<h2>use case example</h2>
<code>

    #import the class RedditVideoScraper
    from reddit_video_scraper import RedditVideoScraper
    
    # set reddit video url
    reddit_url = 'ur reddit video url'
    
    # create scraper video object
    reddit_video = RedditVideoScraper()

    # set the proxy (optional, u can run it with ur own ip)
    #reddit_video.set_proxies('<your http proxy>', '<your https proxy')

    # get video info from url
    reddit_video_info = reddit_video.get_video_json_by_url(reddit_url)

    # get the video details
    reddit_video_urls, video_thumbnail, video_nsfw = reddit_video.reddit_video_details(reddit_video_info)

    # get the video filesize
    video_size = reddit_video.get_video_filesize(reddit_video_urls['video_url'], reddit_video_urls['audio_url'])
    print(f'filesize: ~{video_size} bytes')

    # download the video and audio
    download_details = reddit_video.download(reddit_video_urls)

    # join the video and audio
    # remember install ffmpeg if u dont have it
    downloaded_video_list = reddit_video.ffmpeg_mux(download_details)

    reddit_video.reddit_session.close()
</code>

<h2>installing dependencies</h2>
