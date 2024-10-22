Hello, well here I'll simply share with anyone my experience on how to get a Proxmox server running and how to get a hackintosh or any other virtual machine or container working under Proxmox.
This is more a note to my future self than to anyone :-P

# Get Proxmox installed.

Here the is no big mystery, we have to download a Proxmox iso from https://www.proxmox.com/, get it into a pendrive and run the installation on any PC/Notebook. If we have an old notebook or PC just for this, better.

Here is a video explaining: 
https://www.youtube.com/watch?v=5j0Zb6x_hOk

And here NetworkChuck's explanation, also very helpfull
https://www.youtube.com/watch?v=_u8qTN3cCnQ

# Install a hackintosh.
Why a hackintosh? Because I discovered Proxmox trying to get a hackintosh installed on the "new way", I got some other hackintosh working but on the "traditional way" with no virtualization involved. I followed the manual guide on Harvey’s Virtual Environment to get it running using "the new way" https://hsve.org/. 
Fortunately Harvey's team now has a automated way with pre-configured images and scripts that makes it very simple. Here is a video explaining:
https://www.youtube.com/watch?v=AFOCYOHVNCg

BTW, you need a dedicated video card to get the video passthroug: https://hsve.org/passthrough/

# Install Portainer.
Maybe you want to get Portainer installed to get some containers working with docker and docker-compose, here is how:
https://www.youtube.com/watch?v=Ax66SnZROKA

# Access your server from Internet
After all this, yo may want to access your server remotely, for this you´ll need cloudflare https://www.cloudflare.com/
Here is a video explaining how: https://www.youtube.com/watch?v=jEuZrcTvCos
To run the cloudflare service script I created a container machine on Proxmox using an Ubuntu image.


Take a look on the advice for removing the root user as default.

* You'll need to have a domain registered

I have several hours trying to get it working with HTTPS connection from the Internet. There are several videos explaining this, non of then really help me. I actually got it working with this Cloud Flare tunnel configuration, without touching or adding anything on my local server. Still don´t know how secure connection HTTPS is working... but it does

![](https://www.wd5.com.ar/github/proxmox/cloudflare.jpg)

This example is pointing to a service which is a wordpress container on the Portainer container virtual machine inside Proxmox.

# VM VNC screen resolution
To change the screen resolution for the virtual machines under VNC, when starting the machines press the ESC key several times to enter the OVMF / UEFI BIOS.
There go to Device Manager->OVMF Platform Configuration->change prefered resolution.


# Error 501 accesing console
If you get this error, enable/disable Disable Chunked Encoding on the Cloudflare tunnel



 


 
