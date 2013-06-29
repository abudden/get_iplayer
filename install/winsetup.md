## Windows Installer

Windows users should install get_iplayer with the provided installer.  Download the latest version from:

<http://www.infradead.org/get_iplayer_win/get_iplayer_setup_latest.exe>

### Perl Support

The installer will install a private customised version of [Strawberry Perl](http://strawberryperl.com/) that includes all necessary Perl modules.  It will not interfere with any other Perl distribution you may already have installed.

### External Programs

The installer will download and install all the required Windows support programs.

### Command-line Interface (CLI)

1. Start the installer and follow the wizard in the usual manner.  Select all components for installation The installer will download and install get_iplayer, Perl and the Windows support programs: RTMPDump, FFmpeg, MPlayer, LAME, AtomicParsley and VLC Media Player. 

2. To start the CLI go to `All Programs -> get_iplayer -> Get_iPlayer` on the Start menu.  In the Windows 8 Start screen, click the `Get_iPlayer` tile.   The CLI will launch in a console window.  The working directory of the console window will be the get_iplayer installation directory, typically `C:\Program Files\get_iplayer` or `C:\Program Files (x86)\get_iplayer` on 64-bit Windows.  The CLI expects to operate in that directory, so do not change to another location.

3. The first time MPlayer runs (i.e., the first time you download a regional or local radio programme) after a fresh installation, it will scan the available fonts on your system and will produce a large volume of extra output in your console window.  This will not affect the programme download.

4. **NOTE**: Unless you opt to change the default value, the installer sets the location for recorded programmes to `iPlayer Recordings` on your Windows desktop.  This setting only applies to the administrator user who ran the installer.  If you have multiple users running get_iplayer on one Windows system, the other users will need to configure their own output folders with the CLI:

		get_iplayer --prefs-add --output "%USERPROFILE%\Desktop\iPlayer Recordings"

### Web PVR Manager (WPM)

The WPM is installed along with the CLI.
    
1. To start the WPM go to **All Programs -> get_iplayer -> Web PVR Manager** on the Start menu.  In the Windows 8 Start screen, click the **Web PVR Manager** tile.  

2. The WPM will launch in a console window and your default browser will be opened to this URL:

    <http://127.0.0.1:1935>