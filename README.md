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
