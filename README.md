# Ubuntu + LinuxTV.org media tree custom kernel builder

The kernel that ships with Ubuntu is typically locked to a specific version,
such as 4.4. When this happens support for new media devices and fixes to
drivers are not usually backported by distro maintainers.

This system remedies that problem by taking the Ubuntu kernel and slip
streams in the latest linuxtv.org media tree. The media tree contains
all the latest drivers, so this delivers the most up to date mainline
media drivers seamlessly to Ubuntu users.

The script is designed to patch and build installable Ubuntu kernel packages.
This script is used to develop and maintain the following Launchpad PPA:

https://launchpad.net/~b-rad/+archive/ubuntu/kernel+mediatree+hauppauge

The above ppa provides installable and upgradeable debs, so end users do
not have to recompile the kernel and/or modules themselves.

## To install and keep up to date with the PPA

Two virtual package are provided in the PPA
 * linux-image-mediatree
 * linux-headers-mediatree

### First add the PPA and update

sudo add-apt-repository ppa:b-rad/kernel+mediatree+hauppauge

sudo apt-get update

### Then install the virtual packages (enables updates)

sudo apt-get install linux-image-mediatree

sudo apt-get install linux-headers-mediatree

If you use an NVidia or AMD graphics card it is imperative to install
the linux-headers-mediatree package in order for the graphics card drivers
to sucessfully regenerate on driver upgrade. There are many other packages
similarly requiring kernel headers, so most users should install this.

The PPA will be updated once a week, or immediately upon new Ubuntu kernel release.

## Hauppauge Computer Works is proud sponsor of this effort.

http://www.hauppauge.com

## This script produces installable kernel packages from
 * Ubuntu kernel git for a specific release
 * Latest upstream LinuxTV media tree drivers
 * Minimal patches to get the above to build
 * Additional patches to enable HW and/or optimizations not yet upstreamed


## This script also:
 * A full patch series for reproduction
 * Generate latest LinuxTV driver patch set on demand

## Development use

todo

## Author
 * Brad Love <brad at nextdimension dot cc>


## License

This program utilizes the GNU Publicc License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later version.


## Acknowledgments

https://linuxtv.org

https://ubuntu.org

http://www.hauppauge.com
