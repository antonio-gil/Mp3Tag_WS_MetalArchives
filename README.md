# Mp3Tag_WS_MetalArchives
MP3Tag scripts for pulling data from Metal Archives

```
     _____          __         .__           _____                .__    .__
    /     \   _____/  |______  |  |         /  _  \_______   ____ |  |__ |__|__  __ ____   ______
   /  \ /  \_/ __ \   __\__  \ |  |        /  /_\  \_  __ \_/ ___\|  |  \|  \  \/ // __ \ /  ___/
  /    Y    \  ___/|  |  / __ \|  |__     /    |    \  | \/\  \___|   Y  \  |\   /\  ___/ \___ \ 
  \____|__  /\___  >__| (____  /____/     \____|__  /__|    \___  >___|  /__| \_/  \___  >____  >
          \/     \/          \/                   \/            \/     \/              \/     \/ 
                     
 Mp3tag parsing for Metal-Archives.com, created by dano on 2007-12-15
 
 Only search for Metal music, normal music is not on the site
 
 Also only real Metal. KoRn, Linkin Park or similar is not on the site
 ```
 
These scripts, as the previous decriptions indicates, were created by [**dano**](https://community.mp3tag.de/u/dano/summary), an user from the [MP3Tag Community](https://community.mp3tag.de) (forums, brefore the change to a Discord platform), and they take information from the Encyclopaedia Metallum (a.k.a. Metal Archives, or MA).

Since he doesn't seems to be very active lately, nor there signs that he's doing updates to the scripts, I'm making this repository in order to keep them updated, as the layout on MA changes (if it happens).

---

# Advanced Scripts

## Description

Those scripts make use of Metal Archive's "Advanced Search" to retrieve all available editions/versions of a given album using (generally speaking) Band Name, and Album Title as input parameters. There are, nonetheless, some key differences between both scripts:

* **Search by Band + Album (Advanced)**: This script only uses **Band Name** and **Album Title** to search a given album and it'll retrieve **all editions/versions** available for that album, meaning that all formats will be listed on results dialog (CD, DVD, Vinyl, etc).
* **Search by Band + Album (Advanced By Format)**: This script uses **Band Name**, **Album Title**, as well **Release Format** to search a given album and it'll retrieve **only those editions/versions** that match provided format.

## Usage

Advanced scripts work in the same way as "regular" script, although there are some small differences:

* In both scripts, results dialog will display a couple of additional columns/information, **Catalog** and **Format**, to make easier to locate required edition/version.
* When using "**Advanced By Format**" script, an additional field for album format will be displayed on search dialog, and only one format can be used per search (this due to technical limitations). Available formats are:
    * CD
    * Cassette
    * Vinyl
    * VHS
    * DVD
    * Digital
    * Blu-ray
    * Other

Please keep in mind the following when "**Advanced By Format**" script:

* If no format is defined/indicated on search dialog, script will default to the first edition found. i.e., it'll behave as regular "Band + Album" script.
* Despite this, even when using the "Quick search" button, search dialog will be always shown as Release Format is a value that "doesn't exists" on file and it only exist for search purposes.

## F.A.Q.

Q: Why only one Release Format can be used at a given time?  
A:
* **Long story short:** This is due to how underlying search is performed, as well MP3Tag script language limitations + a potential lack of knowledge.

* **Technical answer:** To be able to search by multiple formats at once, scripting language needs to be able to dynamically construct a query based on how many formats are defined/included on search dialog. As far as I know required language features are not present on MP3Tag's scripting language, so it's almost impossible to be able to implement that (hence why 2 different scripts). Nonetheless, I'll keep an eye on future developments of scripting language in case that it includes a way to implement searching by multiple formats at once (**if needed**).

Q: Why only use a "Band + Album" approach for advanced search?  
A: As mentioned on Release Notes/Changelog, these scripts are still experimental in the sense that although they work as expected, so there could be improvement areas and are subject to future changes. Also, there's the issue that during initial tests, some albums took a while to be loaded into results dialog (mainly due to how many versions are available on MA's database), and to avoid any potential issues I decided to use a restricted way to search an album by using also the Band Name to narrow down potential results.