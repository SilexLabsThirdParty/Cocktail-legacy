/*
	This project is � 2010-2011 Silex Labs and is released under the GPL License:
	This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License (GPL) as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version. 
	This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
	To read the license please visit http://www.gnu.org/copyleft/gpl.html
*/

@author Raphael Harmel
@date 2011-12-06

-----------
DESCRIPTION
-----------

This "simple web app" is aiming to reproduce an iPhone menu screen, with each menu icon pointing to text & pictures lists or to web links.
It is using Cocktail haxe library: http://haxe.org/com/libs/cocktail

It is not intended to be useful, but more to be a proof of concept demonstrating the cross-platform capabilities of Cocktail.


------
STATUS
------

Source code obsolete. Uses cocktail's obsolete DOM abstraction API.


------------------------
PROVIDED BINARY VERSIONS
------------------------

The provided binary versions are as follows:

Online versions:
-JavaScript: http://demos.silexlabs.org/cocktail/simple-webapp/WebApp_js.html
-Flash: http://demos.silexlabs.org/cocktail/simple-webapp/WebApp_As3.html
-HbbTV: http://demos.silexlabs.org/cocktail/simple-webapp/WebApp_js_hbbtv.html

Desktop:
-Win,OSX,Linux (using Adobe Air): http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_air_desktop_and_tv.air

TV versions:
-HbbTV: http://demos.silexlabs.org/cocktail/simple-webapp/WebApp_js_hbbtv.html
-Using Adobe Air: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_air_desktop_and_tv.air

Phones & tablets native applications:
iPhone
To install these versions, you will need a jailbreaked iPhone
-Air version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_iOS_Air_OTA_install.html
-PhoneGap version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_iOS_PhoneGap_OTA_install.html

Android:
-Air version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_android_Air.apk
-PhoneGap version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_android_PhoneGap.apk

BlackBerry
-PhoneGap version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_BlackBerry_PhoneGap.jad

webOS
-PhoneGap version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_webOS_PhoneGap.ipk

Symbian
-PhoneGap version: http://demos.silexlabs.org/cocktail/simple-webapp/native_apps/WebApp_symbian_PhoneGap.wgz

--------------------------
COMPILATION & INSTALLATION
--------------------------

The compilation steps descibed here have been tested on Windows 7.
For other plateforms, some modification might be necessary.


GENERATING ALL VERSIONS IN ONE STEP
-----------------------------------

Most of the steps can be done by one batch file: build/build_all.bat

The requisites are as follows (steps details can be found in "browser versions" and 'native versions" below):
-To be able to compile the cocktail simple-webapp demo, haxe needs to be installed (www.haxe.org)
-To generate iOS applications, you need to be part of the apple developer program (costs 99$), and to generate an apple provisionning file and an apple p12 certificate (details in "REQUISITE iOS" below)
-To use PhoneGap-Build: you need to have a PhoneGap-Build account (free for developers and open-source projects)
-To prepare the PhoneGap-Build archive: you need to have 7zip installed (http://www.7-zip.org/)
-To use Adobe Air engine: you need to have Adobe Air SDK installed



BROWSER VERSIONS
----------------

These are the steps to generate the HTML5 and flash browser versions.

HTML5 + JavaScript version:
haXe needs to be installed first (www.haxe.org).
Then launch build/WebApp_js.hxml


Flash (AS3) version:
haXe needs to be installed first (www.haxe.org).
Then launch build/WebApp_as3.hxml



NATIVE VERSIONS
---------------

To generate the native versions, there are several possible "engines" available.
We will focus on these:
-PhoneGap-Build, which targets Android, iOS, BlackBerry OS, webOS and symbian (Widows Phone is to come)
-Adobe Air, which targets desktop (Windows & OSX, -Linux beeing not supported anymore-), Android, iOS and BlackBerry Tablet OS
-NME, which targets desktop (Windows, OSX & Linux), Android, iOS and webOS

Depending on the used engine and on the targeted platform, there might be some requisites listed below.


- REQUISITES -

iOS
You need to have a valid Apple developer account which which you will generate an apple provisionning file and an apple p12 certificate:
* First, subscribe to [[http://developer.apple.com/programs/ios/|Apple iOS developer program]] for 99$.
* Once you account is created, generate an apple provisionning file (which links your app to your devices) and an apple p12 certificate (details available here [[http://developer.apple.com/ios/manage/overview/index.action]] - link only accessible with a valid account).



- USING PHONEGAP-BUILD -

This is the simplest way to generate native versions.

Here are the needed steps to generate native applications using PhoneGap-Build engine:
-compile the HTML5 + js browser version (cf. above)
-generate an apple provisionning file and an apple p12 certificate (cf. "REQUISITE iOS" part above)
-PhoneGap build setting:
 * First, create a PhoneGap build account on: http://build.phonegap.com/
 * Then create a new application called "CocktailDemo".
 * In the admin interface of your application => signing menu, load the apple provisionning and apple p12 certificate files generated in first step.
-generate the PhoneGap-Build archive:
 * launch build/native_apps/WebApp_PhoneGapBuild.bat
 * the archive will be generated here: build/native_apps/WebApp_PhoneGapBuild.zip
-upload the archive into PhoneGap-Build by clicking on update-code menu
-wait a few minutes for PhoneGap-build to generate all the native applications
-you can now install these applications to your devices.


- USING ADOBE AIR -

Here are the needed steps to generate native applications using Adobe Air engine:
-compile the flash browser version (cf. above)
-install Air SDK
 * Download the Adobe Air Sdk from: http://www.adobe.com/special/products/air/sdk/
 * Then add its path to your "PATH" environment variables. (It should look like: "C:\AdobeAIRSDK\bin\")
 * Install Java JRE: http://www.oracle.com/technetwork/java/javase/downloads/index.html
-generate a Air certificate by launching WebApp_air_generate_certificate.bat
-compile for the needed target (cf. below)



WINDOWS & OSX DESKTOP VERSION (AIR)

If not already done, follow the steps described in "Air SDK installation".
Then launch build/WebApp_air_desktop.bat (default password is "password" if you use the provided certificate).
The binary file will be generated in bin/native_apps/WebApp_desktop.air
To install it on your desktop, double-click on it.


ANDROID VERSION (AIR)

Air Mobile compilation
* Launch /build/WebApp_air_android.bat (default password is "password" if you use the provided certificate).
* The binary file will be generated in /bin/native_apps/WebApp_android.apk.

App installation
* To install it on your android device, copy this file on your SD card and then launch it via your Android device.
* The app will appear on the home screen of your device.


IOS VERSION (AIR)

iOS Ad-Hoc compilation:
* Follow the steps descibed in REQUISITE-iOS part above.
* Copy apple provisionning and apple p12 certificate files to /build directory and rename them to "Cocktail_Web_App.mobileprovision" and "iphone_dev.p12"
* Then launch build/WebApp_air_iOS.bat and use as password the .p12 certicate password
* The binary file will be generated in /bin/native_apps/WebApp_iOS_Air.ipa


iOS application installation
There are two ways to install an Ad-Hoc ipa file: via iTunes or over the air (OTA)
In each case, you need to have a provisionning file which links your app to your devices.
This means you cannot install the ipa on devices for which you do not have the UDID (User Device ID), unless you have a jailbroken iDevice.
We recommend using TestFlight (http://testflightapp.com) for beta tests.

iTunes installation
* To install the application on an iOS device, drag and drop the ipa and provisionning files on iTunes, and then sync the "Cocktail Demo" app on your device.
* The app will appear on the home screen of your iDevice.

Over the Air installation (OTA)
This kind of installation allows you to install the application directly from your device via a specific web page.
* The web page (available here: bin/native_apps/WebApp_iOS_Air_install.html) points to a manifest file.
* The manifest file (available here: bin/native_apps/WebApp_iOS_Air_install_manifest.plist) points to the ipa file


----------------------------------------------------------------------------------------------------------------------

Following information is intended for Silex Labs team and might be of no interest for other people.

----------------------------------------------------------------------------------------------------------------------


HILIGHTED BUGS
--------------

COCKTAIL ?

=> Android Air version shows 2 times smaller than on other devices
   => there was the same issue on iOS which was resoluved by not using HD quality
   => tried using following parameter in the air manifest file, but did not solve the issue:
		<supports-screens android:smallScreens="true"/>
		<supports-screens android:normalScreens="true"/>
		<supports-screens android:largeScreens="false"/>
		<supports-screens android:xlargeScreens="false"/>
 
=> In the native iOS apps, some of the links and download links do not work
   => full http adresses have to be used, and not relative links
   => solved

PHONEGAP:

Splash Screen iPad issue: white lines displayed 
 => issue posted here: http://community.phonegap.com/nitobi/topics/splash_screen_ipad_issue_white_lines_displayed


COCKTAIL

New bugs:

Logged in github:

 => tile not working in flash 
	=> app black background
	=> header tile
	=> solved
 
 => relative + inline style does not seem to work correctly in flash
	=> header back button
	=> solved

 => no scrollbar in flash
	=> notes page
	
 => links page display issue
 
 => DOMElement text value height = 0
    If there is only one line in a textDOMElement, its height is set to 0.
	Works fine for multiple lines.
	=> solved by Yannick on 30/11/11
	
 => domElement.style.verticalAlign does not seem to work correctly
    => � v�rifier avec Yannick dans Iphone Style.hx, ligne 196
	=> il doit finaliser cette fonctionnalit�, pas besoin de poster de bug

Non-bugs:

 => using flash target, space characters are considered as CR
    => not a bug, in flash width has to be set in general to width = 100%
	=> solved

	
TO DO
-----
-Solve the issue were Android Air version shows 2 times smaller than on other devices
-pages should be loaded when accessing them, and not before
-for the sound, embed a player, like => not possible for now, bug assigned to Yannick
 alex:
 => html5 = http://w.soundcloud.com/player/?url=http%3A%2F%2Fapi.soundcloud.com%2Fplaylists%2F1187266&auto_play=false&show_artwork=true&color=2b877f
 => flash = https://player.soundcloud.com/player.swf?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F805447&color=0066cc&show_comments=true
 raph:
 => html5 = http://w.soundcloud.com/player/?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F16530992&auto_play=false&show_artwork=true&color=2b877f
 => flash = https://player.soundcloud.com/player.swf?url=http%3A%2F%2Fapi.soundcloud.com%2Ftracks%2F16530992&color=0066cc&show_comments=true

 
DONE
----

-load a dynamic content (rss)
 => zabojad's gallery => OK
	=> using flickr's superwup images: http://api.flickr.com/services/feeds/photos_public.gne?id=32780881@N06&lang=fr-fr&format=rss_200
-added index.html to detect flash and load the corresponding version (JS or Flash)
-have the flash version work correctly
 => bugs assigned to Yannick
-back button should only go one step back
-home page: silex labs community platform, cocktail site (in SL Labs), links (a list with haxe, website of raph)
-load the gallery demo inside the body (as a skin, keep the web app header) - there has to be a conditional compilation switch (the flash version of the gallery in the flash version of the web app)
-have the flash version work correctly
 => for generic problems, set following styles to all style element: display=static, position=block, width=auto => Done
 => for links, do it with a conditional compilation switch (using windows.location for JS, and getURL for flash) => Done
-use "ul" and "li" tags for all the lists => OK
 => home page icons
 => image gallery
-links => use native functions
-the credit page: silex labs community platform, cocktail site (in SL Labs), links (a list with haxe, website of raph)


TASKS
-----

 => pages => 2 jours => OK
	R�alisation:
		=> construire un dom contenant tout le site
		=> pour la navigation et le passage d'une page � une autre, masquer/afficher les �l�ments correspondants
	Elements:
		=> Home: 4 boutons d'applications (Calendar, Music, Notes, Credits) + SilexLabs
		=> Calendar: Liste clickable de jours
		=> Music: Liste clickable imbriqu�es: Artist => Album => Song
		=> Notes: Liste clickable simple: Libell� => Contenu
		=> Credits: page contenant des listes clickables pour acc�der:
			=> au site de cocktail avec le logo
			=> au site de silexlabs
			=> site haXe
			=> aux fichiers sources

 => Composants n�cessaires => 1 jour => OK
	R�alisation:
		=> cr�ation de "composants" Cocktail simples
	Elements:
		=> icones applications: image + texte
		=> listes clickable
			=> mode simple
			=> mode imbriqu�es
			=> les liens clickables peuvent etre externes ou internes
		
 => css n�cessaire => 0.5 jours
	R�alisation:
		=> les fichiers originaux sont pr�sents dans la demo jPint
		=> les traduire directement en code dans Cocktail
	Elements => OK
		=> Home: fond noir sans barre de navigateur
			=> voir file:iphone-interface/jquery/index.html
		=> Calendar & Music => OK
			=> barre de menu bleue
			=> fond blanc
		=> Notes:
			=> barre de menu marron
			=> fond jaune
		=> Credits:
			=> barre de menu bleue
			=> fond gris ray�
			=> fond liste blanc

 => assets graphiques => OK
	R�alisation:
		=> r�cup�rer les assets dans la demo jPint
	Elements:
		=> Home:
			=> boutons applications => OK
		=> Calendar & Music:
			=> bouton "Back" noir en forme de fl�che => OK
		=> Notes:
			=> scrollbar native

 => navigation => 1+ jours
	R�alisation:
	Elements:
		=> transition slide => 0.5 jours
			=> a faire avec la classe d'interpolation de haxe
			=> faire la transition entre les deux containers
		=> lire des donn�es dynamiques
		=> galerie photo bas�e sur celle de zabojad => a voir � la fin
		=> deeplink => a voir � la fin
		=> calendrier comme dans la demo => non
		=> adaptation automatique mode landscape/portrait => normalement devrait etre automatique

 => recette => 1 jour
 
 Total: 5.5 jours

