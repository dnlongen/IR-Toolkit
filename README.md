# IR Toolkit
=============

* Written by David Longenecker
* Twitter: @dnlongen
* Email: david (at) securityforrealpeople.com
* More info: https://www.securityforrealpeople.com/irtoolkit

A collection of handy tools and scripts useful for computer incident response. With few exceptions, all tools are portable versions so the contents can be put ont a USB flash drive for easy use where needed. It should go without saying that an IR toolkit that will be used on suspected compromised systems should be read-only. I like Kanguru FlashBlu30 for its physical write-block switch and reasonable price, but others will do.

* **WinPython:** Portable installation of Python with a myriad pre-installed packages, supporting the use of Python-based analysis scripts. Download your preferred flavor(s) of Python from https://winpython.github.io.
* **RegistryExplorer:** Eric Zimmerman’s RegistryExplorer.exe (GUI) and RECmd.exe are small, fast Windows registry utility with strong searching capabilities. Find the latest version at https://ericzimmerman.github.io/
* **SQLiteDatabaseBrowserPortable:** Portable SQLite database browser. A variety of mobile and web apps store data in SQLite, and Firefox and Thunderbird use it to store some usage artifacts. Available as a PortableApps package at https://portableapps.com/apps/development/sqlite_database_browser_portable
* **Sysinternals:** Numerous Windows Internals tools, documented at and downloadable from https://technet.microsoft.com/en-us/sysinternals. Note that SysInternals tools can also be run directly from the web, but you may not want your target host connected while forensicating it. Particularly useful:
** autoruns.exe (GUI) and autorunsc.exe (cli): show programs set to run automatically, via registry settings, browser plugins, Windows Explorer hooks, system services, etc.
** procexp.exe: Process Explorer. Windows Task Manager alternative with considerably more features. Find what processes are using what files, registry keys, objects, etc.
** procmon.exe: Process Monitor. Real time monitor foe file system, registry, and process/thread activity.
** strings.exe: Search a binary file for human-readable strings in ASCII or UNICODE format.
** tcpview: Show listing of all TCP and UDP ports in use, and the process associated with each.
* **wget:** command-line, text-based web browser. Useful for downloading suspect links without risking exploitation. Note: some malicious websites will read the user agent string and deliver a benign payload or an error if it detects the default wget UA string. Use “wget –user-agent=AGENT” to spoof a particular browser or device.  Find a download mirror from the downloads list at the GNU project site: https://www.gnu.org/software/wget/faq.html#download. https://udger.com/resources/ua-list is a handy compilation of UA strings by browser, OS, and version.
* **wireshark:** The ubiquitous packet capture utility, for network traffic capture and analysis. Note that wireshark itself comes in a PortableApps package, but the WinPCAP driver must be installed on the system that will collect packets. See https://www.wireshark.org/download.html for the latest Wireshark PortableApps version, and https://www.winpcap.org/install/default.htm for the latest WinPcap driver.
* **exiftool.exe:** Extract EXIF metadata from images, PDFs, Office documents, etc. Obtain it from https://www.sno.phy.queensu.ca/~phil/exiftool/
* **Didier Stevens Tools:** Didier has written and released many handy Python scripts useful for IR and malware analysis. All are available from his blog, https://blog.didierstevens.com/my-software/ Ones that I use most often:
** pdf-parser.py: PDF analyzer: Analyze the individual components of a PDF file. Documentation at https://blog.didierstevens.com/programs/pdf-tools/
** pdfid: Quick and dirty triage tool, shows a count of objects in a PDF file, by object type. Useful for seeing at a glance whether there are JS or URI objects likely to be booby-traped. Documentation at https://blog.didierstevens.com/2017/10/30/update-pdfid-py-version-0-2-2/
* **PDF Stream Dumper:** GUI PDF tool for extracting individual components from a PDF. Source from **(Warning: no HTTPS)** http://sandsprite.com/blogs/index.php?uid=7&pid=57. See https://www.securityforrealpeople.com/2015/08/cracking-ctf-part-1.html for a practical example of using the respective strengths of these two PDF tools together.
* **reglister.py:** Command line utility for searching the registry for large data blobs - a popular technique for hiding malware where antivirus cannot scan for it. Documented at https://github.com/dnlongen/RegLister
* **SnmpWalk.exe:** command line utility for querying SNMP on a target. Available from SolarWinds at https://support.solarwinds.com/Success_Center/Network_Performance_Monitor_(NPM)/SolarWinds_SNMP_Walk_A_new_tool_for_collecting_SNMP_MIB_walks
* **NirSoft Tools:** Download latest versions from http://www.nirsoft.net/utils/index.html
** AlternateStreamView: GUI tool to see Alternate Data Streams, file content that may not be visible in the standard Windows file manager. See http://www.nirsoft.net/utils/alternate_data_streams.html for documentation.
** USBDeview: list USB devices currently connected, as well as that were connected in the past.
** HashMyFiles: Generate MD5, SHA-1, and SHA-256 hashes for a file or folder. Handy for hashing a suspect file to search VT for, instead of submitting a potentially revealing file.

A few additional tools in my toolkit are not strictly incident response items, but come in handy when the right situation presents itself.

* **Binwalk:** Analyze, reverse engineer, and extract contents from firmware binaries. Find the latest version along with documentation at https://github.com/devttys0/binwalk
* **Burpsuite:** The free edition has a MITM web proxy, useful for inspecting and manipulating HTTP and HTTPS traffic to and from your browser. The commercial version adds many more testing and attack bells and whistles. 
* **3CDaemon:** 3Com's ancient TFTP/syslog/FTP client and server. Alas I am not aware of a trustworthy source for it today, but if you have it, it's worth dropping on your thumb drive as a (possibly) safer way to get files on and off a compromised system than using SMB or HTTP.
