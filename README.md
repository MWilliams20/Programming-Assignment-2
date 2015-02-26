Titanium.UI.setBackgroundColor('#000');
 
var tabGroup = Titanium.UI.createTabGroup();
var win1 = Titanium.UI.createWindow({
	title:'Basketball',
	backgroundColor:'#FF6600'
});
var tab1 = Titanium.UI.createTab({
	icon:'KS_nav_views.png',
	title:'Basketball',
	window:win1
});
 
var label1 = Titanium.UI.createLabel({
	color:'#CCCCCC',
	text:'This is a game of movement and patience',
	font:{fontSize:30,fontFamily:'Krungthep'},
	textAlign:'center',
	width:'auto'
});
 
win1.add(label1);
 
var win2 = Titanium.UI.createWindow({
	title:'Football',
	backgroundColor:'#996633'
});
var tab2 = Titanium.UI.createTab({
	icon:'KS_nav_ui.png',
	title:'Football',
	window:win2
});
 
var label2 = Titanium.UI.createLabel({
	color:'#000000',
	text:'This is a game of controlled aggression',
	font:{fontSize:30,fontFamily:'Krungthep'},
	textAlign:'center',
	width:'auto'
});
win2.add(label2);
 
tabGroup.addTab(tab1);
tabGroup.addTab(tab2);

tabGroup.open();

if (Ti.version < 1.8) {
  alert('Sorry - this application template requires Titanium Mobile SDK 1.8 or later');
}

(function() {
	
  var osname = Ti.Platform.osname,
    version = Ti.Platform.version,
    height = Ti.Platform.displayCaps.platformHeight,
    width = Ti.Platform.displayCaps.platformWidth;

  function checkTablet() {
    var platform = Ti.Platform.osname;

    switch (platform) {
      case 'ipad':
        return true;
      case 'android':
        var psc = Ti.Platform.Android.physicalSizeCategory;
        var tiAndroid = Ti.Platform.Android;
        return psc === tiAndroid.PHYSICAL_SIZE_CATEGORY_LARGE || psc === tiAndroid.PHYSICAL_SIZE_CATEGORY_XLARGE;
      default:
        return Math.min(
          Ti.Platform.displayCaps.platformHeight,
          Ti.Platform.displayCaps.platformWidth
        ) >= 400;
    }
  }

  var isTablet = checkTablet();

  var Window;
  if (isTablet) {
    Window = require('ui/tablet/ApplicationWindow');
  } else {
    Window = require('ui/handheld/ApplicationWindow');
  }

  var ApplicationTabGroup = require('ui/common/ApplicationTabGroup');
  new ApplicationTabGroup(Window).open();
})();

<?xml version="1.0" encoding="UTF-8"?>
<ti:app xmlns:ti="http://ti.appcelerator.org">
    <id>com.packtpub.colortheme</id>
    <name>Programming Assignment 2</name>
    <version>1.0</version>
    <publisher>Williams</publisher>
    <url>http://</url>
    <description/>
    <copyright>2015 by Williams</copyright>
    <icon>appicon.png</icon>
    <fullscreen>false</fullscreen>
    <navbar-hidden>false</navbar-hidden>
    <analytics>true</analytics>
    <guid>472271e4-e563-4bdd-a911-80b45ca29677</guid>
    <property name="ti.ui.defaultunit" type="string">dp</property>
    <ios>
        <plist>
            <dict>
                <key>UISupportedInterfaceOrientations~iphone</key>
                <array>
                    <string>UIInterfaceOrientationPortrait</string>
                </array>
                <key>UISupportedInterfaceOrientations~ipad</key>
                <array>
                    <string>UIInterfaceOrientationPortrait</string>
                    <string>UIInterfaceOrientationPortraitUpsideDown</string>
                    <string>UIInterfaceOrientationLandscapeLeft</string>
                    <string>UIInterfaceOrientationLandscapeRight</string>
                </array>
                <key>UIRequiresPersistentWiFi</key>
                <false/>
                <key>UIPrerenderedIcon</key>
                <false/>
                <key>UIStatusBarHidden</key>
                <false/>
                <key>UIStatusBarStyle</key>
                <string>UIStatusBarStyleDefault</string>
            </dict>
        </plist>
    </ios>
    <android xmlns:android="http://schemas.android.com/apk/res/android">
    	<manifest>
    		<activity
    			android:name='org.appcelerator.titanium.TiActivity'
    			android:configChanges='keyboardHidden'
    			android:screenOrientation='portrait'/>
    		</manifest>
    		</android>
    <mobileweb>
        <precache/>
        <splash>
            <enabled>true</enabled>
            <inline-css-images>true</inline-css-images>
        </splash>
        <theme>default</theme>
    </mobileweb>
    <modules/>
    <deployment-targets>
        <target device="android">true</target>
        <target device="blackberry">false</target>
        <target device="ipad">true</target>
        <target device="iphone">true</target>
        <target device="mobileweb">true</target>
    </deployment-targets>
    <sdk-version>3.5.0.GA</sdk-version>
</ti:app>
