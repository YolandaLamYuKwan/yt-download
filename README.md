# yt-download
#A package from git hub for linking YouTube
from pytube import YouTube

#Define the dowload(link) function
def download(link):
    yt = YouTube(link)
#The user only have to input the integer, with no spacing and any other char
    resolution = input("Enter the resolution (144, 360, 480, 720, 1080): ")
#Convert the user-input resolution (represented as a string) into the corresponding resolution string that is recognized by the
    resolution_str = get_resolution_str(resolution)
#Set the limit of the chance of re-input
    retry = 0
#While loop condition to handle the situation which will leads to the failure o fthe programe
    while resolution_str is None and retry < 4:
        print("Invalid resolution")
#when retry>3, the loop will be stopped
        retry = retry + 1
#Looping if all the conditions is satisfied
        resolution = input("Enter the resolution (144, 360, 480, 720, 1080): ")
        resolution_str = get_resolution_str(resolution)
    if resolution_str is None:
#Check if the `resolution_str` variable is `None`, indicating that the user has entered an invalid resolution that doesn't exist in the `switcher` dictionary
        print("Error")
        return
    stream = yt.streams.filter(res=resolution_str, progressive=True).first()
#Filters the available video streams of the YouTube video object `yt` based on the specified resolution
#(`resolution_str`) is the `progressive` parameter set to `True`.
#Selects the first stream that matches the criteria and assigns it to the `stream` variable.
    if stream is None:
#Checks if the `stream` variable is `None`
#Indicating that there is no video available in the specified resolution
#Means the video is not available in the desired resolution, and a message stating that the video is not available in that resolution and returns from the `download` function if it is ‘None’ is printed
        print("Video not available in this resolution")
        return
    output_path = "C:/video/"
#Defines the output path where the downloaded video will be saved.
#It is set to the "C:/video/" directory.
    stream.download(output_path)
#Downloads the selected video stream (`stream`)
#Saves it to the specified output path (`output_path`).
    print("Download completed successfully")

#Translate the input from user to a proper format
def get_resolution_str(resolution):
    switcher = {
        "144": "144p",
        "360": "360p",
        "480": "480p",
        "720": "720p",
        "1080": "1080p",
    }
    return switcher.get(resolution)

#Allows user to input their destinated
link = input("Enter the YouTube video URL: ")
download(link)

!pip install pytube3
from pytube import YouTube


def Download(link):
    yt = YouTube(link)
    resolution = input("input the resolution, e.g.144p, please enter 144")
    retry = 0
def demo(resolution):
    switcher = {
        "144" : "144p",
        "360" : "360p",
        "480" : "480p",
        "1080" : "1080p",
}
    return switcher.get(resolution, "Invalid")
    yt = yt.streams.resolution
    if retry < 4 :
        try:
           yt.download()
           output_path = "./downloads/"
           retry = retry + 1
        except:
           print("An error has occurred")
    print("Download is completed successfully")

link = input("Enter the YouTube video URL: ")
Download(link)

!pip install pytube3
from pytube import YouTube


def Download(link):
    yt = YouTube(link)
    resolution = input("input the resolution, e.g.144p, please enter 144")
    retry = 0
def demo(resolution):
    switcher = {
        "144" : "144p",
        "360" : "360p",
        "480" : "480p",
        "1080" : "1080p",
}
    return switcher.get(resolution, "Invalid")
    yt = yt.streams.resolution
    if retry < 4 :
        try:
           yt.download()
           output_path = "./downloads/"
           retry = retry + 1
        except:
           print("An error has occurred")
    print("Download is completed successfully")

link = input("Enter the YouTube video URL: ")
Download(link)

!pip install pytube3
from pytube import YouTube

def Download(link):
    youtubeObject = YouTube(link)
    youtubeObject = youtubeObject.streams.get_highest_resolution()
    try:
        youtubeObject.download()
    except:
        print("An error has occurred")
    print("Download is completed successfully")


link = input("Enter the YouTube video URL: ")
Download(link)
