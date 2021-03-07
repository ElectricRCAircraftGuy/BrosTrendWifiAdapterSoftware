
Note: [per my eRCaGuy_dotfiles project](https://github.com/ElectricRCAircraftGuy/eRCaGuy_dotfiles/blob/master/git%20%26%20Linux%20cmds%2C%20help%2C%20tips%20%26%20tricks%20-%20Gabriel.txt#L2999), here are some good ways to convert and compress images:

```
convert in.png -resize 1920x1080 out.jpg \
 && cp out.jpg out2.jpg \
 && jpegoptim --size=250k out2.jpg
    <========== VERY USEFUL ==========
    Resize in.png to a max of 1920x1080 pixels (while keeping correct dimensions and convering it to out.jpg), then copy out.jpg to out2.jpg, then optimize out2.jpg to be ~250KB!
```

I used this technique to compress the "disk_photo.jpg" file here:
```bash
convert in.jpg -resize 1920x1080 out.jpg 
```
