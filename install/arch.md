## Arch Linux

These instructions are for Arch Linux 3.9

### Command-line Interface (CLI)

1. Install packages available in official repositories

		sudo pacman -S rtmpdump ffmpeg mplayer id3v2 perl-xml-simple perl-mp3-info

2. Install remaining packages from Arch User Repository (AUR)

	Although not covered here, you may also be able to install the AUR packages with [yaourt](https://wiki.archlinux.org/index.php/Yaourt).

	First, make a base directory for the package builds:

		mkdir ~/packages

	Then download, build and install each package in turn:

		cd ~/packages
		curl -kLO https://aur.archlinux.org/packages/ge/get_iplayer/get_iplayer.tar.gz
		tar xzf get_iplayer.tar.gz
		cd get_iplayer
		makepkg -s
		sudo pacman -U get_iplayer*.tar.xz
	
		cd ~/packages
		curl -kLO https://aur.archlinux.org/packages/at/atomicparsley/atomicparsley.tar.gz
		tar xzf atomicparsley.tar.gz
		cd atomicparsley
		makepkg -s
		sudo pacman -U atomicparsley*.tar.xz
	
		cd ~/packages
		curl -kLO https://aur.archlinux.org/packages/pe/perl-mp3-tag/perl-mp3-tag.tar.gz
		tar xzf perl-mp3-tag.tar.gz
		cd perl-mp3-tag
		makepkg -s
		sudo pacman -U perl-mp3-tag*.tar.xz
	
		cd ~/packages
		curl -kLO https://aur.archlinux.org/packages/pe/perl-net-smtp-tls-butmaintained/perl-net-smtp-tls-butmaintained.tar.gz
		tar xzf perl-net-smtp-tls-butmaintained.tar.gz
		cd perl-net-smtp-tls-butmaintained
		makepkg -s
		sudo pacman -U perl-net-smtp-tls-butmaintained*.tar.xz

	With `perl-net-smtp-tls-butmaintained` version 0.21, makepkg fails with the message "ERROR: Failure while downloading Net-SMTP-TLS-ButMaintained-0.21.tar.gz".  That error indicates the upstream source code was removed.  If that happens you can try this procedure:
	
		# Hack PKGBUILD to download source from a different location
		cp PKGBUILD PKGBUILD.orig
		sed -e "s|search.cpan.org/CPAN|cpan.metacpan.org|g" PKGBUILD.orig > PKGBUILD
		
		# Skip checksum integrity check during package build
		makepkg -s --skipinteg
		
		# Install the package
		sudo pacman -U perl-net-smtp-tls-butmaintained*.tar.xz

NOTE: If you use SSL email, you may see a deprecation warning about the use of SSL_verify_mode, a parameter used by the IO::Socket::SSL module.  However, your emails should still be transmitted successfully.

### Web PVR Manager (WPM)

The WPM is not installed with the get_iplayer package.  Use the [[manual installation procedure|manual]].
