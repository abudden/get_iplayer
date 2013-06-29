## Raspbian / Raspberry Pi

These instructions are for Raspbian wheezy.

### Command-line Interface (CLI)

Although the Debian get-iplayer package is incorporated in Raspbian repositories, Raspbian users are recommended to use the get_iplayer repository version (see below).  If you must use the Debian package, refer to the above instructions for Debian installation.  Note that the version of AtomicParsley
packaged with Raspbian frequently fails with files downloaded with get_iplayer.

#### get_iplayer Repository Installation

1. Add the repository

    Paste these _five_ lines into a terminal window:

	    sudo bash -c "cat > /etc/apt/sources.list.d/packages.hedgerows.org.uk.list <<EOF
	    deb http://packages.hedgerows.org.uk/raspbian wheezy/
	    deb-src http://packages.hedgerows.org.uk/raspbian wheezy/
	    EOF
	    "

2. Update, and install the repository signing key, and update again:

	    sudo apt-get update
	    sudo apt-get --allow-unauthenticated -y install jonhedgerows-keyring
	    sudo apt-get update

3. Install the get-iplayer package

    	sudo apt-get install get-iplayer

4. Run CLI with:

    	get_iplayer […]

### Web PVR Manager (WPM)

The WPM is installed along with the CLI.

1. Launch the WPM in with this command:

    	get_iplayer_web_pvr

2. Once the WPM is running, connect to it by opening this URL in your browser:

    <http://127.0.0.1:1935>

3. Stop the WPM by typing Ctrl-C.
