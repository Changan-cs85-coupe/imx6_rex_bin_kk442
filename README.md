# imx6_rex_kk442
imx6q/dl rex android kitkat binaries


# Download repository
    git clone https://github.com/voipac/imx6_rex_bin_kk442
    cd imx6_rex_bin_kk442/

# Extract system.img
    7z x system.img.7z.001
    
# Install android into mmcblk0 card
    sudo ./fsl-sdcard-partition.sh -f /dev/mmcblk0
    
# Setup u-boot (HDMI)
    setenv bootargs console=ttymxc0,115200 init=/init video=mxcfb0:dev=hdmi,1280x720M@60,if=RGB24,bpp=32 video=mxcfb1:off video=mxcfb2:off fbmem=28M vmalloc=400M androidboot.console=ttymxc0 androidboot.hardware=freescale
    setenv bootcmd booti mmc1
    saveenv
    reset

# Setup u-boot (LVDS)
    setenv bootargs console=ttymxc0,115200 init=/init video=mxcfb0:dev=ldb,LDB-ETV570,if=RGB666 video=mxcfb1:off video=mxcfb2:off fbmem=10M vmalloc=400M androidboot.console=ttymxc0 androidboot.hardware=freescale
    setenv bootcmd booti mmc1
    saveenv
    reset
