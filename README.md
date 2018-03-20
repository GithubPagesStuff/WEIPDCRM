<!DOCTYPE html>
<html lang="ja"><head>
<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=Edge" />
</head>
<body>
<h1>Darwin Cydia Repository Manager (DCRM) Pro Guide</h1>
<h2>DCRM 1.7 Pro Help Manual - Simplified Chinese</h2>
<h3>Welcome</h3>
<div class="lv">
<p>
Welcome to Darwin Cydia Repository Manager Pro ("DCRM" or "WEIPDCRM"), a source manager for CydiaTM clients for Saurik. <br/>
This software was redesigned based on tibounise's "<a href="https://github.com/tibounise/DCRM">DCRM</a>" project. We added more than 95% of new features to make the source of the build more Baton.
</p>
<p>
Using DCRM can build a powerful Cydia personal source, saving you from worrying about background technologies and focusing on content.
</p>
<p>
WEIPDCRM is open source free software that you can redistribute and modify under the terms of the GNU Affero General Public License issued by the Free Software Alliance. <br/>
For details of the agreement, please see: <a href="http://www.gnu.org/licenses/agpl-3.0.html">http://www.gnu.org/licenses/agpl-3.0.html</a>
</p>
<p>
If you need help, you can read this help document in detail, or visit the <b><a href="https://github.com/Lessica/WEIPDCRM">Open Source Home</a></i> on Github at WEIPDCRM > (English) Contact us. I wish you happy!
</p>
</div>
<h3>Environmental deployment</h3>
<div class="lv">
<h4>Environmental Support</h4>
<ol>
<li><strong>Operating system support</strong><br/>class of Unix operating systems (<b>recommendation</b>) or Windows</li>
<li><strong>FastCGI support</strong><br/>PHP >= 5.3<br/><i> Requires pre-compiled GZIP, BZIP2, GD, MYSQL extensions, support for Safe Mode (if not supported) For an extension, simply comment out the relevant line.)</i></li>
<li><strong>Web server support</strong><br/>Apache >= 2.4.7, Nginx >= 1.0.11 (Rewrite: include dcrm.conf;), Lighttpd >= 1.0 (Rewrite: include dcrm_lighttpd .conf;)</li>
<li><strong>Database support</strong><br/>MySQL or MariaDB</li>
</ol>
</div>
<div class="lv">
<h4>Installation Steps</h4>
<ul>
<li>Autoinstall: Configure the server environment above and upload all the files in the main directory to the site directory</li>
<li>Ensure read and write permissions in the root of the program</li>
<li>If you are using a web server other than Apache, you will need some advanced operational knowledge and capabilities. You need to enable the appropriate Rewrite rules as appropriate. </li>
<li>Visit http://{YOUR_REPO_URL} to skip or go directly to http://{YOUR_REPO_URL}/install for database configuration</li>
</ul>
<br/>
If you have special requirements and have some advanced operational knowledge and capabilities, you can manually configure the database by modifying ./system/config/connect.inc.default.php:
<div class="box" style="color:#444;">
1. Set DCRM_CON_SERVER to the full address of the MYSQL database server<br/>
2. Set DCRM_CON_SERVER_PORT to MYSQL database server port<br/>
3. Set DCRM_CON_DATABASE to the established database name.<br/>
4. Set DCRM_CON_USERNAME, DCRM_CON_PASSWORD to a username and password that has access to this database and has sufficient rights.<br/><br/>
5. If you need to keep the database connection, set DCRM_CON_PCONNECT to True<br/>
6. We do not recommend manually initializing the database required by the program. Please visit ./install/setup-install.php to install the database.
</div>
</div>
<div class="lv">
<h4>Upgrade Procedure</h4>
1. Upload or replace all files to the website directory<br/>
2. Visit any page of the source to automatically update
</div>

<h3 class="public_html">Operating Instructions</h3>
<div class="lv">
<h4>First use</h4>
<div class="lv">
Please enter the settings in the upper right corner and the source information settings on the left for initial configuration.
</div>
<h4>Package Features</h4>
<div class="lv">
<ul>
<li>
<strong>Upload packages</strong>
<div> You can upload packages to the upload directory via web pages and FTP for import. </div>
</li>
<li>
<strong>Import packages</strong>
<div> You can import packages from the upload directory into the database. </div>
</li>
<li>
<strong>Upgrade Import</strong>
<div>
If you are performing an upgrade import operation on a software package, an operation prompt appears when you import it.
<div style="margin:0.5em 0em 0.5em 2em;">
· Inherit and replace means that the new package continues to use the original package information (except the version number) and hides the original package;<br/>
· Direct replacement means hiding the original software package;<br/>
· Adding entries means ignoring the existence of the original package;
</div>
</div>
</li>
<li>
<strong>Manage Packages</strong>
<div>
You can:<br/>
· Control software package display, hide;<br/>
· Search, find and select edit or delete packages;<br/>
· View package overview;</div>
</li>
<li>
<strong>Show or hide packages</strong>
<div>
The newly imported package is hidden by default (including upgrade import). The hidden state is represented as <span style="color: green;"> green </span>, and the display state is expressed as <span style="color: blue;" >blue</span>;<br/>
* To change the status, click on the button in front of them and click "Show Package" or "Hide Package" on the left side.
</div>
</li>
<li>
<strong>View Packages</strong>
<div> You can view the control information contained in this package, as well as additional information about the management system. </div>
</li>
<li>
<strong>Edit package</strong>
<div>
· Regular editors provide modification and preservation of common information;<br/>
· Advanced edits provide more field modifications, which require you to have a certain level of advanced operational knowledge and capabilities for Debian packages.
</div>
</li>
<li>
<strong>Find Packages</strong>
<div> You can find packages by more than one field. You cannot use wildcards and regular expressions for the time being. </div>
</li>
<li>
<strong>Bind UDIDs for Packages</strong>
<div>You bind the device UDID for the package, as detailed in the <a href="#UDID">UDID binding</a> section. </div>
</li>
</ul>
</div>
<h4>Classification Management</h4>
<div class="lv">
You can add, delete, view the package classification, and select a configured category for the package when editing it.
</div>
<h4>icon management</h4>
<div class="lv">
You can upload source icons, category icons, and generate icon packages in category management.
</div>
<h4>Run status</h4>
<div class="lv">
You can view information such as database status, system information, total downloads, and software packages.
</div>
<h4>About Program</h4>
<div class="lv">
You can view DCRM's developer list, translation list, thank you list, and more.
</div>
<h4>Refresh list</h4>
<div class="lv">
Before refreshing the list you must put the package to be displayed in the display state;<br/>
Clicking this button will generate Packages, Packages.gz, Packages.bz2 list files and calculate MD5sum and Size.
</div>
</div>
<h3 id="UDID">UDID binding<sup>*</sup></h3>
<div class="lv">
<h4>Introduction</h4>
<div class="lv">
DCRM provides you with the package UDID binding feature that allows you to easily protect your personal software package <sup>+</sup>. <br/>
This function blocks or allows the download of software packages by detecting the UDID of the requesting device. <br/>
<p style="color:#444;">
* The UDID binding is new in 1.6.15.3.26. <br/>
+ This feature is recommended for personal developer's software package testing.
</p>
</div>
</div>
<div class="lv">
<h4>Usage instructions</h4>
<div class="lv">
<ul>
<li>
<strong>Enable this feature for the package</strong>
<div>
You need to enable the <b>Protect</b> option in the regular editing interface in the package you want to enable, and the system will automatically add the <code>cydia::commercial</code> tag to the package. You can also add this tag on your own software package to enable this feature. <br/>
Note: After modifying this option, you need to write the software package to take effect.
</div>
</li>
<li>
<strong>Level Settings</strong>
<div>
In the judgment logic of DCRM, the level has higher priority than UDID binding. <br/>
For example, if you want a device to have special download permissions, you can set the device's level in the UDID management page. At this time, as long as the software package downloaded by the device is lower than the device's level, the device can download the software package without regard to the UDID binding settings.
</div>
</li>
<li>
<strong>Management level</strong>
<div>
The management level in the Manage UDID page is <b>Reserve Interface</b>, and you can currently add comments for the level.
