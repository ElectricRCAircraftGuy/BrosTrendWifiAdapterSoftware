[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FElectricRCAircraftGuy%2FBrosTrendWifiAdapterSoftware&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=views+%28today+%2F+total%29&edge_flat=false)](https://hits.seeyoufarm.com)

# Repo Status

Ready for use. The entire disk which came with the Wifi adapter is in this repo.


# Table of Contents
<details>
<summary><b>(click to expand or hide)</b></summary>
<!-- MarkdownTOC -->

1. [BrosTrendWifiAdapterSoftware](#brostrendwifiadaptersoftware)
    1. [How I copied the entire disk to my Linux Ubuntu laptop](#how-i-copied-the-entire-disk-to-my-linux-ubuntu-laptop)

<!-- /MarkdownTOC -->
</details>


<a id="brostrendwifiadaptersoftware"></a>
# BrosTrendWifiAdapterSoftware
Software that comes on the mini CD (which is inconvenient) with BrosTrend WiFi adapters, and my personal installation notes for Linux.

Here is the adapter I purchased for $36 from Amazon in Mar. 2021: [BrosTrend AC1200 2.4GHz/5GHz WiFi adapter, Model No. AC3L](https://www.amazon.com/gp/product/B07FCN6WGX?ie=UTF8&psc=1&linkCode=ll1&tag=wwwel-20&linkId=b7839451620775257a522bc50b9a33b5&language=en_US&ref_=as_li_ss_tl):

<p align="left" width="100%">
    <a href="https://www.amazon.com/gp/product/B07FCN6WGX?ie=UTF8&psc=1&linkCode=ll1&tag=wwwel-20&linkId=b7839451620775257a522bc50b9a33b5&language=en_US&ref_=as_li_ss_tl">
        <img width="25%" src="images/BrosTrend_AC1200_AC3L.jpg"> 
    </a>
</p>

Disk that came with it:

<p align="left" width="100%">
    <a href="Driver_and_Manual_disk" title="Click to browse BrosTrend Driver_and_Manual_disk files">
        <img width="30%" src="images/disk_photo.jpg"> 
    </a>
</p>

<a id="how-i-copied-the-entire-disk-to-my-linux-ubuntu-laptop"></a>
## How I copied the entire disk to my Linux Ubuntu laptop

1. I used [this external CD/DVD drive which I bought for $27 from Amazon](https://www.amazon.com/gp/product/B08B3SCV18?ie=UTF8&psc=1&linkCode=ll1&tag=wwwel-20&linkId=3d0648e4deeb651fe0ae63f4cc43a2e8&language=en_US&ref_=as_li_ss_tl). It works great! It was plug-and-play on Linux Ubuntu, and required no special setup. I just plugged it into a single USB 3.0 port, from where it drew power as well, and it worked with no problem. 
1. Here is how I copied the entire contents of the DVDs above on my Linux Ubuntu computer, FROM directory `/media/gabriel/Driver&Manual` TO directory `~/GS/dev/BrosTrendWifiAdapterSoftware`:

    ```bash
    # First, do a dry run to make sure the statistics summary at the end all looks good, and that
    # "Number of deleted files" (meaning: files it's going to delete from your destination directory)
    # is 0.
    time rsync -rah --dry-run --info=progress2 --stats '/media/gabriel/Driver&Manual' ~/GS/dev/BrosTrendWifiAdapterSoftware

    # When ready, remove the `--dry-run` flag above to actually do the copy. In the event there are any
    # disk read errors, simply re-run this command repeatedly until you no longer get any errors and it
    # all passes. Any read errors will show up live in the `rsync` terminal output while the command
    # runs. If you get read errors, you may need to clean the disk and try again. `rsync` is great in
    # that it scans for and only copies changes between source and destination, which makes it as though
    # it can pick up where it left off, so re-running the command is usually very fast.
    time rsync -rah --info=progress2 --stats '/media/gabriel/Driver&Manual' ~/GS/dev/BrosTrendWifiAdapterSoftware

    # Once done copying, add (`+`) read/write (`rw`) privileges for your user and group (`ug`) to all
    # files you just copied (in the destination directory), like this. This allows you to be able to
    # move, modify, rename, etc. them as you see fit using your favorite file manager, such as nemo (my
    # favorite; see here for how to install it: https://askubuntu.com/a/1173861/327339) or nautilus (the
    # default that comes with Ubuntu).
    cd ~/GS/dev/BrosTrendWifiAdapterSoftware
    chmod -R ug+rw 'Driver&Manual'
    ```


----

Disclaimer required by Amazon:  
_We are a participant in the Amazon Services LLC Associates Program, an affiliate advertising program designed to provide a means for us to earn fees by linking to Amazon.com and affiliated sites._  
I make virtually nothing from Amazon in this way, but I must include this disclaimer anyway. 
