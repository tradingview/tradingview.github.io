mps = mps || {};
mps._ext = {};
mps._overlayenabled = false;
mps._backendhost = 'mps.cnbc.com'

//-> DEFINE VARIABLE nowrite -> mps._ext.nowrite
mps._ext.nowrite = 2;
//-> DEFINE VARIABLE tm_redirect -> mps._ext.tm_redirect
mps._ext.tm_redirect = 1;
//-> DEFINE VARIABLE dart_mode -> mps._ext.dart_mode
mps._ext.dart_mode = 'gpt-asynchronous';
//-> DEFINE VARIABLE IRSOURCE -> mps._ext.IRSOURCE
mps._ext.IRSOURCE = false;
//-> DEFINE VARIABLE reporting_base_url -> mps._reportingbaseurl
mps._reportingbaseurl = 'pix.nbcuni.com/x.gif';


/* js/internal/mpstools.js */

var mps=mps||{};
var mpsopts=mpsopts||{};
var debugmode=debugmode||{};
var googletag = googletag || {};
googletag.cmd = googletag.cmd || [];
debugmode.log&&window.console||(debugmode.log=0);
mps.debugMsg = [];
mps._gptcmd = mps._gptcmd || [];
mps._queue = mps._queue || {};
mps._queue.gptloadset=mps._queue.gptloadset||{};
mps._queue.mpsloaded = mps._queue.mpsloaded || [];
mps._queue.gptloaded = mps._queue.gptloaded || [];
mps._queue.mpsinit = mps._queue.mpsinit || [];
mps._queue.adload = mps._queue.adload || [];
mps._queue.adexecute=mps._queue.adexecute||[];
mps._queue.adview = mps._queue.adview || [];
mps._queue.adrender = mps._queue.adrender || [];
mps._queue.adviewchange = mps._queue.adviewchange || [];
mps._queue.adclone = mps._queue.adclone || [];
mps._queue.destroyads = mps._queue.destroyads || [];
mps._queue.refreshads = mps._queue.refreshads || [];
mps._queue.activerefresh = mps._queue.activerefresh || [];
mps._queue.lazyload = mps._queue.lazyload || [];
mps._queue.setrails = mps._queue.setrails || [];
mps._queue.adshow = mps._queue.adshow || [];
mps._queue.adhide = mps._queue.adhide || [];
mps._queue.abdetect = mps._queue.abdetect || [];
mps._queue.getad = mps._queue.getad || [];
mps._queue.clonead = [];
mps._queue.errorpixels = mps._queue.errorpixels || [];
mps._queue.error = mps._queue.error || [];
mps._queue.mpsready = mps._queue.mpsready || [];
mps._ext = mps._ext || {};
mps._ext.mpsready = mps._ext.mpsready || false;
mps._ext._jq = typeof(jQuery) === 'function' ? 1 : 0;
mps._clonerunning = false;
mps._gptrefresh = mps._gptrefresh || true;
mps._adviews = mps._adviews || {};
mps._targeting = mps._targeting || {};
mps._delays = mps._delays || {};
mps._delays.reportingdelay = mps._delays.reportingdelay || 2000;
mps._delays.bodyheader = mps._delays.bodyheader || 20000;
mps._delays.bodyheaderint = mps._delays.bodyheaderint || 100;
mps._delays._adview = mps._delays._adview || {};
mps._delays._adview[mps._loadset||0] = mps._delays._adview[mps._loadset||0] || {};
mps._delays._reportingdelay = null;
mps._ext = mps._ext || {};
mps._ext.mpsready = false;

// mpsopts
mpsopts.legacyqueues=mpsopts.legacyqueues||1;

//--(IE<9: indexOf)
if(!Array.prototype.indexOf)Array.prototype.indexOf=function(searchElement,fromIndex){var k;if(this==null)throw new TypeError('"this" is null or not defined');var o=Object(this);var len=o.length>>>0;if(len===0)return-1;var n=fromIndex|0;if(n>=len)return-1;k=Math.max(n>=0?n:len-Math.abs(n),0);while(k<len){if(k in o&&o[k]===searchElement)return k;k++}return-1};
mps._os = mps._os || navigator.platform.indexOf('Win') > -1 ? 'windows' : 'macintosh';

// If KILLCOMPONENTS exists in the query params set in mpscall
if(location.search.indexOf('KILLCOMPONENTS') > -1){
  mpscall.KILLCOMPONENTS = 1;
  mpscall.CACHESKIP = 1;
}

mps._bool = function(val,intval) {
  if(typeof(val)=='boolean') val = val ? 1 : 0;
  if(typeof(val)=='string') {
    if(val=='true') {
      val = 1;
    }
    if(val=='false') {
      val = 0;
    }
  }
  val = parseInt(val,10);
  if(!intval) {
    return val === 1;
  } else {
    return typeof(val) === 'number' ? val : parseInt(val, 10);
  }
};

//: Debug Mode Detection
debugmode.log=navigator.userAgent.toLowerCase().indexOf("android")>-1?null:function(a){
  var b=navigator.cookieEnabled?!0:!1;
  "undefined"!=typeof navigator.cookieEnabled||b||(document.cookie="_ckT",b=-1!=document.cookie.indexOf("_ckT")?!0:!1);
  var c=window.location.search&&window.location.search.indexOf("DEBUGMODE")>-1;
  if(c){
    return 2;
  }
  if(!b){
    return!1;
  }
  a+="=";
  for(var b=document.cookie.split(";"),d=0;d<b.length;d++){
    for(var e=b[d];" "==e.charAt(0);) {
      e=e.substring(1,e.length);
    }
    if(0==e.indexOf(a)){
      return e.substring(a.length,e.length);
    }
  }
  return null;
}
(String.fromCharCode(95,95)+"de"+String.fromCharCode(98,117,103,109,111)+"de"+Array(3).join("_"))||debugmode.log;
//--[MPS Doc Ready] mps._ready(function(){ ... });
mps._ready=function(func){
  if(typeof jQuery=="function"){
    jQuery().ready(func);
  }
  else {
    mps._onload(func,window);
  }
};
//--[Native JS Doc Ready] not invoked directly
mps._onload=function(a,b){
  var c=!1,d=!0,e="object"!=typeof b?window.document:b.document,f=e.documentElement,g=e.addEventListener?"addEventListener":"attachEvent",h=e.addEventListener?"removeEventListener":"detachEvent",i=e.addEventListener?"":"on",j=function(d){
    try{
      ("readystatechange"!=d.type||"complete"==e.readyState)&&(("load"==d.type?b:e)[h](i+d.type,j,!1),!c&&(c=!0)&&a.call(b,d.type||d));
    }catch(f){
      return mps._errorCallback(f, 'mps._onload'),!1;
    }
  },k=function(){
    try{
      f.doScroll("left");
    }catch(a){
      return void setTimeout(k,50);
    }
    j("poll");
  };
  if("complete"==e.readyState) {
    try{
      a.call(b,"lazy");
    }catch(l){
      mps._errorCallback(l, 'mps._onload');
    }
  }else{
    if(e.createEventObject&&f.doScroll){
      try{
        d=!b.frameElement;
      }catch(m){}
      d&&k();
    }
    e[g](i+"DOMContentLoaded",j,!1),e[g](i+"readystatechange",j,!1),b[g](i+"load",j,!1);
  }
};

//--[Get Elapsed Time]
mps._elapsed = function(label,asval) {
  Date.now = Date.now || function() {
    return +new Date;
  };
  var displaylabel = typeof(label)!='undefined' ? ' ('+label+')' : '';
  if(typeof(mps._timer)!='number'||!(mps._timer>1)) {
    mps._timer=Date.now();
    retval = 0;
    ret = '#mpsTimer\u2022 /started/ '+mps._timer+displaylabel;
  } else {
    retval = Date.now()-mps._timer;
    ret = '#mpsTimer\u2022'+retval+'ms'+displaylabel;
  }
  if(typeof(asval)!='undefined'){
    return retval;
  }
  return ret;
};

/**
 * mps.debounce: as long as it continues to be invoked, will not be triggered.
 * The function will be called after it stops being called for {wait} milliseconds.
 * If `immediate` is passed, trigger the function at the beginning.
 * @param {func} function
 * @param {wait} number
 * @param {immediate} boolean
 * @return {executedFunction} function
 */
mps.debounce = function(func, wait, immediate) {
  var timeout;
  return function() {
    var context = this, args = arguments;
    var later = function() {
      timeout = null;
      if (!immediate){
        func.apply(context, args);
      }
    };
    var callNow = immediate && !timeout;
    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
    if (callNow){
      func.apply(context, args);
    }
  };
};

//--[Ad DOM Object] Return DOM selector using slot name
mps.selectAd = function(adunit) {
  if(typeof(adunit)!='undefined' && adunit!='' && typeof(mps)=='object' && typeof(mps.advars)!='undefined' && typeof(mps.adslots[adunit])!='undefined' && typeof(mps._select) == 'function' && (adselect=mps._select('#'+mps.adslots[adunit]))) {
    return adselect;
  } else {
    return false;
  }
};

//--[GPT Ad Object] Return Google ad object reference using the slot name
mps.getSlot = function(slotstr,loadset) {
  var _advars = mps.advars;
  loadset = (loadset !== null && typeof loadset != 'undefined') ? parseInt(loadset,10) : mps._loadset;
  if(parseInt(loadset)>-1) {
    if(!mps._advars[loadset]) {
      return false;
    }
    _advars = mps._advars[loadset];
  }
  if(typeof(slotstr) != 'string') {
    mps._debug('mps.getSlot: param is not a string');
    return false;
  }
  if(typeof(_advars) != 'object' || typeof(_advars[slotstr]) != 'string') {
    mps._debug('mps.getSlot: invalid slot name');
    return false;
  }
  if(typeof(mps._advarprefix) != 'string' || typeof(window[mps._advarprefix]) != 'object') {
    mps._debug('mps.getSlot: invalid page gpt object');
    return false;
  }
  if(typeof(window[mps._advarprefix][_advars[slotstr]]) != 'object') {
    mps._debug('mps.getSlot: failed to load slot object');
    return false;
  }
  return window[mps._advarprefix][_advars[slotstr]];
};

//--[Single DOM Object via Selector String] example strings: #id .class body
mps._select = function(selector) {
  // jQuery available
  if(typeof(jQuery) === 'function') {
    return (jQuery(selector)[0]||false);
  }
  if(typeof(selector) != 'string' || selector.length < 2) {
    return false;
  }
  // Modern Browser
  if(typeof(document.querySelectorAll)=='function' || typeof(document.querySelectorAll)=='object') {
    return (document.querySelectorAll(selector)[0]||false);
  }
  // Old Browser (func by first char)
  if(selector.charAt(0)=='#') {
    return (top.document.getElementById(selector.substr(1))||false);
  } else if(selector.charAt(0)=='.') {
    return (top.document.getElementsByClassName(selector.substr(1))[0]||false);
  } else {
    return (top.document.getElementsByTagName(selector)[0]||false);
  }
};


//--[Insert HTML into Selector] mps._append (obj)domelement,(str)html
mps._append = function(selector, d, name) {
  if(typeof(selector)=='string') {
    selector = mps._select(selector);
  }
  if(typeof(selector)!='object'||typeof(d)!='string') {
    mps._debug('mps._append() invalid parameters');
    return false;
  }
  // jQuery available
  if(typeof(jQuery) === 'function') {
    return (jQuery(selector).append(d)||false);
  }
  var content = d;
  content = Array.prototype.concat( [], content );

  if(content.length) {

    var frag = document.createDocumentFragment();
    var tmp = frag.appendChild( document.createElement('div'));
    tmp.innerHTML = 'X' + content;

    var scripts = tmp.getElementsByTagName('script');
    // Append html.
    if(selector) {
      try {
        selector.insertAdjacentHTML('beforeend', content);
      } catch(err) {
        mps._errorCallback(err, (name || 'mps._append'));
      }
    } else {
      mps._log('Invalid selector provided.');
    }
    for(var i=0; i<scripts.length; i++) {
      var newScript = document.createElement('script');
      if(scripts[i].id) {
        newScript.id = scripts[i].id;
      }
      if(scripts[i].src) {
        newScript.type = 'text/javascript';
        newScript.src = scripts[i].src;
        newScript.onerror = function(){
          mps._loadError(newScript.src);
        };
        document.getElementsByTagName('head')[0].appendChild(newScript);
      } else {
        var nscript = document.createElement('script');
        nscript.type = 'text/javascript';
        nscript.text = 'try{ '+scripts[i].innerHTML+' } catch(err){ mps._errorCallback(err, "mps._append inline"); }';
        document.getElementsByTagName('head')[0].appendChild(nscript).parentNode.removeChild(nscript);
      }
    }
  }
};

mps._arrayToPipeSeparated = function(data) {
  var current_value;
  for (var k in data) {
    current_value = data[k];
    if(current_value instanceof Array) {
      current_value = current_value.join("|");
    }
    data[k] = current_value;
  }
  return data;
};


/**
 * Returns if element is in viewport.
 * Used in lazyload.js and lav.js
 * @param {!(object)} s - A document object
 * @param {boolean} map - returns map for distance (optional)
 * @returns {(boolean|object)} Returns boolean if in viewport, or XY object
 * @alias mps._detect.viewport
 */
mps.inViewport = function(s, map) {
  s = (typeof s === 'string') ? mps._select(s) : s;
  if(typeof s !== 'object' || s === null){
    return false;
  }
  var map=map||false;
  var vpMinX, vpMaxX, vpMinY, vpMaxY;

  if(!mps._bool(mpsopts.activeload) || (mps._bool(mpsopts.activeload) === true && mps._activerefresh._focus === true)) {
    var win = window, winDocElem = win.document.documentElement, docHeight = mps._getDocHeight(), vp = mps._vp(),
        vpW = vp[0], vpH = vp[1], elO = mps._getBoundingRect(s), elY = elO.top, elX = elO.left,
        scY = win.pageYOffset ? win.pageYOffset : winDocElem.scrollTop,
        scX = win.pageXOffset ? win.pageXOffset : winDocElem.scrollLeft,
        slotname = typeof mps._determineSlot === 'function' && mps._determineSlot(s.id).cleanslot,
        defaultPad = mps._detect && Math.abs(mps._detect.padding) >0 ? parseInt(mps._detect.padding) : 0,
        atfPad = mps._detect && mps._bool(mpsopts.detection_above_the_fold) && typeof mps._detect.getATFPadding(slotname) == 'number' ? mps._detect.getATFPadding(slotname) + defaultPad : 0,
        atfEnabled = mps._bool(mpsopts.detection_above_the_fold) && mps._detect,
        vpPad = atfEnabled ? atfPad : defaultPad;
        vpMinX = elX >= ((scX - vpPad) < 0 ? -20 : (scX - vpPad)); //top
        vpMaxX = elX <= (scX + vpW  + vpPad); //left
        vpMinY = elY >= ((scY - vpPad) < 0 ? -20 : (scY - vpPad));  //bottom
        vpMaxY = elY <= (scY + vpH + vpPad);  // right
    if(map) {
      // returns map for distance tracking
      if (mps._detect && mps._detect.tracking && mps._keys(mps._detect.tracking).length === 0 && typeof mps._detect.distanceToViewport === 'function') {
        mps._detect.distanceToViewport(s);
      }
      return {
        elementX: elX,
        elementY: elY,
        screenX: Math.abs(scX),
        screenY: Math.abs(scY),
        inviewX: vpMinX && vpMaxX,
        inviewY: vpMinY && vpMaxY
      };
    }
      // Negative padding, ads at absolute top/bottom, or less than padding.
      //var AtPageBottom = renders ads at page bottom (250 height) or smaller, vpMaxY=true
      var AtPageBottom = scY + vpH > (docHeight-125);
      if(vpPad < 0) {
        if(elY <= 0 || elY < (vpPad * -1)) {
          // Y coords at absolute top, or less than padding.
          vpMinY = true;
        } else if(elY >= docHeight || AtPageBottom) {
          // Y coords at absolute bottom, or greater than (viewport height - padding).
          vpMaxY = true;
        }
        if(elX <= 0 || elX < (vpPad * -1)) {
          // X coords at absolute left or less than padding.
          vpMinX = true;
        } else if(elX <= winDocElem.offsetWidth && elX >= winDocElem.offsetWidth - (vpPad * -1)) {
          // X coords at absolute right, or greater than (viewport width - padding);
          vpMaxX = true;
        }
      }
      return vpMinX && vpMinY && vpMaxX && vpMaxY;
  } else {
    // Activeload - window not focused. (mpsopts.activeload=1) OR Invalid DOM object
    return false;
  }
};

//-- mps.attachData(instance[string, 'test-web'], mpsid[string, 123456789], data[object { "fruits":["kiwi",'dragonfruit"]}])
mps.attachData = function(mpsid, data){
  var mpsid = mpsid || mps.pagevars.mpsid;
  var instance = mps.pagevars.instance;
  var mpsdomain = mps.pagevars.mpsurl ? mps.pagevars.mpsurl : 'mps.nbcuni.com';
  var legacy = !(mps._checkua().oldie === false || mps._checkua().oldie && mps._checkua().oldie > 10);
  var passed_in_data = mps._arrayToPipeSeparated(data);

  // Sort and Serialize object, if omitted, pass empty string
  var attachData = typeof passed_in_data !== 'undefined' && mps._keys(passed_in_data).length ? mps._sortObject(passed_in_data) : '';


  var serializedData = (attachData !== '') ?  mps._serialize(attachData, "cag") : attachData;

  // Compare sorted JSON string with existing
  if(typeof mps.pagevars.cagsattached === 'object' && (JSON.stringify(serializedData) !== JSON.stringify(mps._serialize(mps.pagevars.cagsattached, "cag")))) {
    var xhr;
    var proto = mpsdomain.indexOf('local') > -1 ? mps._protocol() : "https:";
    var url = proto + '//' + mpsdomain + '/request/attachdata/' + instance + '/' + mpsid + '?' + serializedData;
    if(!legacy){

      xhr = new XMLHttpRequest();
      xhr.open('GET', url, true);
      xhr.onreadystatechange = function () {
        if (xhr.readyState == 4) {
          if (xhr.status == 200 && xhr.responseText.length > 0) {
            mps._d('[mps:attachData] SUCCESS 200' + xhr.responseText);
          } else if (xhr.status == 0) {
            mps._d("[mps:attachData] FAILED 410 - Page doesn't exist");
            return false;
          }
        }
      };
      xhr.send(null);
      return true;

    } else {
      xhr = new XDomainRequest();
      xhr.onload=function() {
        return xhr.responseText;
      };
      xhr.onerror=function() {
        return xhr.responseText;
      };
      xhr.open('get', url, true);
      setTimeout(function () {
        xhr.send();
      }, 0);
      return xhr;
    }

  } else {
    mps._d('[mps:attachData] SKIPPED attaching cags - Already Set');
    return false;

  }
};

mps._loadError = function(source){
  mps._errorCallback({name: 'Script', message: source}, 'Load Error');
};

//--[Remove Selector(s) from DOM] mps._remove (obj)
mps._remove = function(elem) {
  if(!elem) { mps._log('Invalid selector provided.'); return false; }
  // jQuery available
  if(typeof(jQuery) === 'function') {
    if((jQuery(elem).length > 0)) {
      jQuery(elem).remove(); return false;
    } else {
      mps._log('Invalid selector provided.'); return false;
    }
  }
  // querySelectorAll, getElementsByClassName, getElementsByTagName
  if(typeof elem.length === 'number' && elem.length > 0) {
    for (var j = elem.length-1; j >= 0; j--) {
      if (elem[j].parentNode) {
        elem[j].parentNode.removeChild(elem[j]);
      }
    }
    // mps._select or getElementById
  } else if(elem.nodeType) {
    if(elem.parentNode) {
      elem.parentNode.removeChild(elem);
    }
  } else {
    mps._log('Invalid selector provided.');
  }
};

//--[Cookies] mps._ck.r(name) | mps._ck.w(name,value,days) | mps._ck.d(name)
mps._ck = {
  params: function() {
    var query = location.search.substr(1);
    var result = {};
    var queryArray = query.split("&");
    for(i = 0; i < queryArray.length; i++) {
      var item = queryArray[i].split("=");
      result[item[0]] = decodeURIComponent(item[1]);
    }
    return result;
  },
  c: function() {
    document.cookie = "cookietest=1";
    var ret = document.cookie.indexOf("cookietest=") != -1;
    // Delete cookie
    document.cookie = "cookietest=1; expires=Thu, 01-Jan-1970 00:00:01 GMT";
    return ret;
  },
  w: function(name, val, days) {
    var p = this.params();
    var dateObj = new Date;
    dateObj.setTime(dateObj.getTime() + 864E5 * days);

    if(mps._ck.c() === true &&
      (typeof p.nocookies === "undefined" || p.nocookies !== "1")) {
      var entireCookie = name + "=" + val + "; expires=" + dateObj.toGMTString() + "; path=/;";
      document.cookie = entireCookie;
    } else {
      if (typeof(localStorage) !== "undefined") {
        localStorage.setItem(name, val);
      }
    }
  },
  r: function(name) {
    var p = this.params();
    if(mps._ck.c() === true &&
      (typeof p.nocookies === "undefined" || p.nocookies !== "1")) {
      var entireCookie  = name + "=";
      for (var pairs = document.cookie.split(";"), x = 0; x < pairs.length; x++) {
        for (var pair = pairs[x];
             " " == pair.charAt(0);) pair = pair.substring(1, pair.length);
        if (0 == pair.indexOf(entireCookie)) {
          return pair.substring(entireCookie.length, pair.length);
        }
      }
    } else {
      if (typeof(localStorage) !== "undefined") {
        return localStorage.getItem(name);
      }
    }
    return null
  },
  d: function(name) {
    mps._ck.w(name, "", -1)
  }
};

//--[_checkQS] used in header-bidding.js et all.
mps._checkQS = function(a) {
  return "string" == typeof a && a ? !1 !== mps._get(a) || !1 !== mps._get(a.toLowerCase()) || !1 !== mps._get(a.toUpperCase()) ? !0 : !1 : !1;
};

//--[MPS Execution Helpers] mps._protocol() mps._checkua()
mps._protocol = function(){
  var c=null,a=window,b=null;try{for(;null!=a&&a!==c;){b=a.location.protocol;if("https:"===b)break;else if("http:"===b||"file:"===b)return"http:";c=a;a=a.parent}}catch(d){}return"https:"
};

mps._checkua = function() {
  if (mps.__ua) return mps.__ua;
  var iecheck = navigator.appVersion.match(/MSIE ([\d]+)/);
  var ret = {};
  ret.os = mps._os;
  ret.mobile = !!(Math.max(document.documentElement.clientWidth, window.innerWidth || 0) < 1025 || window.navigator.userAgent.match('Mobile'));
  if (!!navigator.userAgent.match(/Trident\/7\./)){
    ret.oldie = 11;
  }else if(iecheck){
    ret.oldie = parseInt(iecheck[1]);
  }else{
    ret.oldie = false;
  }
  mps.__ua = ret;
  return ret;
};

// _getBoundingRect(elem) returns offset top and left (used in lazyload.js, ab.js, rails.js)
mps._getBoundingRect = function(elem) {
  if(!elem){
    return {
      top: 0,
      left: 0,
      bottom: 0,
      right: 0
    };
  }
  var box = elem.getBoundingClientRect();
  var body = document.body;
  var docEl = document.documentElement;
  var scrollTop = window.pageYOffset || docEl.scrollTop || body.scrollTop;
  var scrollLeft = window.pageXOffset || docEl.scrollLeft || body.scrollLeft;
  var clientTop = docEl.clientTop || body.clientTop || 0;
  var clientLeft = docEl.clientLeft || body.clientLeft || 0;
  var top  = box.top +  scrollTop - clientTop;
  var left = box.left + scrollLeft - clientLeft;
  var bottom  = box.top + box.height;
  var right = box.left + box.width;

  return {
    top: Math.round(top),
    left: Math.round(left),
    bottom: Math.round(bottom),
    right: Math.round(right)
  };

};


// _getDocHeight() returns document height, cross browser
mps._getDocHeight = function(){
  var D = document;
  return Math.max(
      D.body.scrollHeight, D.documentElement.scrollHeight,
      D.body.offsetHeight, D.documentElement.offsetHeight,
      D.body.clientHeight, D.documentElement.clientHeight
  );
};


//--Check for debugmode.
mps._isdebug = function() { return typeof(debugmode)==='object' && parseInt(debugmode.log) === 2; };

//--[Get Query String Parameter] mps._get([parameter],[url],[decode],keyonly))
mps._get=function(n,r,e,t){if("undefined"==typeof e&&(e=!0),"string"!=typeof r&&(r=""),r=r.length?r:window.location.search,0>r.indexOf("?"))return!1;r=r.split("?")[1].split("&");for(var i=function(n){return t===!0&&"undefined"==typeof n?!0:n},o=!0,p=0;p<r.length;p++){if(parr=r[p].split("="),parr[0]==n)return e?decodeURIComponent(i(parr[1])):i(parr[1]);o=!1}return o?void 0:!1};

//--[Serializes object for query string] mps._serialize=function({key:{val}}, 'cag'), encodes and lowercases all key/val
mps._serialize=function(obj,prefix){var str=[],p,v;for(p in obj)if(obj.hasOwnProperty(p)){var k=prefix?prefix+"["+p+"]":p;v=obj[p];if(typeof v==="object")v=JSON.stringify(v); if(typeof v.toString==="function")v=v.toString();if(v!==null&&v instanceof Array){var pipeval="";for(var i=0;i<v.length;i++)pipeval+=i==v.length-1?v[i].toLowerCase():v[i].toLowerCase()+"|";str.push(encodeURIComponent(k)+"="+encodeURIComponent(pipeval))}else if(v!==null&&typeof v==="object"&&!(v instanceof Array))str.push(mps._serialize(v, k));else str.push(encodeURIComponent(k)+"="+encodeURIComponent(v.toLowerCase()))}return str.join("&")};
//--Returns input sorted alphabetically on property names  mps._sortObject(o[object])
mps._sortObject=function(c){var d={},a,b=[];for(a in c)c.hasOwnProperty(a)&&b.push(a);b.sort();for(a=0;a<b.length;a++)d[b[a]]=c[b[a]];return d};

//--[Strings] mps._trim(str,charlist)
mps._trim = function(a,e){var c,d=0,b=0;a+="";c=e?(e+"").replace(/([\[\]\(\)\.\?\/\*\{\}\+\$\^\:])/g,"$1"):" \n\r\t\f\x0B\u00a0\u2000\u2001\u2002\u2003\u2004\u2005\u2006\u2007\u2008\u2009\u200a\u200b\u2028\u2029\u3000";d=a.length;for(b=0;b<d;b++)if(-1===c.indexOf(a.charAt(b))){a=a.substring(b);break}d=a.length;for(b=d-1;0<=b;b--)if(-1===c.indexOf(a.charAt(b))){a=a.substring(0,b+1);break}return-1===c.indexOf(a.charAt(0))?a:""};

//--[Sets] mps._merge(obj1,obj2,...) mps._keys(obj,[filter])
mps._merge = function(){var d=Array.prototype.slice.call(arguments),g=d.length,a,e={},c="",k=0,f=0,b=0,h=0,l=Object.prototype.toString;a=!0;for(b=0;b<g;b++)if("[object Array]"!==l.call(d[b])){a=!1;break}if(a){a=[];for(b=0;b<g;b++)a=a.concat(d[b]);return a}for(h=b=0;b<g;b++)if(a=d[b],"[object Array]"===l.call(a))for(f=0,k=a.length;f<k;f++)e[h++]=a[f];else for(c in a)a.hasOwnProperty(c)&&(parseInt(c,10)+""===c?e[h++]=a[c]:e[c]=a[c]);return e};
mps._keys = function(a,c,f){var g="undefined"!==typeof c,e=[],h=!!f,d=!0,b="";if(a&&"object"===typeof a&&a.change_key_case)return a.keys(c,f);for(b in a)a.hasOwnProperty(b)&&(d=!0,g&&(h&&a[b]!==c?d=!1:a[b]!=c&&(d=!1)),d&&(e[e.length]=b));return e};

//--[DOM Object Class] mps._classHas(elem,class) mps._classAdd(elem,class) mps._classRemove(elem,class)
mps._classHas=function(a,b){return RegExp(" "+b+" ").test(" "+a.className+" ")};mps._classAdd=function(a,b){return mps._classHas(a,b)||(a.className+=" "+b)};mps._classRemove=function(a,b){if(!0!==mps._classHas(a,b))return!1;var c=" "+a.className.replace(/[\t\r\n]/g," ")+" ";if(mps._classHas(a,b)){for(;0<=c.indexOf(" "+b+" ");)c=c.replace(" "+b+" "," ");a.className=c.replace(/^\s+|\s+$/g,"")}return!0};

//--[Remove Event Handler] mps._eventRemove(elem,eventType,handler)
mps._eventRemove=function(a,b,c){a.removeEventListener&&a.removeEventListener(b,c,!1);a.detachEvent&&a.detachEvent("on"+b,c)};

// [check if Element exists in DOM] mps._isElement(elem)
mps._isElement=function(e){try{return e instanceof HTMLElement}catch(t){return typeof e==="object"&&e.nodeType===1&&typeof e.style==="object"&&typeof e.ownerDocument==="object"}};

//--[Load External JS] url(str): file url, onload(func): callback, noasync(bool)
mps._loadJS = function(url,onload,noasync) {
  if(!url) return false;
  noasync = typeof noasync !== 'undefined';
  var scr = document.createElement('script');
  if(!noasync) scr.async = true;
  scr.type = 'text/javascript';
  if(url.substring(0,4) == 'http' || url.substring(0,2) == '//') url = url.replace('http://','').replace('https://','').replace('//','');
  scr.src = mps._protocol()+'//'+url;
  scr.onload=function(){
    mps._log('#[mps:loadJS] async:'+!noasync+', '+url.split('/').pop());
    if(typeof(onload)=='function') { onload.call(scr); }
  };
  scr.onerror = function(){ mps._loadError(scr.src); }

  document.getElementsByTagName('head')[0].appendChild(scr);
  return true;
};

//--[ResetTargetingObj] insertAd & cloneAd to retrieve save originalTargeting
mps._resetTargetingObj=function(a){if("[object Array]"===Object.prototype.toString.call(a)){for(var c=[],b=0,d=a.length;b<d;b++)c[b]=arguments.callee(a[b]);return c}if("object"===typeof a){c={};for(b in a)c[b]=arguments.callee(a[b]);return c}return a};

//--[Detect if Horizontal Scrollbar exists] returns boolean, 15px for mac, 17px for windows
mps._hscroll=function(docElem){
  return docElem&&window&&docElem.clientHeight<window.innerHeight?Math.round(window.innerHeight-docElem.clientHeight):0;
};

//--[Detect if Vertical Scrollbar exists] returns boolean, 15px for mac, 17px for windows
mps._vscroll=function(docElem){
  return docElem&&window&&docElem.clientWidth<window.innerWidth?Math.round(window.innerWidth-docElem.clientWidth):0;
};

//--[Get Viewport Size] returns array of [width, height]
mps._viewport=function(){
  var d=window,a=document,e=a.documentElement,a=a.getElementsByTagName("body")[0],b=mps._hscroll(e)?mps._hscroll(e):0,c=mps._vscroll(e)?mps._vscroll(e):0;
  return [d.innerWidth-c||e.clientWidth-c||a.clientWidth-c,d.innerHeight-b||e.clientHeight-b||a.clientHeight-b];
};

//--[Browser Safe Debugging] !error ^warning  #debug ~log
// (internal) call using: mps._log / mps._l
mps.__console = {
  log: function() {
    if(mps.__nolog) {
      return false;
    }
    var args = Array.prototype.slice.call(arguments);
    var i_arg = 0;
    while (args[i_arg]){
      var m = args[i_arg];
      i_arg++;
      if(window.console && console.log && console.warn && console.debug && console.error) {
        if(typeof(m)!='string') {
          if(mps.__console._last && typeof(console[mps.__console._last])){
            console[mps.__console._last](m);
          }
          else {
            console.log(m);
            mps.__console.overlay(m, 'log');
          }
          continue;
        }
        var f = m.charAt(0);
        if(f=='~') {
          console.log(m.substring(1));
          mps.__console.overlay(m.substring(1), 'log');
          mps.__console._last = false;
        } else if(f=='!') {
          mps.__console._last='error';
          mps.__console.overlay(m.substring(1), 'error');
          console.error(m.substring(1));
        } else if(f=='^') {
          mps.__console._last='warn';
          mps.__console.overlay(m.substring(1), 'warn');
          console.warn(m.substring(1));
        } else if(f=='#') {
          mps.__console._last='debug';
          mps.__console.overlay(m.substring(1), 'debug');
          console.debug(m.substring(1));
        } else {
          mps.__console.auto(m);
        }
      } else if(window.console && console.log) {
        console.log(m);
        mps.__console.overlay(m, 'log');
        mps._console._last=false;
      } else {
        return false;
      }
    }
    return true;
  },
  debug: function() {
    if(!mps._isdebug()) {
      return false;
    }
    var args = Array.prototype.slice.call(arguments);
    return mps.__console.log.apply(this, args);
  },
  //(internal) don't call directly
  overlay: function(m, type){
    type = type || '';
    m = (typeof m != 'undefined') ? m.toString() : '';
    var $debugPanel = mps._isElement(mps._select('#debugPanel')) ? $('#debugPanel') : false;
      var prefix = (m.match(/\[(.*?)\]/)) ? m.match(/\[(.*?)\]/)[0] : '[MPS]';
      var debugMsgInx = mps._keys(mps.debugMsg).length || 0;
      var debugMarkup = '';
      mps.debugMsg.push({
        'm': m,
        'type': type,
        'prefix': prefix
      });
      if($debugPanel) {
        var date = new Date(),
            mil = date.getMilliseconds(),
            sec = date.getSeconds(),
            min = date.getMinutes(),
            hrs = date.getHours(),
            now = hrs + ':' + min + ':' + sec + '.' + mil;
        if (typeof 's'.indexOf == 'function' && m.indexOf('loadmore') === -1) {
          debugMarkup = '<p class="' + type + '" title="' + now + '">' + m + '</p>';
        } else {
          debugMarkup = m;
        }
        if (debugMsgInx > 0) {
          for (var i in mps.debugMsg) {
            if (mps.debugMsg.hasOwnProperty(i)) {
              if (typeof 's'.indexOf == 'function' && mps.debugMsg[i].m.indexOf('loadmore') === -1) {
                debugMarkup += '<p class="' + mps.debugMsg[i].type + '" title="' + now + '">' + mps.debugMsg[i].m + '</p>';
              } else {
                debugMarkup += mps.debugMsg[i].m;
              }
            }
          }
          if (mps._ext._jq) {
            $debugPanel.html(debugMarkup);
          } else {
            $debugPanel.outerHTML = debugMarkup;
          }
        }
        $debugPanel.scrollTop = $debugPanel.scrollHeight;
        return true;
      } else {
        return false;
      }
  },
  // (internal) do not call directly
  auto: function(m) {
    var typemap = {
      // debug
      '#': [,'called','loaded','disabled','enabled','init','callback','calling '],
      // warning
      '^': ['warning','skip','bypass'],
      // error
      '!': ['error','invalid','fail','terminated']
    };
    for(var t in typemap) {
      for(var tv in typemap[t]) {
        if(m.toLowerCase().indexOf(typemap[t][tv]) > -1) {
          return mps.__console.log(t+m);
        }
      }
    }
    return mps.__console.log('~'+m);
  },
  _last: false
};

//--SHORTCUTS, ALIASES
mps._log=mps._l=mps._console=mps.__console.log;
mps._vp=mps._viewport;
mps._debug=mps._d=mps.__console.debug;

//--[Queues]
if(!mps._loadset) {
  mps._queue.exec = function(args, param) {
    if (typeof(args) === 'function') {
      try {
        typeof(param) === 'undefined' ? args.call() : args.call(this, param);
      } catch (err) {
        mps._errorCallback(err);
      }
    }
  };
  // Copy queued functions from mps._gptcmd.
  mps._gptcmdtmp = mps._gptcmd;
  mps._gptcmd = [];
  mps._gptcmd.push = function() {
    var _args = arguments[0];
    var _func = function() {
      try {
        _args.call();
      } catch(err) {
        mps._errorCallback(err, 'mps._gptcmd.push');
        googletag.cmd.push(_args);
      }
    };
    googletag.cmd.push(_func);
    return Array.prototype.push.apply(this, arguments);
  };
  // Push queued functions to mps._gptcmd after being extended.
  while(mps._gptcmdtmp.length) {
    mps._gptcmd.push(mps._gptcmdtmp[0]);
    mps._gptcmdtmp.shift();
  }
  mps._queue['mpsinit'].push = function () {
    if (mps._ext && mps._ext.loaded === 1) {
      mps._queue.exec(arguments[0]);
    }
    return Array.prototype.push.apply(this, arguments);
  };
  mps._queue['abdetect'].push = function () {
    if (mps._ab && mps._ab.run) {
      mps._queue.exec(arguments[0], mps._ab.type);
    }
    return Array.prototype.push.apply(this, arguments);
  };
  mps._queue.gptloadset[0] = mps._queue.gptloadset[0] || [];
  if (typeof(mps._queue.gptloaded.length) !== 'undefined') {
    for (var i = 0; i < mps._queue.gptloaded.length; i++) {
      mps._queue.gptloadset[0].push(mps._queue.gptloaded[i]);
    }
    mps._queue.gptloaded = [];
  }
  mps._queue['gptloaded'].push = function () {
    if (arguments[0]) {
      if (mpsopts.legacyqueues === 1) {
        var gptLoadset = mps._reqset;
      } else {
        var gptLoadset = mps._gptloaded ? mps._reqset + 1 : mps._reqset;
      }
      mps._queue.gptloadset[gptLoadset] = mps._queue.gptloadset[gptLoadset] || [];
      // GPT callback already executed for this loadset.
      if ((mps._reqset === mps._loadset) && mps._gptloaded) {
        mps._gptcmd.push(arguments[0]);
      } else {
        mps._queue.gptloadset[gptLoadset].push(arguments[0]);
      }
    }
    return Array.prototype.push.apply(this);
  };
  mps._queue['mpsready'].push = function () {
    if (arguments[0] && mps._ext.mpsready === true) {
      try {
        arguments[0].call();
      } catch (err) {
        mps._errorCallback(err, 'mps._queue.mpsready');
      }
    } else {
      return Array.prototype.push.apply(this, arguments);
    }
  };
}
mps._queue.render = function(type, param1, param2, param3, param4) {
  debugmsg = '[mps:QUEUE] ' + type;
  warnmsg = '^'+debugmsg;
  queuelen = 0;
  try {
    switch (type) {
      case 'mpsinit':
        for (var i = 0; i < mps._queue.mpsinit.length; i++) {
          mps._queue.mpsinit[i].call();
          queuelen++;
        }
        mps._debug(debugmsg + ' items ran: ' + queuelen + ' '  + mps._elapsed());
        break;
      case 'mpsready':
        while(mps._queue.mpsready.length) {
          mps._queue.mpsready.shift().call();
          queuelen++;
        }
        mps._debug(debugmsg + ' items dequeued: ' + queuelen + ' '  + mps._elapsed());
        break;
      case 'gptloaded':
        for (var j = 0; j < mps._queue[type].length; j++) {
          mps._queue[type][j].call(this, param1, param2, param3, param4);
          queuelen++;
        }
        mps._debug(debugmsg + ' loadset: ' + param1 + ' ' + ' items ran: ' + queuelen + ' ' + mps._elapsed());
        break;
      case 'error':
        for (var j = 0; j < mps._queue[type].length; j++) {
          mps._queue[type][j].call(this, param1, param2, param3, param4);
          mps._debug(warnmsg + ' p1: ' + param1+ ' ' + ' p2: ' + param2 + ' ' + ' p3: ' + param3+ ' ' + ' p4: ' + param4 + ' '  + mps._elapsed());
        }
        break;
      case 'adviewchange':
        for (var k = 0; k < mps._queue[type].length; k++) {
          mps._queue[type][k].call(this, param1, param2, param3, param4);
        }
        break;
      case 'adexecute':
        for (var k = 0; k < mps._queue[type].length; k++) {
          mps._queue[type][k].call(this, param1, param2, param3, param4);
          queuelen++;
        }
        mps._debug(debugmsg + ' ' + param1 + ' ' + ' items ran: ' + queuelen + ' '+ mps._elapsed());
        break;
      case 'adrender':
      case 'adload':
        for (var k = 0; k < mps._queue[type].length; k++) {
          mps._queue[type][k].call(this, param1, param2, param3, param4);
          queuelen++;
        }
        var loadset = typeof(param1._mps)==='object' ? param1._mps.loadset : 'R'+param1[0].loadset;
        var slot = typeof(param1._mps)==='object' ? param1._mps._slot : param1[0]._slot;
        mps._debug(debugmsg + ' ' + loadset + ':' + slot + ' isEmpty: ' + param1.isEmpty + ' ' + ' items ran: ' + queuelen + ' '  + mps._elapsed());
        break;
      case 'adclone':
        for (var d = 0; d < mps._queue[type].length; d++) {
          typeof(param2 === 'number') ? mps._queue[type][d].call(this, param1, param2, param3) : mps._queue[type][d].call(this, param1);
          queuelen++;
        }
        mps._queue.clear(type);
        mps._debug(debugmsg + ' ' + param2 + ':' + param1 +  ' ' + mps._elapsed());
        break;
      default:
        for (var d = 0; d < mps._queue[type].length; d++) {
          typeof(param2 === 'number') ? mps._queue[type][d].call(this, param1, param2, param3) : mps._queue[type][d].call(this, param1);
          queuelen++;
        }
        mps._debug(debugmsg + ' items ran: ' + queuelen + ' '  + mps._elapsed());
        break;
    }
  } catch(err) {
    mps._errorCallback(err, 'mps._queue.render(' + type + ')');
  }
};
mps._queue.clear = function(type) {
  if(type) {
    mps._debug('[mps:QUEUE] (clear ' + type + ') items cleared: ' + mps._queue[type].length);
    mps._queue[type] ? mps._queue[type] = [] : mps._debug('[mps:QUEUE] (clear ' + type + ') is not a valid queue.');
  } else {
    mps._debug('[mps:QUEUE] (clear all…)');
    for(var i in mps._queue) {
      if(typeof(mps._queue[i]) === 'object' && i!='mpsloaded' && mps._queue[i].length > 0 ) {
        mps._debug('[mps:QUEUE] (clear ' + i + ') items cleared: ' + mps._queue[i].length);
        mps._queue[i] = [];
      }
    }
  }
};

/* ----- Error handling ----- */
// Execute error tracking pixel.
mps._errorpixel = function(_errsrc) {
  var _errimg = '<img width="1" height="1" src="'+encodeURI(_errsrc)+'" />';
  mps._append(mps._select('body'), _errimg);
};

// Error callback.
mps._errorCallback = function(err, func) {
  if(err.name) {
    if(err.message) {
      mps._debug('![mps:!] ERROR ' + func + ' - Uncaught ' + err.name + ': ' + err.message + ' (' + mps._elapsed() + ')');
    } else {
      mps._debug('![mps:!] ERROR ' + func + ' - Uncaught ' + err.name + ' (' + mps._elapsed() + ')');
    }
  }
  if(typeof mps.errorCallback === 'function') {
    mps.errorCallback(err.name, err.message, err.lineNumber, func);
  }
  if(mps._queue.error.length) {
    for(var i = 0; i < mps._queue.error.length; i += 1) {
      mps._queue.render('error', err.name, err.message, err.lineNumber, func);
    }
  }
  // Error tracking url for Splunk
  if(typeof mps._reportingbaseurl === 'string' && mps._reportingbaseurl.trim() !== '') {
    var _errsrc = mps._protocol() + '//' + mps._reportingbaseurl,
      _mpsid = (mps.pagevars && mps.pagevars.mpsid) ? mps.pagevars.mpsid: '',
      _authuser = (mps.pagevars && mps.pagevars.authuser) ? mps.pagevars.authuser: '';
    _errsrc += '?mpsid=' + _mpsid;
    _errsrc += '&mpspath=' + encodeURIComponent(mps.pagevars.path);
    _errsrc += '&site=' + mps.pagevars.instance;
    _errsrc += '&authusr=' + _authuser;

    if (err.name) {
      _errsrc += '&errtype=' + err.name;
      if (err.message) {
        _errsrc += '&errmsg=' + func + ' - ' + encodeURIComponent(err.message);
      }
      if (err.stack) {
        _errsrc += '&errstack=' + encodeURIComponent(err.stack);
      }
      if (err.lineNumber) {
        _errsrc += '&errline=' + err.lineNumber;
      }
    }
    if (typeof(mps._delays._reportingdelay) === 'number' && (mps._elapsed('', true) > mps._delays._reportingdelay)) {
      mps._errorpixel(_errsrc);
    } else {
      mps._queue.errorpixels.push(function () {
        mps._errorpixel(_errsrc);
      });
    }
  }
};

// Set pixel reporting delay atleast 2s from mps._ready.
mps._ready(function() {
  mps._ext.mpsready = true;
  mps._delays._reportingdelay = (mps._elapsed('', true) + mps._delays.reportingdelay);
  var _execpixels = setTimeout(function() {
    while(mps._queue.errorpixels.length) {
      mps._queue.errorpixels.shift().call();
    }
    clearTimeout(_execpixels);
  }, mps._delays._reportingdelay);
});

// Update and Get correctlor, store correlators by loadset
mps._correlator = {
  sets: this.sets || {},
  update: function(){
    mps._gptcmd.push(function(){
      googletag.pubads().updateCorrelator();
    });
    if(googletag && typeof googletag.pubads().updateCorrelator() == 'object'){
      mps._debug('[mps:Loader] Update Correlator: public');
      return googletag.pubads().getCorrelator();
    }else{
      mps._debug('[mps:Loader] FAILED Update Correlator: public');
      return false;
    }
  },
  get: function(){
    if(typeof googletag.pubads() == 'object' && typeof googletag.pubads().getCorrelator() == 'string'){
      mps._debug('[mps:Loader] Get Correlator');
      return googletag.pubads().getCorrelator();
    }else{
      mps._debug('[mps:Loader] FAILED Get Correlator');
      return false;
    }
  }
};

mps._setPageTargeting = function(key,val) {
  try {
    // normalize all val inputs into array and validate
    if (!key || !val) {
      return false;
    }
    if (typeof(val) == 'boolean') {
      val = val + 0;
    }
    if (typeof(val) == 'number') {
      val = val.toString();
    }
    if (typeof(val) == 'string') {
      val = [val];
    }
    // array check
    if (val.constructor !== Array) {
      return false;
    }
    // normalize and validate key
    if (typeof(key) == 'boolean') {
      key = key + 0;
    }
    if (typeof(key) == 'number') {
      key = key.toString();
    }
    if (typeof(key) != 'string' || !key.length) {
      return key;
    }
    if (val.length === 1) {
      val = val[0].split(',');
    }
    // strip unsupported characters from key & val
    key = key.replace(/[^a-zA-Z0-9\.~_-]/gi, '');
    for (i = 0; i < val.length; i++) {
      val[i] = val[i].replace(/[^a-zA-Z0-9\.~_-]/gi, '');
    }
  } catch(err) {
    mps._errorCallback(err, 'mps._setPageTargeting');
    return false;
  }
  mps._gptcmd.push(function () {
    // call gpt page targeting
    if (mps._keys(mps._targeting).indexOf(key) === -1) {
      googletag.pubads().setTargeting(key, val);
      // save page targeting
      mps._targeting[key] = mps._targeting[key] || [];
      mps._targeting[key] = mps._merge(mps._targeting[key], val);
    }
  });
};

mps._clearPageTargeting = function(key) {
  if(typeof(key)=='boolean') {
    key=key+0;
  }
  if(typeof(key)=='number') {
    key=key.toString();
  }
  // If no arg passed, clear all targeting
  if(key == undefined) {
    if(!mps._targeting || typeof(mps._targeting)!='object') {
      return false;
    }
    for(var k in mps._targeting) {
      if(k.length) {
        mps._clearPageTargeting(key);
      }
    }
  } else {
    key=key.replace(/[^a-zA-Z0-9\.~_-]/gi,'');
    delete mps._targeting[key];
    mps._gptcmd.push(function() {
      googletag.pubads().clearTargeting(mps._targeting[key]);
    });
  }
};

//--mps._clone(a[obj]) returns deep copy
mps._clone=function(a){if(null==a||"object"!=typeof a)return a;var c=a.constructor(),b;for(b in a)a.hasOwnProperty(b)&&(c[b]=a[b]);return c};

// _haskeyval(obj[a],key[b],val[c]) Returns true if obj has a key called "key" and that key has "val" as its value.
mps._haskeyval=function(a,b,c){return a.hasOwnProperty(b)&&a[b]==c};

mps._debug('[mps:JS] LOADED: MPStools');

mps._bool = function(val,intval) {
  if(typeof(val)=='boolean') {
    val = val ? 1 : 0;
  }
  if(typeof(val)=='string') {
    if(val=='true') {
      val = 1;
    }
    if(val=='false') {
      val = 0;
    }
  }
  val = parseInt(val,10);
  if(!intval) {
    return val === 1;
  } else {
    return typeof(val) === 'number' ? val : parseInt(val, 10);
  }
};

// Active refresh.
mps._activerefresh = mps._activerefresh || {};
mps._activerefresh._focus = document.hasFocus();
mps._activerefresh._callback = function(func, name) {
  try {
    func();
  } catch(err) {
    mps._errorCallback(err, name);
  }
};

mps._activerefresh._wfocus = function() {
  mps._activerefresh._focus = true;
  if(typeof mps.detectwinfocusCallback === 'function') {
    mps._activerefresh._callback(mps.detectwinfocusCallback, 'mps.detectwinfocusCallback');
  }
};
mps._activerefresh._wblur = function() {
  mps._activerefresh._focus = false;
  if(typeof mps.detectwinblurCallback === 'function') {
    mps._activerefresh._callback(mps.detectwinblurCallback, 'mps.detectwinblurCallback');
  }
};
mps._activerefresh.blisten = window.addEventListener ? window.addEventListener('blur', mps._activerefresh._wblur) : window.attachEvent('onblur', mps._activerefresh._wblur);
mps._activerefresh.flisten = window.addEventListener ? window.addEventListener('focus', mps._activerefresh._wfocus) : window.attachEvent('onfocus', mps._activerefresh._wfocus);

mps.submit = mps.submit || {};
mps.submit._requested = mps.submit._requested || {};
mps.submit._responses = mps.submit._responses || {};
mps.submit._legacy = !(mps._checkua().oldie === false || mps._checkua().oldie && mps._checkua().oldie > 10);
mps.submit._getparams = function(getobj) {
  var _paramstr = '';
  for(var i in getobj) {
    _paramstr += encodeURIComponent(i);
    _paramstr += getobj[i] ? '=' + encodeURIComponent(getobj[i]) + '&' : '&';
  }
  return _paramstr.slice(0, -1);
};
mps.submit._response = function(_response, _statuscode, _key, _callback) {
  mps._debug('[mps:submit]: response received from url: ' + mps.submit._requested[0].url + ' with status code: ' + _statuscode);
  var _res = {
    response: _response,
    statuscode: _statuscode,
    elapsed: mps._elapsed('', true)
  };
  mps.submit._responses[_key] = _res;
  if(_callback) {
    return _callback.call(this, _statuscode, _response);
  }
  return _statuscode;
};
mps.submit._jq = function(_requested, _key, _callback, _timeout) {
  if(mps.submit._legacy === true) {
    jQuery.support.cors = true;
  }
  return jQuery.ajax({
    type: _requested.type,
    url:  _requested.url,
    data: _requested.type === 'POST' ? _requested.data : false,
    timout: _requested.timeout,
    dataType: mps.submit._legacy === true ? 'jsonp':'json',
    success: function(data, textStatus, xhr) {
      mps.submit._response(data, xhr.status, _key, _callback);
    },
    error: function(data, exception) {
      var _res = exception;
      var _xhrstatus = data && data.statusText ? data.statusText : false;
      mps.submit._response(_res, _xhrstatus, _key, _callback);
    }
  });
};
mps.submit._xhr = function(_requested, _key, _callback, _timeout) {
  var _newxhr;
  var _send = _requested.type === 'POST' ? mps.submit._getparams(_requested.data) : null;
  if(mps.submit._legacy === false) {
    _newxhr = new XMLHttpRequest();
    _newxhr.timeout = _requested.timeout;
    _newxhr.responseType = 'json';
    _newxhr.onreadystatechange = function() {
      if(_newxhr.readyState == 4) {
        var _responseobj = _newxhr.status === 200 ?_newxhr.response : _newxhr.statusText;
        return mps.submit._response(_responseobj, _newxhr.status, _key, _callback);
      }
    };
    _newxhr.open(_requested.type, _requested.url, true);
    _newxhr.send(_send);
    return _newxhr;
  } else {
    _newxhr = new XDomainRequest();
    _newxhr.onload=function() {
      return mps.submit._response(_newxhr.responseText, 200, _key, _callback);
    };
    _newxhr.onerror=function() {
      return mps.submit._response(_newxhr.responseText, 0, _key, _callback);
    };
    _newxhr.open(_requested.type, _requested.url, true);
    _newxhr.send(_send);
    return _newxhr;
  }
};

mps.submit.request = function(endpointurl, kvdata, usepost, timeoutsecs, callback) {
  var _endpointurl = typeof(endpointurl) === 'string' && endpointurl.length ? endpointurl : false;
  var _kvdata = typeof(kvdata) === 'object' && mps._keys(kvdata).length ? kvdata : false;
  var _type = mps._bool(usepost) === true ? 'POST': 'GET';
  var _timeoutsecs = typeof(timeoutsecs) === 'number' && timeoutsecs > 0 ? timeoutsecs * 1000 : 4000;
  var _callback = typeof(callback) === 'function' ? callback : false;
  if(_endpointurl && _kvdata) {
    _endpointurl = _type === 'POST' ? _endpointurl : _endpointurl + '?' + this._getparams(_kvdata);
    var _key = mps._keys(mps.submit._requested).length;
    var _requested = {
      url: _endpointurl,
      data: _kvdata,
      type: _type,
      timeout: _timeoutsecs,
      elapsed: mps._elapsed('', true)
    };
    mps.submit._requested[_key] = _requested;
    if(typeof(jQuery) === 'function') {
      return mps.submit._jq(_requested, _key, _callback);
    } else {
      return mps.submit._xhr(_requested, _key, _callback);
    }
  } else {
    mps._debug('[mps:submit]: invalid url or key value data specified.');
    return false;
  }
};

/* ----- Return breakpoint from responsive map ----- */
mps.getResponsiveSet = function(width,height) {
  var vpsize = mps._viewport(),
      vpwidth = width ? width : vpsize[0],
      vpheight = height ? height : vpsize[1],
      rset = '';
  var responsivesets = mps.response && mps.response.dart && mps.response.dart.params && mps.response.dart.params.responsive_sets;
  if (!responsivesets || responsivesets.length == 0) {
    mps._debug('^[mps:getResponsiveSet] No responsive map set.');
    return false;
  }
  for (var size in responsivesets) {
    if (vpwidth >= responsivesets[size][0] && vpheight >= responsivesets[size][1]){
      rset = size;
    }
  }
  if(typeof(rset)!='undefined') {
    return rset;
  } else {
    return false;
  }
};

/**
 * getValueWithoutKey return properties values without the keys
 * @param {object}  obj
 * @return {values} array
 */
mps.getValueWithoutKey = function(obj) {
  var values = [];
  for (var key in obj) {
    if (Object.prototype.hasOwnProperty.call(obj, key)) {
      values.push(obj[key]);
    }
  }
  return values;
};




/* js/core/gpt-shared.js */

var mps = mps || {},
    gpt = gpt || {};
mps._gptloaded = false;
mps._adloads=mps._adloads||{};
mps._correlator=mps._correlator||{};
mps._adviews=mps._adviews||{};
mps._adobs=mps._adobs||{};
mps._adslots=mps._adslots||{};
mps._advars=mps._advars||{};
mps._slotscalled=mps._slotscalled||{};
mps._slotscalled[mps._loadset||0]={};
mps._slotsdisabled=mps._slotsdisabled||{};
mps._slotsdisabled[mps._loadset||0]||[];
mps._resetrsizemap = mps._resetrsizemap || {};
mps._collapsemap = mps._collapsemap || {};
mps.slotsdisabled = mps.slotsdisabled||{};
mps.slotsdisabled[mps._loadset||0]||[];
mps._gptTargeting = mps._gptTargeting || {};
mps._resetcatexclusion = mps._resetcatexclusion || {};
mps._resettargeting = mps._resettargeting || {};
mps._pagecontext = mps._pagecontext || {};
mps._adsizes = mps._adsizes || {};
mps._gptTargeting[mps._loadset||0] = mps._gptTargeting[mps._loadset||0] || {};
mps._ext = mps._ext || {};
mps._ext._jq = typeof(jQuery) === 'function' ? 1 : 0;

/** @namespace */
mps._gptshared = mps._gptshared || {};

//[v3.57.1] patch for nbcnews-bento, nbcnews-web
if((typeof mpscall === 'object' && mpscall.site && mpscall.site.indexOf("nbcnews") > -1 && mps._ext.nowrite === "jq") || mps._ext.nowrite === true || mps._ext.nowrite === ""){
  mps._ext.nowrite=2;
}
//[v3.57.1+] patch for cnbc.com-relaunch
if(typeof mpscall === 'object' && mpscall.site && mpscall.site.indexOf("cnbc.com-relaunch") > -1 && mps._ext.nowrite === "2"){
  mps._ext.nowrite="jq";
}
mps._ext.nowrite = !isNaN(parseInt(mps._ext.nowrite),10) ? parseInt(mps._ext.nowrite,10) : mps._ext.nowrite;

/**
 * Anonymous function:  defines MPS styles, scripts.
 */
(function() {
  // CSS styles
  var _mpsstyles = document.createElement('style');
  _mpsstyles.type = 'text/css';
  _mpsstyles.styleSheet ? style.styleSheet.cssText = '.mps-gpt-hidden { display: none; }' : _mpsstyles.appendChild(document.createTextNode('.mps-gpt-hidden { display: none; }'));
  document.getElementsByTagName('head')[0].appendChild(_mpsstyles);
  // Class and ID
  var _mpsscripts = document.currentScript ? document.currentScript : null;
  if(_mpsscripts) {
    _mpsscripts.id = 'mps-gpt-shared';
    _mpsscripts.className = 'mps-script';
  }
})();

/**
 * Loads gpt.js library, either asynchronously (default) or synchronously
 * @return {boolean}
 */
mps.loadGPT = function() {
  if (mps._gptrefresh) {
    try {
      var proto = 'https:' === document.location.protocol ? 'https://' : 'http://';
      var gptsrc =  typeof (mps.response) === 'object' ? proto + mps.response.dart.params.gpt_js_uri : proto + 'www.googletagservices.com/tag/js/gpt.js';
      if (mps._ext.dart_mode === 'gpt-asynchronous' && mps._ext.nowrite > 0) {
        mps._debug('[mps:GPT] loadGPT: asynchronous ' + mps._elapsed());
        var gads = document.createElement('script');
        var node = document.getElementsByTagName('script')[0];
          gads.src = gptsrc;
          gads.async = true;
          gads.type = 'text/javascript';
          var i =0;
          do{
            i++;
            mps._debug('[mps:GPT] node.parentNode ' + node.parentNode + ' i:' + i);
            if (mpsopts && mps._bool(mpsopts.loadgptfirst)) {
              node.parentNode.insertBefore(gads, node);
            } else {
              setTimeout(function () {
                node.parentNode.insertBefore(gads, node);
              }, 0);
            }
          } while (node.parentNode === null && i < 10);
      } else {
        mps._debug('[mps:GPT] loadGPT: synchronous ' + mps._elapsed());
        document.write('<scr' + 'ipt src="' + gptsrc + '"></scr' + 'ipt>');
        document.write('<scr' + 'ipt>' + 'mps._gptcmd.push(function(){mps._gptloadCallback();});' + '</scr' + 'ipt>');
      }
    } catch(err) {
      mps._errorCallback(err, 'mps.loadGPT');
    }
    return true;
  }
};

/**
 * _adLoadCallbackObj => used in OVERLAY: overview.js and timing.js
 * @type {Array}
 */
mps._adLoadCallbackObj = [];
/**
 * mps._adloadCallback => triggered by slotRenderEnded googletag listener
 * @param {object} eo
 * @param {number} loadset
 * @return {boolean}
 * */
mps._adloadCallback = function (eo, loadset) {
  // Clear clonead queue due to forced delay during cloneAd
  if(mps._queue.clonead.length) {
    mps._queue.clonead.shift().call();
  }
  if (typeof (eo) === 'object' && typeof (eo.slot) === 'object') {
    // Create vars
    var _slotid = mps._determineSlot(eo.slot.getSlotElementId()),
        _adslot = _slotid.slotname,
        _cleanslot = _slotid.cleanslot,
        _cloneslot = _slotid.slotname,
        _loadset = _slotid.loadset;
    // refreshed ad
    var _refreshed = (mps._adloads && mps._adloads[_loadset] && mps._adloads[_loadset][_adslot] && mps._keys(mps._slotscalled[_loadset]).indexOf(_adslot) > -1) ? 1 : 0;

    // Create internal eo[slot]._mps object
    if(typeof(eo._mps) !== 'object' && typeof loadset === 'number'){
      var eodata = mps._attachEoData(eo, _loadset, 'adload');
      var _correlator = eodata._mps.correlator;
      eo._mps = eodata._mps;
    }

    //Create mps._adloads
    if (typeof _loadset === 'number' && _adslot.length > 0) {
      mps._adloads[_loadset] = mps._adloads[_loadset] || {};
      mps._adloads[_loadset][_adslot] = mps._adloads[_loadset][_adslot] || [];
      mps._correlator.sets[_loadset] = mps._correlator.sets[_loadset] || {};
      mps._correlator.sets[_loadset][_adslot] = mps._correlator.sets[_loadset][_adslot] || [];
      var radload = 'R' + _loadset;
      if(_refreshed) {
        // Refreshed ads
        mps._correlator.sets[radload] = mps._correlator.sets[radload] ||{};
        mps._correlator.sets[radload][_adslot] = mps._correlator.sets[radload][_adslot]  ||[];
        mps._correlator.sets[radload][_adslot] = _correlator;
        mps._adloads[radload] = mps._adloads[radload] || {};
        mps._adloads[radload][_adslot] = mps._adloads[radload][_adslot] || [];
        mps._adloads[radload][_adslot].push({
          'elapsed': mps._elapsed('', true),
          'correlator': _correlator,
          'empty': eo.isEmpty,
          '_slot': _adslot=_adslot||'',
          '_gpt': eo.slot,
          'loadset': _loadset
        });
        mps._adloads[_loadset][_adslot]._mps._refreshed = (mps._adloads[radload][_adslot].length) ? mps._adloads[radload][_adslot].length : 0;
      } else {
        eo._mps._refreshed = 0;
        eo._mps._destroyed = 0;
        mps._clonerunning = false;
        if (!_slotid.clone) {
          // Non-Clone ads
          eo._mps._clone = false;
          mps._adloads[_loadset][_adslot] = eo;
        }else if (_slotid.clone) {
          // Cloned ads
          eo._mps._clone = _slotid.cloneset;
          mps._adloads[_loadset][_adslot] = eo;
          if(typeof mps._adloads[_loadset][_cleanslot] !== 'undefined'){
            mps._adloads[_loadset][_cleanslot]._mps._clone = true;
          }
        }
        mps._correlator.sets[_loadset][_adslot] = _correlator;
        mps._debug("[mps:GPT] CORRELATOR: " + _correlator + ', '+_loadset+':' + _adslot + ', ' + mps._elapsed('', true) + 'ms');
      }
    }
    //save mps._req _adslot end time
    if(mps._reqs && mps._reqs[_loadset] && eo._mps._slot !== '_oop'){
      mps._reqs[_loadset]['end_'+_adslot] = mps._reqs[_loadset]['end_'+_adslot] || mps._elapsed('',true);
    }
    var adload_refresh = !mps._bool(_refreshed) ? 'ADLOAD' : 'REFRESH';
    mps._debug("[mps:GPT] "+adload_refresh+" "+_loadset+":"+_adslot+" "+(eo.isEmpty ? "(isEmpty) ":"")+mps._elapsed());

    // Create mps._adsizes from eo.size
    var sizeval = false;
    var sizekey = eo._mps.loadset+'|'+(eo._mps._cloneslot) ? eo._mps._cloneslot : eo._slot; // handles refreshes and clones
    if(typeof(eo.size)=='object' && eo.size) sizeval = eo.size.join('x');
    mps._adsizes[sizekey] = sizeval;

    //used only if OVERLAY cookie is set
    if(mps._overlayenabled) {
      var eodata = {};
      if(eo.isEmpty === false && eo._mps._slot !== '_oop'){
        if(_refreshed){
          eodata = {
            '_slot': (!_slotid.clone) ? _cleanslot : _adslot,
            '_refreshed': mps._adloads[_loadset][_adslot]._mps._refreshed,
            'correlator': eo._mps.correlator,
            '_elapsed': mps._elapsed('',true),
            'empty': eo.isEmpty
          }
        }
        else{ eodata = eo._mps }
        var adLoadCallbackObj = {
          'eo': eodata,
          'adload': _loadset,
          '_refreshed':_refreshed
        };
        mps._adLoadCallbackObj.push(adLoadCallbackObj);
      }
    }
    // External adload queue and callback
    mps._queue.render('adload', eo);

    if(typeof(mps.adloadCallback) === 'function') {
      try {
        mps.adloadCallback(eo);
      } catch(err) {
        mps._errorCallback(err, 'mps.adloadCallback');
      }
    }
  }
  return true;
};

/**
 * mps._adrenderCallback => triggered by slotOnload googletag listener. Calls adrender
 * @param {object} eo
 * @return {none}
 */
mps._adrenderCallback = function (eo){
  var _slotid = mps._determineSlot(eo.slot.getSlotElementId()),
      _adslot = _slotid.slotname,
      _loadset = _slotid.loadset,
      _refreshed = false;
  // Refreshed Ads - 'R0'
  if(mps._adloads[_loadset][_adslot]._mps._refreshed) {
    var rcount = mps._adloads[_loadset][_adslot]._mps._refreshed;
    _loadset = 'R' + _loadset;
    _refreshed = true;
  }
  // Refreshed Ads : Delay between _rendered & _elapsed
  mps._delays._adview[_loadset] = mps._delays._adview[_loadset] || {};
  mps._delays._adview[_loadset][_adslot] = mps._delays._adview[_loadset][_adslot] || {};
  if(_refreshed){
    mps._adloads[_loadset][_adslot][rcount-1]._rendered = mps._elapsed('', true);
    mps._delays._adview[_loadset][_adslot][rcount-1] = parseInt(mps._adloads[_loadset][_adslot][rcount-1]._rendered - mps._adloads[_loadset][_adslot][rcount-1].elapsed, 10);
  }
  // Regular Ads: Delay between _rendered & _elapsed
  else if(!_refreshed && _adslot !== '_oop' && mps._adloads[_loadset] && mps._adloads[_loadset][_adslot] && mps._adloads[_loadset][_adslot]._mps._rendered === 0){
    mps._adloads[_loadset][_adslot]._mps._rendered = mps._elapsed('', true);
    mps._delays._adview[_loadset][_adslot] = parseInt(mps._adloads[_loadset][_adslot]._mps._rendered - mps._adloads[_loadset][_adslot]._mps._elapsed, 10);
  }
  var _eodata = mps._adloads[_loadset][_adslot];
  if(typeof(_eodata._mps) !== 'object' && typeof loadset === 'number'){
    _eodata = mps._attachEoData(eo, _loadset, 'adrender');
  }
  if(typeof(mps.adrenderCallback)==='function') {
    try {
      mps.adrenderCallback(_eodata);
    } catch(err) {
      mps._errorCallback(err, 'mps.adrenderCallback');
    }
  }
  mps._queue.render('adrender', _eodata);
};

/**
 * mps._adViewCallback => triggered by impressionViewable google listener
 * @param {object} eo
 * @return {none}
 */
mps._adViewCallback = function (eo) {
  var _slotid = mps._determineSlot(eo.slot.getSlotElementId()),
      _adslot = _slotid.slotname,
      _loadset = _slotid.loadset,
      _eodata = mps._adloads[_loadset][_adslot];
  if(typeof(_eodata._mps) !== 'object' && typeof loadset === 'number'){
    _eodata = mps._attachEoData(eo, _loadset, 'adview');
  }
  mps._adviews[_loadset] = mps._adviews[_loadset] || [];
  for(var slot in mps._adloads[_loadset]) {
    if(mps._adloads[_loadset].hasOwnProperty(slot)) {
      if (mps._adloads[_loadset][slot]._mps.adslot === eo.slot.getSlotElementId()) {
        var _time = (mps._elapsed('', true) - mps._adloads[_loadset][slot]._mps._elapsed);
        mps._debug("[mps:GPT] ADVIEW " +_loadset +":"+ slot + " in " + _time + 'ms');
        // Refreshed ad.
        if (mps._adviews[_loadset].indexOf(slot) > -1) {
          _loadset = 'R' + _loadset;
          var _index = (mps._keys(mps._adloads[_loadset][slot]).length) - 1;
          mps._adloads[_loadset][slot][_index]._viewed = 1;
          mps._adloads[_loadset][slot][_index]._viewtime = _time;
          mps._adviews[_loadset] = mps._adviews[_loadset] || [];
          var _resindex = 0;
          while (mps._adviews[_loadset].indexOf(slot) > -1) {
            _resindex += 1;
            slot = slot.split('-R');
            slot = (slot[0] + '-R' + _resindex);
          }
          mps._adviews[_loadset].push(slot);
          // Ad or cloned ad.
        } else {
          mps._adloads[_loadset][slot]._mps._viewed = 1;
          mps._adloads[_loadset][slot]._mps._viewtime = _time;
          mps._adviews[_loadset].push(slot);
        }
        break;
      }
    }
  }
  if(typeof(mps.adViewCallback)=='function') {
    try {
      mps.adViewCallback(_eodata);
    } catch(err) {
      mps._errorCallback(err, 'mps.adViewCallback');
    }
  }
  mps._queue.render('adview', _eodata);
  return true;
};

/**
 * Triggered by slotVisibilityChanged google listener. Calls render adviewchange
 * @param {object} eo
 * @return {none}
 */
mps._adviewchangeCallback = function(eo) {
  var inviewpercentage = eo.inViewPercentage;
  var slot = mps._determineSlot(eo.slot.getSlotElementId());
  var adslot = slot.slotname;
  var loadset = slot.loadset;
  var slotobj = eo.slot;

  if(typeof(mps.adviewchangeCallback) === 'function') {
    try {
      mps.adviewchangeCallback(adslot, loadset, inviewpercentage, slotobj);
    } catch(err) {
      mps._errorCallback(err, 'mps.adviewchangeCallback');
    }
  }
  mps._queue.render('adviewchange', adslot, loadset, inviewpercentage, slotobj);
};

/**
 * mps._attachEoData => Create internal eo[slot]._mps
 * @param {object} eo
 * @param {number} loadset
 * @param {string} type
 * @return {object} _eodata
 * @private
 */
mps._attachEoData = function(eo, loadset, type){
  if(!eo || (typeof eo !== 'object' && typeof eo.slot !== 'object')){
    mps._debug('^[mps:GPT] _attachEoData invalid params');
    return false;
  }
  var _eodata = {},
      _slotid = mps._determineSlot(eo.slot.getSlotElementId()),
      _adslot = _slotid.slotname;
  _eodata._mps = {
    '_elapsed': mps._elapsed('', true),
    '_rendered': type === 'adrender' ? mps._elapsed('', true) : 0,
    '_refreshed': 0,
    '_clone': mps._bool(_slotid.cloneset),
    '_slot': _slotid.cleanslot,
    '_cloneslot': _slotid.slotname,
    '_targeting': eo.slot.getTargetingMap(),
    '_unit': (_adslot !== '_oop') ? mps._keys(mps.adunits, _adslot).toString() : 'outofpage',
    'adslot': mps._adslots[loadset][_adslot],
    'advar': mps._advars[loadset][_adslot],
    'gptid': eo.slot.getAdUnitPath(),
    'correlator': mps._correlator.get(),
    'loadset': loadset
  };
  return _eodata;
};

/**
 * mps.__defineAdSlot => GPT Slot Definitions (Unit-Level Targeting & Exclusions) w/ Responsive Map.
 * @param {string} mpsid
 * @param {object} slotobj
 * @private
 */
mps._defineAdSlot = function(mpsid, slotobj) {
  var _mpsid = mpsid;
  var _slotobj = slotobj;
  _slotobj.name = "outofpage"===_slotobj.name ? "_oop" : _slotobj.name.toLowerCase().replace(/\s+/g, '');
  if(_slotobj.name === "_oop" && _slotobj.gptid === null){
    _slotobj.gptid = mps.response.page.gpt_adid;
  }
  _slotobj.categoryexclusion=_slotobj.categoryexclusion||[];

  // Replace tokens of [[UNITNAME]] and [[SLOTNAME]]
  if(_slotobj.gptid) {
    _slotobj.gptid = _slotobj.gptid.replace('[[UNITNAME]]', _slotobj.name);
    _slotobj.gptid = _slotobj.gptid.replace('[[SLOTNAME]]', _slotobj.name);
  }
  // Define slot and OOP slot
  if (_slotobj.name !== '_oop') {
    gpt[_slotobj.advars] = gpt[_slotobj.advars] || googletag.defineSlot(mps._setAdId(_slotobj.gptid), _slotobj.sizes, _slotobj.id);
  } else {
    gpt[_slotobj.advars] = gpt[_slotobj.advars] || googletag.defineOutOfPageSlot(mps._setAdId(_slotobj.gptid), _slotobj.id);
  }

  // Set Collapse Empty Divs
  if (_slotobj.collapse === 0) {
    // 0 Collapse If Empty
    gpt[_slotobj.advars].setCollapseEmptyDiv(false);
  } else if (_slotobj.collapse === 1) {
    // 1 No Collapse
    gpt[_slotobj.advars].setCollapseEmptyDiv(true);
  } else if (_slotobj.collapse === 2) {
    // 2 Start Collapsed
    gpt[_slotobj.advars].setCollapseEmptyDiv(true, true);
  }

  //  Disabled Adunits by responsive set
  var rset = (typeof mps.getResponsiveSet === 'function') ? mps.getResponsiveSet() : 0,
      loadset = mps._loadset ? mps._loadset : 0,
      slotname = _slotobj.name;
  if(mps.responsiveslots && mps.responsiveslots[loadset] && mps.responsiveslots[loadset][slotname] && mps.responsiveslots[loadset][slotname][rset] && mps.responsiveslots[loadset][slotname][rset][0] === "NONE"){
    if(mps.slotsdisabled[loadset] && mps.slotsdisabled[loadset].indexOf(slotname) === -1) {
      mps.slotsdisabled[loadset].push(slotname);
    }
  }
  // slot name to targeting
  _slotobj.targeting["slot"] = slotname;

  // loadset number to targeting
  if(typeof loadset === 'number') {
    _slotobj.targeting["loadset"] = loadset.toString();
  }

  // Init Service
  if (_slotobj.advars && gpt[_slotobj.advars] != null) {
    gpt[_slotobj.advars].addService(googletag.pubads());
  }

  // Reset category exclusions
  if (mps._loadset === 0) {
    mps._resetcatexclusion[_slotobj.advars] = mps._resetcatexclusion[_slotobj.gptid] || [];
    mps._resetcatexclusion[_slotobj.advars].push('test');
  }

  // Collapse Map
  mps._collapsemap[_slotobj.name] = _slotobj.collapse;

  // Targeting (filter allowable keys)
  for (var k in _slotobj.targeting) {
    if(_slotobj.targeting.hasOwnProperty(k) && (k==="slot" || k==="loadset" || mps.response.dart.params.allowable_targeting_keys.length && mps.response.dart.params.allowable_targeting_keys.indexOf(k) > -1)) {
      var _targeting = (_slotobj.targeting[k] instanceof Array) ? _slotobj.targeting[k].sort() : _slotobj.targeting[k];
      gpt[_slotobj.advars].setTargeting(k, _targeting);
    }
  }

  // Apply category exclusions
  for (var l = 0; l < _slotobj.categoryexclusion.length; l += 1) {
    gpt[_slotobj.advars].setCategoryExclusion(_slotobj.categoryexclusion[l]);
  }

  // Define Responisve Size Mapping
  if(mps._keys(_slotobj.responsivemap).length) {
    mps.responsiveslots = mps.responsiveslots ||{};
    mps.responsiveslots[mps._loadset || 0] = mps.responsiveslots[mps._loadset || 0] ||{};
    mps.responsiveslots[mps._loadset][_slotobj.name] = _slotobj.responsivemap;
  }
  if(typeof mps._rsizemap[_mpsid] === 'object' && typeof mps._rsizemap[_mpsid][_slotobj.name] === 'object' && mps._keys(mps._rsizemap[_mpsid][_slotobj.name]).length > 0) {
    gpt[_slotobj.advars].defineSizeMapping(mps._rsizemap[_mpsid][_slotobj.name]);
  }

  // Populate MPS vars.
  mps.adslots[_slotobj.name] = _slotobj.id;
  mps.advars[_slotobj.name] = _slotobj.advars;

};

/**
 * mps._determineSlot => Returns object data to be used for callbacks
 * @param {string} slotid
 * @return {object} slotdata
 */
mps._determineSlot = function(slotid) {
  if(typeof slotid !== 'string'){
    return false;
  }
  var _loadset = (parseInt(slotid.split('-')[4]) > 0) ? parseInt(slotid.split('-')[4]) : 0;
  var _adslot = slotid.replace(mps.response && mps.response.dart.params.ad_div_prefix || 'div-gpt-', '').split('-');
  var _cleanslot = (_adslot[0] != 'outofpage') ? _adslot[0].toString() : '_oop';
  if (_adslot[2] && _adslot[2].indexOf('C') != -1) {
    var _dirtyslot = _cleanslot + '-' + _adslot[2];
  } else if (_adslot[3] && _adslot[3].indexOf('C') != -1) {
    var _dirtyslot = _cleanslot + '-' + _adslot[3];
  } else {
    var _dirtyslot = _cleanslot;
  }
  var _clonenum = (_dirtyslot != '' && _dirtyslot.indexOf('C') > -1) ? parseInt(_dirtyslot.split('C')[1], 10) : null;
  var _cloneset = (_clonenum != null) ? _clonenum : 0;
  return {
    slotname:  _dirtyslot, // topbanner or topbanner-C1
    cleanslot: _cleanslot, // topbanner
    cloneset:  _cloneset,  // number
    loadset:   _loadset,   // number
    clone:     _cloneset > 0 ? true : false
  };
};

/**
 * mps._determineDelay => returns _delay from ad render in ms
 * @param {object} slot
 * @return {number}
 */
mps._determineDelay = function(slot) {
  var _delay = 0;
  var _slot = mps._determineSlot(slot.getSlotElementId());
  var _adslot = _slot.slotname;
  var _loadset = _slot.loadset;
  var _refresh = (mps._adloads[_loadset] && mps._adloads[_loadset][_adslot] && mps._keys(mps._slotscalled[_loadset]).indexOf(_adslot) > -1 && mps._adloads[_loadset][_adslot]._mps._refreshed) ? 1 : 0;
  if (_refresh && mps._delays._adview['R' + _loadset] && mps._delays._adview['R' + _loadset][_adslot] && typeof(mps._delays._adview['R' + _loadset][_adslot][0]) === 'number') {
    var _rcount = mps._keys(mps._delays._adview['R' + _loadset][_adslot]).length;
    _delay = mps._delays._adview['R' + _loadset][_adslot][_rcount - 1];
  } else if (mps._delays._adview[_loadset] && mps._delays._adview[_loadset][_adslot] && typeof(mps._delays._adview[_loadset][_adslot]) === 'number') {
    _delay = mps._delays._adview[_loadset][_adslot];
  }
  return _delay;
};

/**
 * mps._execAd calls googletag.display, rendering ad, control for detected display
 * @param {string} slot
 * @param {nubmer} loadset
 * @param {number} clone
 * @param {boolean} detect
 * @return {boolean}
 */
mps._execAd = function(slot,loadset,clone,detect) {
  try {
    if(!slot){ return false; }
    clone =  clone || 0 ;
    if(slot.indexOf('-C') === -1){
      slot = slot.toLowerCase().replace(/\s+/g, '');
    }
    detect = detect || false;
    loadset = (parseInt(loadset)>-1) ? parseInt(loadset) : mps._loadset;
    if((!clone && !mps._adslots) || (!clone && !mps._adslots[loadset]) || (mps._kvinsert && !mps._kvinsert.status())) {
      mps._delays.execadready = mps._delays.execadready||250;
      if(mps._kvinsert && mps._kvinsert.status()) { mps._debug('[mps:GPT] DELAYING mps._execAd: adslot ('+slot+','+loadset+')'+mps._elapsed()); }
      if(mps._ext.dart_mode === 'gpt-asynchronous') {
        setTimeout(function() {
          mps._execAd(slot,loadset);
        }, mps._delays.execadready);
      }
      return false;
    }
    if(!clone && mps._slotscalled[loadset][slot]) {
      mps._debug('[mps:GPT] FAILED mps._execAd('+slot+','+loadset+','+clone+'): Already called on loadset.'+mps._elapsed());
      return false;
    }
    // topbanner-C1 or topbanner
    var slotvar = (typeof clone === 'number' && clone>0) ? (slot+'-C'+clone) : slot;
    var gptdiv = mps._adslots[loadset][slotvar] || false;
    var gptdom = document.getElementById(gptdiv);
    var islazyslot = (mps._detect && typeof mps._detect._pending === 'object' && mps.lazyload && mps.lazyload[loadset] && mps.lazyload[loadset].length && mps.lazyload[loadset].indexOf(slot) > -1) || false;
    var islazyclone = !!(mps.lazyloadclone && mps.lazyloadclone[loadset] && mps.lazyloadclone[loadset].length && mps.lazyloadclone[loadset].indexOf(slotvar) > -1);
    var isdetectelem = (loadset !== 0 || (mps._detect && mps._detect.detectionelement && mps._detect && mps._detect.detectionelement[slot] === true));
    var inviewport = mps.inViewport(gptdom, false);
    var oop = slot === '_oop';

    // Slot or element doesn't exist
    if(!slot || !mps.adslots || !gptdiv || !gptdom) {
      if(islazyslot && !oop) {
        mps._detect._pending.push({'slot': slotvar, 'loadset': loadset});
      }
      mps._debug('[mps:GPT] FAILED mps._execAd: '+ slot +', '+ !mps.adslots +', '+ !gptdiv +', '+ !(document.getElementById(gptdiv)));
      return false;
    }
    if((islazyslot || islazyclone) && !detect && (!isdetectelem || !inviewport)) {
      // All Ads push to detect pending
      if(!oop) {
        mps._detect._pending.push({ 'slot': slotvar, 'loadset': loadset });
      }
      // Cloned Ads, clear queue
      if(clone > 0 && (islazyclone || islazyslot)) {
        mps._clonerunning = false;
      }
      return false;
    }

    mps._slotscalled[loadset] = mps._slotscalled[loadset] || [];
    mps._slotscalled[loadset][slotvar] = gptdiv;
    if(mps.ab && typeof mps.ab._callback === 'function') {
      mps.ab._callback(slot, loadset);
    }
    if(mps._ext.dart_mode === 'gpt-asynchronous') {
      mps._gptcmd.push(function () {
        mps._delays.gptdisplay = mps._delays.gptdisplay || 0;
        if (!parseInt(mps._delays.gptdisplay)){
          mps._delays.gptdisplay = 0;
        }
        if (!mps.slotsdisabled[loadset] || (mps.slotsdisabled[loadset] && mps.slotsdisabled[loadset].indexOf(slotvar) === -1)) {
          setTimeout(function () {
            mps._debug('[mps:GPT] googletag.display ' + loadset + ':' + slot + ' ' + mps._elapsed());
            googletag.display(gptdiv);
            if(typeof mps._adexecuteCallback === 'function') {
              mps._adexecuteCallback(slotvar, loadset);
            }
            mps._queue.render('adexecute', slotvar, loadset);
          }, mps._delays.gptdisplay);
        } else {
          // Responsive Disabled for that slot
          mps._slotsdisabled[loadset] = mps._slotsdisabled[loadset] || [];
          mps._slotsdisabled[loadset][slotvar] = gptdiv;
          delete mps._slotscalled[loadset][slotvar];
          mps._classAdd(gptdom,'mps-gpt-hidden');
          if(mps._clonerunning) {
            mps._clonerunning=false;
          }
          mps._debug('[mps:GPT] SKIP googletag.display <'+loadset+':'+slotvar+'> Responsive Disabled '+mps._elapsed());
        }
      });
    } else{
      document.write('<scr' + 'ipt>' + mps._gptcmd.push(function() { googletag.display(gptdiv); }) + '</scr' + 'ipt>');
    }
    return true;
  } catch(err) {
    mps._errorCallback(err, 'mps._execAd');
    return false;
  }
};

/**
 * mps._execgpt => Define adunits, wrap in mps._gptcmd.push for async.
 * @private
 */
mps._execgpt = function() {
  // Define adslots with gpt.
  var _mpsid = mps.pagevars.mpsid;
  var _adslots = mps.response.dart.params.adunits;
  var _path = mps.pagevars.path;
  var _loadset = mps._loadset = mps._loadset || 0;
  mps.adobs = [];
  mps.adslots = {};
  mps.advars = {};
  mps._rsizemap = mps._rsizemap || {};
  mps._slotscalled[_loadset] = {};
  mps._gptTargeting[_loadset] = mps._gptTargeting[_loadset] || {};
  mps._resettargeting[_path] = mps._resettargeting[_path] || {};

  // Responsive Slots
  if (typeof mps.response.dart.params.responsive_sets === 'object' && typeof mps.getResponsiveSet === 'function') {
    mps._rset = mps.getResponsiveSet();
    mps.responsiveslots = mps.responsiveslots || {};
    mps.responsiveslots[_loadset] = {};
  }

  if (mps._loadset === 0 && mps.lazyload && mps.lazyload[0]) {
    mps._lazyloadmap = mps._clone(mps.lazyload[0]);
  }

  var _mpscall = typeof mpscall !== 'undefined' && typeof(mpscall.path) !== 'undefined';
  var _pagecontext = typeof(mps._loadset) === 'undefined' || mps._loadset === 0 || mps._pagecontextKey() === false;

  // Check if mpscall & page context exists.
  if(_mpscall && _pagecontext) {
    var _pagecontextlen = mps._keys(mps._pagecontext).length;
    var _pagecontextindex = (typeof(_pagecontextlen) === 'number' && _pagecontextlen > 0) ? _pagecontextlen : 0;
    var _pagecontext = mpscall.path;
    // New page context.
    mps._pagecontext[_pagecontextindex] = {
      mpscall: mps._clone(mpscall),
      loadsets: [mps._loadset],
      targeting: {},
      mpsid: _mpsid,
      adunits: mps._responseAdunits() ? mps.response.dart.params.adunits : null,
      gpt: {},
      prefix: mps._responseAdunits() ? mps.response.dart.params.ad_div_prefix : null
    };
    if(!mps._loadset) {
      mps._pagecontext[_pagecontextindex].pagevars = mps.response.pagevars;
    }
    for (var i in mps.advars) {
      if(gpt.length && typeof gpt[mps.advars[i]] === 'object') {
        mps._pagecontext[_pagecontextindex]['targeting'][i] = mps._resetTargetingObj(gpt[mps.advars[i]].getTargetingMap());
      }
    }
  }

  // Define ad units.
  for (var i in _adslots) {
    var _adslot = _adslots[i];

    // Update loadset in dart response.
    if (typeof(_adslots[i].adunit_slot_div) === 'string' && typeof(_adslots[i].html) === 'string') {
      if (typeof(mps._loadset) === 'number' && mps._loadset > 0 && _adslots[i].html.length > 0) {
        mps.response.dart.params.adunits[i].html = mps._updateAdCode(_adslots[i].html, i, _loadset, false);
      }

      // Get adslot sizes.
      var _adslotsizes = [];
      var _gptid = _adslot.ad_unit_gpt_ad_id;
      var _gptdiv = _adslot.adunit_slot_div;
      var _slotname = _adslot.adunit_slotname;
      var _gptadvars = _adslot.adunit_slot_var;
      _gptadvars = _gptadvars.split('.');
      _gptadvars = _gptadvars[1];
      // Ad unit sizes.
      if (_adslot.sizes) {
        for (var j = 0; j < _adslot.sizes.length; j += 1) {
          if (_adslot.sizes.length === 1) {
            // fluid size
            _adslotsizes.push(_adslot.sizes[j]);
          } else {
            // pixel dimensions
            _adslotsizes.push([_adslot.sizes[j][0], _adslot.sizes[j][1]]);
          }
        }
      }

      // Responsive mapping
      var _responsiveset = mps.response.dart.params.responsive_sets;
      if (i !== '_oop' && mps._keys(_adslot.responsive_map).length > 0 && mps._keys(_responsiveset).length > 0) {
        mps.responsiveslots = mps.responsiveslots || {};
        mps.responsiveslots[_loadset] = mps.responsiveslots[_loadset] || {};
        mps.responsiveslots[_loadset][i] = _adslot.responsive_map;
        var _responsivemap = {};
        var _rset = mps.getResponsiveSet();
        // Responsive Ad size map
        for (var k in _adslot.responsive_map) {
          if (_adslot.responsive_map[k].indexOf('NONE') === -1) {
            _responsivemap[k] = _adslot.responsive_map[k];
          } else if (_rset === k) {
            _responsivemap[k] = [];
            // Disable this ad for this size
            mps.slotsdisabled[_loadset] = mps.slotsdisabled[_loadset] || [];
            if(mps.slotsdisabled[_loadset].indexOf(k) === -1) {
              mps.slotsdisabled[_loadset].push(_slotname);
            }
          }
        }
        // Responsive Viewport breakpoints
        // https://goo.gl/V69Shk
        var _sizemap = googletag.sizeMapping();
        mps._keys(_responsiveset).forEach(function (set, index) {
          if ((_responsivemap.hasOwnProperty(set) && _responsivemap[set].length) || (_responsivemap.hasOwnProperty(set) && _responsivemap[set].length && _responsivemap.indexOf('fluid') > -1 )) {
            _sizemap.addSize(_responsiveset[set], _responsivemap[set]);
          }
        });
        mps._rsizemap = mps._rsizemap || {};
        mps._rsizemap[_mpsid] = mps._rsizemap[_mpsid] || {};
        mps._rsizemap[_mpsid][i] = _sizemap.build();
        mps._resetrsizemap = mps._clone(mps._rsizemap[_mpsid]);
      }

      mps._gptTargeting[mps._loadset][_adslot.adunit_slot_var] = {
        sizes: _adslotsizes,
        gptid: _gptid,
        gptdiv: _gptdiv
      };

      if (mps._keys(_adslot.responsive_map).length > 0) {
        mps._gptTargeting[mps._loadset][_adslot.adunit_slot_var].responsivemap = _adslot.responsive_map;
      }
      var slot = i.toLowerCase().replace(/\s+/g, '');
      var slotparams = {
        'name': slot,
        'loadset': mps._loadset,
        'gptid': _gptid,
        'advars': _gptadvars,
        'sizes': _adslotsizes,
        'id': _gptdiv,
        'targeting': _adslot.targeting,
        'categoryexclusion': _adslot.category_exclusions,
        'collapse': _adslot.collapse,
        'responsivemap': _adslot.responsive_map
      };
      mps._defineAdSlot(_mpsid, slotparams);

      if (_mpscall && _pagecontext) {
        mps._pagecontext[_pagecontextindex].targeting[slot] = _adslot.targeting;
      }
    }
  }

  if(_mpscall && _pagecontext) {
    mps._pagecontext[_pagecontextindex].gpt = mps._clone(mps._gptTargeting[mps._loadset]);
  }

  // Slot Render Event
  if(mps._loadset === 0) {
    googletag.pubads().addEventListener('slotRenderEnded',function(eo){
      if(typeof(mps._adloadCallback)=='function') {
        mps._gptcmd.push( function() {
          mps._adloadCallback(eo, mps._loadset);
        });
      }
    });

    // Slot Loaded (Creative)
    googletag.pubads().addEventListener('slotOnload',function(eo){
      if(typeof(mps._adrenderCallback)=='function') {
        mps._gptcmd.push( function() {
          setTimeout(function(){
            mps._adrenderCallback(eo);
          }, 0);
        });
      }
    });

    // Ad Impression View.
    googletag.pubads().addEventListener('impressionViewable',function(eo){
      if(typeof(mps._adViewCallback)=='function') {
        var  slotobj = mps._determineSlot(eo.slot.getSlotElementId());
        mps._debug('[mps:GPT] ADVIEW '+ slotobj.loadset +':' +slotobj.slotname+ ' delayed ' +mps._determineDelay(eo.slot)+'ms');
        mps._gptcmd.push( function() {
          setTimeout(function(){
            mps._adViewCallback(eo);
          }, mps._determineDelay(eo.slot))
        });
      }
    });

    // Ad Visiblity Change
    googletag.pubads().addEventListener('slotVisibilityChanged',function(eo){
      if(typeof(mps._adviewchangeCallback)=='function') {
        mps._gptcmd.push( function() {
          mps._adviewchangeCallback(eo);
        });
      }
    });

  }

  // QS Targeting i.e.(&adtest=foobar)
  if(typeof(mps._dtparamsappend)=='string' && mps._dtparamsappend.length > 0) {
    mps._dtparamsappend = mps._trim(mps._dtparamsappend,' ;')+';'.replace(';;',';');
    var __dtp = mps._trim(mps._dtparamsappend,'; ').split(';');
    var i_param = 0;
    while (__dtp[i_param]){
      dk = __dtp[i_param];
      var dtparr = dk.split('=');
      if(dtparr.length===2 && dtparr[0].length>0 && dtparr[1].length>0) {
        mps._setPageTargeting(dtparr[0], dtparr[1]);
      }
      i_param++;
    }
  }

  // Pixelman Page Targeting
  if (typeof(__nbcudigitaladops_inject) === 'object' && __nbcudigitaladops_inject.getGPT) {
    mps._debug('[mps:GPT] PIXELMAN: set targeting');
    var _GPT_params = __nbcudigitaladops_inject.getGPT();
    for(var _key in _GPT_params){
      if(_GPT_params.hasOwnProperty(_key)){
        mps._setPageTargeting(_key, _GPT_params[_key]);
      }
    }
  }

  // Asynchronous Rendering Call
  if(mps._ext.dart_mode === 'gpt-asynchronous'){
    googletag.pubads().enableAsyncRendering();
    // Synchronous Rendering Call
  }else{
    googletag.pubads().enableSyncRendering();
  }

  // Disable Inital Load
  if((mps._bool(mps.response.dart.params.disable_initial_load) && !mps._bool(mpsopts.skipdisableinitialload))) {
    googletag.pubads().disableInitialLoad();
  }

  // Consent Management Platform
  // Vendor: OneTrust, validate 'npa=4' param in Google call
  if(typeof OptanonActiveGroups !== 'undefined'){
    mps._debug("[mps:GPT] OptanonActiveGroups loaded");
    if(OptanonActiveGroups.match(/,4,/)){
      googletag.pubads().setRequestNonPersonalizedAds(0);
      mps._debug("[mps:GPT] OptanonActiveGroups personalized ads (,4,)");
    }
    else{
      googletag.pubads().setRequestNonPersonalizedAds(1);
      mps._debug("[mps:GPT] OptanonActiveGroups set to non-personalized ads");
    }
  }
  else{
    mps._debug("[mps:GPT] OptanonActiveGroups not loaded");
  }

  // Enable Single-Request Mode
  if(mps.response.dart.params.single_request_mode === 1){
    googletag.pubads().enableSingleRequest();
  }

  googletag.enableServices();

  mps._adslots[mps._loadset] = mps.adslots;
  mps._advars[mps._loadset] = mps.advars;
  mps._advarprefix = mps.response.dart.params.ad_slot_var_prefix;

  if(typeof mpscall !== 'undefined' && typeof(mpscall.path) !== 'undefined') {
    mps._gptcmd.push(function () {
      for (var i in mps.advars) {
        if(gpt.length && typeof gpt[mps.advars[i]] === 'object') {
          mps._resettargeting[mpscall.path][i] = mps._resetTargetingObj(gpt[mps.advars[i]].getTargetingMap());
        }
      }
    });
  }

  while(mps._queue.getad.length) {
    mps._queue.getad.shift().call();
  }

  mps._gptloadCallback();

};

/**
 * mps._execgptinit initializes gpt.js
 * @private
 */
mps._execgptinit = function() {
  // Execute gpt init.js
  if (typeof(mps.response.dart.params.gpt_init_js) === 'string' && mps.response.dart.params.gpt_init_js.length > 0) {
    var _gptinit = '<scri' + 'pt>' + mps.response.dart.params.gpt_init_js + '<\/scr' + 'ipt>';
    try {
      if (mps._bool(mps._ext._jq) === true) {
        jQuery('head').append(_gptinit);
      } else {
        mps._append(mps._select('head'), _gptinit);
      }
    } catch (err) {
      mps._errorCallback(err, "gpt_init_js");
    }
  }
};

/**
 * mps._gptloadCallback after gpt library and API is ready
 * Also handles the popular *gptloaded* queue
 * @return {none}
 */
mps._gptloadCallback = function(){
  if ((mps._loadset === 'undefined' || mps._loadset === 0) && mps._reqs){
    mps._reqs[0] = mps._reqs[0] || {};
    mps._reqs[0]['gptready'] = mps._elapsed('',true);
  }
  for(avk in mps.advars) {
    if(typeof(mps.advars[avk]) === 'string' && typeof(gpt[mps.advars[avk]]) === 'object') mps.adobs.push(gpt[mps.advars[avk]]);
  }
  mps._adobs[mps._loadset||0] = mps.adobs;
  mps._gptloaded = true;
  mps._gptrefresh = true;
  if(typeof(mps._cloneObjects) === 'function') {
    mps._cloneObjects();
  }
  // mps._queue.gptloaded functions queued by loadset are pushed to googletag.cmd.
  if(mps._queue.gptloadset[mps._loadset]) {
    while(mps._queue.gptloadset[mps._loadset].length) {
      mps._gptcmd.push(mps._queue.gptloadset[mps._loadset][0]);
      mps._queue.gptloadset[mps._loadset].shift();
    }
  }
  if(!mps._queue.gptloadset[mps._loadset]) {
    mps._queue.gptloadset[mps._loadset] = [];
  }
  if(typeof(mps.gptloadCallback) === 'function') {
    try {
      mps.gptloadCallback();
    } catch(err) {
      mps._errorCallback(err, 'mps.gptloadCallback');
    }
  }
  if(mps._queue.mpsloaded.length) {
    mps._queue.mpsloaded.shift().call();
  }
  mps._queue.render('gptloaded', mps._loadset);
};

/**
 * mps._setAdId => used to modify gptadid in g.definedSlot().
 * @param gptadid
 * @return {string} gptadid
 */
mps._setAdId = function(gptadid){
  if(typeof mps.transformAdId === 'function' && gptadid) {
    var modgptadid = mps.transformAdId(gptadid).toString();
    mps._debug('[mps:GPT] OVERRIDE gptid: '+modgptadid);
    return modgptadid;
  }else{
    return gptadid;
  }
};

// Load GPT Library
(function() {
  mps.loadGPT();
})();







/* js/core/pre-include-autoloader.js */

/*--------------------------------------
 [mps:EXT] Client-Side MPS Load + Execute
 --------------------------------------*/

//--> SCRIPT INIT
var mps = mps||{}, gpt=gpt||{}, debugmode=debugmode||{}, mpscall=mpscall||{}, mpsopts=mpsopts||{}, mpsinstance=mpsinstance||false;
mps._ext = mps._ext || {};
mps._ext._p = {};
mps._ext.loaded = 0;
mps._ext.loadhead = 0;
mps._ext.loadheader = 0;
mps._ext.loadfooter = 0;
mps._ext._jq = typeof(jQuery) === 'function' ? 1 : 0;
mps._ext._insertedads = mps._ext._insertedads || {};
mpsopts.callback = mpsopts.callback || 'mpsCallback';
mpsopts.catprefix = mpsopts.catprefix || '';
mpsopts.deriveparams = mpsopts.deriveparams || {1:'cat1',2:'cat2',3:'cat3',4:'cat4',5:'cat5',6:'cat6'};
mpsopts.deriveoff = !!mpsopts.deriveoff;
mpsopts.maxcats = mpsopts.maxcats || 6;
mpsopts.updatecorrelator = (typeof mpsopts.updatecorrelator !== 'undefined')? mpsopts.updatecorrelator : 1;
mpsopts.maxpathsegs = mpsopts.maxpathsegs || 4;
mpsopts.subset = mpsopts.subset || mpsopts.subset || false;
mpsopts.skipheader = (typeof(mpsopts.skipheader)==='undefined'||mpsopts.skipheader!=1) ? 0 : 1;
mpsopts.legacyqueues=(typeof(mpsopts.legacyqueues)==='undefined') ? 1 : mpsopts.legacyqueues;
mpsopts.forcenetcalls = mpsopts.forcenetcalls || false;
mpsopts.skipautorequest = (typeof(mpsopts.skipautorequest)==='undefined' || mpsopts.skipautorequest===0 || !mps._bool(mpsopts.skipautorequest)) ? 0 : 1;
mpsopts.skipdisableinitialload = typeof(mpsopts.skipdisableinitialload)==='undefined' || mpsopts.skipdisableinitialload===0 || !mps._bool(mpsopts.skipdisableinitialload) ?  0 : 1;
mpsopts.detection_above_the_fold = mpsopts.detection_above_the_fold || 0;
mpsopts.loadgptfirst=mpsopts.loadgptfirst||1;
mps._ext._set = mps._ext._set || -1;
mps._reqs = mps._reqs || {};
mps._clonevars = mps._clonevars || {};
mps._ext._ = mps._loadset || 0;
mps._reqset = mps._reqset || 0;
mps._gptloaded=false;
mps.adobs=[];
mps._delays = mps._delays || {};
mps.lazyloadclone=mps.lazyloadclone||{};
mps._adsheld2=mps._adsheld2||[]; // tracking queued ads (before gpt ready)
mpscall_original = mpscall;
mps._elapsed(); // Begin execution timer

//--> SET REQUEST VARS & OPTS
mps._debug(($dM=(new Array(8).join('*')))+' [mps] Debug Mode: ('+debugmode.log+') '+$dM);

if(mps._ext.IRSOURCE) {
  mpsinstance=mps._backendhost;
} else if (typeof(mpsopts.host) === 'string' && mpsopts.host.length>0) {
  mpsinstance=mpsopts.host;
} else if (typeof(mpsinstance)!='string' || mpsinstance=='') {
  mpsinstance=mps._backendhost;
}

/**
 * Returns the formatted mpscall object
 * @param {object}  mpscall
 * @return {object} mpscall
 */
mps._ext.mpsRequestParams = function(mpscall) {
mps._debug('[mps:preLoader] mpsRequestParams()');
  //(paths) mps._ext._pathsegs
  sitepath = mpscall.path || window.location.pathname;
  if(sitepath!='' && sitepath!='/' && sitepath.indexOf('/') > -1) {
    if(sitepath.substr(-1)=='/') sitepath=sitepath.substr(0, sitepath.length-1);
    if(sitepath.substr(0,1)=='/') sitepath=sitepath.substr(1,sitepath.length-1);
    sitepatharr = sitepath.split('/');
    mps._ext._pathsegs=[];
    var cleanpatharr=[],cutpatharr=[];
    for (var i=0; i<sitepatharr.length; i++) {
      mps._ext._pathsegs[i+1] = sitepatharr[i];
      if(i < mpsopts.maxpathsegs) {
        cleanpatharr[i+1]= sitepatharr[i];
      } else {
        cutpatharr[i+1] = sitepatharr[i];
      }
    }
    cleanpath = cleanpatharr.join('/');
    mpscall.path = cleanpath;
  } else {
    mps._ext._pathsegs = (sitepath!='/' && sitepath!='') ? [undefined,sitepath] : [undefined];
    mpscall.path = sitepath;
  }
  var qs = window.location.search.substring(1).split('&'),qsv;
  mps._ext._qsparams={};
  for(var i=0; i<qs.length; i++){
    qsv = qs[i].split('=');
    if(typeof(qsv[1])!='undefined') mps._ext._qsparams[qsv[0]] = qsv[1];
  }
  return mpscall;
};

mps._ext.mpsDeriveParams = function() {
  derived={};
  if(mpsopts.deriveoff) return derived;
mps._debug('[mps:preLoader] EXECUTE mpsDeriveParams()');

  // Extract mpscall params using format defined in mpsopts.deriveparams
  if(typeof(mpsopts.deriveparams)=='object') {
    var catkeys=['cat1','cat2','cat3','cat4','cat5','cat6'], catstring='';
    for(var k in mpsopts.deriveparams) {
      if(isNaN(k)) { //qs
        if(typeof(mps._ext._qsparams[k])=='string') derived[mpsopts.deriveparams[k]] = mps._ext._qsparams[k];
      } else { //url
        if(typeof(mps._ext._pathsegs[k])=='string') derived[mpsopts.deriveparams[k]] = mps._ext._pathsegs[k];
      }
    }
    for (var i=0; i<catkeys.length; i++) {
      if(typeof(derived[catkeys[i]])=='string') {
        catstring+=derived[catkeys[i]].replace('|','~');
        delete(derived[catkeys[i]]);
      }
      catstring+='|';
    }
    derived.cat = mps._trim(catstring,'| ').replace('||','|~|');
  mps._debug('[mps:preLoader] (derived params) '+JSON.stringify(derived));
  }
  return derived;
};

/**
 * Returns the formatted query string
 * @param {object}  mpscall
 * @return {string} mpscallenc
 */
mps._ext.mpsQueryString = function(mpscall) {
  if(typeof(mpscall)!='object') return '';
  var mpscallenc='';
  for(var key in mpscall) {
    if(typeof(mpscall[key])=='object') {
      for(var keyk in mpscall[key]) {
        mpscall[key+'['+keyk+']'] = mpscall[key][keyk];
        //remove nulls, undefined, empty
        if(mpscall[key][keyk] == 'undefined' || mpscall[key][keyk] == '' || mpscall[key][keyk] == null){
          delete mpscall[key+'['+keyk+']'];
          mps._debug('^[mps:preLoader] Removed mpscall:'+key+'['+keyk+'], is empty.');
        } else {
        }
      }
      delete mpscall[key];
    }
  }
  for (var k in mpscall) {
    if(typeof(mpscall[k])!='undefined' && mpscall[k] !== '' ) {
      // Truncate really long strings at 250 chars
      if(typeof(mpscall[k]==='string') && mpscall.length > 0) mpscall[k]=mps._trim(mpscall[k].substring(0,250));
      mpscallenc+=encodeURIComponent(k)+'='+encodeURIComponent(mpscall[k]) + '&';
    }
  }
  if(mpscallenc.substr(-1)=='&') mpscallenc = mpscallenc.substr(0, mpscallenc.length - 1);
  return mpscallenc;
};

/**
 * Returns the formatted RequestUrl string
 * @param {string}  LOADMODE
 * @return {string} mps.requesturl
 */
mps._ext.mpsRequestUrl = function(LOADMODE) {
  if(typeof(mpscall)!='object') return '';
  mpscall.LOADMODE = LOADMODE = typeof LOADMODE != 'undefined' ? LOADMODE : '';
  mpscall.NOLOAD='mpstools';
  mpscall.USE_OVERLAY = mps._overlayenabled ? 1 : 0;
  mpscall.IRSOURCE = typeof mps._ext.IRSOURCE != 'undefined' ? mps._ext.IRSOURCE : '';
  if(mps._ext.nowrite > 0 || mps._bool(mpsopts.skipautorequest) || mpscall.LOADMODE.toLowerCase() === 'more') {
    mpscall.ASYNC=1;
    mps._ext._async=1;
    mps._ext.datatype="json";
  }else{
    mps._ext.datatype="jsonp";
  }
  mps.qs = mps._ext.mpsQueryString(mpscall);
  var subset = (typeof(mpsopts.subset)=='string' && mpsopts.subset.length>0) ? '/'+mpsopts.subset : '';
  mps.requesturl = mpsinstance + '/request/page/'+mps._ext.datatype+'/params/'+subset+'?CALLBACK=' + mpsopts.callback + '&'+ mps.qs;
  mps._debug('[mps:preLoader] mpsRequestUrl('+LOADMODE+'): '+mps.requesturl);
  return mps.requesturl;
};

/**
 * mpsOnReady - returns if mps is ready
 * @param {boolean}  usejq
 */
mps._ext.mpsOnReady = function(usejq) {
  mps._debug("^[mps:preLoader] CALLED mpsOnReady() NOWRITE:"+ mps._ext.nowrite);
  if(mps._ext && mps._ext.nowrite!=1 && mps._ext.loaded === 1 && mps._ext.loadfooter === 0) {
    if(mps._bool(usejq)) {
    mps._debug('[mps:preLoader] No Footer Detected - Append Footer (jquery) NOWRITE:'+ mps._ext.nowrite);
      jQuery('body').append(mps.response.pagevars.insert_bodyfooter);
    } else {
      mps._append(mps._select('body'),mps.response.pagevars.insert_bodyfooter);
    mps._debug('[mps:preLoader] No Footer Detected - Append Footer (non-jquery) NOWRITE:'+ mps._ext.nowrite);
    }
    mps._ext.loadfooter=1;
  }
};

/**
 * Injects bodyheader html
 * @param {boolean}  jq
 */
mps.executeBodyheader = function(jq) {
  mps._debug('[mps:preLoader] body defined, execute bodyheader inserts.' + mps._elapsed(true));
  if(jq === true) {
    jQuery('body').prepend(mps.response.pagevars.insert_bodyheader);
  } else {
    mps._append(mps._select('body'),mps.response.pagevars.insert_bodyheader);
  }
  mps._ext.loadheader = 1;
  return true;
};

/**
 * Initializes bodyheader html
 * @param {boolean}  jq
 */
mps.intBodyheader = function(jq) {
  mps._debug('[mps:preLoader] body not defined, set listener.' + mps._elapsed(true));
  mps._ext.loadfooter = 1;
  var _jq = mps._bool(jq);
  var _reqanimation = typeof(window.requestAnimationFrame) === 'function';
  var _body = function() {
    return _jq === true ? jQuery('body').length : mps._select('body');
  };
  var _exec = function(body) {
    if(body && _body()) {
      mps.executeBodyheader(_jq);
      mps._ext.loadfooter = 0;
      mps._ext._async = true;
      mps.writeFooter();
      return false;
    } else {
      if(_reqanimation === true) {
        window.requestAnimationFrame(_exec);
      }
    }
  };
  if(_reqanimation === true) {
    _exec();
  } else {
    var _time = 0;
    var _int = setInterval(function() {
      if(_time <= mps._delays.bodyheader) {
        if(_body()) {
          _exec(true);
          clearInterval(_int);
        }
      } else {
        clearInterval(_int);
      }
      _time += mps._delays.bodyheaderint;
    }, mps._delays.bodyheaderint);
  }
};

// mps.executeInserts (insert_head, insert_bodyheader)
// Autoloader: If(async) mps.__intcode=2 else(document.write)
mps.executeInserts = function() {
  if(typeof(mps)!='object' || typeof(mps.response)!='object') {
    mps._debug('^[mps:preLoader] Failed executeInserts(): No MPS Response');
    return false;
  }
  var _jq = typeof(jQuery) === 'function';
  if(mps._ext.nowrite > 0 && !mps.__intcode && !mpsopts.skipautorequest) {
    _jq === true ? jQuery('body').append(mps.response.pagevars.insert_head) : mps._append(mps._select('head'), mps.response.pagevars.insert_head);
    mps._ext.loadhead = 1;
    if(mpsopts.skipheader != 1) {
      if((!mps._select('body') && !mps.__intcode) || mps._ext.mpsready === true || typeof mps._postscribe !== 'function') {
        mps.intBodyheader(_jq);
      } else {
        document.write(mps.response.pagevars.insert_bodyheader);
      }
      mps._ext.loadheader = 1;
    }
    return true;
  } else {
    if(_jq === false) {
      mps._debug('[mps:preLoader] executeInserts (non-jquery)');
      mps._append(mps._select('head'),mps.response.pagevars.insert_head);
      mps._ext.loadhead = 1;
      if(mps._select('body')) {
        mps.executeBodyheader(false);
      } else {
        mps.intBodyheader(false);
      }
    } else {
      mps._debug('[mps:preLoader] executeInserts (jquery)');
      jQuery('head').append(mps.response.pagevars.insert_head);
      mps._ext.loadhead = 1;
      if(jQuery('body').length) {
        mps.executeBodyheader(true);
      } else {
        mps.intBodyheader(true);
      }
    }
    return true;
  }
};

//--> JSONP CALLBACK
var mpsCallback = function(data, update) {
mps._debug('[mps:preLoader] JSONP Callback Execution, Update:'+!!update+' '+mps._elapsed());
  if(typeof(data) === 'object' && typeof(data.pagevars) !== 'undefined' && typeof(data.pagevars.insert_head) !== 'undefined') {
    mps.response = data;
    mps.adslothtml = {};
    if(typeof(mps)=='object' && typeof(mps.response)=='object' && typeof(mps.response.dart)=='object' && typeof(mps.response.dart.params)=='object' && typeof(mps.response.dart.params.adunits)=='object') {
      for(var adunit in mps.response.dart.params.adunits) {
        // .data needed for backward compatibility
        mps.response.dart.adunits = mps.response.dart.adunits || {};
        mps.response.dart.adunits[adunit] = mps.response.dart.adunits[adunit] || {};
        mps.adslothtml[adunit] = mps.response.dart.adunits[adunit].data = mps.response.dart.params.adunits[adunit].html;
      }
    }
    mps._ext.loaded = 1;
    mps.executeInserts();
    //--> DOCUMENT READY EVENT HOOK
    if(typeof(jQuery)!=='function') {
    mps._debug('[mps:preLoader] NO JQUERY (using native js)');
      mps._ready(function(){
        mps._ext.mpsOnReady(false);
      });
    } else {
    mps._debug('[mps:preLoader] JQUERY AVAILABLE');
      jQuery().ready(function() {
        mps._ext.mpsOnReady(true);
      });
    }
    if(!update) {
      if(!mps._loadset) {
        mps._queue.render('mpsready');
      }
      mps._queue.render('mpsinit');
      if(typeof(mps.initCallback) === 'function') {
        try {
          mps.initCallback();
        } catch(err) {
          mps._errorCallback(err, 'mps.initCallback');
        }
      }
    }
  }
};

/**
 * Determines Slot object
 * @param {string}  adslot
 * @param {number}  loadset
 * @return {object}
 */
mps._ext.determineSlot = function(adunit) {
  if(typeof(adunit)=='string' && typeof(mps)=='object' && typeof(mps.adunits)=='object' && typeof(mps.response)=='object' && typeof(mps.response.dart)=='object' && typeof(mps.response.dart.params.adunits)=='object') {
    if(typeof(mps.response.dart.params.adunits[adunit])=='object' && typeof(mps.response.dart.params.adunits[adunit].html)!='undefined' && mps.response.dart.params.adunits[adunit].html!='') {
      return adunit;
    }
    // Determine whether to use slot name or regular name
    if(typeof(mps.adunits[adunit])=='string') {
      if(typeof(mps.response.dart.params.adunits[mps.adunits[adunit]]) =='object' && typeof(mps.response.dart.params.adunits[mps.adunits[adunit]].html)!='undefined' && mps.response.dart.params.adunits[mps.adunits[adunit]].html!='') {
        return mps.adunits[adunit];
      }
      // Get other ad units that have same slot
      for(var i in mps.adunits) {
        if(mps.adunits[i] == mps.adunits[adunit]) {
          if(typeof(mps.response.dart.params.adunits[i]) == 'object' && typeof(mps.response.dart.params.adunits[i].html) != 'undefined' && mps.response.dart.params.adunits[i].html != '') {
            return i;
          }
        }
      }
    }
  }
  return adunit;
};

/**
 * Replicates inserted Ad data, used for mps.cloneAd
 * @param {string}  adslot
 * @param {number}  loadset
 * @return {object}
 */
mps._replicateAd = function (adslot,loadset) {
  if(adslot.length>0 && typeof adslot == 'string'){
    loadset = (!isNaN(loadset) && loadset <= mps._keys(mps._adloads).length) ? parseInt(loadset,10) : mps._loadset;
    if(gpt && mps._advars && mps._advars[loadset] && mps._advars[loadset][adslot]){
      mps._clonevars[loadset]=mps._clonevars[loadset]||{};
      mps._clonevars[loadset][adslot] = mps._clonevars[loadset][adslot] || '';
      var count = (mps._clonevars[loadset][adslot].length > 0 && parseInt(mps._clonevars[loadset][adslot].split('_C')[1], 10) > 0) ? parseInt(mps._clonevars[loadset][adslot].split('_C')[1],10)+1 : 1;
      mps._clonevars[loadset][adslot] = mps._advars[loadset][adslot]+'_C'+count;
      mps._debug('[mps:preLoader] _replicateAd: gpt.'+mps._clonevars[loadset][adslot]);
      mps.advars[adslot+'-C'+ count] = mps._advars[loadset][adslot+'-C'+ count] =  mps._advars[loadset][adslot]+ '_C' +count;      // create var name
      mps._adslots[loadset][adslot +'-C'+ count] =  mps._adslots[loadset][adslot]+ '-C' +count;   // create slot name
      gpt[mps._clonevars[loadset][adslot]] = gpt[mps._advars[loadset][adslot]];                   // clone object
      return gpt[mps._clonevars[loadset][adslot]];
    } else {
      //_replicateAd SKIPPED: Slot Disabled
      return false;
    }
  }else{
  mps._debug('[mps:preLoader] _replicateAd invalid parameters');
    return false;
  }
};

/**
 * Legacy ad injection, replaced by mps.insertAd
 * @param {string}   adunit
 * @param {boolean}  _swap //TODO: deprecate
 * @param {number}  loadset
 * @return {string} adslothtml
 */
mps.getAd = function(adunit, _swap, loadset) {
  try {
    var adunit = mps._ext.determineSlot(adunit);
    var _slotid = 'mps-getad-' + adunit.toLowerCase().replace(/\s+/g, '');
    var adslothtml = '<div id="' + _slotid + '" class="mps-wrapper" data-mps-fill-slot="' + _slotid + '"></div>';

    if (_swap) {
      for (var adunitname in mps.adunits) {
        if (adunit == mps.adunits[adunitname]) {
          adunit = adunitname;
          break;
        } else if (mps.adunits.hasOwnProperty(adunit)) {
          adunit = mps.adunits[adunit];
          break;
        }
      }
    }

    if (typeof(adunit) != 'undefined' && typeof(mps) === 'object' && typeof(mps.response) === 'object' && typeof(mps.response.dart) === 'object' && typeof(mps.response.dart.adunits) === 'object' && typeof(mps.response.dart.adunits[adunit]) === 'object' && typeof(mps.response.dart.adunits[adunit].data) !== 'undefined') {
      var ls = typeof(loadset) === 'number' ? parseInt(loadset, 10) : mps._loadset;
      mps._ext._insertedads[ls] = mps._ext._insertedads[ls] || [];
      var adunitlower = adunit.toLowerCase().replace(/\s+/g, '');
      for (var unit in mps.adunits) {
        if (mps.adunits.hasOwnProperty(unit) && mps.adunits[unit] === adunitlower && mps._ext._insertedads[ls].indexOf(adunitlower) == -1) {
          mps._ext._insertedads[ls].push(adunitlower);
        }
      }

      if (mps._keys(mps.response.dart.adunits).indexOf(adunit) === -1 || mps.response.dart.adunits[adunit].data !== '') {
        // .data needed for backward compatibility
        adslothtml = mps.response.dart.adunits[adunit].data = mps.response.dart.params.adunits[adunit].html;

        // outofpage
        if (mps.response.dart.params.use_out_of_page_slot == adunit && mps.response.dart.params.adunits._oop && mps.response.dart.params.adunits._oop.html !== '') {
          adslothtml += mps.response.dart.params.adunits._oop.html;
        }
        if (typeof mps._ext == 'object' && typeof mps._reqs == 'object') {
          mps._reqs[ls] = mps._reqs[ls] || {};
          mps._reqs[ls]['begin_' + adunit] = mps._elapsed('', true);
        }
      } else {
        mps._debug("^[mps:preLoader] mps.getAd(" + adunit + ") SKIPPED: Disabled " + mps._elapsed());
        adslothtml = '<!--(mps.getAd) ' + adunit + ' disabled-->';
      }
    } else {
      if (_swap) {
        if (mps.response && mps.response.dart &&  mps.response.dart.adunits && mps._keys(mps.response.dart.adunits).indexOf(adunit) === -1) {
          mps._debug("^[mps:preLoader] mps.getAd(" + adunit + ") SKIPPED: Disabled " + mps._elapsed());
        }
        if (!mps._ext.loaded) {
          mps._queue.gptloaded.push(function() {
            mps.insertAd("#" + _slotid, adunit);
          });
          mps._adsheld2.push(adunit);
        }
        return adslothtml;
      } else {
        return mps.getAd(adunit, true);
      }
    }
    return adslothtml;
  } catch (err) {
    mps._errorCallback(err, 'mps.getAd');
    return false;
  }
};


/**
 * Takes a component id and returns data as a string (html, js css)
 * @param {string}  sid
 * @return {string} componentdata
 */
mps.getComponent = function(sid) {
  componentdata='';
  if(typeof(sid)!='undefined' && sid !='' && typeof(mps)=='object' && typeof(mps.response)=='object' && typeof(mps.response.components)=='object' && typeof(mps.response.components[sid])=='object' && typeof(mps.response.components[sid].data)!='undefined') {
  mps._debug('[mps:preLoader] mps.getComponent() LOAD: '+sid);
    if(mps.response.components[sid].data != '') {
      componentdata = mps.response.components[sid].data;
    }
  } else {
  mps._debug('[mps:preLoader] mps.getComponent() SKIP: '+sid);
  }
  return componentdata;
};

/**
 * Takes targeting strings and returns a map
 * @param {string}  target
 * @return {array}  targetingArray
 */
mps.targetingArray = function(target) {
  if(typeof(target)=='string'&&target.length) {
    var targetingArray = [],_tmpArr = [],map={},_str = target.split(';');
    for(var i=0;i<_str.length;i++) {
      if(_str[i].indexOf('=') > -1) {
        _kv = _str[i].split('=');
        _tmpArr.push(_kv);
      }
    }
    for(var i=0; i<_tmpArr.length; i++) {
      if(_tmpArr[i][0] in map) {
        map[_tmpArr[i][0]].push(_tmpArr[i][1]);
      } else {
        map[_tmpArr[i][0]] = [_tmpArr[i][1]];
      }
    }
    for(var k in map) {
      if(map[k].length > 1) {
	      targetingArray.push([k,map[k]]);
      } else {
	      targetingArray.push([k,map[k][0]]);
      }
    }
    return targetingArray;
  }
  return false;
};

/**
 * Prepends Defaults targeting, if override=true doesn't append
 * @param {object}  targeting
 * @param {string}  adslot
 * @param {boolean} override
 * @return {string} _currentTargeting
 */
mps.prependDefaultTargeting = function(targeting, adslot, override) {
  try {
    override=override||false;
    var _pagecontextKey = mps._pagecontextKey();
    if(_pagecontextKey === false)  { return false; }
    var _currentTargeting = typeof(mps._pagecontext[_pagecontextKey]['targeting'][adslot]) === 'object' ? mps._clone(mps._pagecontext[_pagecontextKey]['targeting'][adslot]) : {};
    if(!_currentTargeting || mps._keys(_currentTargeting).length === 0) {
      mps._debug('^[mps:preLoader] setTargeting('+adslot+') SKIPPED: Disabled');
      return false;
    }
    var _currTargetingObj = [];
    var _currentTargetingKeys = mps._keys(_currentTargeting);
    // Merge existing objects.
    for(var i in targeting) {
      // Merge param.
      if(typeof targeting[i] !== 'function' && typeof targeting[i] !== 'undefined' && targeting[i] != null) {
        if(_currentTargetingKeys.indexOf(targeting[i][0]) > -1 && !override) {
          var tmpArr = [];
          _currTargetingObj.push(_currentTargeting[targeting[i][0]]);
          if(typeof targeting[i][1] === 'string') {
            tmpArr = [targeting[i][1]];
          } else {
            tmpArr = targeting[i][1];
          }
          for(var j=0; j<_currTargetingObj.length;j++) {
            if(tmpArr.indexOf(_currTargetingObj[j]) === -1) {
              tmpArr.push(_currTargetingObj[j]);
            }
          }
          _currentTargeting[targeting[i][0]] = tmpArr;
          // New param or override param.
        } else {
          if(targeting[i][1] && typeof targeting[i][1] === 'string') {
            _currentTargeting[targeting[i][0]] = [targeting[i][1]];
          } else {
            _currentTargeting[targeting[i][0]] = targeting[i][1];
          }
        }
      }
    }
    return _currentTargeting;
  } catch(err) {
    mps._errorCallback(err, 'mps.prependDefaultTargeting');
    return false;
  }
};

/**
 * Sets Ad Targeting or Exclusions
 * @param {object} targeting
 * @param {string} adslot
 */
mps._setAdunitTargeting = function(targeting, adslot) {
  for(var i in targeting) {
    if(i.indexOf('!c') != -1 ){
      gpt[mps.advars[adslot]].setCategoryExclusion(targeting[i][0]);
    } else {
      gpt[mps.advars[adslot]].setTargeting(i, targeting[i]);
    }
  }
};

/**
 * Sets page Context for new loadsets
 * @private
 */
mps._setpageContext = function() {
  var _mpscallslen = (mps._keys(mps._ext.mpscalls).length - 1);
  while(_mpscallslen > -1) {
    if(_mpscallslen > 0) {
      if(typeof(mps._ext.mpscalls[_mpscallslen].path) === 'string' && (mpscall.path !== mps._ext.mpscalls[_mpscallslen].path) && mps._bool(mps._ext.mpscalls[_mpscallslen].adreq) === false) {
      mps._debug('[mps:preLoader]: Path: reset mps.pagevars and mpscall objects to previous path.');
        mps.pagevars = mps._clone(mps._ext.pagevars[_mpscallslen]);
        mpscall = mps._clone(mps._ext.mpscalls[_mpscallslen]);
        break;
      }
    } else {
      mps._debug('[mps:preLoader]: Path: no different previous path found in additional loadsets, reset to default.');
      if(typeof mps._ext.pagevars[0] == 'object'){ mps.pagevars = mps._clone(mps._ext.pagevars[0]); }
      if(typeof mps._ext.mpscalls[0] == 'object'){ mpscall = mps._clone(mps._ext.mpscalls[0]); }
    }
    _mpscallslen -= 1;
  }
};

/**
 * Appends or Overrides targeting key/value pairs
 * @params {string} selector
 * @param {string}  adslot
 * @param {string}  targetingappend
 * @param {boolean} disabledetect
 * @param {string}  newpath
 * @param {boolean} overridetargeting
 * @param {number}  clone
 * @param {number}  loadset
 */
mps.targetingAppend = function(selector,adslot,targetingappend,disabledetect,newpath,overridetargeting,clone,loadset) {
  clone = clone || 0;
  newpath = newpath || null;
  disabledetect = disabledetect || false;
  overridetargeting = overridetargeting || false;
  loadset = (typeof loadset != 'undefined') ? parseInt(loadset,10) : mps._loadset; //loadset to clone
  var adslotopt = (clone > 0) ? adslot + '-C' + clone : adslot;
  if(newpath && typeof(newpath)==='string' && newpath.length > 0)   {
  mps._debug('[mps:preLoader]: Path: ' + newpath + ' specified, mps.makeRequest()');
    mpscall.path = mps.pagevars.path = newpath;
    mpscall.READONLY = 1;
    mpscall.adreq = 1;
    var _pagecontextKey = mps._pagecontextKeyPath(newpath);
    if(_setTargeting && mps.advars[adslotopt]) {
      if(!mps.pagevars.fields) {
        mps.pagevars.fields = {};
      }
      for(var i in _setTargeting) {
        mpscall['field[' + i + ']'] = _setTargeting[i].toString();
        mps.pagevars.fields[i] = _setTargeting[i].toString();
      }
    }
    var gptQueue = mps._reqset > mps._loadset ? mps._reqset : mps._loadset;
    gptQueue = gptQueue + 1;
    mps._queue.gptloadset[gptQueue]=mps._queue.gptloadset[gptQueue]||[];
    var newrequest = !!(_pagecontextKey === false || mpsopts.forcenetcalls);
    if(newrequest) {
      mps._queue.gptloadset[gptQueue].push(function() {
        mps._gptcmd.push(function(){
          var _setTargeting = mps.prependDefaultTargeting(mps.targetingArray(targetingappend), adslot, overridetargeting);
          if(_setTargeting && adslotopt) {
            mps._setAdunitTargeting(_setTargeting, adslotopt);
          } else {
          mps._debug('[mps:preLoader]: New path, no targeting params specified');
          }
          mps.insertAd(selector, adslot, null, disabledetect, null, null, clone, loadset);
        });
      });
    }
    // Check if new network request is needed.
    if(clone === 0){
      if(newrequest) {
      mps._debug('[mps:preLoader]: Path: ' + newpath + ' specified and not previously loaded, mps.makeRequest().');
        mps._queue.gptloadset[gptQueue].push(function() {
          mps._setpageContext();
        });
        setTimeout(function(){
          mps.makeRequest('more');
        }, 0);
      } else {
        // Path already called, reference mps._pagecontext.
      mps._debug('[mps:preLoader]: Path: ' + newpath + ' specified but previously loaded, reference mps._pagecontext.');

        var _loadsettotal = (mps._pagecontext[_pagecontextKey].loadsets.length - 1);
        var _loadset = mps._pagecontext[_pagecontextKey].loadsets[_loadsettotal];
        var _mpscallslen = (mps._keys(mps._ext.mpscalls).length - 1);
        for (var j in mps._ext.mpscalls) {
          if (mps._ext.mpscalls[j].path === mpscall.path) {
            var _loadsetstotal = (mps._pagecontext[_pagecontextKey].loadsets.length - 1);
            var _loadset = mps._pagecontext[_pagecontextKey].loadsets[_loadsetstotal];
            mps.pagevars.mpsid = mps._pagecontext[_pagecontextKey].mpsid;
            break;
          }
        }
        if (mps._ext._insertedads[_loadset] && mps._ext._insertedads[_loadset].indexOf(adslot) > -1) {
          mps.cloneAd(selector, adslot, targetingappend, disabledetect, overridetargeting, _loadset);
        } else {
          mps.insertAd(selector, adslot, null, disabledetect, null, null, 0, _loadset, true);
        }
        mps._setpageContext();
      }
    }
  } else { // no path set
    var _setTargeting = mps.prependDefaultTargeting(mps.targetingArray(targetingappend), adslot, overridetargeting);
    var _advar = mps._advars[loadset] && mps._advars[loadset][adslotopt] ? mps._advars[loadset][adslotopt] : null;
    if(_setTargeting && _advar) {
      mps._debug('[mps:preLoader]: set targeting and insertAd()');
        for(var i in _setTargeting) {
          if(i.indexOf('!c') != -1 ){
            gpt[_advar].setCategoryExclusion(_setTargeting[i][0]);
            delete _setTargeting[i];
          }else {
            gpt[_advar].setTargeting(i, _setTargeting[i]);
          }
        }
    } else {
    mps._debug('[mps:preLoader]: no path or targeting params specified, insertAd()');
    }
    mps.insertAd(selector, adslot, null, disabledetect, null, null, clone, loadset);
  }
};

/**
 *mps.replaceAd  allows SPA (i.e pca.eonline.com)by updating the Google Page View by destroying and cloning the slot.
 * @param {string} selector
 * @param {string} adslot
 * @param {number} loadset (optional)
 */
mps.replaceAd = function(selector, adslot, loadset) {
  // skip replaceAd --> call cloneAd
  var loadset = (typeof loadset != 'undefined') ? parseInt(loadset, 10) : mps._loadset;
  mps._ext._insertedads[loadset] = mps._ext._insertedads[loadset] || [];
  var slotname = adslot;
  var selected = mps._select(selector);
  var selectorName = (selected.id) ? '#'+selected.id : (document.body === selected) ? 'body' : '.'+selected.className;

  if (mps._ext._insertedads[loadset].indexOf(adslot) > -1) {
    // loop through all loadsets and clones and remove adslot
    for (var i=0; i<mps._keys(mps._slotscalled[loadset]).length; i++) {
      if (mps._keys(mps._slotscalled[loadset])[i].indexOf(adslot) > -1) {
        slotname = mps._keys(mps._slotscalled[loadset])[i];
        mps._debug('[mps:preLoader] destroyAds=>MATCH('+slotname+')');
        mps.destroyAds(slotname);
      } else if (slotname !== '_oop'){
        mps._debug('[mps:preLoader] destroyAds=>NO_MATCH('+slotname+')');
        mps.destroyAds(slotname);
      }
    }
    // Destroy OOP
    if (mps._keys(mps._slotscalled[loadset]).length && mps._keys(mps._slotscalled[loadset])[0].indexOf('_oop') > -1) {
      mps._debug('[mps:preLoader] destroyAds=>(_oop)');
      mps.destroyAds('_oop');
    }

    mps._queue.gptloaded.push(function() {
      mps._debug('[mps:preLoader] replaceAd('+loadset+') => cloneAd(' + selectorName + ':' + adslot + ')');
      mps.cloneAd(selector, adslot);
    });
  } else {
    mps._queue.gptloaded.push(function() {
      mps._debug('[mps:preLoader] replaceAd('+loadset+') => insertAd(' + selectorName + ':' + adslot + ')');
      mps.insertAd(selector, adslot);
    });
  }
};

/**
 * Clones an Ad with optional parameters
 * @params {string} selector
 * @param {string}  adslot
 * @param {string}  targetingappend
 * @param {boolean} disabledetect
 * @param {string}  newpath
 * @param {boolean} overridetargeting
 * @param {number}  loadset
 */

mps.cloneAd = function (selector, adslot, targetingappend, disabledetect, overridetargeting, loadset) {
  targetingappend = targetingappend || '';
  disabledetect = (disabledetect !== undefined) ? mps._bool(disabledetect) : false;
  overridetargeting = overridetargeting || false;
  loadset = (typeof loadset != 'undefined') ? parseInt(loadset,10) : mps._loadset;
  if(mps._clonerunning) {
    mps._queue.clonead.push(function() {
      mps.cloneAd(selector, adslot, targetingappend, disabledetect, overridetargeting, loadset);
    });
    return false;
  }
  mps._clonerunning = true;
  if(!mps._gptloaded){
    mps._queue.gptloaded.push( function(){
      mps.cloneAd(selector, adslot, targetingappend, disabledetect, overridetargeting, loadset);
    });
    mps._clonerunning = false;
    return false;
  }
  if (selector && mps._select(selector) && adslot.length > 0 && typeof adslot === 'string' && typeof mps._replicateAd === 'function' && typeof mps._ext === 'object') {
    mps._ext._insertedads[loadset] = mps._ext._insertedads[loadset] || [];
    if (mps._ext._insertedads[loadset].indexOf(adslot) == -1) {
      // skip cloneAd --> call insertAd
    mps._debug('^[mps:preLoader] SKIPPED cloneAd, call insertAd('+ adslot +':'+ loadset +')');
      mps.insertAd(selector, adslot, targetingappend, disabledetect, null, overridetargeting, 0, loadset);
      mps._clonerunning = false;
      return false;
    } else {
      try {
        var cloneObj = mps._replicateAd(adslot, loadset);
        if( typeof cloneObj == 'object'){
          var cloneSizes = [], cloneTargeting = '';
          // Get clone sizes
          var cloneSize = cloneObj.getSizes();
          for (var key in cloneSize) {
            if(cloneSize.hasOwnProperty(key)){
              if(key == 0 && cloneSize[key] == 'fluid'){ cloneSizes = cloneSize[key]; }
              else{
                var oneSize = mps.getValueWithoutKey(cloneSize[key]);
                cloneSizes.push([oneSize[0], oneSize[1]]);
              }
            }
          }
          // Define slot
          var currentCloneVar = mps._clonevars[loadset][adslot];
          if( currentCloneVar && currentCloneVar.length > 0){
            var clonecount = parseInt(currentCloneVar.split('_C')[1], 10),
              clonevar = mps._advars[loadset][adslot] + '_C' + clonecount, // gpt_slot_id
              cloneslot = mps._adslots[loadset][adslot] + '-C' + clonecount, // gpt-div-id
              cloneadslot = adslot + '-C' + clonecount;   // topbanner-C1
            // disable detect display cloneAd using mps.lazyloadclone
            mps.lazyloadclone[loadset] = mps.lazyloadclone[loadset] || [];
            var cloneIndex = mps.lazyloadclone[loadset] ? mps.lazyloadclone[loadset].indexOf(cloneadslot) : -1;
            if(!disabledetect && cloneIndex == -1 && mps._detect && mps._detect.removed && mps._detect.removed[loadset] && mps._detect.removed[loadset].indexOf(adslot) > -1){
              mps.lazyloadclone[loadset].push(cloneadslot);
            }
            if(disabledetect && cloneIndex > -1){
              mps.lazyloadclone[mps._loadset].splice(cloneIndex, 1);
            }

            // Define Slot
            gpt[clonevar]=googletag.defineSlot(cloneObj.getAdUnitPath(),cloneSizes,cloneslot);
            if(mps._resetrsizemap && mps._resetrsizemap[adslot]) {
              gpt[clonevar].defineSizeMapping(mps._resetrsizemap[adslot]);
            } else {
              gpt[clonevar].defineSizeMapping([[[0,0],cloneSizes]]);
            }
            for(var i in cloneObj.getCategoryExclusions()) {
              gpt[clonevar].setCategoryExclusion(cloneObj.getCategoryExclusions()[i]);
            }


            // Add Service
            gpt[clonevar].addService(googletag.pubads());
            mps._gptcmd.push(function(){
              //call insertAd(clone) --> skip getAd
              mps.insertAd(selector, adslot, targetingappend, disabledetect, null, overridetargeting, clonecount, loadset);
              mps._queue.render('adclone',cloneadslot,loadset,clonecount); // render adclone queue
              if(mps.responsiveslots && mps.responsiveslots[loadset] && mps.responsiveslots[loadset][adslot]){
                mps.responsiveslots[loadset][cloneadslot] = mps.responsiveslots[loadset][adslot];
              }
            });

            for(var i in cloneObj.getCategoryExclusions()) {
              gpt[clonevar].setCategoryExclusion(cloneObj.getCategoryExclusions()[i]);
            }

            // Set custom targeting.
            if(!overridetargeting && mpscall.path && typeof mps._resettargeting[mpscall.path] !== 'undefined' && mps._keys(mps._resettargeting[mpscall.path]).length) {
              for (var i in mps.advars) {
                mps._resettargeting[mpscall.path][i] = mps._resetTargetingObj(gpt[mps.advars[i]].getTargetingMap());
              }
              for(var l in mps._resettargeting[mpscall.path][adslot]) {
                for(var m=0; m<mps._resettargeting[mpscall.path][adslot][l].length; m++) {
                  gpt[clonevar].setTargeting(l,mps._resettargeting[mpscall.path][adslot][l][m]);
                }
              }
            } else {
              // Set default targeting.
              var _setTargeting =  mps.prependDefaultTargeting(mps.targetingArray(targetingappend), adslot, overridetargeting);
              for(var t in _setTargeting) {
                gpt[clonevar].setTargeting(t, _setTargeting[t]);
              }
              if(clonecount>0) {
                // clone number to targeting
                gpt[clonevar].setTargeting('clone', clonecount);

                // parent slot to targeting
                gpt[clonevar].setTargeting('slot', adslot);
              }
            }
            // Set Collapse Empty Divs
            if(mps._collapsemap[adslot] === 0){
              // 0 Collapse If Empty
              gpt[clonevar].setCollapseEmptyDiv(false);
            } else if(mps._collapsemap[adslot] === 1){
              // 1 No Collapse
              gpt[clonevar].setCollapseEmptyDiv(true);
            }else if(mps._collapsemap[adslot] === 2){
              // 2 Start Collapsed
              gpt[clonevar].setCollapseEmptyDiv(true, true);
            }

            // Update Clone adobs
            mps.adobs.push(gpt[clonevar]);
            return true;
          }

        }else{
          if(typeof mps.response.dart.params.adunits == 'object' && mps.response.dart.params.adunits[adslot] && mps.response.dart.params.adunits[adslot].html !== ''){
            mps._debug("^[mps:preLoader] cloneAd("+adslot+") SKIPPED: Disabled "+mps._elapsed());
          }else{
          mps._debug('[mps:preLoader] _replicateAd invalid slot or loadset.');
          }
          mps._clonerunning = false;
          return false;
        }
      } catch(err) {
        mps._errorCallback(err, 'mps.cloneAd');
      }
    }
  }else{
  mps._debug('[mps:preLoader] cloneAd FAILED: Invalid parameters. ');
    mps._clonerunning = false;
    return false;
  }
};

/**
 * Inserts and Ad with optional parameters
 * @params {string} selector
 * @param {string}  adslot
 * @param {string}  targetingappend
 * @param {boolean} disabledetect
 * @param {string}  newpath
 * @param {boolean} overridetargeting
 * @param {number}  clone
 * @param {number}  loadset
 * @param {number}  prevloadset
 */
mps.insertAd = function(selector, adslot, targetingappend, disabledetect, newpath, overridetargeting, clone, loadset, prevloadset){
  if(!selector) return false;
  clone = clone || 0;
  prevloadset = (typeof prevloadset != 'undefined') ? mps._bool(prevloadset) : false;
  targetingappend = targetingappend !== null ? targetingappend : '';
  var loadset = (clone > 0 || prevloadset) && (typeof loadset != 'undefined') ? parseInt(loadset,10) : mps._loadset;
  // disable detect display insertAd
  if(disabledetect && mps.lazyload && mps.lazyload[loadset]) {
    var detectIndex = mps.lazyload[loadset].indexOf(adslot);
    if(detectIndex > -1) {
    mps._debug('[mps:preLoader] insertAd disable detected display called on adslot: '+adslot);
      mps.lazyload[loadset].splice(detectIndex, 1);
      mps._detect.removed[loadset] = mps._detect.removed[loadset] || [];
      mps._detect.removed[loadset].push(adslot);
    }
  }
  if(mps._gptloaded == false) {
    var gptQueue = 0;
    if(typeof mps._loadset === 'number' && !isNaN(mps._loadset)) {
      gptQueue = mps._reqset > mps._loadset ? mps._reqset : mps._loadset;
    }
    mps._queue.gptloadset[gptQueue]=mps._queue.gptloadset[gptQueue]||[];
    mps._queue.gptloadset[gptQueue].push(function(){
      mps.insertAd(selector,adslot,targetingappend,disabledetect,newpath,overridetargeting,clone,loadset)
    });
    return true;
  }
  if(targetingappend && targetingappend.length || newpath) {
    mps.targetingAppend(selector,adslot,targetingappend,disabledetect,newpath,overridetargeting,clone,loadset);
    return false;
  }
  if(selector) {
    var selected = mps._select(selector);
	  var selectorName = (selected.id) ? '#'+selected.id : (document.body == selected) ? 'body' : '.'+selected.className;
    if(clone > 0){
      mps._clonevars[loadset]=mps._clonevars[loadset]||{};
      mps._clonevars[loadset][adslot] = mps._clonevars[loadset][adslot] || [];
      var count = (mps._clonevars[loadset][adslot].length > 0 && parseInt(mps._clonevars[loadset][adslot].split('_C')[1],10) > 0) ? parseInt(mps._clonevars[loadset][adslot].split('_C')[1],10) : 1;
      var cloneadslot = adslot+'-C'+ count;
      mps._debug('[mps:preLoader] cloneAd('+selectorName+','+adslot+', C'+count+') '+mps._elapsed());
      var adcode = '<div id="'+mps._adslots[loadset][cloneadslot]+'" class="mps-slot" data-mps-slot="' +cloneadslot+ '" data-mps-loadset="' + loadset + '" data-mps-clone="' + count+ '"><script>mps._execAd("'+ adslot +'",'+ loadset +',' + count +',false);</script></div>';
      mps._ext._insertedads[loadset] = mps._ext._insertedads[loadset] || [];
      mps._ext._insertedads[loadset].push(cloneadslot);
      var _rset = (typeof mps.getResponsiveSet === 'function') ? mps.getResponsiveSet() : 0;
      if(mps.responsiveslots && mps.responsiveslots[loadset] && mps.responsiveslots[loadset][adslot] && mps.responsiveslots[loadset][adslot][_rset] && mps.responsiveslots[loadset][adslot][_rset][0] === "NONE"){
        if(mps.slotsdisabled[loadset] && mps.slotsdisabled[loadset].indexOf(cloneadslot) === -1) {
          mps.slotsdisabled[loadset].push(cloneadslot);
        }
      }
      if(typeof mps._ext == 'object' && typeof mps._reqs == 'object'){
        mps._reqs[loadset] = mps._reqs[loadset] || {};
        mps._reqs[loadset]['begin_'+cloneadslot] = mps._reqs[loadset]['begin_'+cloneadslot] || mps._elapsed('',true);
      }
      if(adcode && (typeof(selector) === 'object' || mps._select(selector))) {
        mps._append(selector,adcode,'mps.insertAd');
        return true;
      } else {
        mps._clonerunning = false;
      }
    }else{
    mps._debug('[mps:preLoader] insertAd('+selectorName+','+adslot+') '+mps._elapsed());
      if(!prevloadset) {
        var adcode = mps.getAd(adslot);
      } else {
        var adcode = mps.getAd(adslot, false, loadset);
        if(mps._validateAdCode(adcode)) {
          adcode = mps._updateAdCode(adcode, adslot, loadset, true, null);
        }
      }
      if(adcode){
        mps._append(selector,adcode,'mps.insertAd');
        return true;
      }
    }
  }
  return false;
};

/**
 * Inserts a single component (sid) the element (selector)
 * @param {object} selector
 * @param {string} sid
 * @return {string} componentdata
 */
mps.insertComponent = function(selector,sid){
  var componentdata='';
  if(typeof(sid)!='undefined' && sid !='' && typeof(mps)=='object' && typeof(mps.response)=='object' && typeof(mps.response.components)=='object' && typeof(mps.response.components[sid])=='object' && typeof(mps.response.components[sid].data)!='undefined') {
  mps._debug('[mps:preLoader] mps.getComponent() LOAD: '+sid);
    if(mps.response.components[sid].data != '' && !(selector)) {
      componentdata = mps.response.components[sid].data;
    } else if (mps.response.components[sid].data != '' && selector){
      componentdata = mps._append(selector,mps.response.components[sid].data, 'mps.getComponent: ' + sid);
    }
  } else {
  mps._debug('[mps:preLoader] mps.getComponent() SKIP: '+sid);
  }
  return componentdata;
};

/**
 * Appends or document.writes the footer html (includes components)
 * @return {boolean}
 */
mps.writeFooter = function() {
  var _loadfooter = mps._bool(mps._ext.loadfooter);
  var _footerdata = mps.response && mps.response.pagevars && typeof(mps.response.pagevars.insert_bodyfooter) === 'string' ? mps.response.pagevars.insert_bodyfooter : '';
  if(!_footerdata.length) {
  mps._debug('[mps:preLoader] mps.writeFooter SKIP: undefined response (async) or empty response.');
    return false;
  }
  if(mps._ext.nowrite !== 1 && _loadfooter === false) {
    mps._ext.loadfooter = 1;
    if(typeof(mps._ext._async) === 'undefined' || mps._bool(mps._ext._async) === false) {
    mps._debug('[mps:preLoader] mps.writeFooter: DOCUMENT.WRITE');
      document.write(_footerdata);
    } else {
    mps._debug('[mps:preLoader] mps.writeFooter: ASYNC.');
      mps._append('body', _footerdata, 'mps.writeFooter');
    }
  } else {
    mps._ext.loadfooter = 1;
    var _msg = _loadfooter === true ? 'FOOTER DELAYED OR ALREADY EXECUTED VIA mpsOnReady().' : 'Append NOWRITE=1';
    mps._debug('[mps:preLoader] mps.writeFooter ' + _msg);
    if(!_loadfooter){
      mps._append('body', _footerdata, 'mps.writeFooter');
      return true;
    } else {
      return false;
    }
  }
};

/**
 * Clones mpscall and pagevars object for pagecontext
 * @return loadset {number}
 */
mps._cloneObjects = function() {
  var loadset = (typeof mps._loadset === 'number' && !isNaN(mps._loadset)) ? mps._loadset : 0;
  mps._ext.pagevars = mps._ext.pagevars||{};
  mps._ext.pagevars[loadset]=mps._ext.pagevars[loadset]||{};
  mps._ext.mpscalls = mps._ext.mpscalls||{};
  if(loadset == 0) {
    if(typeof mpscall == 'object') mps._ext.mpscalls[0] = mps._clone(mpscall);
    if(typeof mps.pagevars == 'object') mps._ext.pagevars[0] = mps._clone(mps.pagevars);
  } else if(loadset > 0){
    mps._ext.pagevars[loadset] = mps._clone(mps.pagevars);
    mps._ext.mpscalls[loadset] = mps._clone(mpscall);
  }
  if(mps._ext.mpscalls[loadset].type) {
    mps._ext.pagevars[loadset].type = mps._ext.mpscalls[loadset].type;
  }
  if(mps._ext.mpscalls[loadset].content_id) {
    mps._ext.pagevars[loadset].cid = mps._ext.mpscalls[loadset].content_id;
  }
  return loadset;
};

/**
 * Validates Ad Code
 * @param {string} adcode
 * @return {boolean}
 */
mps._validateAdCode = function(adcode) {
  return typeof(adcode) === 'string' && adcode.indexOf('<!--') === -1;
};

/**
 * Updates Ad HTML code
 * @param {string}  adcode
 * @param {string}  adunit
 * @param {number}  loadset
 * @param {number}  appendloadset
 * @param {number}  mpsid
 * @return {string} _adhtml
 */
mps._updateAdCode = function(adcode, adunit, loadset, appendloadset, mpsid) {
  try {
    var _adunit = adunit.toLowerCase().replace(/\s+/g, ''),
      _classname = (_adunit === '_oop') ? 'mps-slot-oop' : 'mps-slot',
      // Insert fixed size styles into ad containers for single sizes
      _style = (_adunit === '_oop') ? ' style="width:0;height:0;margin:0;padding:0;line-height:0;"' : '';
      _divid = (_adunit === '_oop') ? 'outofpage' : _adunit,
      _loadsetid = loadset > 0 ? '-' + loadset : '',
      _mpsid = typeof(mpsid) === 'number' ? mpsid : mps.pagevars.mpsid,
      _prefix = mps.response.dart.params.ad_div_prefix || 'div-gpt-',
      _adhtml = '<div id="' + _prefix + _divid + '-' + _mpsid + _loadsetid + '" ';
      _adhtml += 'class="' + _classname + '" ';
      _adhtml += 'data-mps-slot="' + _adunit + '" ';
      _adhtml += 'data-mps-loadset="' + loadset + '"' + _style + '>';
      _adhtml += '<script>mps._execAd("' + _adunit + '",'+ loadset + ');</script>';
      _adhtml += '</div>';
    return _adhtml;
  } catch (err) {
    mps._errorCallback(err, 'mps._updateAdCode');
    return false;
  }
};

mps._responseAdunits = function() {
  return typeof(mps.response) === 'object' && typeof(mps.response.dart) === 'object' && typeof(mps.response.dart.params) === 'object' && typeof(mps.response.dart.params.adunits) === 'object';
};

// updateRequest called when new inserts but not new path.
// No new xhr call, unless mpsopts.forcenetcalls=true
mps.updateRequest = function() {
mps._debug('[mps:preLoader] updateRequest');
  var _pagecontextKey = mps._pagecontextKey();
  if(_pagecontextKey === false) {
    return false;
  }
  mps._gptloaded = false;
  mps._gptrefresh = false;
  // Re-execute inserts if original path.
  if(_pagecontextKey === 0) {
    mps.response.pagevars = mps._pagecontext[_pagecontextKey].pagevars;
    mpsCallback(mps.response, true);
  } else {
    mps._loadset++;
  }

  try {
    var _loadset = mps._loadset;
    mps.adobs=[];
    mps.adslots={};
    mps.advars={};
    mps._slotscalled[_loadset]={};
    mps._slotsdisabled[_loadset]={};
    mps.slotsdisabled[_loadset]=[];
    mps.slotsdisabled[_loadset] = mps.slotsdisabled[0];
    var _originalloadset = mps._pagecontext[_pagecontextKey].loadsets[0];
    var _mpsid = mps._pagecontext[_pagecontextKey].mpsid;

    // Update dart response.
    var _adunits = mps._pagecontext[_pagecontextKey].adunits;
    for(var i in _adunits) {
      if(typeof(_adunits[i]) === 'object' && typeof(_adunits[i].adunit_slot_div) === 'string' && typeof(_adunits[i].html) === 'string' && _adunits[i].html.length > 0){
        _adunits[i].html = mps._updateAdCode(_adunits[i].data, i, _loadset, false, _mpsid);
      }
    }
    // Update response.dart.adunits to updated context adunits.
    mps.response.dart.params.adunits = mps._pagecontext[_pagecontextKey].adunits;

    // Copy adslothtml.
    if(mps._responseAdunits()) {
      for(var adunit in mps.response.dart.params.adunits) {
        // .data needed for backward compatibility
        mps.adslothtml[adunit] = mps.response.dart.adunits[adunit].data = mps.response.dart.params.adunits[adunit].html;
      }
    }
    // update lazyload (insert,clone) adslots from loadset 0 map
    if(typeof mps.lazyload !== 'undefined' && mps.lazyload[_originalloadset]) {
      mps.lazyload[mps._loadset] = mps._lazyloadmap;
      mps.lazyloadclone[mps._loadset] = mps._lazyloadmap;
    }

    var buildSlotName = function(slotname) {
      var _slotname = slotname.split('_');
      var _name = '';
      for(var i = 0; i < _slotname.length; i += 1) {
        if(_slotname[i] != _mpsid) {
          _name += _name.length > 1 ? '_' + _slotname[i] : _slotname[i];
        } else {
          break;
        }
      }
      return _name;
    };

    // Define googletag slots, set targeting and enable pubads.
    for(var i in mps._pagecontext[_pagecontextKey].gpt) {
      var _gptTargeting = mps._pagecontext[_pagecontextKey].gpt[i];
      if(_gptTargeting.gptid && _gptTargeting.gptdiv) {
        // Set targeting and define in GPT.
        var gptKey = i;
        var _gptKey = gptKey.split('.');
        var _slotName = buildSlotName(_gptKey[1]);
        _gptKey = _slotName + '_' + _mpsid + '_' + _loadset;
        var _gptDiv = 'div-' + mps._advarprefix + '-' + _slotName + '-' + _mpsid + '-' + _loadset;
        var _slottargeting = mps._pagecontext[_pagecontextKey]['targeting'] && mps._pagecontext[_pagecontextKey]['targeting'][(_slotName === 'outofpage') ? '_oop' : _slotName] ? mps._pagecontext[_pagecontextKey]['targeting'][(_slotName === 'outofpage') ? '_oop' : _slotName] : null;
        mps._defineAdSlot(_mpsid, {
          'name': _slotName,
          'gptid': _gptTargeting.gptid,
          'advars': _gptKey,
          'sizes': _gptTargeting.sizes,
          'responsivemap': _gptTargeting.responsivemap,
          'id': _gptDiv,
          'targeting': _slottargeting,
          'catexclusion': mps._resetcatexclusion[gptKey],
          'collapse': mps._collapsemap[(_slotName === 'outofpage') ? '_oop' : _slotName]
        });

      }
    }
    mps._adslots[mps._loadset] = mps._clone(mps.adslots);
    mps._advars[mps._loadset] = mps._clone(mps.advars);
  } catch(err) {
    mpsopts.forcenetcalls = true;
    mps.makeRequest('more');
    mps._errorCallback(err, 'mps.updateRequest');
    return false;
  }

  mps._gptcmd.push(function() {
    // Callbacks.
    mps._queue.render('mpsinit');
    if(typeof(mps.initCallback) === 'function') {
      try {
        mps.initCallback();
      } catch(err) {
        mps._errorCallback(err, 'mps.initCallback');
      }
    }
    mps._pagecontext[_pagecontextKey].loadsets.push(mps._loadset);
    mps._gptloadCallback();
  });
};

// COMPARE: (A) mps._ext.mpscalls[mps._keys(mps._ext.mpscalls).length-1] (B) mpscall
// PARAMS: site, path, cat, type, content_id, cag[*], field[*]
mps._pagecontextKey = function() {
  // Return true if any differences, else return false.
  var params = ['site', 'path', 'cat', 'type', 'content_id'],
    wildparams = /(field|cag)+\[([a-z0-9-_\.]*?)\]/i,
    contextKey = false;

  for(var i in mps._pagecontext) {
    contextKey = parseInt(i, 10);
    for(var j in mpscall){
      if(params.indexOf(j) > -1 || wildparams.test(j)){
        // Field and cag - check key and value.
        if(wildparams.test(j)) {
          if((mps._keys(mpscall).indexOf(j) == -1 || (mpscall[j] !== mps._pagecontext[i].mpscall[j]) && mps._haskeyval && !mps._haskeyval(mpscall,j,mps._pagecontext[i].mpscall[j]))) {
            contextKey = false;
          }
          // Check values and key exists.
        } else if((mps._haskeyval && !mps._haskeyval(mpscall,j,mps._pagecontext[i].mpscall[j])) || typeof(mps._pagecontext[i].mpscall[j]) === 'undefined'){
          contextKey = false;
        }
      }
    }
    if(typeof contextKey === 'number') {
      return contextKey;
    }
  }
  return false;
};

/**
 * Validates page context path
 * @param {string} path
 * @param {boolean}
 */
mps._pagecontextKeyPath = function(path) {
  for(var i in mps._pagecontext) {
    if(mps._pagecontext[i].mpscall.path === path) {
      return i;
    }
  }
  return false;
};

mps._matchprevRequest = function() {
  if(mpsopts.forcenetcalls || typeof(mps._loadset)=='undefined') return false;
  return mps._pagecontextKey();
};

/**
 * mps._xhr invokes mpsCallback with JSON or false
 * @param requesturl {string)
 * @return mps.response {string|JSON)
 * @private
 */
mps._xhr = function() {
  var mpsxhr = new XMLHttpRequest();
  mpsxhr.open('GET', mps._protocol()+ '//' +mps.requesturl, true);
  mpsxhr.onload = function(data) {
    if (mpsxhr.status === 200 && data.currentTarget) {
      mps.response = JSON.parse(data.currentTarget.response);
      // MPS Callback.
      mpsCallback(mps.response);
      mps.compareRequestReturn(mpscall_original);

      // Only Lazy loaded ads
      var params = mps.response.dart.params;
      if (typeof mps._detect === 'object' && params.lazy_load_slots && params.lazy_load_slots.length) {
        mps.lazyload = mps.lazyload || {};
        mps.lazyload[mps._loadset || 0] = mps.lazyload[mps._loadset || 0] || params.lazy_load_slots;
      }

      // Define adslots with gpt, once gpt.js is loaded.
      var _mpssyncdelay = mps._ext.dart_mode === 'gpt-asynchronous' ? 0 : 500;

      mps._gptcmd.push(function () {
        setTimeout(function () {
          mps._execgptinit();
        }, _mpssyncdelay);
      });
      mps._gptcmd.push(function () {
        setTimeout(function () {
          mps._execgpt();
        }, _mpssyncdelay);
      });
    } else {
      mps.response = false;
      mpsCallback(mps.response);
    }
  };

  mpsxhr.send();
  return mps.response;

};

mps.compareRequestReturn = function(original) {
  mps.compare = {};
  mps.compare.mpscall = {};
  mps.compare.mpscall.dif = {};
  mps.compare.mpscall.original = original;
  mps.compare.mpscall.final = mpscall;
  for( var v in mpscall ){
    if ( typeof(original[v]) !== 'string')
    {
      mps.compare.mpscall.dif[v] =  '[' + mpscall[v] + '] : was not in original mpscall ';
    }
  };
  for( var v in original ){
    if ( typeof(mpscall[v]) !== 'string')
    {
      mps.compare.mpscall.dif[v] = 'was [' + original[v] + '] then removed.';
    } else if ( original[v] !== mpscall[v] ) {
      mps.compare.mpscall.dif[v] = '[' + original[v] + '] --> [' + mpscall[v] + ']';
    }
  };
};

/**
 * Makes a new xhr request and increase loadset
 * @param {string} loadmode
 * @param {boolean} retry
 */
mps.makeRequest = function(loadmode, retry) {
  try {
    if (!retry && loadmode === 'more') {
      if (mps._reqset > mps._loadset || !mps._gptloaded) {
        mps._reqset++;
        mps._queue.mpsloaded.push(function () {
          mps.makeRequest('more', true)
        });

        return false;
      }
      mps._adslots[mps._reqset] = mps.adslots;
      mps._reqset++;
    }
    mps._ext._insertedads = mps._ext._insertedads || {};
    mps._ext.loaded = 0;
    mps._ext.loadhead = 0;
    mps._ext.loadheader = 0;
    mps._ext.loadfooter = 0;
    mps._gptloaded = false;
    loadmode = (typeof(loadmode) === 'string' && loadmode.length > 0) ? loadmode : '';
    mpscall['LOADMODE'] = loadmode;
    if (mps._overlayenabled) {
      mps._debug("<span class='loadmore'>loadset:" + mps._reqset + "</span><p class='loadmore' title=''>[mps:preLoader] mps.makeRequest(" + loadmode + ")</p>");
    }
    if (typeof(mps.requesturl) !== 'string' || mps.requesturl === '') {
      return false;
    }
    if (typeof(loadmode) === 'string' && loadmode.length > 0) {
      if (loadmode === 'more') {
        mpscall['ASYNC'] = 1;
        mpscall['_'] = mps._loadset + 1;
        mps._ext._async = true;
      }
      // If page exists in mps._pagecontext, refresh objects without a new request.
      if (typeof(mps._matchprevRequest()) === 'number') {
        mps.updateRequest();
        return false;
      }
    }
    delete(mps.response);
    mps.requesturl = mps._ext.mpsRequestUrl(loadmode);
    var gptQueue = typeof mps._loadset === 'number' && !isNaN(mps._loadset) ? mps._loadset + 1 : 0;
    mps._ext._set++;
    mps._reqs[gptQueue] = {};
    // Load response
    if (!mps._ext.loaded) {
      mps._xhr();
    }
    // Load GPT
    if (!googletag.apiReady) {
      mps.loadGPT();
    }
  } catch(err) {
    mps._errorCallback(err, 'mps.makeRequest');
    return false;
  }
};

// BUILD MPS REQUEST VARS
mps._ext._p.defined = mps._ext.mpsRequestParams(mpscall);
mps._ext._p.defined.path = typeof(mps._ext._p.defined.path)!='undefined' ? mps._ext._p.defined.path : '~';
mps._ext._p.derived = mps._ext.mpsDeriveParams();
mpscall = mps._merge(mps._ext._p.derived,mps._ext._p.defined);
mps._ext.mpscalls = mps._ext.mpscalls||{};
mps._ext.mpscalls[0] = mps._clone(mpscall);
mps._debug('[mps:preLoader] (merge params)'+JSON.stringify(mps._ext._p));

// VARIABLES FOR INCLUDE
if(typeof(mpscall.cat)=='string') {
  mpscall.cat = mps._trim(mpscall.cat,'| ');
  var cats = mpscall.cat.split('|'), lastcat = cats[cats.length-1];
} else {
  var cats = [], lastcat = undefined;
}




//--> INCLUDE CODE [cnbc-web]
/* MPS GEO Target - User Geo Data from Akamai (loader js) 1-11-2021 */
mps.geo=mps.geo||{}; mps._queue.geo=mps._queue.geo||[]; mps.geo._groups=mps.geo._groups||{};
mps.geo._get=function(){
  mps._d('[mps/geo] Loading Script');
  mps._loadJS('https://www.nbcudigitaladops.com/hosted/util/geo_data.js',function(){
    if(typeof(__nbcudigitaladops_geo)=='object') {
      mps.geo.data = __nbcudigitaladops_geo;
      mps.geo.data.c = mps.geo.data.c.toLowerCase();
      mps.geo.data.d = parseInt(mps.geo.data.d);
      mps._d('[mps/geo] Loaded: '+JSON.stringify(mps.geo.data));
      mps.geo._got = 1;
      mps._queue.render('geo',mps.geo.data);
      return mps.geo.data;
    }
    mps._d('[mps/geo] FAILED');
    return false;
  });
}
mps.geo.inGroup = function(group,datakey) {
  if(!datakey) var datakey='c';
  if(!mps.geo._groups[group] || !mps.geo.data || !mps.geo.data[datakey]) return false;
  if(mps.geo._groups[group].indexOf(mps.geo.data[datakey])>-1) return true;
  return false;
}
mps._queue.geo.push = function(){
  if(mps.geo._got) mps._queue.exec(arguments[0],mps.geo.data);
  return Array.prototype.push.apply(this, arguments);
}
mps.geo._groups['eu'] = ['at','be','bg','cy','cz','de','dk','ee','el','es','fi','fr','hr','hu','ie','it','lt','lu','lv','mt','nl','pl','pt','ro','se','sk','so','uk'];
mps.geo._groups['eea'] = mps.geo._groups['eu'].slice(0);
mps.geo._groups['eea'].push('no','is','li','gb');
mps.geo._get();
/* MPS GEO Target - END */

/*  OneTrust Cookies Consent Notice start */
(function () {
  let ot_status = false;
  let script_element = document.getElementsByTagName("script");
  if(script_element) {
      for(let i = 0; i < script_element.length; i++) {
          if(script_element[i].src == "https://cdn.cookielaw.org/consent/29fbab1a-4edf-4f34-9e94-35f9113beb8b/otSDKStub.js") {
              ot_status = true;
              console.log('onetrust script');
          }
      }
      if(ot_status == false) {
          var s = document.createElement("script");
          s.type = "text/javascript";
          s.charset = "UTF-8";
          s.setAttribute("data-domain-script", "29fbab1a-4edf-4f34-9e94-35f9113beb8b");
          s.setAttribute("integrity", "sha384-RMzc1apF4FYscreDULKoAOkixJy0RAZisHFQ1jXAH8TwA1oKHVYXqSEwOczvg/pN");
          s.setAttribute("crossorigin", "anonymous");
          s.async = 0;
          s.src = "https://cdn.cookielaw.org/consent/29fbab1a-4edf-4f34-9e94-35f9113beb8b/otSDKStub.js";
          var d = document.getElementsByTagName("script")[0];
          d.parentNode.insertBefore(s, d);
      }
  }
 
})();
// function to pull cookie value
function getCookie(name) {
var value = "; " + document.cookie;
var parts = value.split("; " + name + "=");
if (parts.length == 2) return parts.pop().split(";").shift();
}
function OptanonWrapper() {
console.log("OptanonWrapper called");
var OABCcookieName = "OptanonAlertBoxClosed";
var bannerAcceptBtn = document.getElementById("onetrust-accept-btn-handler");
var pcAllowAllBtn = document.getElementById("accept-recommended-btn-handler");
var pcSaveBtn = document.getElementsByClassName("save-preference-btn-handler onetrust-close-btn-handler button-theme")[0];
var OABCcookie = getCookie(OABCcookieName);
// IF logic needed here because ot-banner-sdk DIV is not injected on page loads if banner is not exposed
if (!OABCcookie && bannerAcceptBtn) {
  bannerAcceptBtn.addEventListener('click', function() {
      console.log("Allowed all via Banner");
      location.reload();
  });
}
if (pcAllowAllBtn) {
pcAllowAllBtn.addEventListener('click', function() {
  console.log("Allowed all via Preference Center");
  location.reload();
});
}
if (pcSaveBtn) {    
pcSaveBtn.addEventListener('click', function() {
  console.log("Set custom settings via Preference Center");
  location.reload();
});
}
}
console.log('OneTrust: Optanon Init Load');
/*  OneTrust Cookies Consent Notice end */

mpsopts.detection_above_the_fold=1;
mps.refreshAdsIntervalCNBC = function (intervalsecs,slotname,loadset=0,intervalkey) {
  if(slotname === false) {
    return false;
  }
  mps._debug("[mps:Refresh]: js-include window has focus, refresh ads. : "+ slotname);
  mps.refreshintervals = mps.refreshintervals || {};
  var intervalkey = intervalkey || (mps._keys(mps.refreshintervals).length + 1);
  if(intervalsecs > 0) {
    mps._debug('[mps:Refresh] js-include Set ad refresh interval for '+intervalsecs+'s ('+intervalsecs*1000 + 'ms) [interval key: '+intervalkey+']');
    mps.refreshintervals[intervalkey] = setInterval(function(){
      mps._debug('[mps:Refresh] js-include Reached '+intervalsecs+'s ('+intervalsecs*1000 + 'ms) interval - Refreshing ad slots [interval key: '+intervalkey+']');
      // Detected display active refresh enabled.
      if(mps._bool(mpsopts.activerefresh) === true || mpsopts.activerefresh > 0) {
        // Check if window has focus.
        if(mps._activerefresh._focus === true ) {
          mps._debug("[mps:Refresh]: js-include window has focus, refresh ads.");
          var len = slotname.length;
          	for (i = 0;  i < len; i++) {
          		mps._debug("[mps:Refresh]: js-include refresh ad. adslots is : "+ slotname[i] +" : "+ mps._advars[loadset][slotname[i]]);
          		var adelem = '#'+mps._adslots[loadset][slotname[i]];
          		if( mps.inViewport(adelem,false) ) {
          			mps._debug("[mps:Refresh]: js-include refresh ad IS in view. "+ slotname[i]);
          			mps.refreshAds(slotname[i],loadset);
          		} else {
          			mps._debug("[mps:Refresh]: js-include refresh ad NOT in view. "+ slotname[i]);
          		}
      		}
        } else {
          mps._debug("[mps:Refresh]: js-include window doesn't have focus, or ad not in viewport, don't refresh ads.");
        }
      } else {
        mps.refreshAds(slotname,loadset);
      }
    }, intervalsecs*1000);
    return intervalkey;
  }
};

/* [2017-02-16] <START> Header Bidding (v4) */ 
mps.cnbc = mps.cnbc || {};
mps.cnbc.hb=mps.cnbc.hb||{}; mps.cnbc.hb.executed=0;
/*====[config]============================*/
mps.cnbc.hb.a9pubid = '3219';
mps.cnbc.hb.ixjs = '185796-151042474895997.js';
mps.cnbc.hb._version = '4.9cnbc';
/*========================================*/
// @TODO !c=headerbid
mps.cnbc.hb.a9timeout = mps.cnbc.hb.a9timeout || 3000;
mps.cnbc.hb.ixtimeout = mps.cnbc.hb.ixtimeout || 3000;
mps.cnbc.hb._ixready = 0;
mps.cnbc.hb.execute = function() {
  if(typeof(mps.cnbc.hb.customConfig)=='function') mps.cnbc.hb.customConfig();
  if(mps._checkQS('DISABLEHB') || (!mps.cnbc.hb.a9pubid && !mps.cnbc.hb.ixjs)) {
    mpsopts.skipdisableinitialload = 1;
    mps._d('[mps/hb] SKIPPED (DISABLEHB)');
    return false;
  } else {
		mps._d('[mps/hb] HERE COMES HB');
		mpsopts.skipdisableinitialload = 0;
    googletag.cmd.push(function() {
      googletag.pubads().disableInitialLoad();
    });
  }
  mps._reqs.hb=mps._reqs.hb||{}; mps.cnbc.hb.executed++; mps.cnbc.hb.loadedads=0;
  mps._d('[mps/hb] Starting Execution');
  if(mps.cnbc.hb.ixjs) {
    mps._d('[mps/hb] IX: Load ('+mps.cnbc.hb.ixjs+')');
    mps.cnbc.hb.ixurl = 'https://js-sec.indexww.com/ht/p/'+mps.cnbc.hb.ixjs;
    mps._reqs.hb['ix_begin']=mps._elapsed('',true);
    mps._loadJS(mps.cnbc.hb.ixurl,function(){
      mps._d('[mps/hb] IX: Loaded');
      mps._reqs.hb['ix_loaded']=mps._elapsed('',true);
    });
  }
  if(mps.cnbc.hb.a9pubid) {
    mps._reqs.hb['a9_begin']=mps._elapsed('',true);
    mps._d('[mps/hb] A9: Load ('+mps.cnbc.hb.a9pubid+')');
    !function(a9,a,p,s,t,A,g){if(a[a9])return;function q(c,r){a[a9]._Q.push([c,r])}a[a9]={init:function() {q("i",arguments)},fetchBids:function(){q("f",arguments)},setDisplayBids:function(){},targetingKeys:function(){return[]},_Q: []};A=p.createElement(s);A.async=!0;A.src=t;g=p.getElementsByTagName(s)[0];g.parentNode.insertBefore(A,g)} ("apstag",window,document,"script","//c.amazon-adsystem.com/aax2/apstag.js");
    apstag.init({
      pubID: mps.cnbc.hb.a9pubid,
      adServer: 'googletag'
    });
  }
  mps._queue=mps._queue||{}; mps._queue.gptloaded=mps._queue.gptloaded||{}; mps._queue.mpsloaded=mps._queue.mpsloaded||{}; mps._queue.mpsready=mps._queue.mpsready||{};
  mps._queue.mpsloaded.push(function() {
    mps._d('[mps/hb] MPS Loaded');
    mps._reqs.hb['mpsload']=mps._elapsed('',true);
  });
  mps._queue.mpsready.push(function() {
    mps._d('[mps/hb] MPS Ready');
    mps._reqs.hb['mpsready']=mps._elapsed('',true);
  });
  mps._queue.gptloaded.push(function() {
    mps._d('[mps/hb] GPT Loaded');
    mps._reqs.hb['gptload']=mps._elapsed('',true);
  });
  mps._queue.gptloaded.push(function() {
    if(mps.cnbc.hb.a9pubid) {
      mps._d('[mps/hb] A9: fetchBids');
      mps.cnbc.hb.a9slots=mps.cnbc.hb.a9slots||[];
      for(var i in mps._advars[mps._loadset]) {
        if(i=='_oop') continue;
        var adobj = gpt[mps._advars[mps._loadset][i]], slot = {};
        if(!adobj || !adobj.getSlotElementId || !adobj.getAdUnitPath || !adobj.getSizes  || !adobj.getTargetingMap) continue;
        var targ = adobj.getTargetingMap();
        if(targ.nohb && targ.nohb.indexOf('a9')>-1) {
          mps._d('[mps/hb] A9: skipping '+i+' (nohb=a9)');
          continue;
        }
        slot.slotID = adobj.getSlotElementId();
        slot.slotName = adobj.getAdUnitPath();
        // clean slot by removing trailing numbers
        if(slot.slotID.indexOf('-') > -1){
          slot.slotID = slot.slotID.slice(0,slot.slotID .lastIndexOf("-"));
          slot.slotName = slot.slotID;
        }
        if(mps.getResponsiveSet && mps.responsiveslots && mps.responsiveslots[mps._loadset] && mps.responsiveslots[mps._loadset][i]) {
          slot.sizes = mps.responsiveslots[mps._loadset][i][mps.getResponsiveSet()];
          mps._d('[mps/hb] responsive slot sizes: ' + slot.sizes);
          if( slot.sizes == 'NONE' ) { 
            mps._d('[mps/hb] A9 skipped size: NONE ' + slot.slotID);
            continue; 
          }
        }
        if(!slot.sizes) {
          var sizeobj = adobj.getSizes();
          slot.sizes = [];
          for(var ii in sizeobj){ 
            mps._d('[mps/hb] a9 no responsive slot size: ' + sizeobj[ii].l + ' : ' + sizeobj[ii].j);
            slot.sizes.push([sizeobj[ii].l,sizeobj[ii].j])
          };
        }
        mps.cnbc.hb.a9slots.push(slot);
      }
      if(mps.cnbc.hb.a9slots.length) {
        mps._d('[mps/hb] A9: Passing '+mps.cnbc.hb.a9slots.length+' ad slots',mps.cnbc.hb.a9slots);
        // apstag.fetchBids...
        apstag.fetchBids({slots:mps.cnbc.hb.a9slots, timeout:mps.cnbc.hb.a9timeout}, function(bids){
          apstag.setDisplayBids();
          mps._d('[mps/hb] A9: Loaded');
          mps._reqs.hb['a9_loaded']=mps._elapsed('',true);
          setTimeout(function () {
						mps.cnbc.hb._ixready = 1;
						mps._d('[mps/hb] CONTINUE startAdExecution (IX+A9, timeout:' + mps.cnbc.hb.ixtimeout + 'ms)');
						mps.cnbc.hb.startAdExecution();
					}, mps.cnbc.hb.ixtimeout);
        });
      } else {
        setTimeout(function () {
					mps.cnbc.hb._ixready = 1;
					mps._d('[mps/hb] CONTINUE startAdExecution (IX (no a9pubid), timeout:' + mps.cnbc.hb.ixtimeout + 'ms)');
					mps.cnbc.hb.startAdExecution();
				}, mps.cnbc.hb.ixtimeout);
      }
    } else {
      setTimeout(function () {
        mps.cnbc.hb._ixready = 1;
        mps._d('[mps/hb] CONTINUE startAdExecution (IX, timeout:' + mps.cnbc.hb.ixtimeout + 'ms)');
        mps.cnbc.hb.startAdExecution();
      }, mps.cnbc.hb.ixtimeout);
    }
  });
  return 1;
}
mps.cnbc.hb.startAdExecution = function(a) {
	console.warn('[mps/hb] HB startAdExecution begun');
  mps._queue.gptloaded.push(function(){
    mps.cnbc.hb.loadedads = 1;
    var refreshobs=[]; mps.cnbc.hb._initialads=mps.cnbc.hb._initialads||{}; mps.cnbc.hb._initialads[mps._loadset]=[];
    for(var sloti in mps._slotscalled[mps._loadset]) {
      //if(sloti=='_oop') continue;
      refreshobs.push(gpt[mps._advars[mps._loadset][sloti]]);
      mps.cnbc.hb._initialads[mps._loadset].push(sloti);
      mps._reqs.hb['adcall-'+mps._loadset+'-'+sloti] = mps._elapsed('',true);
    }
    mps._d('[mps/hb] startAdExecution: '+mps.cnbc.hb._initialads[mps._loadset].join(', '));
    googletag.pubads().refresh(refreshobs,{changeCorrelator:false});
    mps._reqs.hb['start_ad_execution']=mps._elapsed('',true);
  });
  return 1;
}
mps._checkQS=function(a){return"string"==typeof a&&a?!1!==mps._get(a)||!1!==mps._get(a.toLowerCase())||!1!==mps._get(a.toUpperCase())?!0:!1:!1};
mps.cnbc.hb.execute();
/* <END> Header Bidding (v4.9cnbc) */



//--> HEADER BIDDING CONFIG [cnbc-web]
mps.hb = mps.hb || {}; 
/*=======HB VENDORS=======*/
mps.hb.a9pubid = '3219';
mps.hb.ixjs =   '185796-151042474895997.js';
mps.hb.moatyi = '';
/*=======OPTIONAL CONFIG=======*/
mps.hb.a9timeout = 2000;
mps.hb.ixtimeout = 2000;
mps.hb.moatyitimeout = 2000;
mps.hb.a9sisectoverride = '';



/* js/core/header-bidding.js */

/**
 * Created on 2/20/19
 * Header Bidding (v8)
 * Authored by rrajkowski, kenbrocx
 * Jira ticket MPS-3438*
 */

/** @namespace */
mps.hb = mps.hb || {};
mps.hb.executed = 0;
mps.hb._version = 8.0;
mps.hb._core = true;

// @TODO Exchanges work with mpsopts.activeload
// @TODO Exchanges work with loadset > 0,  mps.cloneAd, mps.refreshAds
// @TODO Remove call to mps._detect.load
// @TODO Use promises instead of timeouts/callbacks
// @TODO Investigate golf slotiv getElementId issue
// @TODO convert mps._adexecuteCallback() to mps._queue.adexecute.push()

mps.hb.a9timeout = mps.hb.a9timeout||2000;
mps.hb.ixtimeout = mps.hb.ixtimeout||2000;
mps.hb.moatyitimeout = mps.hb.moatyitimeout||2000;
mps.hb.kvinsertcheckinterval = mps.hb.kvinsertcheckinterval||250;
mps.hb.a9sisectoverride = mps.hb.a9sisectoverride ||'';
mps.hb.loadedads = mps.hb.loadedads||0;
mps.hb.nohb = mps.hb.nohb || {};
mps.hb.nohb.a9 = mps.hb.nohb.a9 || [];
mps.hb.excluded = mps.hb.excluded || [];
mps.hb.previousloadset = mps.hb.previousloadset || -1;
mps.hb.a9sizes = mps.hb.a9sizes||['300,250','300,600','728,90','970,66','970,90','970,90','970,250','1400,600'];
/**
 * mps.hb.execute
 * Init HB execution
 * @return {boolean}
 */
mps.hb.execute = function() {
  if (typeof(mps.hb.customConfig) === 'function'){
    mps.hb.customConfig();
  }
  if (typeof(mps.hb.executeCheck) === 'function' && !mps.hb.executeCheck() && !mps._checkQS('ENABLEHB')) {
    mpsopts.skipdisableinitialload = 1;
    mps._d('[mps:hb] HEADER BIDDING DISABLED (executeCheck)');
    return false;
  }
  if (mps._checkQS('DISABLEHB') || (!mps.hb.a9pubid && !mps.hb.ixjs && !mps.hb.moatyi)) {
    mpsopts.skipdisableinitialload = 1;
    mps._d('[mps:hb] SKIPPED (DISABLEHB)');
    return false;
  } else {
    mpsopts.skipdisableinitialload = 0;
    googletag.cmd.push(function() {
      googletag.pubads().disableInitialLoad();
    });
  }
  return mps.hb.executeCall();
};
mps.hb.executeCall = function() {
  mps._reqs.hb = mps._reqs.hb || {};
  mps.hb.executed=1;
  mps.hb._gptrefreshes = mps.hb._gptrefreshes || {};
  mps.hb._gptrefreshes.initial = mps.hb._gptrefreshes.initial || [];
  mps.hb._gptrefreshes.adexecute = mps.hb._gptrefreshes.adexecute || [];
  mps._d('[mps:hb] Starting Execution v8.0 (CORE)');
  // Load moatyi
  if (mps.hb.moatyi) {
    mps.hb.loadMoatYI();
  }
  // Load ixjs
  if (mps.hb.ixjs) {
    mps.hb.loadIX();
  }
  // Load a9pubid
  if(mps.hb.a9pubid && (typeof(apstag) !== 'object')) {
    mps.hb.loadA9();
  }
  mps._queue.mpsready.push(function() {
    mps._d('[mps:hb] Loaded MPS: '+mps._elapsed());
    mps._reqs.hb.mpsready = mps._elapsed('', true);
  });
  mps._queue.gptloaded.push(function() {
    mps._d('[mps:hb] Loaded GPT: '+ mps._elapsed());
    mps._reqs.hb.gptload = mps._elapsed('', true);
  });
  mps._queue.gptloaded.push(function() {
    if (mps.hb.a9pubid) {
      mps._d('[mps:hb] A9: Assembling ad slot data');
      mps.hb.a9slots = mps.hb.a9slots || [];
      mps.hb.a9BuildSlots();
      if (mps.hb.a9slots && mps.hb.a9slots.length) {
        mps.hb.a9FetchBids();
      } else {
        mps.hb._a9ready = 1;
        mps.hb.startAdExecution();
      }
    } else {
      mps._d('[mps:hb] CONTINUE startAdExecution (skip A9)');
      mps.hb.startAdExecution();
    }
  });
  return true;
};
/**
 * mps.hb.loadMoatYI
 * Loads the Moat Yield Intelligence script
 * @return {boolean}
 */
mps.hb.loadMoatYI = function(){
  try {
    var loadset = mps._loadset || 0;
    mps._reqs.hb.moatyi_begin = mps._elapsed('', true);
    mps.hb.moatyiurl = 'https://z.moatads.com/' + mps.hb.moatyi + '/yi.js';
    mps._loadJS(mps.hb.moatyiurl, function () {
      mps.hb._moatyiready = 1;
      mps._d('[mps:hb] Loaded MoatYI: ('+mps.hb.moatyi+') ' +mps._elapsed());
      mps._reqs.hb.moatyi_loaded = mps._elapsed('', true);
    });
    setTimeout(function () {
      if (!mps.hb._moatyiready) {
        mps.hb._moatyiready = 1;
        mps._d('[mps:hb] CONTINUE startAdExecution (skip MOATYI, timeout:' + mps.hb.moatyitimeout + 'ms)');
        mps.hb.startAdExecution();
      }
    }, mps.hb.moatyitimeout);
    if (debugmode.log && window.moatPrebidApi && typeof(window.moatPrebidApi.enableLogging) === 'function') {
      mps._d('[mps:hb] MoatYI: typeof(window.moatPrebidApi.enableLogging)');
      window.moatPrebidApi.enableLogging();
    }
    mps._queue.adexecute.push(function () {
      mps.hb.moatyislots = mps.hb.moatyislots || [];
      for (var i in mps._advars[loadset]) {
        var adobj = gpt[mps._advars[loadset][i]];
        if (!adobj || !adobj.getSlotElementId || !adobj.getAdUnitPath || !adobj.getSizes || !adobj.getTargetingMap){
          mps._d('[mps:hb] MoatYI: skipped adobj missing data');
          continue;
        }
        var exclude = adobj !== null && adobj.getCategoryExclusions();
        if (exclude && exclude.indexOf('headerbid') > -1) {
          mps._d('[mps:hb] MoatYI: skip cat exclusion of headerbidding '+ adobj.getCategoryExclusions());
          continue;
        }
        if (i === '_oop' || !adobj || !adobj.setTargeting){
          continue;
        }
        mps._d('[mps:hb] MoatYI: pushing moat to slot ' + adobj.getSlotId());
        mps.hb.moatyislots.push(i);
      }
      if (window.moatPrebidApi && window.moatPrebidApi.slotDataAvailable()) {
        mps._d('[mps:hb] MoatYI: Call setMoatTargetingForAllSlots for ' + mps.hb.moatyislots.length + ' ad slots');
        window.moatPrebidApi.setMoatTargetingForAllSlots();
      } else {
        mps._d('[mps:hb] MoatYI: Call setMoatTargetingForAllSlots err window.moatPrebidApi.slotDataAvailable() doesnt exist');
      }
    });
  } catch(err) {
    mps._d('[mps:hb] MoatYI: error');
    mps._errorCallback(err, 'mps.hb.loadMoatYI');
  }
  return true;
};
/**
 * mps.hb.loadIX
 * Loads the Index Exchange script
 * @return {boolean}
 */
mps.hb.loadIX = function () {
  try {
    if (mps.hb.ixjs.split('.').pop() === 'js') {
      mps.hb.ixjs = mps.hb.ixjs.slice(0, -3);
    }
    if (!mps.hb._ixready) {
      mps.hb.ixurl = 'https://js-sec.indexww.com/ht/p/' + mps.hb.ixjs + '.js';
      mps._reqs.hb.ix_begin = mps._elapsed('', true);
      mps._loadJS(mps.hb.ixurl, function () {
        mps.hb._ixready = 1;
        mps._d('[mps:hb] Loaded IX: (' + mps.hb.ixjs + ') ' + mps._elapsed());
        mps._reqs.hb.ix_loaded = mps._elapsed('', true);
        mps.hb.startAdExecution();
      });
      setTimeout(function () {
        mps.hb._ixready = 1;
        mps._d('[mps:hb] CONTINUE startAdExecution (skip IX, timeout:' + mps.hb.ixtimeout + 'ms)');
        mps.hb.startAdExecution();
      }, mps.hb.ixtimeout);
    }
  } catch(err){
    mps._errorCallback(err, 'mps.hb.loadIX');
  }
  return true;
};
/**
 * mps.hb.loadA9
 * Loads the a9 (Amazon) script
 * @return {boolean}
 */
mps.hb.loadA9 = function(){
  try {
    mps._reqs.hb.a9_begin=mps._elapsed('',true);
    !function(a9,a,p,s,t,A,g){if(a[a9])return;function q(c,r){a[a9]._Q.push([c,r])}a[a9]={init:function() {q("i",arguments)},fetchBids:function(){q("f",arguments)},setDisplayBids:function(){},targetingKeys:function(){return[]},_Q: []};A=p.createElement(s);A.async=!0;A.src=t;g=p.getElementsByTagName(s)[0];g.parentNode.insertBefore(A,g)} ("apstag",window,document,"script","//c.amazon-adsystem.com/aax2/apstag.js");
    var a9sisect = mpscall.cat ? mpscall.cat : 'PAGE';
    a9sisect = mpscall.site+'|'+a9sisect.split('|')[0];
    a9sisect = mps.hb.a9sisectoverride ? mps.hb.a9sisectoverride : a9sisect;
    a9sisect = a9sisect.substring(0,50);
    mps._d('[mps:hb] A9: Setting SI Section ('+a9sisect+')');
    apstag.init({
      pubID: mps.hb.a9pubid,
      adServer: 'googletag',
      params: {
        si_section: a9sisect
      }
    });
  } catch(err){
    mps._errorCallback(err, 'mps.hb.loadA9');
  }
};
/**
 * mps.hb.a9BuildSlots
 * Loop through mps._advars and define a9slots
 * {return} {mps.hb.a9slots|Array}
 */
mps.hb.a9BuildSlots = function (adobj) {
  var loadset = mps._loadset||0;
  var a9slotnames = [];
  for (var i in mps._advars[loadset]) {
    if (i === '_oop'){
      continue;
    }
    var adobj =  gpt[mps._advars[loadset][i]],
        slot = {};
    if (!adobj || !adobj.getSlotElementId || !adobj.getAdUnitPath || !adobj.getSizes || !adobj.getTargetingMap){
      continue;
    }
    var targ = adobj.getTargetingMap();
    if(targ.nohb && targ.nohb.indexOf('a9')>-1) {
      mps.hb.nohb.a9.push(i);
      continue;
    }
    slot.slotID = adobj.getSlotElementId();
    slot.slotName = adobj.getAdUnitPath() + '/' + adobj.getSlotElementId();
    if (mps.getResponsiveSet && mps.responsiveslots && mps.responsiveslots[loadset] && mps.responsiveslots[loadset][i]) {
      slot.sizes = mps.responsiveslots[loadset][i][mps.getResponsiveSet()];
    }
    if (slot.sizes && !slot.sizes.length) {
      slot.sizes = mps.hb.getSlotSizes(adobj);
    }
    var slotsizes = slot.sizes || [];
    var approvedSizesOnly = true;
    var unapprovedSize = "";
    var i_slotsizes = 0;
    while (slotsizes[i_slotsizes]) {
      sz = slotsizes[i_slotsizes];
      if (typeof(sz) != 'object'){
        approvedSizesOnly = false;
        unapprovedSize = sz;
      } else if (!mps.hb.a9sizes.includes(sz.join(','))){
        approvedSizesOnly = false;
        unapprovedSize = sz;
      }
      i_slotsizes++;
    }
    if(approvedSizesOnly === false){
      mps._d('^[mps:hb] A9 skipped for slot : '+i+' : due to size ' + unapprovedSize);
      continue;
    }
    if( a9slotnames.indexOf(i) == -1 ){
      mps.hb.a9slots.push(slot);
    } else {
      a9slotnames.push(i);
      mps._d('[mps:hb] EXCLUDED already called: '+i);
    }
  }
  if (mps.hb.nohb.a9 && mps.hb.nohb.a9.length) {
    mps._d('^[mps:hb] EXCLUDED "nohb=a9" (' + mps.hb.nohb.a9.length + '): ' + mps.hb.nohb.a9.join(', '));
  }
  return mps.hb.a9slots;
};
/**
 * mps.hb.a9FetchBids reduce complexity (sonar)
 * @return {boolean}
 */
mps.hb.a9FetchBids = function() {
  mps.hb.a9slots = mps.hb.a9slots || [];
  mps._d('[mps:hb] A9: Passing ' + mps.hb.a9slots.length + ' ad slots');
  apstag.fetchBids({
    slots: mps.hb.a9slots,
    timeout: mps.hb.a9timeout
  }, function (bids) {
    apstag.setDisplayBids();
    var adcount = mps._keys(mps._advars[mps._loadset]).length-1 || 1;
    mps._d('[mps:hb] Loaded A9: ('+mps.hb.a9pubid+') '+ mps._elapsed());
    mps._d('[mps:hb] fetchBids A9: ' + JSON.stringify(bids.slice(bids.length-adcount, bids.length-1)));
    mps._reqs.hb.a9_loaded = mps._elapsed('', true);
    mps.hb._a9ready = 1;
    mps.hb.startAdExecution();
  });
  return true;
};
/**
 * mps.hb.getSlotSizes
 * Fetches size array if not defined
 * @param {object} adobj
 * @return {Array} sizes
 */
mps.hb.getSlotSizes = function(adobj){
  var sizeobj = adobj.getSizes();
  var sizes = [];
  for (var ii in sizeobj) {
    var onesize = mps.getValueWithoutKey(sizeobj[ii]);
    sizes.push([onesize[0], onesize[1]]);
  }
  return sizes;
};
/**
 * mps.hb.startAdExecution
 * Main execution for all HB exchanges
 * @return {boolean}
 */
mps.hb.startAdExecution = function() {
  var loadset = mps._loadset;
  mps.hb.previousloadset = loadset;
  if (mps.hb.ixjs && !mps.hb._ixready) {
    mps._d('[mps:hb] SKIP startAdExecution (waiting for ixjs)');
    return false;
  }
  if (mps.hb.moatyi && !mps.hb._moatyiready) {
    mps._d('[mps:hb] SKIP startAdExecution (waiting for moatyiready)');
    return false;
  }
  if (mps.hb.a9pubid && !mps.hb._a9ready) {
    mps._d('[mps:hb] SKIP startAdExecution (waiting for a9ready)');
    return false;
  }
  if (mps.hb._adexecstarted === 1 && (mps.hb.previousloadset === mps._loadset)) {
    mps._d('[mps:hb] SKIP startAdExecution (already called on loadset) - '+ mps._loadset);
    return false;
  }
  mps.hb._adexecstarted = 1;
  if (mps._kvinsert && mps._kvinsert.pending.length > 0) {
    mps._d('[mps:hb] SKIP startAdExecution (waiting for kvinserts to complete)');
    setTimeout(function() {
      mps.hb.startAdExecution();
    }, mps.hb.kvinsertcheckinterval);
    return false;
  }
  mps._queue.gptloaded.push(function() {
    var refreshobs = [];
    mps.hb._initialads = mps.hb._initialads || {};
    mps.hb._initialads[loadset] = [];
    if (mps._detect && mps._detect.load){
      mps._detect.load();
    }
    mps.hb.loadedads = 1;
    for (var sloti in mps._slotscalled[loadset]) {
      mps.hb._initialads[loadset].push(sloti);
    }
    for (var i in mps.hb._initialads[loadset]) {
      var sloti = mps.hb._initialads[loadset][i],
          slotiv = gpt[mps._advars[loadset][sloti]];
      var exclude = slotiv.getCategoryExclusions();
      if (exclude &&  exclude.indexOf('headerbid') > -1) {
        mps.hb.excluded.push(sloti);
      }
      if (!slotiv){
        continue;
      }
      refreshobs.push(slotiv);
      mps.hb._gptrefreshes.initial.push(slotiv.getSlotElementId());
      mps._reqs.hb['adcall-' + loadset + '-' + sloti] = mps._elapsed('', true);
    }
    if (mps.hb.excluded.length) {
      mps._d('^[mps:hb] EXCLUDED "!c=headerbid" INIT(' + mps.hb.excluded.length + '): ' + mps.hb.excluded.join(', '));
    }
    mps._d('[mps:hb] startAdExecution: ' + mps.hb._initialads[loadset].join(', '));
    googletag.pubads().refresh(refreshobs, {
      changeCorrelator: false
    });
    mps._reqs.hb.start_ad_execution = mps._elapsed('', true);
  });
  return true;
};
/**
 * mps._adexecuteCallback
 * Fallback for normal HB execution is delayed or skipped
 * @param {string} slot
 * @param {number} loadset
 * @return {boolean}
 * @private
 */
mps._adexecuteCallback = function(slot, loadset) {
  if (!mps._bool(mpsopts.skipdisableinitialload)) {
    mps._reqs.hb = mps._reqs.hb || {};
    mps.hb._executedads = mps.hb._executedads || {};
    if (!mps.hb.loadedads) {
      mps._d('[mps:hb] WAIT: ' + loadset + '/' + slot + ' (adexecuteCallback)' + mps._elapsed('', true));
      return false;
    }
    var adobj = gpt[mps._advars[loadset][slot]];
    if (mps.hb._executedads[loadset] && mps.hb._executedads[loadset].indexOf(slot) > -1) {
      mps._d('[mps:hb] SKIP: ' + loadset + '/' + slot + ' (adexecuteCallback)' + mps._elapsed());
      return false;
    }
    var exclude = adobj !== null && adobj.getCategoryExclusions() || [];
    if (exclude &&  exclude.indexOf('headerbid') > -1) {
      mps.hb.excluded.push(slot);
      mps._d('^[mps:hb] EXCLUDED "!c=headerbid": ' + slot);
    }
    mps._queue.gptloaded.push(function() {
      setTimeout(function() {
        mps._d('[mps:hb] CALL: ' + loadset + '/' + slot + ' (adexecuteCallback) ' + mps._elapsed());
        mps._reqs.hb['adcall-' + loadset + '-' + slot] = mps._elapsed('', true);
        mps.hb._gptrefreshes.adexecute.push(adobj.getSlotElementId());
        googletag.pubads().refresh([adobj], {
          changeCorrelator: false
        });
        mps.hb._executedads[loadset] = mps.hb._executedads[loadset] || [];
        mps.hb._executedads[loadset].push(slot);
      }, 50);
    });
  }
};




/* js/core/post-include-autoloader.js */

mps._debug('[mps:postLoader] (mpsopts) '+JSON.stringify(mpsopts));

//(cat) resplit cat string
mps._ext._cats = (typeof(mpscall.cat)=='string') ? mpscall.cat.split('|') : [];
lastcat = mps._ext._cats[mps._ext._cats.length-1];
//(cat) set depth limit on cat level
mpsopts.maxcats = (typeof(mpsopts.maxcats)=='string') ? parseInt(mpsopts.maxcats) : mpsopts.maxcats||0;
if(mpsopts.maxcats > 0  && mps._ext._cats.length > mpsopts.maxcats) {
  mps._ext._catscut = mps._ext._cats.splice(mpsopts.maxcats+1);
}
//(cat) remove last level if filename or numeric
if(!isNaN(lastcat) || lastcat.lastIndexOf('.')>0 || lastcat.indexOf('index')===0) {
  mps._ext._cats.splice(mps._ext._cats.length-1,mps._ext._cats.length);
}
//(cat) attach prefix
mpsopts.catprefix = mps._trim(mpsopts.catprefix,'| ');
if(mpsopts.catprefix != '') {
  mps._ext._cats = mps._merge(mpsopts.catprefix.split('|'),mps._ext._cats);
}
//(cat) join and override existing value
mpscall.cat = mps._ext._cats.join('|');

mps._debug('[mps:postLoader] (mpscall) '+JSON.stringify(mpscall));
if(parseInt(debugmode.log) == 2) mpscall.CACHESKIP=1;

//--> CREATE URL AND REQUEST,
mps.requesturl = mps._ext.mpsRequestUrl();

//--> BACKWARDS COMPATIBILITY
mpsGetAd=mps.getAd; mpsrequesturl=mps.requesturl; mps.writeHeader=function(){};

/* ----- GPT Main ----- */
/* GPT Main - async mode only */
var _mpshead = document.getElementsByTagName('head')[0];
mps._adLoadCallbackObj = [];

// Append MPS styles.
var _mpsstyles = document.createElement('style');
_mpsstyles.style.type = 'text/css';
_mpsstyles.cssText = '.mps-gpt-hidden { display: none; }';
_mpshead.appendChild(_mpsstyles);

// http request to get json.
mps._gptloaded = false;
mps._adloads=mps._adloads||{};       // global adloads object
mps._correlator=mps._correlator||{}; // global correlator array
mps._adobs=mps._adobs||{};
mps._adslots=mps._adslots||{};
mps._advars=mps._advars||{};
mps._slotscalled=mps._slotscalled||{};
mps._slotscalled[mps._loadset || 0]={};
mps._slotsdisabled=mps._slotsdisabled||{};
mps._slotsdisabled[mps._loadset || 0]={};
mps._rsizemap={};
mps._resetrsizemap = mps._resetrsizemap || {};
mps.slotsdisabled = mps.slotsdisabled||{};
mps.slotsdisabled[mps._loadset || 0]=[];
mps._gptTargeting = mps._gptTargeting || {};
mps._resetcatexclusion = mps._resetcatexclusion || {};
mps._resettargeting = mps._resettargeting || {};
if(typeof mpscall != 'undefined' && typeof(mpscall.path)!='undefined'){
  mps._resettargeting[mpscall.path] = {};
}
mps.adslots={}; mps.advars={}; mps._advarprefix = 'gpt'||{}; mps.responsiveslots=mps.responsiveslots||{}; mps.responsiveslots[mps._loadset || 0]={};


//--> CREATE URL AND REQUEST
(function() {
  if (mpsinstance != '') {
    if (!mps._bool(mpsopts.skipautorequest) && mps._ext.nowrite != 1) {
      if (mps._ext.nowrite === 2) {
        // Standard: async MPS Request
        mps._xhr();
        mps._debug('[mps:postLoader] REQUEST ASYNC:' + mps._protocol() + '//' + mps.requesturl + ' ' + mps._elapsed());
      }
      else {
        // Legacy: document.write MPS Request
        document.write('<scr' + 'ipt id="mps-request-' + mps._loadset + '" src="' + mps._protocol() + '//' + mps.requesturl + '"></scr' + 'ipt>');

        // Legacy: document.write _execgpt, and _execgptinit
        document.write('<scr' + 'ipt id="mps-exec-gpt-init">mps._gptcmd.push(function(){mps._execgptinit();});</scr' + 'ipt>');
        document.write('<scr' + 'ipt id="mps-exec-gpt">mps._gptcmd.push(function(){mps._execgpt();});</scr' + 'ipt>');

        mps._debug('[mps:postLoader] REQUEST DOCUMENT.WRITE: ' + mps._protocol() + '//' + mps.requesturl);
      }
      mps._ext._set += 1;
      mps._reqs[mps._ext._set] = {'mpsready': mps._elapsed('', true)};
    } else if (mps._bool(mpsopts.skipautorequest) || parseInt(mps._ext.nowrite) === 1) {
      var _skipautoreq = mpsopts.skipautorequest ? 'mpsopts.skipautorequest=' + mpsopts.skipautorequest : 'nowrite=' + mps._ext.nowrite;
      mps._debug('^[mps:postLoader] Skipped MPS Request: ' + _skipautoreq);
    } else {
      mps.makeRequest();
    }
  }
  delete(mps.qs);
})();



/* js/advertising/pixelman.js */

mps.execute_pixelman_js = function() {
  mps=mps||{}; debugmode=debugmode||{};
  debugmode.log&&window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  // Requires js/advertising/postscribe.js [include htmlParser]
  
  // Delay mps._execAd until all requirements have completed: 0/1
  mps._delays=mps._delays||{};
  mps._delays.kvtimeout = mps._delays.kvtimeout || 3000;
  mps._kvinsert = {
    // required, before complete
    pending: [],
    // after complete finishes
    ready: [],
    // force complete after timeout
    timeout: [],
  
    require: function(type) {
      if(!type || type.length==0){
        mps._debug('^[PM:kvinsert] invalid require()');
        return false;
      }
      if( mps._kvinsert.pending.indexOf(type) > -1  || mps._kvinsert.ready.indexOf(type) > -1) {
        mps._debug('[PM:kvinsert] SKIPPED: '+type+' '+mps._elapsed());
        return false;
      }
      if(mps._kvinsert.pending.indexOf(type) == -1){
        mps._kvinsert.pending.push(type);
      }
      mps._debug('[PM:kvinsert required: '+type+' '+mps._elapsed());
      setTimeout(function () {
        if (mps._kvinsert.ready.indexOf(type) == -1) {
          mps._debug('^[PM:kvinsert] Force complete: '+type+' after '+mps._delays.kvtimeout+'ms');
          mps._kvinsert.complete(type, true);
        }
      }, mps._delays.kvtimeout);
      return this.status();
    },
  
    // type=[str], OPTIONAL force[bool] complete
    complete: function(type,force){
      if(!type || type.length===0){
        mps._debug('^[PM:kvinsert invalid complete()');
        return false;
      }
      force = force || false;
      mps._reqs = mps._reqs || {};
      mps._reqs[mps._loadset] = mps._reqs[mps._loadset] || {};
      mps._reqs[mps._loadset].kvinserts = mps._reqs[mps._loadset].kvinserts || {};
      if (this.pending.indexOf(type) > -1) {
        var i = this.pending.indexOf(type);
        this.pending.splice(i, 1);
      }
      if(this.timeout.indexOf(type) == -1) {
        // force complete
        if (force) {
          this.timeout.push(type);
          this.pending = [];
          return false;
        }
        else {
          // good complete
          mps._reqs[mps._loadset].kvinserts['kv_' + type] = mps._elapsed('', true);
          if (this.ready.indexOf(type) == -1) {
            this.ready.push(type);
          }
          // Set Page Targeting
          this.injectgpt();
          if (typeof mps.kvcomplete === 'function') {
            mps.kvcomplete(type);
          }
          mps._debug('[PM:kvinsert complete: ' + type + ' ' + mps._elapsed());
          return this.status();
        }
      }
    },
  
    status: function(){
      var state = true;
      if(this.pending.length === 0) {
        state = 1;
      }
      if(this.pending.length > 0) {
        state = false;
      }
      return state;
    },
  
    injectgpt:  function() {
      if (typeof(__nbcudigitaladops_inject) == 'object' && __nbcudigitaladops_inject.getGPT) {
        var _GPT_params = __nbcudigitaladops_inject.getGPT();
        for (var _key in _GPT_params) {
          if (_GPT_params.hasOwnProperty(_key) &&  mps._keys(mps._targeting).indexOf(_key) == -1) {
            mps._debug('[PM:injectgpt] Page targeting: '+_key);
            mps._setPageTargeting(_key, _GPT_params[_key]);
          }
        }
      }
    }
  };
  
  __nbcudigitaladops_dtparams = "pm=1;";
  
  // Pixelman Header Methods
  __nbcudigitaladops_inject = {
    version: '3.0',
    init : function(){
      // legacy variables (requires optimisation)
      this.c_name = 'adops_master_kvs';
      this.c_expire_hour = 1440;
      this.qsparam = 'dart';
      this.sitefilter = ['google.com','go','ask.com','as','aol.com','ao','yahoo.com','ya'];
      this.drt_r = 'ref';
      if(this.qspass()) {
        this.dtprm( this.qspass() );
      }
      if(typeof this.ref == 'function'&& typeof this.dtprm == 'function'){
        this.dtprm( this.ref() );
      }
      if(typeof this.gc == 'function' && this.c_name) {
        this.dtprm( this.gc(this.c_name) );
      }
    },
    dtprm : function(p){
      // set object
      if(p==''||p==undefined) {
        return false;
      }
      p = mps._trim(p,';') +';';
      if(__nbcudigitaladops_dtparams.indexOf(p) == -1) {
        __nbcudigitaladops_dtparams += p;
        this._setGPTGlobal();
      }
      return __nbcudigitaladops_dtparams;
    },
    gc : function(n){
      var c_val = (n && mps._ck && typeof mps._ck.r == 'function') ? mps._ck.r(n) : false;
      c_val = (c_val == null) ? '' : c_val;
      return c_val;
    },
    sc: function(cd,cn,ch){
      cn = (cn!=undefined) ? cn.toString().replace('null','') : this.c_name;
      ch = ch || this.c_expire_hour;
      var days = (ch/24);
      if((!cn || !mps._ck || typeof mps._ck.w != 'function')) {
        return false;
      }
      mps._ck.w(cn,cd,days);
    },
    qspass: function(){
      var qsval = this.getQSValue(this.qsparam);
      if(qsval!=''){
        qsval = this.qsparam+'='+qsval+';';
      }
      return qsval;
    },
    getQSValue: function(p){
      var qs=location.search+'';
      // Find p after another param, avoid mid-param match
      var i=qs.indexOf('&'+p+"=");
      // Find p as the first param
      if(-1==i){
        i=qs.indexOf('?'+p+"=");
      }
      if(-1==i){
        return '';
      }
      var len=i+p.length+2;
      var end=qs.indexOf("&", len);
      return qs.substring(len,end<0?qs.length:end);
    },
    ref: function(){
      var r = document.referrer,dlen = '',ref='',result='';
      r=r.replace(/^https*:\/\//i,'');
      r=r.split('/')[0];
      r=r.split('.');
      if(r!='' && r.length>1){
        ref=r[r.length-2]+'.'+r[r.length-1];
        dlen = r[r.length-2].length;
      }
      this.ref = ref;
      var f = this.sitefilter;
      for(var x=0;x<f.length;x+=2){
        if(f[x].toLowerCase() == this.ref){
          result = f[x+1]+dlen;
        }
      }
      if (result!=''){
        result = this.drt_r+'='+result+';';
      }
      return result;
    },
    getGPT: function(){
      var gpt = {};
      var dtparams = __nbcudigitaladops_dtparams.replace(/;+$/,'').split(/;/);
      for(var x=0;x<dtparams.length;x++){
        var d = dtparams[x].split(/=/);
        gpt[d[0]] = gpt[d[0]] || [];
        gpt[d[0]].push(d[1]);
      }
      for ( var y in gpt ){
        if( gpt.hasOwnProperty(y) ){
          gpt[y] = gpt[y].join(',');
        }
      }
      return gpt;
    },
    _setGPTGlobal: function(){
      var gpt = this.getGPT();
      var gpt_arr = [];
      var gpt_var = '';
      for ( var y in gpt ){
        if( gpt.hasOwnProperty(y) ){
          gpt_arr.push(y+'%3D'+gpt[y]);
        }
      }
      gpt_var = gpt_arr.join('%26');
      __nbcudigitaladops_gptparams = gpt_var;
      return gpt_var;
    }
  };
  
  //init pixel header inclusion
  if(Math.floor(__nbcudigitaladops_inject.version) === 3){
    __nbcudigitaladops_inject.init();
  }
  
  // Pixelman Footer Methods
  __nbcudigitaladops = {
    init : function(){
      __nbcudigitaladops_inject.sc('');
    },
    dtprm : function(p){
      // set cookie
      if(p==''||p==undefined){
        return false;
      }
      p = p.replace(/;+$/,'') + ';';
      var cd = this.gc( this.c_name );
      cd += p;
      this.sc(cd,this.c_name,this.c_expire_hour);
    },
    // Duplicate setcookie function in__nbcudigitaladops (supports legacy pixelman)
    sc: function(cd,cn,ch){
      cn = (cn!=undefined) ? cn.toString().replace('null','') : this.c_name;
      ch = ch || this.c_expire_hour;
      var days = (ch/24);
      if((!cn || !mps._ck || typeof mps._ck.w != 'function')) {
        return false;
      }
      mps._ck.w(cn,cd,days);
    }
  };
  
  // Legacy Pixelman Mapping
  __nbcudigitaladops_header = __nbcudigitaladops;
  __nbcudigitaladops.gc = __nbcudigitaladops_inject.gc || {};
  __nbcudigitaladops.version = __nbcudigitaladops_inject.version;
  __nbcudigitaladops.c_name = __nbcudigitaladops_inject.c_name || '';
  __nbcudigitaladops.c_expire_hour = __nbcudigitaladops_inject.c_expire_hour || '';
  
  //init pixel footer inclusion
  if(Math.floor(__nbcudigitaladops.version) === 3){
    __nbcudigitaladops.init();
  }
  
  typeof mps._debug == 'function' && mps._debug('[mps:JS] LOADED: Pixelman');
  
}



/* js/advertising/postscribe.js */

mps.execute_postscribe_js = function() {
  // htmlParser used for postscribe.js 1.4.0
  // Based on http://ejohn.org/blog/pure-javascript-html-parser/
  (function(){function d(a,e){a=a||"";e=e||{};for(var b in g)g.hasOwnProperty(b)&&(e.autoFix&&(e["fix_"+b]=!0),e.fix=e.fix||e["fix_"+b]);var k=document.createElement("div"),h={comment:/^\x3c!--/,endTag:/^<\//,atomicTag:/^<\s*(script|style|noscript|iframe|textarea)[\s\/>]/i,startTag:/^</,chars:/^[^<]/},d={comment:function(){var c=a.indexOf("--\x3e");if(0<=c)return{content:a.substr(4,c),length:c+3}},endTag:function(){var c=a.match(t);if(c)return{tagName:c[1],length:c[0].length}},atomicTag:function(){var c=
      d.startTag();if(c){var b=a.slice(c.length);if(b.match(new RegExp("</\\s*"+c.tagName+"\\s*>","i"))&&(b=b.match(new RegExp("([\\s\\S]*?)</\\s*"+c.tagName+"\\s*>","i"))))return{tagName:c.tagName,attrs:c.attrs,content:b[1],length:b[0].length+c.length}}},startTag:function(){if(-1===a.indexOf(">"))return null;var c=a.match(u);if(c){var b={},e={},d=c[2];c[2].replace(v,function(c,a,f,h,q,n){f||h||q||n?n?(b[n]="",e[a]=!0):(f=f||h||q||w.test(a)&&a||"","string"===typeof f&&-1!==f.indexOf("&")&&(k.innerHTML=
      f,f=k.textContent||k.innerText||f),b[a]=f):b[a]=null;d=d.replace(c,"")});return{tagName:c[1],attrs:b,booleanAttrs:e,rest:d,unary:!!c[3],length:c[0].length}}},chars:function(){var c=a.indexOf("<");return{length:0<=c?c:a.length}}},m=function(){for(var c in h)if(h[c].test(a)){var b=d[c]();return b?(b.type=b.type||c,b.text=a.substr(0,b.length),a=a.slice(b.length),b):null}};e.fix&&function(){var b=/^(AREA|BASE|BASEFONT|BR|COL|FRAME|HR|IMG|INPUT|ISINDEX|LINK|META|PARAM|EMBED)$/i,k=/^(COLGROUP|DD|DT|LI|OPTIONS|P|TD|TFOOT|TH|THEAD|TR)$/i,
      d=[];d.last=function(){return this[this.length-1]};d.lastTagNameEq=function(b){var a=this.last();return a&&a.tagName&&a.tagName.toUpperCase()===b.toUpperCase()};d.containsTagName=function(b){for(var a=0,c;c=this[a];a++)if(c.tagName===b)return!0;return!1};var h=function(a){a&&"startTag"===a.type&&(a.unary=b.test(a.tagName)||a.unary,a.html5Unary=!/\/>$/.test(a.text));return a},g=m,p=function(){a="</"+d.pop().tagName+">"+a},f={startTag:function(b){var c=b.tagName;"TR"===c.toUpperCase()&&d.lastTagNameEq("TABLE")?
      (a="<TBODY>"+a,l()):e.fix_selfClose&&k.test(c)&&d.containsTagName(c)?d.lastTagNameEq(c)?p():(a="</"+b.tagName+">"+a,l()):b.unary||d.push(b)},endTag:function(a){d.last()?e.fix_tagSoup&&!d.lastTagNameEq(a.tagName)?p():d.pop():e.fix_tagSoup&&(g(),l())}},l=function(){var b=a,c=h(g());a=b;if(c&&f[c.type])f[c.type](c)};m=function(){l();return h(g())}}();return{append:function(b){a+=b},readToken:m,readTokens:function(a){for(var b;(b=m())&&(!a[b.type]||!1!==a[b.type](b)););},clear:function(){var b=a;a="";
    return b},rest:function(){return a},stack:[]}}var g=function(){var a={},e=this.document.createElement("div");e.innerHTML="<P><I></P></I>";a.tagSoup="<P><I></P></I>"!==e.innerHTML;e.innerHTML="<P><i><P></P></i></P>";a.selfClose=2===e.childNodes.length;return a}(),u=/^<([\-A-Za-z0-9_]+)((?:\s+[\w\-]+(?:\s*=?\s*(?:(?:"[^"]*")|(?:'[^']*')|[^>\s]+))?)*)\s*(\/?)>/,t=/^<\/([\-A-Za-z0-9_]+)[^>]*>/,v=/(?:([\-A-Za-z0-9_]+)\s*=\s*(?:(?:"((?:\\.|[^"])*)")|(?:'((?:\\.|[^'])*)')|([^>\s]+)))|(?:([\-A-Za-z0-9_]+)(\s|$)+)/g,
      w=/^(checked|compact|declare|defer|disabled|ismap|multiple|nohref|noresize|noshade|nowrap|readonly|selected)$/i;d.supports=g;d.tokenToString=function(a){var e={comment:function(b){return"\x3c!--"+b.content},endTag:function(b){return"</"+b.tagName+">"},atomicTag:function(b){return e.startTag(b)+b.content+e.endTag(b)},startTag:function(b){var a="<"+b.tagName,e;for(e in b.attrs){var a=a+(" "+e),d=b.attrs[e];if("undefined"==typeof b.booleanAttrs||"undefined"==typeof b.booleanAttrs[e])a+='="'+(d?d.replace(/(^|[^\\])"/g,
          '$1\\"'):"")+'"'}b.rest&&(a+=b.rest);return a+(b.unary&&!b.html5Unary?"/>":">")},chars:function(a){return a.text}};return e[a.type](a)};d.escapeAttributes=function(a){var e={},b;for(b in a){var d=a[b];e[b]=d&&d.replace(/(^|[^\\])"/g,'$1\\"')}return e};for(var r in g)d.browserHasFlaw=d.browserHasFlaw||!g[r]&&r;this.htmlParser=d})();
  
  //  postscribe.js 1.4.0
  //  (c) Copyright 2012-2015 to the present, Krux
  //  postscribe is freely distributable under the MIT license.
  //  For all details and documentation:
  //  http://krux.github.io/postscribe
  /*globals htmlParser:false*/
  (function() {
    // A function that intentionally does nothing.
    function doNothing() {}
  
    // Available options and defaults.
    var OPTIONS = {
      // Called when an async script has loaded.
      afterAsync: doNothing,
      // Called immediately before removing from the write queue.
      afterDequeue: doNothing,
      // Called sync after a stream's first thread release.
      afterStreamStart: doNothing,
      // Called after writing buffered document.write calls.
      afterWrite: doNothing,
      // Allows disabling the autoFix feature of htmlParser
      autoFix: true,
      // Called immediately before adding to the write queue.
      beforeEnqueue: doNothing,
      // Called before writing a token.
      beforeWriteToken: function(tok) { return tok; },
      // Called before writing buffered document.write calls.
      beforeWrite: function(str) { return str; },
      // Called when evaluation is finished.
      done: doNothing,
      // Called when a write results in an error.
      error: function(e) { throw e; },
      // Whether to let scripts w/ async attribute set fall out of the queue.
      releaseAsync: false
    };
  
    var global = this;
  
    var UNDEFINED = void 0;
  
    function existy(thing) {
      return thing !== UNDEFINED && thing !== null;
    }
  
    if(global.postscribe) {
      return;
    }
  
    // Turn on to debug how each chunk affected the DOM.
    var DEBUG_CHUNK = false;
  
    // # Helper Functions
  
    var slice = Array.prototype.slice;
  
    // Is this a function?
    function isFunction(x) {
      return 'function' === typeof x;
    }
  
    // Loop over each item in an array-like value.
    function each(arr, fn, _this) {
      var i, len = (arr && arr.length) || 0;
      for(i = 0; i < len; i++) {
        fn.call(_this, arr[i], i);
      }
    }
  
    // Loop over each key/value pair in a hash.
    function eachKey(obj, fn, _this) {
      var key;
      for(key in obj) {
        if(obj.hasOwnProperty(key)) {
          fn.call(_this, key, obj[key]);
        }
      }
    }
  
    // Set properties on an object.
    function set(obj, props) {
      eachKey(props, function(key, value) {
        obj[key] = value;
      });
      return obj;
    }
  
    // Set default options where some option was not specified.
    function defaults(options, _defaults) {
      options = options || {};
      eachKey(_defaults, function(key, val) {
        if(!existy(options[key])) {
          options[key] = val;
        }
      });
      return options;
    }
  
    // Convert value (e.g., a NodeList) to an array.
    function toArray(obj) {
      try {
        return slice.call(obj);
      } catch(e) {
        var ret = [];
        each(obj, function(val) {
          ret.push(val);
        });
        return ret;
      }
    }
  
    var last = function(array) {
      return array[array.length - 1];
    };
  
    // Test if token is a script tag.
    function isScript(tok) {
      return !tok || !('tagName' in tok) ? !1 : !!~tok.tagName.toLowerCase().indexOf('script');
    }
  
    function isStyle(tok) {
      return !tok || !('tagName' in tok) ? !1 : !!~tok.tagName.toLowerCase().indexOf('style');
    }
  
    // # Class WriteStream
  
    // Stream static html to an element, where "static html" denotes "html without scripts".
  
    // This class maintains a *history of writes devoid of any attributes* or "proxy history".
    // Injecting the proxy history into a temporary div has no side-effects,
    // other than to create proxy elements for previously written elements.
  
    // Given the `staticHtml` of a new write, a `tempDiv`'s innerHTML is set to `proxy_history + staticHtml`.
    // The *structure* of `tempDiv`'s contents, (i.e., the placement of new nodes beside or inside of proxy elements),
    // reflects the DOM structure that would have resulted if all writes had been squashed into a single write.
  
    // For each descendent `node` of `tempDiv` whose parentNode is a *proxy*, `node` is appended to the corresponding *real* element within the DOM.
  
    // Proxy elements are mapped to *actual* elements in the DOM by injecting a data-id attribute into each start tag in `staticHtml`.
    var WriteStream = (function(){
  
      // Prefix for data attributes on DOM elements.
      var BASEATTR = 'data-ps-';
  
      // get / set data attributes
      function data(el, name, value) {
        var attr = BASEATTR + name;
  
        if(arguments.length === 2) {
          // Get
          var val = el.getAttribute(attr);
  
          // IE 8 returns a number if it's a number
          return !existy(val) ? val : String(val);
  
        } else if(existy(value) && value !== '') {
          // Set
          el.setAttribute(attr, value);
  
        } else {
          // Remove
          el.removeAttribute(attr);
        }
      }
  
      function WriteStream(root, options) {
        var doc = (root.ownerDocument != null) ? root.ownerDocument : (document.getElementsByTagName("body") && document.getElementsByTagName("body")[0].ownerDocument) || (document.getElementsByTagName('head') && document.getElementsByTagName('head')[0].ownerDocument);
        set(this, {
          root: root,
  
          options: options,
  
          win: doc.defaultView || doc.parentWindow,
  
          doc: doc,
  
          parser: htmlParser('', { autoFix: options.autoFix }),
  
          // Actual elements by id.
          actuals: [root],
  
          // Embodies the "structure" of what's been written so far, devoid of attributes.
          proxyHistory: '',
  
          // Create a proxy of the root element.
          proxyRoot: doc.createElement(root.nodeName),
  
          scriptStack: [],
  
          writeQueue: []
        });
  
        data(this.proxyRoot, 'proxyof', 0);
  
      }
  
      WriteStream.prototype.write = function() {
        [].push.apply(this.writeQueue, arguments);
        // Process writes
        // When new script gets pushed or pending this will stop
        // because new writeQueue gets pushed
        var arg;
        while(!this.deferredRemote &&
        this.writeQueue.length) {
          arg = this.writeQueue.shift();
  
          if(isFunction(arg)) {
            this.callFunction(arg);
          } else {
            this.writeImpl(arg);
          }
        }
      };
  
      WriteStream.prototype.callFunction = function(fn) {
        var tok = { type: 'function', value: fn.name || fn.toString() };
        this.onScriptStart(tok);
        fn.call(this.win, this.doc);
        this.onScriptDone(tok);
      };
  
      WriteStream.prototype.writeImpl = function(html) {
        this.parser.append(html);
  
        var tok, tokens = [], script, style;
  
        // stop if we see a script token
        while((tok = this.parser.readToken()) && !(script=isScript(tok)) && !(style=isStyle(tok))) {
          tok = this.options.beforeWriteToken(tok);
  
          if (tok) {
            tokens.push(tok);
          }
        }
  
        this.writeStaticTokens(tokens);
  
        if(script) {
          this.handleScriptToken(tok);
        }
        if(style){
          this.handleStyleToken(tok);
        }
      };
  
      // ## Contiguous non-script tokens (a chunk)
      WriteStream.prototype.writeStaticTokens = function(tokens) {
  
        var chunk = this.buildChunk(tokens);
  
        if(!chunk.actual) {
          // e.g., no tokens, or a noscript that got ignored
          return;
        }
        chunk.html = this.proxyHistory + chunk.actual;
        this.proxyHistory += chunk.proxy;
  
        this.proxyRoot.innerHTML = chunk.html;
  
        if(DEBUG_CHUNK) {
          chunk.proxyInnerHTML = this.proxyRoot.innerHTML;
        }
  
        this.walkChunk();
  
        if(DEBUG_CHUNK) {
          chunk.actualInnerHTML = this.root.innerHTML; //root
        }
  
        return chunk;
      };
  
      WriteStream.prototype.buildChunk = function (tokens) {
        var nextId = this.actuals.length,
  
        // The raw html of this chunk.
            raw = [],
  
        // The html to create the nodes in the tokens (with id's injected).
            actual = [],
  
        // Html that can later be used to proxy the nodes in the tokens.
            proxy = [];
  
        each(tokens, function(tok) {
  
          var tokenRaw = htmlParser.tokenToString(tok);
  
          raw.push(tokenRaw);
  
          if(tok.attrs) { // tok.attrs <==> startTag or atomicTag or cursor
            // Ignore noscript tags. They are atomic, so we don't have to worry about children.
            if(!(/^noscript$/i).test(tok.tagName)) {
              var id = nextId++;
  
              // Actual: inject id attribute: replace '>' at end of start tag with id attribute + '>'
              actual.push(
                  tokenRaw.replace(/(\/?>)/, ' '+BASEATTR+'id='+id+' $1')
              );
  
              // Don't proxy scripts: they have no bearing on DOM structure.
              if(tok.attrs.id !== 'ps-script' && tok.attrs.id !== 'ps-style') {
                // Proxy: strip all attributes and inject proxyof attribute
                proxy.push(
                    // ignore atomic tags (e.g., style): they have no "structural" effect
                    tok.type === 'atomicTag' ? '' :
                    '<'+tok.tagName+' '+BASEATTR+'proxyof='+id+(tok.unary ? ' />' : '>')
                );
              }
            }
  
          } else {
            // Visit any other type of token
            // Actual: append.
            actual.push(tokenRaw);
            // Proxy: append endTags. Ignore everything else.
            proxy.push(tok.type === 'endTag' ? tokenRaw : '');
          }
        });
  
        return {
          tokens: tokens,
          raw: raw.join(''),
          actual: actual.join(''),
          proxy: proxy.join('')
        };
      };
  
      WriteStream.prototype.walkChunk = function() {
        var node, stack = [this.proxyRoot];
  
        // use shift/unshift so that children are walked in document order
  
        while(existy(node = stack.shift())) {
  
          var isElement = node.nodeType === 1;
          var isProxy = isElement && data(node, 'proxyof');
  
          // Ignore proxies
          if(!isProxy) {
  
            if(isElement) {
              // New actual element: register it and remove the the id attr.
              this.actuals[data(node, 'id')] = node;
              data(node, 'id', null);
            }
  
            // Is node's parent a proxy?
            var parentIsProxyOf = node.parentNode && data(node.parentNode, 'proxyof');
            if(parentIsProxyOf) {
              // Move node under actual parent.
              this.actuals[parentIsProxyOf].appendChild(node);
              // MPS tracking array of inserted nodes
              "function" == typeof mps._postscribeCallback && "ps-script"!=node.id && mps._postscribeCallback(node.outerHTML);
            }
          }
          // prepend childNodes to stack
          stack.unshift.apply(stack, toArray(node.childNodes));
        }
      };
  
      // ### Script tokens
      WriteStream.prototype.handleScriptToken = function(tok) {
        var remainder = this.parser.clear();
  
        if(remainder) {
          // Write remainder immediately behind this script.
          this.writeQueue.unshift(remainder);
        }
  
        //noinspection JSUnresolvedVariable
        tok.src = tok.attrs.src || tok.attrs.SRC;
  
        tok = this.options.beforeWriteToken(tok);
  
        if(!tok) {
          // User has removed this token
          return;
        }
  
        if(tok.src && this.scriptStack.length) {
          // Defer this script until scriptStack is empty.
          // Assumption 1: This script will not start executing until
          // scriptStack is empty.
          this.deferredRemote = tok;
        } else {
          this.onScriptStart(tok);
        }
  
        // Put the script node in the DOM.
        var _this = this;
        this.writeScriptToken(tok, function() {
          _this.onScriptDone(tok);
        });
        // MPS tracking array of inserted scripts
        "function" == typeof mps._postscribeCallback && tok.content.length && mps._postscribeCallback("<script>"+tok.content+"\x3c/script>");
      };
  
      // ### Style tokens
      WriteStream.prototype.handleStyleToken = function(tok) {
        var remainder = this.parser.clear();
  
        if(remainder) {
          // Write remainder immediately behind this style.
          this.writeQueue.unshift(remainder);
        }
  
        tok.type = tok.attrs.type || tok.attrs.TYPE || 'text/css';
  
        tok = this.options.beforeWriteToken(tok);
  
        if(tok) {
          // Put the style node in the DOM.
          this.writeStyleToken(tok);
        }
  
        if(remainder) {
          this.write();
        }
      };
  
      // Build a style and insert it into the DOM.
      WriteStream.prototype.writeStyleToken = function(tok) {
        var el = this.buildStyle(tok);
  
        this.insertStyle(el);
  
        // Set content
        if(tok.content) {
          //noinspection JSUnresolvedVariable
          if(el.styleSheet && !el.sheet) {
            el.styleSheet.cssText=tok.content;
          }
          else {
            el.appendChild(this.doc.createTextNode(tok.content));
          }
        }
      };
  
      // Build a style element from an atomic style token.
      WriteStream.prototype.buildStyle = function(tok) {
        var el = this.doc.createElement(tok.tagName);
  
        el.setAttribute('type', tok.type);
        // Set attributes
        eachKey(tok.attrs, function(name, value) {
          el.setAttribute(name, value);
        });
  
        return el;
      };
  
      // Insert style into DOM where it would naturally be written.
      WriteStream.prototype.insertStyle = function(el) {
        // Append a span to the stream. That span will act as a cursor
        // (i.e. insertion point) for the style.
        this.writeImpl('<span id="ps-style"/>');
  
        // Grab that span from the DOM.
        var cursor = this.doc.getElementById('ps-style');
  
        // Replace cursor with style.
        cursor.parentNode.replaceChild(el, cursor);
      };
  
      WriteStream.prototype.onScriptStart = function(tok) {
        tok.outerWrites = this.writeQueue;
        this.writeQueue = [];
        this.scriptStack.unshift(tok);
      };
  
      WriteStream.prototype.onScriptDone = function(tok) {
        // Pop script and check nesting.
        if(tok !== this.scriptStack[0]) {
          this.options.error({ message: 'Bad script nesting or script finished twice' });
          return;
        }
        this.scriptStack.shift();
  
        // Append outer writes to queue and process them.
        this.write.apply(this, tok.outerWrites);
  
        // Check for pending remote
  
        // Assumption 2: if remote_script1 writes remote_script2 then
        // the we notice remote_script1 finishes before remote_script2 starts.
        // I think this is equivalent to assumption 1
        if(!this.scriptStack.length && this.deferredRemote) {
          this.onScriptStart(this.deferredRemote);
          this.deferredRemote = null;
        }
      };
  
      // Build a script and insert it into the DOM.
      // Done is called once script has executed.
      WriteStream.prototype.writeScriptToken = function(tok, done) {
        var el = this.buildScript(tok);
        var asyncRelease = this.shouldRelease(el);
        var afterAsync = this.options.afterAsync;
  
        if(tok.src) {
          // Fix for attribute "SRC" (capitalized). IE does not recognize it.
          el.src = tok.src;
          this.scriptLoadHandler(el, !asyncRelease ? function() {
            done();
            afterAsync();
          } : afterAsync);
        }
  
        try {
          this.insertScript(el);
          if(!tok.src || asyncRelease) {
            done();
          }
        } catch(e) {
          this.options.error(e);
          done();
        }
      };
  
      // Build a script element from an atomic script token.
      WriteStream.prototype.buildScript = function(tok) {
        var el = this.doc.createElement(tok.tagName);
        // Set attributes
        eachKey(tok.attrs, function(name, value) {
          el.setAttribute(name, value);
        });
        // Set content
        if(tok.content) {
          el.text = tok.content;
        }
        return el;
      };
  
      // Insert script into DOM where it would naturally be written.
      WriteStream.prototype.insertScript = function(el) {
        // Append a span to the stream. That span will act as a cursor
        // (i.e. insertion point) for the script.
        this.writeImpl('<span id="ps-script"/>');
        // Grab that span from the DOM.
        var cursor = this.doc.getElementById('ps-script');
        // Replace cursor with script.
        cursor.parentNode.replaceChild(el, cursor);
      };
  
      WriteStream.prototype.scriptLoadHandler = function(el, done) {
        function cleanup() {
          el = el.onload = el.onreadystatechange = el.onerror = null;
        }
        // Error handler
        var error = this.options.error;
        function success() {
          cleanup();
          done();
        }
        function failure(err) {
          cleanup();
          error(err);
          done();
        }
        // Set handlers
        set(el, {
          onload: function() {
            success();
          },
          onreadystatechange: function() {
            if(/^(loaded|complete)$/.test( el.readyState )) {
              success();
            }
          },
          onerror: function() {
            failure({ message: 'remote script failed ' + el.src });
          }
        });
      };
      WriteStream.prototype.shouldRelease = function(el) {
        var isScript = /^script$/i.test(el.nodeName);
        return !isScript || !!(this.options.releaseAsync && el.src && el.hasAttribute('async'));
      };
      return WriteStream;
    }());
  
    // Public-facing interface and queuing
    global.postscribe = (function() {
      var nextId = 0;
      var queue = [];
      var active = null;
      function nextStream() {
        var args = queue.shift();
        var options;
        if(args) {
          options = last(args);
          options.afterDequeue();
          args.stream = runStream.apply(null, args);
          options.afterStreamStart();
        }
      }
  
      function runStream(el, html, options) {
        active = new WriteStream(el, options);
  
        // Identify this stream.
        active.id = nextId++;
        active.name = options.name || active.id;
        postscribe.streams[active.name] = active;
  
        // Override document.write.
        var doc = (el.ownerDocument != null) ? el.ownerDocument : (document.getElementsByTagName("body") && document.getElementsByTagName("body")[0].ownerDocument) || (document.getElementsByTagName('head') && document.getElementsByTagName('head')[0].ownerDocument);
  
        var stash = {
          close: doc.close,
          open: doc.open,
          write: doc.write,
          writeln: doc.writeln
        };
        function write(str) {
          str = options.beforeWrite(str);
          active.write(str);
          options.afterWrite(str);
        }
        set(doc, {
          close: doNothing,
          open: doNothing,
          write: function(){
            return write(toArray(arguments).join(''));
          },
          writeln: function() {
            return write(toArray(arguments).join('') + '\n');
          }
        });
        // Override window.onerror
        var oldOnError = active.win.onerror || doNothing;
        // This works together with the try/catch around WriteStream::insertScript
        // In modern browsers, exceptions in tag scripts go directly to top level
        active.win.onerror = function(msg, url, line) {
          options.error({ msg: msg + ' - ' + url + ':' + line });
          oldOnError.apply(active.win, arguments);
        };
        // Write to the stream
        active.write(html, function streamDone() {
          // restore document.write
          set(doc, stash);
          // restore window.onerror
          active.win.onerror = oldOnError;
  
          options.done();
          active = null;
          nextStream();
        });
        return active;
      }
      function postscribe(el, html, options) {
        if(isFunction(options)) {
          options = { done: options };
        }
        options = defaults(options, OPTIONS);
        el =
          // id selector
            (/^#/).test(el) ? global.document.getElementById(el.substr(1)) :
              // jquery object. TODO: loop over all elements.
                el.jquery ? el[0] : el;
  
  
        var args = [el, html, options];
        el.postscribe = {
          cancel: function() {
            if(args.stream) {
              // TODO: implement this
              args.stream.abort();
            } else {
              args[1] = doNothing;
            }
          }
        };
        options.beforeEnqueue(args);
        queue.push(args);
        if(!active) {
          nextStream();
        }
        return el.postscribe;
      }
      return set(postscribe, {
        // Streams by name.
        streams: {},
        // Queue of streams.
        queue: queue,
        // Expose internal classes.
        WriteStream: WriteStream
      });
    }());
  }());
  
  // MPS internal postscribe control and tracking functions
  mps._postscribe = {
    enabled: 0,
    loaded: [],
    // Enable Postscribe: override document.write with async IE8+
    enable: function() {
      if((!this.enabled && typeof postscribe == "function" && !mps._checkua().oldie) || (!this.enabled &&  typeof postscribe == "function" && mps._checkua().oldie && mps._checkua().oldie > 8)) {
        document.write = function (write) {
          var el = document.getElementsByTagName("body")[0] || document.getElementsByTagName("head")[0];
          return function (write) {
            postscribe(el, write);
          }
        }(document.write);
        this.enabled = 1;
        return this.status();
      } else{
        this.disable();
        this.enabled = 0;
        mps._debug('[mps:Postscribe] Warning. Postscribe already enabled or using IE8');
      }
    },
    // Disable Postscribe: return document.write to native IE8+
    disable: function() {
      if(this.enabled && (mps._checkua().oldie && mps._checkua().oldie > 8) || (this.enabled && !mps._checkua().oldie)) {
        var iframeDocWrite = document.createElement('iframe');
        iframeDocWrite.setAttribute("id", "iframeDW");
        iframeDocWrite.width = "0px";
        iframeDocWrite.height = "0px";
        iframeDocWrite.style.visibility = "hidden";
        var docElement = document.getElementsByTagName("body")[0] || document.getElementsByTagName("head")[0];
        docElement.appendChild(iframeDocWrite);
        document.write = iframeDocWrite.contentWindow.document.write;
        if(!mps._checkua().oldie){
          docElement.removeChild(iframeDocWrite);
        }
        /*else {
          // Throws can't execude from freed script error
          document.getElementById('iframeDW').removeNode(true);
         }*/
      }
      this.enabled = 0;
      return this.status();
    },
    status: function() {
      mps._debug('[mps:Postscribe] status:' + this.enabled);
      return this.enabled;
    }
  };
  
  // Postscribe Callback, track content
  // Track each snippet that postscribe loads: postscribe.streams[2].actuals[1]
  mps._postscribeCallback = function(content) {
    mps._postscribe.loaded.push(content);
    //mps._debug('[mps:Pixelman] postscribeCallback:'+ content);
  };
  
  typeof mps._debug == 'function' && mps._debug('[mps:JS] LOADED: Postscribe');
}



/* js/advertising/lazyload.js */

mps.execute_lazyload_js = function() {
  mps=mps||{},mpsopts=mpsopts||{},debugmode=debugmode||{};
  debugmode.log&&window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  /** @namespace */
  mps._detect=mps._detect||{};
  mps._detect._pending=mps._detect._pending||[];
  mps._detect._refresh=mps._detect._refresh||{};
  mps._detect.tracking=mps._detect.tracking||{};
  mps._detect.padding=mps._detect.padding||10;
  mps._detect.removed=mps._detect.removed||{};
  mps._detect.detectionelement = mps._detect.detectionelement || {};
  mps._detect.intVal = mps._detect.intVal || 500;
  mps._detect.detectelementtimeout = mps._delays.detectelementtimeout || 8000;
  mps._detect.detectelementinterval = mps._delays.detectelementinterval || 250;
  /***
   * Creates a listener for elements to be lazy loaded
   */
  mps._detect.elementsListener = function() {
    for(var i in mpsopts.detectionelement) {
      if(!mps._detect.detectionelement[i] && mps._select(mpsopts.detectionelement[i]) && mps._select(mpsopts.detectionelement[i]).clientHeight > 0) {
        mps._d('[mps:Detect] Detect element ' + mpsopts.detectionelement[i] + ' is in viewport and has a height greater than 0.');
        mps._detect.detectionelement[i] = true;
        mps._detect.load();
      }
    }
  };
  /***
   * Creates a timeout for elements to be lazy loaded
   */
  mps._detect.elements = function() {
    mps._detect._timeout = mps._detect.detectelementtimeout < (Date.now() - mps._timer);
    for(var i in mpsopts.detectionelement) {
      mps._detect.detectionelement[i] = !mps._detect._timeout ? (mps._detect.detectionelement[i] || false) : true;
    }
    if(!mps._detect._timeout) {
      var _to = setTimeout(function() {
        mps._detect.elements();
      }, mps._detect.detectelementtimeout);
      mps._detect.parentint = setInterval(function() {
        mps._detect.elementsListener();
      }, mps._detect.detectelementinterval);
    } else {
      mps._d('[mps:Detect] Detect element timeout reached.');
      clearInterval(mps._detect.parentint);
    }
  };
  
  /**
   * Alias for mps._detect.viewport = mps.inViewport
   * @type {*}
   */
  mps._detect.viewport = typeof mps.inViewport === 'function' &&  mps.inViewport;
  
  /**
   * Method to call mps._execAd or mps.refreshAds
   */
  mps._detect.load = mps.debounce(function() {
    // Load DD ads
    var pending = mps._detect._pending;
    mps._loadset=mps._loadset||0;
    mps._detect.tracking[mps._loadset]=mps._detect.tracking[mps._loadset]||{};
    if(pending.length) {
      for(var a=0; a<pending.length; a++) {
        var _ads = pending[a],
            gptdiv = mps._adslots[_ads.loadset][_ads.slot],
            distance_to_vp = {};
  
        // Delay Detected Display
        if(_ads.loadset === 0 && _ads.slot && typeof(mpsopts.detectiondelay) === 'object' && mpsopts.detectiondelay[_ads.slot] && parseInt(mpsopts.detectiondelay[_ads.slot]) >= (Date.now() - mps._timer)) {
          mps._d('[mps:Detect] delay detected display for '+ _ads.slot + ':' + mpsopts.detectiondelay[_ads.slot] +'ms.');
          return false;
        }
        if(typeof gptdiv === 'string' && typeof document.getElementById(gptdiv) == 'object' && ((_ads.loadset !== 0 || typeof(mps._detect.detectionelement[_ads.slot]) !== 'boolean') || mps._detect.detectionelement[_ads.slot] === true) && mps.inViewport(document.getElementById(gptdiv))) {
          var clone = (mps._clonevars && mps._clonevars[_ads.loadset] && typeof mps._clonevars[_ads.loadset][_ads.slot] != 'undefined' && mps._clonevars[_ads.loadset][_ads.slot].length > 0) ? mps._clonevars[_ads.loadset][_ads.slot].split('_C')[1] : 0;
          // Load ad, remove atf padding
          mps._execAd(_ads.slot, _ads.loadset, clone, true);
  
          // Tracking and Cleanup
          mps._detect.tracking[_ads.loadset]=mps._detect.tracking[_ads.loadset]||{};
          mps._detect.tracking[_ads.loadset][_ads.slot] = distance_to_vp;
          mps._detect.remove(_ads.slot, _ads.loadset);
          mps._d('[mps:Detect] ' + _ads.loadset + ':' + _ads.slot + ' in viewport - loading ad');
  
          // Callback
          mps._queue.render('lazyload', _ads.slot, _ads.loadset);
          if(typeof(mps.lazyloadCallback) === 'function') {
            try {
              mps.lazyloadCallback(_ads.slot, _ads.loadset);
            } catch(err) {
              mps._errorCallback(err, 'mps.lazyLoadCallback');
            }
          }
  
          return true;
        }
        else {
          // Update tracking position
          mps._detect.tracking[_ads.loadset]=mps._detect.tracking[_ads.loadset]||{};
          mps._detect.tracking[_ads.loadset][_ads.slot] = distance_to_vp;
        }
      }
    }
  
    // Refresh DD ads
    var refresh = mps._detect._refresh;
    if(mps._keys(refresh).length) {
      for (var i in refresh) {
        for (var j in refresh[i]) {
          if (((mps._detect.detectionelement && !mps._keys(mps._detect.detectionelement).length) || (mps._detect.detectionelement && mps._keys(mps._detect.detectionelement).length && typeof mps._detect.detectionelement[refresh[i][j]] !== 'boolean')) && (mpsopts.activerefresh != 2 || (mpsopts.activerefresh == 2 && mps._activerefresh._focus === true))) {
            mps._detect.tracking[i][j] = mps._detect.distanceToViewport(mps._select('#' + refresh[i][j])) ? mps._detect.distanceToViewport(mps._select('#' + refresh[i][j])): {};
            if(mps.inViewport(document.getElementById(refresh[i][j]))) {
              mps._d('[mps:Detect] ' + i + ':' + j + ' in viewport - refreshing ad');
              delete mps._detect._refresh[i][j];
              if (mps._keys(mps._detect._refresh[i]).length == 0) {
                delete mps._detect._refresh[i];
              }
              mps.refreshAds(j, i);
              if (typeof mps.lazyloadRefreshCallback === 'function') {
                mps.lazyloadRefreshCallback(j, i);
              }
            }
          }
        }
      }
    }
  }, 250);
  
  
  /**
   * Removes the slot and loadset from mps._detect._pending
   * @param slot {string}
   * @param loadset {number}
   */
  mps._detect.remove = function(slot, loadset) {
    var pending = [];
    for(var i =0; i<mps._detect._pending.length; i++) {
      if(mps._detect._pending[i].slot !== slot || mps._detect._pending[i].loadset !== loadset) {
        pending.push(mps._detect._pending[i]);
      }
    }
    mps._detect._pending = pending;
    return pending;
  };
  
  /**
   * Track detected display ads distance from viewport
   * distance_to_vp: element (s) top, left in pixels
   * vp_size: Current viewport size in pixels
   * @param {object} s
   * @return {(boolean|object)} vp_delay, vp_distance, vp_size, vp_visible, false
   */
  mps._detect.distanceToViewport = mps.debounce(function(s) {
    s = (typeof s === 'string') ? mps._select(s) : s;
    if(typeof s !== 'object' || s === null){
      return false;
    }
  
    var vp = mps._vp(),
        element = mps.inViewport(s, true),
        elementId = s.id,
        dataset = s.dataset,
        slotname = dataset.mpsSlot,
        loadset = dataset.mpsLoadset,
        inviewY = element.inviewY,
        inviewX = element.inviewX,
        yNegOffset = !inviewY ? -(element.elementY - element.screenY - vp[1]) : 0,
        xNegOffset = !inviewX ? -(element.elementX - element.screenX - vp[0]) : 0,
        yPosOffset = !inviewY ? (element.screenY - element.elementY) : 0,
        xPosOffset = !inviewX ? (element.screenX - element.elementX) : 0;
  
    return {
      "vp_delay": mpsopts.detectiondelay && mpsopts.detectiondelay[slotname] || 0,
      "vp_distance": [
        Math.abs(element.elementY - element.screenY) > vp[1] ? Math.round(yNegOffset) : Math.round(yPosOffset),
        Math.abs(element.elementX - element.screenX) > vp[0] ? Math.round(xNegOffset) : Math.round(xPosOffset)
      ],
      "vp_size": vp,
      "vp_visible": mps._detect && mps._detect._pending[loadset||0] && mps._detect._pending[loadset||0].slot.indexOf(elementId) > -1 || inviewY && inviewX
    };
  }, mps._detect.intVal);
  
  /**
   * Used to add additional padding to detected display ads 'above the fold' = ATF.
   * Returns 50% of the smallest creative size height (px) per slot (i.e topbanner)
   * @param slot {string}
   * @return halfSmallestHeight {number}
   */
  mps._detect.getATFPadding = function(slot){
    if(typeof slot === 'string' && mps.response && mps.response.dart.params.adunits[slot]){
      var sizes = mps.response.dart.params.adunits[slot].sizes || [];
      if(!sizes.length){
        return false;
      }
      // skip fluid size
      var fluidIndex = sizes.indexOf('fluid');
      if(fluidIndex > -1){
        sizes.splice(fluidIndex, 1);
      }
      // skip x1 athena size
      for(var sz=0; sz < sizes.length; sz++) {
        if(sizes[sz][1] === 1){
            var athenaIndex = sz;
        }
      }
      if(athenaIndex > -1){
        sizes.splice(athenaIndex, 1);
      }
  
    } else {
      //getATFPadding => invalid param or slot disabled or missing mps.response
      return false;
    }
  
    var heights = sizes.map(function(size){
      return size[size.length - 1];
    });
    var halfSmallestHeight = Math.round(Math.min.apply(null, heights)/2);
    return -(halfSmallestHeight);
  };
  
  /**
   * Force Loads slot and loadset passed from mps._detect._pending
   * @param slot {string}
   * @param loadset {number}
   * @return {boolean}
   */
  mps._detect.forceLoad = function(slot, loadset) {
    loadset = typeof(loadset) !== 'undefined' ? loadset : mps._loadset;
    mps._detect.tracking[loadset]=mps._detect.tracking[loadset]||{};
    // Add property to _detect for DD overrides.
    mps._detect.forceloadparams = { 'slot': slot, 'loadset': loadset };
    var slotfound = false;
    var pending = mps._detect._pending;
    for (var i = 0; i < pending.length; i++) {
      if (pending[i].slot === slot && pending[i].loadset === loadset) {
        slotfound = true;
        var clone_match = /-C([0-9]+)$/.exec(slot);
        var clone = (clone_match && clone_match[1]) || 0;
        mps._d('[mps:Detect] Force loading ' + loadset + ':' + slot + (clone ? ('(clone ' + clone + ')') : '') + ' ad');
        if (mps._execAd(slot, loadset, clone, 1)) {
          mps._detect.remove(slot, loadset);
        }
      }
    }
  
    var refresh = mps._detect._refresh && mps._detect._refresh[loadset] && mps._detect._refresh[loadset][slot];
    if (refresh && mps._detect._refresh[loadset][slot].length) {
      slotfound = true;
      mps._d('[mps:Detect] Force refresh ' + loadset + ':' + slot + (clone ? ('(clone ' + clone + ')') : '') + ' ad');
      if (mps.refreshAds(slot, loadset)) {
        mps._detect.tracking[loadset][slot] = mps._detect.distanceToViewport(mps._select('#' + mps._detect._refresh[loadset][slot])) || {};
        delete(mps._detect._refresh[loadset][slot]);
      }
    }
    delete(mps._detect.forceloadparams);
  
    if (!slotfound) {
      mps._d('[mps:Detect] slot ' + slot + ' not found in loadset ' + loadset);
    }
  
    return slotfound;
  };
  
  if(mps._bool(mps._detect.activerefresh) === true) {
    mpsopts.activerefresh = true;
  }
  if(typeof(typeof mpsopts != 'undefined' && mpsopts.detectionelement) === 'object') {
    mps._detect.elements();
  }
  
  // Clear detect intervals
  if(mps._detect.interval) {
    clearInterval(mps._detect.interval);
  }
  
  // Run detect load initially, and on interval
  mps._detect.interval = setInterval(mps._detect.load, mps._detect.intVal);
  
  /*
   * Creates window 'scroll' and 'onresize' event listeners, calls mps._detect.load
   */
  if(window.addEventListener) {
    if(mps._bool(mpsopts.activeload)){
      mps._d('^[mps:Detect] mpsopts.activeload=true. Focus window or tab.');
    }
    mps._scroll = window.addEventListener('scroll', mps._detect.load, {passive:true});
    mps._resize = window.addEventListener('resize', mps._detect.load);
  } else {
    mps._scroll = window.attachEvent('onresize', mps._detect.load, {passive:true});
    mps._resize = window.attachEvent('onscroll', mps._detect.load);
  }
  
  mps._d('[mps:JS] LOADED: Lazyload');
  
}



/* js/internal/responsive.js */

mps.execute_responsive_js = function() {
  mps=mps||{},debugmode=debugmode||{};
  debugmode.log&&window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  // mps._responsiveSizeCheck determines if ads should refresh
  mps._responsiveSizeCheck = function(sizestr, slot, loadset, rset) {
    if (typeof(sizestr) != 'string' || typeof(slot) != 'string' || typeof(rset) != 'string' || typeof(mps.responsiveslots) != 'object' || typeof(mps.responsiveslots[loadset]) != 'object' || typeof(mps.responsiveslots[loadset][slot]) != 'object' || !mps.responsiveslots[loadset][slot][rset]) {
      return false;
    }
    for (i in mps.responsiveslots[loadset][slot][rset]) {
      if (mps.responsiveslots[loadset][slot][rset][i].join('x') === sizestr) {
        return true;
      }
    }
    return false;
  };
  
  mps.responsiveApply = function(norefresh) {
    mps._debug('[mps:Responsive] responsiveApply ('+(norefresh?'no refresh':'with refresh')+')');//DEBUG
    if(!mps.pagevars.responsive) {
      return false;
    }
    var _slot, _skiprefresh, rset=mps.getResponsiveSet();
    // skip if the responsive set hasn't changed
    if(rset===mps._rset) {
      mps._debug('[mps:Responsive] SKIP responsiveApply: Unchanged Set');//DEBUG
      return false;
    }
    var _execute = function(ask,lsk,clonenum) {
      var refreshdelayms = mps._refreshdelayms || 0;
      // execute ad with delay (gpt limitation)
      setTimeout(function(){
        mps._execAd(ask,lsk,clonenum);
      },refreshdelayms*lsk);
    };
    // go through all responsive slots for each loadset
    loop1: for (lsk in mps.responsiveslots) { // loadset
      var _refreshset = [],
          _cloneset = [];
      loop2: for (ask in mps.responsiveslots[lsk]) { // slot
        if (mps.responsiveslots[lsk].hasOwnProperty(ask) && mps._ext._insertedads && mps._ext._insertedads[lsk] && mps._ext._insertedads[lsk].indexOf(ask) > -1) {
          _skiprefresh = false;
          var slotid = mps._adslots[lsk][ask];
          var isclone = ask.indexOf('-C') > -1;
          var clonenum = isclone ? ask.split("-C")[1] : 0;
  
          // SHOW  ADSLOT
          if (mps.responsiveslots[lsk][ask][rset] && mps.responsiveslots[lsk][ask][rset] && mps.responsiveslots[lsk][ask][rset][0] !== 'NONE' && mps.slotsdisabled[lsk].indexOf(ask) > -1) {
            mps._debug('[mps:Responsive] SHOW <' + lsk + ':' + ask + '>'); //DEBUG
  
            mps.slotsdisabled[lsk].splice(mps.slotsdisabled[lsk].indexOf(ask), 1);
            if (slotid) {
              mps._classRemove(mps._select("#" + slotid), "mps-gpt-hidden");
            }
            mps._queue.render('adshow', ask, lsk);
            if (typeof(mps.adshowCallback) == 'function') {
              mps.adshowCallback(ask, lsk);
            }
            if (!mps._slotscalled[lsk][ask] && mps._slotsdisabled[lsk][ask]) {
              _execute(ask, lsk, clonenum);
              _skiprefresh = true;
            }
            delete mps._slotsdisabled[lsk][ask];
  
            // HIDE  ADSLOT
          } else if (mps.responsiveslots[lsk][ask][rset] && mps.responsiveslots[lsk][ask][rset] && mps.responsiveslots[lsk][ask][rset][0] === 'NONE') {
            mps._debug('[mps:Responsive] HIDE <' + lsk + ':' + ask + '>'); //DEBUG
            mps.slotsdisabled[lsk].push(ask);
            mps._slotsdisabled[lsk][ask] = mps._adslots[lsk][ask];
            mps._classAdd(mps._select('#' + slotid), 'mps-gpt-hidden');
            mps._queue.render('adhide', ask, lsk);
            if (typeof(mps.adhideCallback) == 'function') {
              mps.adhideCallback(ask, lsk);
            }
          }
          // Refresh if enabled
          if (!norefresh && !_skiprefresh && mps._slotscalled[lsk][ask] && !mps._slotsdisabled[lsk][ask]) {
            // Refresh if changed from previous responsive set
            if (!mps.responsiveslots[lsk][ask][rset] || !mps.responsiveslots[lsk][ask][mps._rset] || (mps.responsiveslots[lsk][ask][rset].join() != mps.responsiveslots[lsk][ask][mps._rset].join())) {
              if (mps._advars[lsk][ask] && typeof(gpt[mps._advars[lsk][ask]]) == 'object') {
                _cloneset[0] = _cloneset[0] || [];
                // INSERTED ADS + CLONES:  Refresh combined inserted ad and clones together
                // SKIP if loaded ad size exists in the new responsive set
                if (mps._adloads && mps._adloads[lsk] && mps._adloads[lsk][ask] && !mps._adloads[lsk][ask].isEmpty && mps._adloads[lsk][ask].size && mps._adsizes && mps._adsizes[lsk + '|' + ask]) {
                  if (mps._responsiveSizeCheck(mps._adsizes[lsk + '|' + ask], ask, lsk, rset)) {
                    mps._d('[mps:ResponsiveSizeCheck] ' + ' Current ' + lsk + ':' + ask + ' Ad Size (' + mps._adsizes[lsk + '|' + ask] + '): SKIP REFRESH');
                    continue loop2;
                  } else {
                    mps._d('[mps:ResponsiveSizeCheck] ' + ' Current ' + lsk + ':' + ask + ' Ad Size (' + mps._adsizes[lsk + '|' + ask] + '): REFRESHING');
                  }
                }
                if (typeof mps._clonevars == 'object' && mps._clonevars[lsk] && mps._clonevars[lsk][ask] && mps._clonevars[lsk][ask].length > 0) {
                  _cloneset[0].push(gpt[mps._advars[lsk][ask]]);
                  mps._debug('[mps:Responsive] LOADSET+CLONE  <' + lsk + ':' + ask + '>');
                  // INSERTED ADS: Refresh group based off loadset
                } else if (ask.indexOf('-C') === -1) {
                  _refreshset.push(gpt[mps._advars[lsk][ask]]);
                  mps._debug('[mps:Responsive] LOADSET <' + lsk + ':' + ask + '>');
                }
                // CLONE ADS: Refresh array _cloneset for respective cloned ads
                if (isclone) {
                  _cloneset[clonenum] = _cloneset[clonenum] || [];
                  _cloneset[clonenum].push(gpt[mps._advars[lsk][ask]]);
                  mps._debug('[mps:Responsive] CLONESET  <' + clonenum + ':' + ask + '>');
                }
              }
            }
          }
        }
      }
      // Execute refresh on insertAds per loadset (first)
      if (_refreshset.length > 0) {
        var changecorrelator = mps._bool(mpsopts.updatecorrelator) == true || (mpsopts.updatecorrelator > 1 && lsk % mps._bool(mpsopts.updatecorrelator, true) === 0) ? true : false;
        mps._debug('[mps:Responsive] Refresh (LOADSET ' + lsk + '), correlator:' + changecorrelator); //DEBUG
        mps.refreshAds(_refreshset, lsk, changecorrelator, true);
      }
      // Execute refresh on cloneAds per cloneset (second)
      if (_cloneset.length > 1) {
        for (var j = 0; j < _cloneset.length; j++) {
          var clonecorrelator = mps._bool(mpsopts.updatecorrelator) == true || (mpsopts.updatecorrelator > 1 && lsk % mps._bool(mpsopts.updatecorrelator, true) === 0) ? true : false;
          mps._debug('[mps:Responsive] Refresh (CLONESET ' + (j) + '), correlator:' + clonecorrelator); //DEBUG
          mps.refreshAds(_cloneset[j], lsk, clonecorrelator, true);
          delete _cloneset[j];
        }
      }
    }
  
    mps._rset = rset;
    return true;
  };
  mps._debug('[mps:JS] LOADED: Responsive'); //DEBUG
  
}



/* js/advertising/refresh.js */

mps.execute_refresh_js = function() {
  mps=mps||{},mpsopts=mpsopts||{},debugmode=debugmode||{};
  debugmode.log&&window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  /**
   * @member {array[]} __refreshed
   * @memberOf mps
   */
  mps.__refreshed=mps.__refreshed||[];
  mps.__refreshed[mps._loadset]=false;
  
  // mpsopts.multiplyrefresh used to shorten delay between refresh calls to Google
  mpsopts.multiplyrefresh = mpsopts.multiplyrefresh||false;
  if(typeof(debugmode.log)=='undefined'||typeof(window.console)!='object'){
    debugmode.log=0;
  }
  mps._elapsed = (typeof(mps._elapsed)=='function') ? mps._elapsed  : function(){return '';};
  mps.__refreshing = false;
  
  /**
   * mps.refreshDetect refreshs detected display ads
   * @param {object} slotname
   * @param {number} loadset
   * @param {boolean} _skipresponsive
   * @return {boolean}
   */
  mps.refreshDetect = function(slotname, loadset, _skipresponsive) {
    // undefined loadset or string slotname
    var slotElemName, slotElemId, slotElem, cleanslot, isclone, ls, lazyLoadEnabled;
    if((typeof loadset !== 'undefined' || typeof loadset === 'number') && typeof slotname !== 'object') {
      slotElem = document.getElementById(mps._slotscalled[loadset][slotname]);
      slotElemName = slotname;
      cleanslot = (slotname.indexOf('-C') > -1) ? slotname.split('-C')[0] : slotname;
      isclone = slotElemName.indexOf('-C') > -1;
      lazyLoadEnabled = !!(!_skipresponsive &&  (mps.lazyload[loadset].indexOf(cleanslot) > -1) || (isclone && mps.lazyloadclone[loadset] && mps.lazyloadclone[loadset].indexOf(slotname) > -1));
      // object slotname
    } else {
      slotElemId = slotname && slotname.getSlotElementId !== null ? slotname.getSlotElementId() : mps._slotscalled[loadset||mps._loadset]['topbanner'];
      slotElem = document.getElementById(slotElemId);
      if(slotElem && slotElem.dataset){
        slotElemName =  slotElem.dataset.mpsSlot;
      } else if(slotElem && slotElem.getAttribute){
        slotElemName =  slotElem.getAttribute('data-mps-slot');
      }else{
        slotElemName = 'topbanner';
      }
      if(!slotElem) {
        return false;
      }
      ls = (slotElem && slotElem.dataset && slotElem.getAttribute) ? parseInt(slotElem.dataset.mpsLoadset) : 0;
      isclone = slotElemName.indexOf('-C') > -1;
      lazyLoadEnabled = !!(_skipresponsive && mps.lazyload && mps.lazyload[ls] && mps.lazyload[ls].indexOf(slotElemName) > -1) || (isclone && mps.lazyloadclone[ls] && mps.lazyloadclone[ls].indexOf(slotElemName) > -1);
      slotname=slotElemName;
      if(typeof ls !== 'number') {
        mps._debug('[mps:Refresh] Slot ' + slotname + ' loadset could not be determined.');
        return false;
      }
    }
    if (mps._detect.forceloadparams && slotname === mps._detect.forceloadparams.slot
        && (mps._detect.forceloadparams.loadset === false || (typeof loadset !== 'undefined' && loadset === mps._detect.forceloadparams.loadset))) {
      return true;
    }
    if((lazyLoadEnabled || mpsopts.activerefresh > 0) && slotElem != null && !mps._detect.viewport(slotElem)) {
      mps._debug('[mps:Refresh] ' + slotElemName + ' isn\'t in the viewport, pushing to mps._detect._refresh queue: '+mps._slotscalled[loadset][slotElemName]);
      mps._detect._refresh[loadset]  = mps._detect._refresh[loadset]||{};
      mps._detect._refresh[loadset][slotElemName] = mps._slotscalled[loadset][slotElemName];
      return false;
    }
    return true;
  };
  
  /**
   * mps.refreshClone refreshs cloned ads ie 'topbanner-C1'
   * @param {object} adob
   * @param {number} timer
   * @param {object} gptopts
   */
  mps.refreshClone = function(adob, timer, gptopts) {
    var _adob = adob;
    var _timer = timer;
    setTimeout(function() {
      mps._gptcmd.push(function() {
        googletag.pubads().refresh([_adob], gptopts);
      });
    }, _timer);
    return true;
  };
  
  /**
   * mps.refreshAds main refresh function, see develop.mps.io for more
   * @param {!(string|string[])} slotname
   * @param {number} loadset
   * @param {boolean} changecorrelator
   * @param {boolean} _skipresponsive
   * @param {number} _interval
   * @return {boolean}
   */
  mps.refreshAds = function (slotname,loadset,changecorrelator,_skipresponsive,_interval) {
    var gptopts = {};
    _skipresponsive = _skipresponsive === 'undefined';
    gptopts.changeCorrelator = (typeof changecorrelator == 'undefined') ?  mps._bool(mpsopts.updatecorrelator) : mps._bool(changecorrelator);
  
    var _set = _set+1 || 0, totalAds = [], loadcount= 0, numOfAds=0;
    mps._delays.refreshads = mps._delays.refreshads||1500;
    if(_interval) {
      clearInterval(_interval);
    }
    if(mpsopts.activerefresh > 0 && !mps._activerefresh._focus){
      mps._d('^[mps:Refresh] mpsopts.activerefresh=true. Focus window or tab.');
    }
  
    if(mps.__refreshing) {
      _interval = setInterval(function(){
        mps.refreshAds(slotname,loadset,changecorrelator,_skipresponsive,_interval);
        return false;
      },mps._delays.refreshads);
      return false;
    }
    mps.__refreshing = true;
    !_skipresponsive && mps.responsiveApply && mps.responsiveApply(true);
    var _oopExec = function(loadset) {
      if(mps.loadrails && mps.removeRails) {
        mps.removeRails(loadset);
      }
      mps._debug('[mps:Refresh] w/ OOP Slot');
    };
  
    // Build Refresh Object
    if(slotname === false) {
      return false;
    }
    if((!window.googletag || !googletag.apiReady) || typeof(mps.pagevars.dart_mode) == "undefined" || mps.pagevars.dart_mode != "gpt-asynchronous") {
      mps._d('^[mps:Refresh] FAILED refreshAds: googletag is unavailable or non-asynchronous mode');
      mps.__refreshing=false;
      return false;
    } else {
      if(typeof(slotname) == 'string' && slotname.length > 0) {
        slotname = [slotname];
      }
      if(typeof(slotname) == 'object' && typeof(slotname.getName)=='function') {
        slotname = [slotname];
      }
      var slotvar, slotvars=[], _slotvars={};
      if(typeof(slotname) != 'object') {
        slotvars = '';
      } else {
        if (slotname.length < 1) {
          mps._delays.refreshads = 0;
        }
        for (var i in slotname) {
          // Refresh all clones, per loadset
          for (var ls in mps._advars) {
            var _ls = (typeof loadset != 'undefined') ? parseInt(loadset) : ls;
            mps._slotsdisabled[_ls] = mps._slotsdisabled[_ls] || {};
            for (var cs=0; cs<mps._keys(mps._advars[_ls]).length; cs++) {
              if (typeof(slotname[i])== 'string'  && mps._keys(mps._advars[_ls])[cs].indexOf(slotname[i] + '-C') > -1) {
                var _loadset = (typeof loadset != 'undefined' && typeof parseInt(loadset) == 'number') ? '_' : _ls;
                var disabledslot = (mps._slotsdisabled[_ls].length && mps._slotsdisabled[_ls].indexOf(slotname[i]) == -1);
                _slotvars[_loadset] = _slotvars[_loadset] || [];
                clonevar = (typeof(slotname[i]) == 'object') ? slotname[i] : mps.getSlot(mps._keys(mps._advars[_ls])[cs], _ls);
                if (typeof(clonevar) == 'object' && !disabledslot) {
                  if (!mps.lazyload) {
                    slotvars.push(clonevar);
                    _slotvars[_loadset].push(clonevar);
                  } else {
                    if (mps.refreshDetect(mps._keys(mps._advars[_ls])[cs], _ls, _skipresponsive)) {
                      slotvars.push(clonevar);
                      _slotvars[_loadset].push(clonevar);
                    }
                  }
                }
              }
            }
            if(typeof loadset != 'undefined'){
              mps._debug('[mps:Refresh] Break loop on loadset: '+loadset);
              break;
            }
          }
          // Refresh by slot object ALL loadsets
          if (typeof loadset === 'undefined' && typeof(slotname[i]) !== 'undefined') {
            for (var aok in mps._adobs) {
              _slotvars[aok] = _slotvars[aok] || [];
              if (slotname[i] == '_oop'){
                _oopExec(aok);
                break;
              }
              slotvar = (typeof(slotname[i]) == 'object') ? slotname[i] : mps.getSlot(slotname[i], aok);
              var disabledslot = (mps._slotsdisabled[aok] && mps._slotsdisabled[aok].length && mps._slotsdisabled[aok].indexOf(slotname[i]) == -1);
              if (typeof(slotvar) == 'object' && !disabledslot) {
                if (!mps.lazyload) {
                  slotvars.push(slotvar);
                  _slotvars[aok].push(slotvar);
                } else {
                  if(mps.refreshDetect(slotname[i],aok,_skipresponsive)) {
                    slotvars.push(slotvar);
                    _slotvars[aok].push(slotvar);
                  }
                }
              }
            }
          } else {
            var numOfAds = slotname.length;
            mps._delays.refreshads = (mpsopts.multiplyrefresh && (numOfAds > 0) && (300 * numOfAds) <= 1800) ? (300 * numOfAds) : 1500;
            if(slotname[i]=='_oop') {
              _oopExec((loadset==undefined)?loadset:null);
            }
            _slotvars['_'] = _slotvars['_']||[];
            slotvar = (typeof(slotname[i])=='object') ? slotname[i] : mps.getSlot(slotname[i],loadset);
            if(typeof(slotvar)=='object') {
              if(!mps.lazyload) {
                slotvars.push(slotvar);
                _slotvars['_'].push(slotvar);
              } else {
                if(mps.refreshDetect(slotvar, loadset, _skipresponsive)) {
                  slotvars.push(slotvar);
                  _slotvars['_'].push(slotvar);
                }
              }
            }
          }
        }
        if (mps.lazyload && !slotvars.length) {
          mps.__refreshing = false;
          return false;
        }
      }
      // No Slot Param - Refresh All
      if(typeof(slotname) != 'object' || slotvars === '') {
        _slotvars = [];
        mps._debug('[mps:Refresh] Refreshing [ALL] ad slots on page or in loadset: '+loadset);
        // loadset
        for(lsk in mps._slotscalled) {
          if(typeof loadset != 'undefined' && lsk != loadset) {
            continue;
          }
          _slotvars[lsk] = [];
          //slot
          for(ask in mps._slotscalled[lsk]) {
            mps._slotsdisabled[lsk] = mps._slotsdisabled[lsk] || {};
            if(!mps._slotsdisabled[lsk][ask] && mps._advars[lsk][ask] && gpt[mps._advars[lsk][ask]]) {
              if(ask=='_oop') {
                _oopExec(lsk);
              }
              if((!mps.lazyload || (typeof(mps.lazyload[lsk]) === 'undefined')) && (!mpsopts.activerefresh || mpsopts.activerefresh == 0)) {
                _slotvars[lsk].push(gpt[mps._advars[lsk][ask]]);
              } else {
                // All Ads ie.  'topbanner' and 'topbanner-C1'
                var askclean = (ask.indexOf('-C') > -1) ? ask.split('-C')[0] : ask;
                mps._detect._refresh[lsk] = mps._detect._refresh[lsk] || {};
                if(ask !== '_oop' &&  mpsopts.activerefresh > 0 || (mps.lazyload[lsk] && mps.lazyload[lsk].indexOf(askclean) > -1) || (mps.lazyloadclone && mps.lazyloadclone[lsk] && mps.lazyloadclone[lsk].indexOf(ask) > -1)) {
                  var _slotElem = document.getElementById(mps._slotscalled[lsk][ask]);
                  if(mps._detect.viewport(_slotElem) && (mpsopts.activerefresh > 0 || (mpsopts.activerefresh > 0 && mps._activerefresh._focus === true))) {
                    _slotvars[lsk].push(gpt[mps._advars[lsk][ask]]);
                  } else {
                    mps._detect._refresh[lsk][ask] = mps._detect._refresh[lsk][ask] || '';
                    mps._detect._refresh[lsk][ask] = mps._slotscalled[lsk][ask];
                  }
                }else{
                  _slotvars[lsk].push(gpt[mps._advars[lsk][ask]]);
                }
              }
            }
          }
        }
      }
      // Validate Refresh Set
      var keys = mps._keys(_slotvars);
      if((typeof(slotvars)=='object' && !keys.length) || !keys.length) {
        mps._log("[mps:Refresh] FAILED refreshAds: No ads to refresh");
        return false;
      }
      var _execute = function(svk,_slotvars,_set, clone) {
        // delay execution between sets (gpt limitation)
        setTimeout(function() {
          var _clonedslotvars =[], _updatedslotvars = [];
          //DEBUG
          mps._debug('[mps:Refresh] Execute Refresh ('+svk+') delay:'+_set*mps._delays.refreshads+' : '+mps._elapsed());
          if(!gptopts.changeCorrelator && _slotvars.length) {
            _updatedslotvars = _slotvars[_set];
          } else {
            // Remove cloned ads, queue.
            for(var i = 0; i < _slotvars[svk].length; i += 1) {
              var _id = typeof _slotvars[svk][i] == 'object' ? _slotvars[svk][i].getSlotElementId() : '';
              if(_id.indexOf('-C') === -1) {
                _updatedslotvars.push(_slotvars[svk][i]);
              } else {
                _clonedslotvars.push( _slotvars[svk][i]);
              }
            }
          }
          // Refresh ads in loadset.
          mps._gptcmd.push(function() {
            googletag.pubads().refresh(_updatedslotvars, gptopts);
          });
          // Refresh cloned ads with new correlators.
          mps._gptcmd.push(function() {
            for(var j = 0; j < _clonedslotvars.length; j += 1) {
              mps.refreshClone(_clonedslotvars[j], (j + 1) * 500, gptopts);
            }
          });
        }, _set*mps._delays.refreshads);
      };
      if(typeof(mps.__refreshed[mps._loadset])!='object') {
        mps.__refreshed[mps._loadset] = [];
      }
      mps.__refreshed[mps._loadset].push(_slotvars);
      for(var svk in _slotvars) {
        if(parseInt(svk) === 0) {
          _set=0;
        } else {
          _set=+1;
        }
        if(typeof loadset != 'undefined') {
          _set = loadset;
        }
        _execute(svk,_slotvars,_set);
      }
      setTimeout(function(){
        mps._queue.render('refreshads', _slotvars);
        if(typeof(mps.refreshAdsCallback) === 'function') {
          mps._debug('[mps:Refresh] mps.refreshAdsCallback delay: '+mps._delays.refreshads*(_set+1)+'ms'+' : '+mps._elapsed());
          try {
            mps.refreshAdsCallback(_slotvars);
          } catch(err) {
            mps._errorCallback(err, 'mps.refreshAdsCallback');
          }
        }
        mps.__refreshing = false;
      },mps._delays.refreshads*(_set+1));
      return true;
    }
  };
  
  /**
   * mps.refreshAdsInterval calls refreshAds on set interval
   * @param {number} intervalsecs
   * @param {string} slotname
   * @param {number} loadset
   * @param {number} intervalkey
   * @return {number} intervalkey
   */
  mps.refreshAdsInterval = function (intervalsecs,slotname,loadset,intervalkey) {
    if(slotname === false) {
      return false;
    }
    mps.refreshintervals = mps.refreshintervals || {};
    var intervalkey = intervalkey || (mps._keys(mps.refreshintervals).length + 1);
    if(intervalsecs > 0) {
      mps._debug('[mps:Refresh] Set ad refresh interval for '+intervalsecs+'s ('+intervalsecs*1000 + 'ms) [interval key: '+intervalkey+']');
      mps.refreshintervals[intervalkey] = setInterval(function(){
        mps._debug('[mps:Refresh] Reached '+intervalsecs+'s ('+intervalsecs*1000 + 'ms) interval - Refreshing ad slots [interval key: '+intervalkey+']');
        // Detected display active refresh enabled.
        if(mps._bool(mpsopts.activerefresh) === true || mpsopts.activerefresh > 0) {
          // Check if window has focus.
          if(mps._activerefresh._focus === true) {
            mps._debug("[mps:Refresh]: window has focus, refresh ads.");
            mps.refreshAds(slotname,loadset);
          } else {
            mps._debug("[mps:Refresh]: window doesn't have focus, don't refresh ads.");
          }
        } else {
          mps.refreshAds(slotname,loadset);
        }
      }, intervalsecs*1000);
      return intervalkey;
    }
  };
  
  /**
   * mps.removeRefreshAdsInterval removes intervalkey, returns length
   * @param {number} intervalkey
   * @return {number} refreshinterval
   */
  mps.removeRefreshAdsInterval = function (intervalkey) {
    mps.refreshintervals = mps.refreshintervals || {};
    if(typeof(mps.refreshintervals) != 'object' || (mps._keys(mps.refreshintervals).length) < 1) {
      mps._debug('[mps:Refresh] There are no intervals to remove.');
      return false;
    }
    // If no key is passed, remove all refresh intervals
    if(typeof(intervalkey) != 'string' && typeof(intervalkey) != 'number') {
      for (rik in mps.refreshintervals) {
        clearInterval(mps.refreshintervals[rik]);
        delete mps.refreshintervals[rik];
        mps._debug('[mps:Refresh]  Removed interval [interval key: '+rik+']');
      }
    } else {
      if(typeof(mps.refreshintervals[intervalkey]) != 'undefined') {
        clearInterval(mps.refreshintervals[intervalkey]);
        delete mps.refreshintervals[intervalkey];
        mps._debug('[mps:Refresh] Removed interval [interval key: '+intervalkey+']');
      } else {
        mps._debug('[mps:Refresh] No matching interval found [interval key: '+intervalkey+']');
      }
    }
    return mps.refreshintervals;
  };
  
  mps._debug('[mps:JS] LOADED: Refresh');
  
}



/* js/advertising/destroy.js */

mps.execute_destroy_js = function() {
  mps=mps||{};
  mpsopts=mpsopts||{};
  debugmode=debugmode||{};
  debugmode.log && window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  /** @namespace */
  mps._destroy = mps._destroy || {};
  
  /**
   * @member {Object[]} _destroyedads - Array of destroyed ads, indexed by loadset number
   * @memberOf mps
   */
  mps._destroyedads = mps._destroyedads || {};
  
  /**
   * Destroy ads by picking a scenario based on params.
   * Calls {@link mps._destroy.destroyAdsPassThrough} and {@link mps._destroy._executeDestroyAdsCallback}
   * @param {!(string|string[])} slot - A slot name or an array of slot names. Pass in "all" as the slot name
   *   to destroy all slots.
   * @param {number} [loadset] - If you only want to destroy an ad for a single load set
   * @returns {boolean} Returns false if there was a problem
   */
  mps.destroyAds = function (slot, loadset) {
    if (!mps._keys(gpt).length || !window.googletag || !googletag.apiReady) {
      mps._debug("[mps:DestroyAds] GPT or Google API is unavailable.");
      return false;
    }
    // Validate params
    var slotarray = slot instanceof Array;
    var slotobject = typeof slot === "object" && !(slot instanceof Array);
    var slotstring = typeof slot === "string";
    var slotstodestroy = [];
  
    /*
     // Scenarios 1:  string or an array of strings
     // mps.destroyAds("topbanner");     // excludes clones
     // mps.destroyAds("topbanner" , 0); // excludes clones
     // mps.destroyAds([ "topbanner", "topbanner-C1"]);
     // mps.destroyAds("all");
     // mps.destroyAds("all", 0);
     */
    if ((slotstring && mps._destroy.validateLoadset(loadset)) || (slotarray && typeof slot[0] === "string")) {
  
      if(slot === "all"){
        // Destroy all slots by loadset
        if(mps._destroy.validateLoadset(loadset) && loadset !== undefined){
          if (googletag.destroySlots(mps._adobs[loadset])) {
            mps._destroy.executeDestroyAdsCallback(mps._adobs[loadset]);
            return true;
          }
          // Destroy all slots
        } else if(mps._keys(mps._slotscalled).length && loadset === undefined){
          if (googletag.destroySlots()) {
            mps._destroy.executeDestroyAdsCallback(slot);
            return true;
          }
        } else {
          mps._debug("^[mps:DestroyAds] FAILED No slots to destroy.");
          return false;
        }
  
      }else if(slotstring && mps._destroy.validateSlot(slot, loadset) || (slotarray  && typeof slot[0] === "string" && mps._destroy.validateSlot(slot[0], loadset))){
        if(slotstring){
          slot = [slot];
        }
        for (var i = 0; i < slot.length; i++) {
          for (var ls in mps._slotscalled) {
            if(mps._destroy.validateLoadset(loadset) && loadset !== undefined && ls == loadset) {
              for (var as in mps._slotscalled[ls]) {
                if (as === slot[i] && typeof gpt === "object" && typeof mps._advars === "object") {
                  slotstodestroy.push(gpt[mps._advars[ls][as]]);
                }
              }
            }else if(typeof loadset === "undefined"){
              for (var as in mps._slotscalled[ls]) {
                if (as === slot[i] && typeof gpt === "object" && typeof mps._advars === "object") {
                  slotstodestroy.push(gpt[mps._advars[ls][as]]);
                }
              }
            }
          }
        }
        mps._destroy.destroyAdsPassThrough(slotstodestroy, loadset);
        return true;
        /*
         // Scenario 3: slot doesn"t exist in mps._slotscalled
         // mps.destroyAds("invalidslot");
         */
      } else {
        mps._debug("^[mps:DestroyAds] FAILED! '"+slot+"' not found or hasn't loaded.");
        return false;
      }
      /*
       // Scenario 2: object or an array of objects
       // mps.destroyAds(gpt[mps._advars[0]["topbanner"]]);
       // mps.destroyAds([gpt[mps._advars[0]["topbanner"]], gpt[mps._advars[0]["detectboxada"]]]);
       */
    } else if (slotobject && mps._keys(slot).length || (slotarray && typeof slot[0] === "object")) {
  
      if(slotobject){
        slotstodestroy = [slot];
      }
      else {
        for (var j=0; j<slot.length; j++) {
          slotstodestroy.push(slot[j]);
        }
      }
  
      mps._destroy.destroyAdsPassThrough(slotstodestroy, loadset);
      return true;
      /*
       // Scenario 4: Invalid param
       // mps.destroyAds();
       // mps.destroyAds(null);
       */
    } else {
      var message = "";
      if((slotobject && mps._keys(slot).length === 0) || (slotarray  && slot.length === 0) || slot === undefined){
        message = "first param ("+slot+")";
      }else{
        message = (mps._destroy.validateLoadset(loadset) && loadset !== undefined) ? "slot: "+slot : "loadset "+ loadset +", must be <= "+mps._loadset;
      }
      mps._debug("^[mps:DestroyAds] FAILED! Invalid "+message+".");
      return false;
    }
  };
  
  /**
   * Handles cleanup of objects and elements
   * @param {object} {!(string|string[])} slotstodestroy - A slot name or an array of slot names. Pass in "all" as the slot name
   *   to destroy all slots.
   * @param {number} loadset
   * @param {return} undefined
   */
  mps._destroy.executeDestroyAdsCallback = function(slotstodestroy, loadset) {
    // Set up slot names and loadset
    var slot,
        slotname = "",
        hasloadset = mps._destroy.validateLoadset(loadset) ? true : undefined,
        loadset = hasloadset ? loadset : 0,
        destroyall = false,
        destroyed = [],
        elemid;
  
    // #1 Delete all slots
    if(slotstodestroy === "all"){
      if(mps._detect) {
        mps._destroy.clearDetectPending(slotstodestroy, loadset);
      }
      if(mps._destroy.validateLoadset(loadset) && loadset !== undefined){
        slotstodestroy = mps._adobs[loadset];
      } else {
        var gptslots = mps._keys(gpt).map(function (val) {
          return gpt[val];
        });
        slotstodestroy = gptslots;
        destroyall = true;
      }
    }
  
    // #2 Single delete
    if (mps._keys(slotstodestroy).length === 1 && !destroyall && typeof slotstodestroy[0].getSlotElementId === 'function') {
      elemid = slotstodestroy[0].getSlotElementId();
      slotname = mps._determineSlot(elemid).slotname;
      loadset = mps._determineSlot(elemid).loadset;
  
      // 1. Remove element
      mps._destroy.removeElement(elemid);
  
      // 2. Delete slotscalled
      if (mps._keys(mps._slotscalled[loadset]).indexOf(slotname) > -1){
        delete mps._slotscalled[loadset][slotname];
      }
  
      // 3. Update destroyedads
      mps._destroyedads[loadset] = mps._destroyedads[loadset] || [];
      if (mps._destroyedads[loadset].indexOf(slotname) === -1) {
        mps._destroyedads[loadset].push(slotname);
      }
  
      // 4. Debug
      if(mps._adloads[loadset] && mps._adloads[loadset][slotname]){
        destroyed.push(loadset +":" +slotname);
        mps._adloads[loadset][slotname]=mps._adloads[loadset][slotname]||{};
        mps._adloads[loadset][slotname]._mps=mps._adloads[loadset][slotname]._mps||{};
        mps._adloads[loadset][slotname]._mps._destroyed = 1;
      }
  
      // ## Batch delete
    } else {
  
      for (var k in slotstodestroy) {
        if (mps._keys(slotstodestroy).length && slotstodestroy[k] && typeof slotstodestroy[k].getSlotElementId === 'function') {
          elemid = slotstodestroy[k].getSlotElementId();
          slot = mps._determineSlot(elemid);
          slotname = slot.slotname;
          loadset = slot.loadset;
  
          for (var ls in mps._slotscalled) {
            if (ls == loadset) {
              for (var as in mps._slotscalled[ls]) {
                if (as == slotname) {
  
                  // 1. Remove multiple elements
                  mps._destroy.removeElement(elemid);
  
                  // 2. Delete multiple slotscalleds
                  if (mps._keys(mps._slotscalled[loadset]).indexOf(slotname) > -1) {
                    delete mps._slotscalled[loadset][slotname];
                    if (mps._keys(mps._slotscalled[loadset]).length === 0) {
                      delete mps._slotscalled[loadset];
                    }
                  }
  
                  // 3. Update multiple destroyedads
                  mps._destroyedads[loadset] = mps._destroyedads[loadset] || [];
                  if (mps._destroyedads[loadset].indexOf(slotname) === -1) {
                    mps._destroyedads[loadset].push(slotname);
                  }
  
                  // 4. Debug
                  if(mps._adloads[loadset] && mps._adloads[loadset][slotname]){
                    destroyed.push(loadset + ":" + slotname);
                    mps._adloads[loadset][slotname]=mps._adloads[loadset][slotname]||{};
                    mps._adloads[loadset][slotname]._mps=mps._adloads[loadset][slotname]._mps||{};
                    mps._adloads[loadset][slotname]._mps._destroyed = 1;
                  }
                }
              }
            }
          }
        }
      }
    }
    // Debugging
    var count = destroyall ? "All ("+destroyed.length+")" : "("+destroyed.length+")";
    mps._debug("[mps:DestroyAds] Removed "+count+": [" + destroyed + "], See mps._destroyedads. " + mps._elapsed());
  
    mps._queue.render("destroyads", slotstodestroy);
    if(typeof(mps._destroyAdsCallback) === "function") {
      try {
        mps._destroyAdsCallback(slotstodestroy);
        mps._debug('[mps:DestroyAds] mps._destroyAdsCallback called');
      } catch(err) {
        mps._errorCallback(err, "mps._destroyAdsCallback");
      }
    }
  };
  
  /**
   * Removes Element (div) from page
   * @param {string} elemid
   * @returns {boolean}
   */
  mps._destroy.removeElement = function(elemid){
    var elem = document.getElementById(elemid);
    if (elem !== null && typeof elem.remove === 'function') {
      elem.remove();
      return true;
    }else if(elem && elem.parentNode) {
      elem.parentNode.removeChild(elem);
      return true;
    } else {
      return false;
    }
  
  };
  
  /**
   * Removes Deleted slot from Detect Pending Queue
   * @param {!(string|object)} slot
   * @returns {boolean}
   */
  mps._destroy.clearDetectPending = function(slot){
    if(!slot){
      return false;
    }
    if(slot === "all"){
      mps._detect._pending = [];
      return true;
    }
    if(slot && typeof mps._detect === "object" && mps._keys(mps._detect._pending).length) {
      for(var i in mps._detect._pending) {
        var loadset = mps._detect._pending[i].loadset,
            slotname = mps._detect._pending[i].slot;
        if (slotname !== slot){
          return false;
          // remove slot from queue
        } else {
          // 1. Remove element
          var elemid = mps._adslots[loadset][slotname];
          mps._destroy.removeElement(elemid);
          // 2. Update destroyedads
          mps._destroyedads[loadset] = mps._destroyedads[loadset] || [];
          mps._destroyedads[loadset].push(slotname);
          // 3. Remove from detect pending
          mps._detect._pending.splice(i, 1);
          return true;
        }
      }
    }
  };
  
  /**
   * Validates that slot exists in {@link mps._slotscalled} and calls {@link mps._clearDetectPending}.
   * @param {!(string|object)} slot
   * @param {number} loadset
   * @returns {boolean}
   */
  mps._destroy.validateSlot = function(slot, loadset) {
    var validslot = ("object" !== typeof slot || slot instanceof Array) ? slot : mps._determineSlot(slot.getSlotElementId()).slotname;
    mps._destroy.clearDetectPending(validslot);
    if(loadset !== undefined) {
      return mps._keys(mps._slotscalled[loadset]).indexOf(validslot) > -1;
    } else if(validslot && loadset === undefined){
      for(var i in mps._keys(mps._slotscalled)) {
        if (mps._slotscalled.hasOwnProperty(i)) {
          return mps._keys(mps._slotscalled[i]).indexOf(validslot) > -1;
        }
      }
    }
  
  };
  
  /**
   * Validates that a variable representing a loadset is either a number or undefined.
   * @param {number} loadset - Zero-based loadset number
   * @returns {boolean}
   */
  mps._destroy.validateLoadset = function(loadset){
    return typeof loadset === "undefined" || ((typeof parseInt(loadset) === "number" && !isNaN(parseInt(loadset)) && loadset <= mps._loadset));
  };
  
  /**
   * Calls {@link https://developers.google.com/doubleclick-gpt/reference#googletag.destroySlots|googletag.destroySlots}.
   * @param {string[]} slotstodestroy - String array of ad slot names we want to destroy
   * @param {number} loadset - Zero-based loadset number
   */
  mps._destroy.destroyAdsPassThrough = function(slotstodestroy, loadset){
    if(window.googletag && googletag.destroySlots(slotstodestroy)) {
      mps._destroy.executeDestroyAdsCallback(slotstodestroy, loadset);
    }
  };
  
}



/* js/advertising/rails.js */

mps.execute_rails_js = function() {
  mps=mps||{},debugmode=debugmode||{};
  debugmode.log&&window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  mps.loadrails = mps.loadrails || 0;
  mps._loadrails = mps._loadrails || 0;
  mps._delays.railscroll = mps._delays.railscroll || 2000;
  
  // _pauseScroll window scroll and touchmove
  mps._pauseScroll = function(e) {
    mps._debug('^[mps:Rails] PAUSE SCROLL!');
    e = e || window.event;
    if (e.preventDefault) {
      e.preventDefault();
    }
    e.returnValue = false;
    setTimeout(function(){
      mps._resumeScroll();
    }, mps._delays.railscroll);
  };
  // resumeScroll
  mps._resumeScroll = function() {
    mps._debug('^[mps:Rails] RESUME SCROLL >');
    window.addEventListener && window.removeEventListener('DOMMouseScroll', mps._pauseScroll, false);
    window.onmousewheel = document.onmousewheel = null;
    window.onwheel = null;
    window.ontouchmove = null;
    document.onkeydown = null;
  };
  
  // mps._setInterscroller(railvars[obj]) _type can be skin or fishtank
  mps._setInterscroller = function(railvars) {
    if(!railvars){
      mps._debug('[mps:Rails] _setInterscroller empty railvars');
      return false;
    }
    var bgAttach = mps._bool(railvars.railParallax) ? 'fixed' : railvars.railAdBgAttachment;
    railvars._selector.style.backgroundAttachment = bgAttach;
    railvars._selector.style.overflowX = 'hidden';
    railvars._selector.style.overflowY = 'auto';
    railvars._selector.style.backgroundPosition = 'center top';
    setTimeout(function(){
      railvars._selector.style.height = railvars.railInterscrollerHeight;
    },1000);
    return railvars;
  };
  
  //--mps._shiftViewport(railvars[obj])
  mps._shiftViewport = function(railvars) {
    if(!railvars){
      mps._debug('[mps:RAILS] _shiftViewport missing railvars');
      return false;
    }
    var offSetTop = parseInt(railvars.leftAdContainer.style.top);
    // Update container div coordinates.
    var updatedWidth = railvars._selector.clientWidth;
    var updatedLeft = railvars._selector.getBoundingClientRect().left;
    var adWidth = parseInt(railvars.railContainerWidth);
    // False = change top offset until X pixels, true = always fixed.
    if(!railvars.offsetDynamic) {
      if(mps._checkua().oldie && mps._checkua().oldie <=8) {
        var pageYOffSet = window.document.documentElement.scrollTop;
      } else {
        var pageYOffSet = window.pageYOffset;
      }
      if(pageYOffSet <= offSetTop) {
        railvars.leftAdContainer.style.top = offSetTop - pageYOffSet + 'px';
        railvars.rightAdContainer.style.top = offSetTop - pageYOffSet + 'px';
      } else {
        railvars.leftAdContainer.style.top = '0px';
        railvars.rightAdContainer.style.top = '0px';
      }
    }
    var leftAdContainerX = updatedLeft - adWidth;
    var rightAdContainerX = updatedWidth + updatedLeft;
    railvars.leftAdContainer.style.left = leftAdContainerX + 'px';
    railvars.rightAdContainer.style.left = rightAdContainerX + 'px';
    return railvars;
  };
  
  //--mps._railsAdjustPadding(railvars[obj)
  mps._setRailsPadding = function(railvars){
    if(!railvars){
      mps._debug('[mps:RAILS] _railsSetPadding missing railvars');
      return false;
    }
    var creativeHeight = railvars.targetheight - railvars.currheight;
    var centerAd = creativeHeight / 2;
    railvars.PADTOP = parseInt(railvars.railOffsetTop);
    railvars.PADBOTTOM = parseInt(railvars.railOffsetBottom);
    var offsetTopSet = !!(railvars.PADTOP && railvars.PADTOP > 0);
    var offsetBottomSet = !!(railvars.PADBOTTOM && railvars.PADBOTTOM > 0);
  
    if(offsetTopSet || offsetBottomSet) {
      // Use offsetTop if both are used.
      if(offsetTopSet && offsetBottomSet) {
        offsetBottomSet = false;
      }
      // use PADTOP OR PADBOTTOM offset
      if(offsetTopSet && !offsetBottomSet) {
        railvars.PADBOTTOM = creativeHeight - railvars.PADTOP;
      } else if(!offsetTopSet && offsetBottomSet) {
        railvars.PADTOP = creativeHeight - railvars.PADBOTTOM;
      }
    } else{
      // Default center ad
      railvars.PADTOP = railvars.PADBOTTOM = centerAd;
    }
    mps._debug('^[mps:Rails] height: '+(creativeHeight)+' PADTOP: '+railvars.PADTOP+' PADBOTTOM: '+railvars.PADBOTTOM);
    railvars._selector.style.paddingTop = (railvars.PADTOP) + 'px';
    railvars._selector.style.paddingBottom = (railvars.PADBOTTOM) + 'px';
  
    return railvars;
  };
  
  //--mps.setRails(railvars[obj])
  // Ad triggered unified handler for rails/skins/fishtanks
  if(typeof(mps.setRails) !== 'function'){
    mps.setRails = function (railvars) {
      mps.railvars = mps.railvars || {};
      mps._prerailstate = mps._prerailstate || {};
      mps._debug('[mps:Rails] CALLED mps.setRails() '+mps._elapsed());
      top.railvars = railvars;
      // Alias deprecated vars
      // Determine rails mode (railContainerWidth = rails2)
      railvars.railContainerWidth = railvars.railContainerWidth || railvars.railClassicWidth;
      railvars.railContainerHeight = railvars.railContainerHeight || railvars.railContainer;
      railvars.railContainerHeight = Math.floor(railvars.railContainerHeight) > 0 ?  Math.floor(railvars.railContainerHeight) : railvars.railContainerHeight;
  
      if(typeof(railvars)!='object' || typeof(railvars.railAdBg)!='string' || (typeof(mps.disableRails)!='undefined' && mps.disableRails==0)) {
        mps._debug('[mps:Rails] setRails Failed (undefined railvars, disabled rails or invalid selector)');
        return false;
      } else {
        mps._debug('[mps:Rails] TRIGGER mps.setRails() '+mps._elapsed());
        var _loadrails = mps._loadrails+1;
        // Merge mps.railvarsOverride (if defined)
        if(typeof(mps.railvarsOverride)=='object' && typeof(mps._merge)=='function') {
          mps._debug('[mps:Rails] OVERRIDE Merge (railvars + mps.railvarsOverride)');
          railvars = mps._merge(railvars,mps.railvarsOverride);
        }
  
        // On rails mode allow settings from mps.pagevars.rails
        if(railvars.railContainerWidth && typeof(mps.pagevars.rails)=='object') {
          if(mps.pagevars.rails.target){
            railvars.railTarget = mps.pagevars.rails.target;
          }
          if(mps.pagevars.rails.offset){
            railvars.railOffsetTop = mps.pagevars.rails.offset;
          }
          if(mps.pagevars.rails.offsetdynamic){
            railvars.offsetDynamic = mps.pagevars.rails.offsetdynamic;
          }
          mps._debug('[mps:Rails] USING mps.pagevars.rails '+JSON.stringify(mps.pagevars.rails));
        }
        // set railvars options
        railvars.railAdBgColor = mps._trim(railvars.railAdBgColor,'#');
        railvars.railAdBgColor = (railvars.railAdBgColor.length && /(^[0-9A-F]{6}$)|(^[0-9A-F]{3}$)/i.test(railvars.railAdBgColor)) ? '#'+railvars.railAdBgColor : '';
        railvars._target = (typeof railvars.railTarget =='string' && railvars.railTarget.length > 1) ? railvars.railTarget : 'body';
        railvars._selector = mps._select(railvars._target);
        railvars._target = (typeof railvars.railTarget =='string' && railvars.railTarget.length > 1) ? railvars.railTarget : 'body';
        railvars._selector = mps._select(railvars._target);
  
        // document ready
        mps._ready(function(){
          if(typeof(railvars._selector)!='object') {
            mps._debug('[mps:Rails] FAILED setRails missing selector: '+railvars._target);
            return false;
          } else {
            // If mps-has-rails class exists return false.
            if(mps._classHas(railvars._selector, 'mps-has-rails')){
              mps._debug('[mps:Rails] SKIP setRails (target already set)');
              return false;
            }
            // Execute Rails (selector and railvars available)
            railvars._selector.className = railvars._selector.className + " mps-rails-" + _loadrails;
            mps._prs = (railvars.railContainerWidth) ? mps._select('body') : railvars._selector;
            if(!mps._prerailstate[_loadrails]) {
              mps._prerailstate[_loadrails] = {"background":mps._prs.style.background,"backgroundImage":mps._prs.style.backgroundImage,"backgroundAttachment":mps._prs.style.backgroundAttachment,"backgroundPosition":mps._prs.style.backgroundPosition,"backgroundColor":mps._prs.style.backgroundColor,"backgroundRepeat":mps._prs.style.backgroundRepeat,"backgroundSize":mps._prs.style.backgroundSize,"height":mps._prs.style.height,"width":mps._prs.style.width,"margin":mps._prs.style.margin,"padding":mps._prs.style.padding,"cursor":mps._prs.style.cursor};
            }
            //--EXECUTE: Skins & Fishtanks
            if(!railvars.railContainerWidth) {
              railvars._type = 'skin';
              // 600  px
              railvars.railContainerHeight = Math.floor(railvars.railContainerHeight) > 0 ?  Math.floor(railvars.railContainerHeight) : railvars.railContainerHeight;
              //railvars.railContainerHeight =  railvars.railContainerHeight !== 'full' ?  'full': railvars.railContainerHeight; // 'full' or false
              if(Math.floor(railvars.railParallax)==1) {
                railvars.railAdBgAttachment = 'fixed';
                railvars._type = 'fishtank';
              }
              if(railvars.railAdBgAttachment == 'fixed' && mps._checkua().mobile) {
                railvars.railAdBgAttachment = 'scroll';
                railvars._selector.style.backgroundSize = '100%';
              }
              if(railvars.railAdBg) {
                if((railvars._type === 'skin' || railvars._type === 'fishtank') && railvars.railContainerHeight === 'full'){
                  var fullheight,
                      railBgImage = new Image();
                  railBgImage.src = railvars.railAdBg;
                  railBgImage.onload = function() {
                    var width = this.width,
                        height = this.height;
                    if(mps._checkua().oldie && mps._checkua().oldie < 11 ){
                      var ieFullHeight = Math.max(document.documentElement.clientHeight, window.innerHeight || mps._viewport()[1]);
                      fullheight = (typeof ieFullHeight == 'number' && height > ieFullHeight)  ? height + 'px' : ieFullHeight + 'px';
                    }else{
                      fullheight = (height > mps._viewport()[1]) ? height + 'px' : '100vh';
                    }
                    railvars.railInterscrollerHeight = fullheight;
                  };
                }
                railvars._selector.style.backgroundImage = 'url('+railvars.railAdBg+')';
                railvars._selector.style.backgroundPosition = 'top center';
              }
              railvars._selector.style.backgroundAttachment = (railvars.railAdBgAttachment) ? railvars.railAdBgAttachment : 'fixed';
              railvars._selector.style.backgroundPosition = (railvars.railAdBgPosition) ? railvars.railAdBgPosition : '';
              railvars._selector.style.backgroundSize = (railvars.railAdBgSize) ? railvars.railAdBgSize : '';
              if(railvars.railAdBgColor) {
                railvars._selector.style.backgroundColor = railvars.railAdBgColor;
              }
              if(railvars.railAdBgRepeat) {
                railvars._selector.style.backgroundRepeat = railvars.railAdBgRepeat;
              }
  
              if(railvars.railAdBgClickthru) {
                if(railvars._target == 'body') {
                  railvars._type = 'rails1';
                } else {
                  railvars._selector.style.cursor = 'pointer';
                }
  
                if (railvars._selector.addEventListener) {
                  railvars._selector.addEventListener('click', mps._railsClick, false);
                } else {
                  railvars._selector.attachEvent('onclick', mps._railsClick);
                }
              }
              if(railvars._target == 'body') {
                railvars._bodytarget = (typeof(railvars._bodytarget)=='string') ? railvars._bodytarget : 'mps-slot:first';
                railvars._selector = mps._select(railvars._bodyselector);
                mps._debug('[mps:Rails] OVERRIDE body selector');
              }
              mps._classAdd(railvars._selector,'mps-has-rails');
              railvars._selector.className += " "+railvars._type;
  
              if(railvars.railContainerHeight === 'full' && (railvars._type === 'skin' || railvars._type === 'fishtank')) {
                mps._setInterscroller(railvars);
  
                // TODO: add scroll pause/resume listeners
                /*window.addEventListener("scroll", function (e) {
                  var scrollTop = $(window).scrollTop(),
                      elementTop = Math.round($(railvars._selector).offset().top),
                      elementLeft = Math.round($(railvars._selector).offset().left),
                      distance = Math.round(elementTop - scrollTop);
                  if (distance > -5 && distance < 0) {
                    //window.scrollTo(0, elementTop);
                    window.addEventListener && window.addEventListener('DOMMouseScroll', mps._pauseScroll, false);
                    window.onwheel = mps._pauseScroll; // modern
                    window.onmousewheel = document.onmousewheel = mps._pauseScroll; // IE
                    window.ontouchmove  = mps._pauseScroll; // mobile
                  }
                });*/
              }
            } else {
              //--EXECUTE: New Rails
              railvars._type = 'rails2';
              //get target dimensions and create divs
              var contentDiv = railvars._selector.getBoundingClientRect(),
                  contentWidth = contentDiv.width,
                  contentHeight = contentDiv.height,
                  adWidth = parseInt(railvars.railContainerWidth),
                  railsAdWrapper = document.createElement('div'),
                  leftAdContainer = document.createElement('div'),
                  rightAdContainer = document.createElement('div'),
                  creativeBg = new Image();
              // append railsAdWrapper to body
              if(mps._checkua().oldie && mps._checkua().oldie <=8) {
                var ieWidth = railvars._selector.currentStyle['width'];
                ieWidth = ieWidth.replace('px', '');
                contentWidth = parseInt(ieWidth);
              }
  
              // If creative + content well < viewport skip setRails
              var railVarsForce = railvars.railForceSet&&railvars.railForceSet==1;
              var pagevarsForce = mps.pagevars.rails&&mps.pagevars.rails.forceset&&mps.pagevars.rails.forceset==1;
              if(mps._viewport()[0] < (adWidth * 2 + contentWidth) && !railVarsForce && !pagevarsForce) {
                mps._debug('[mps:Rails] SKIP setRails (viewport too small)');
                return false;
              }
  
              document.body.insertBefore(railsAdWrapper, document.body.childNodes[0]);
              mps._classAdd(railvars._selector,'mps-has-rails');
              mps._classAdd(railsAdWrapper,'rails-ad-wrapper mps-has-rails');
              mps._classAdd(leftAdContainer,'mps-rails-left');
              mps._classAdd(rightAdContainer,'mps-rails-right');
              railsAdWrapper.appendChild(leftAdContainer);
              railsAdWrapper.appendChild(rightAdContainer);
              // Set background style properties
              if(railvars.railAdBg) {
                creativeBg.src = railvars.railAdBg;
                creativeBg.height = (creativeBg.height > 0) ? creativeBg.height : 720;
                if(railvars.railAdBgColor){
                  var _bodyselect =  mps._select('body');
                  _bodyselect.style.background = 'none';
                  _bodyselect.style.backgroundImage = 'none';
                  _bodyselect.style.backgroundColor = railvars.railAdBgColor;
                  leftAdContainer.style.backgroundColor = railvars.railAdBgColor;
                  rightAdContainer.style.backgroundColor = railvars.railAdBgColor;
                }
                if(railvars.railAdBgRepeat){
                  leftAdContainer.style.backgroundRepeat = railvars.railAdBgRepeat;
                  rightAdContainer.style.backgroundRepeat = railvars.railAdBgRepeat;
                }
                leftAdContainer.style.backgroundPosition = (railvars.railAdBgPosition) ? railvars.railAdBgPosition : 'top left';
                rightAdContainer.style.backgroundPosition = (railvars.railAdBgPosition) ? railvars.railAdBgPosition : 'top right';
                if(adWidth > 0 && contentWidth > 0){
                  leftAdContainer.style.left = contentWidth - adWidth + 'px';
                  rightAdContainer.style.left = contentWidth + 'px';
                  leftAdContainer.style.width = adWidth + 'px';
                  rightAdContainer.style.width = adWidth + 'px';
                  mps._select('.rails-ad-wrapper').style.width = contentWidth +'px';
                }
                var offSetTop = railvars.railOffsetTop ? Math.floor(railvars.railOffsetTop) : 0;
                rightAdContainer.style.height = creativeBg.height+ 'px';
                leftAdContainer.style.height = creativeBg.height+ 'px';
                leftAdContainer.style.position = 'fixed';
                rightAdContainer.style.position = 'fixed';
                leftAdContainer.style.zIndex = (railvars.railZindex) ? railvars.railZindex : 4999;
                rightAdContainer.style.zIndex = (railvars.railZindex) ? railvars.railZindex : 4999;
                leftAdContainer.style.backgroundImage = 'url('+railvars.railAdBg+')';
                rightAdContainer.style.backgroundImage = 'url('+railvars.railAdBg+')';
                leftAdContainer.style.top = offSetTop + 'px';
                rightAdContainer.style.top = offSetTop + 'px';
                railvars.rightAdContainer = rightAdContainer;
                railvars.leftAdContainer = leftAdContainer;
  
                mps._shiftViewport(railvars);
              }
  
              // add click handler
              if(railvars.railAdBgClickthru) {
                mps._railsClickHandler(railvars);
              }
  
              mps._debug('[mps:Rails] EXECUTED mps.setRails() '+mps._elapsed());
              // scroll rail ads with window scroll and window resize
              if(leftAdContainer && rightAdContainer){
                if(!mps._checkua().mobile){
                  window.onscroll = mps._shiftViewport(railvars);
                  window.onresize = mps._shiftViewport(railvars);
                }
              }
            }
  
            // Save railvars and trigger callback
            mps.railvars[_loadrails] = railvars;
            mps._loadrails = _loadrails;
            if(typeof(top.mps._setRailsCallback)=='function') {
              if(typeof(top.mps)!='undefined' && typeof(top.mps._setRailsCallback)=='function') {
                delayms = 200;
                mps._debug('[mps:Rails] TRIGGER setRailsCallback [delayed: '+delayms+'ms]');
                mps._gptcmd.push(function() {
                  setTimeout(function(){
                    top.mps._setRailsCallback(mps.railvars[_loadrails]);
                  },delayms);
                });
              }
            }
            mps.loadrails++;
            mps._debug('[mps:Rails] EXECUTED setRails() '+mps._elapsed());
          }
        });
      }
      return mps.loadrails;
    };
  } else {
    mps._debug('[mps:Rails] OVERRIDE: Using custom mps.setRails function');
  }
  
  // rails callback function for skins and fishtank only
  mps._setRailsCallback = function(railvars) {
    if (railvars._type !== 'rails2' && typeof(railvars) === 'object' && typeof(railvars._selector) === 'object' && (railvars.railContainerHeight > 0 || railvars.railContainerHeight == 'full')) {
      if(!mps._checkua().oldie && !mps._checkua().oldie <= 8) {
        var currentPadTop = parseInt(window.getComputedStyle(railvars._selector, null).paddingTop.replace('px', ''), 10);
        var currentPadBottom = parseInt(window.getComputedStyle(railvars._selector, null).paddingBottom.replace('px', ''), 10);
      } else {
        var currentPadTop = parseInt(railvars._selector.currentStyle.paddingTop.replace('px', ''), 10);
        var currentPadBottom = parseInt(railvars._selector.currentStyle.paddingBottom.replace('px', ''), 10);
      }
      railvars.currheight = parseInt(railvars._selector.clientHeight, 10) >= 0 ? parseInt(railvars._selector.clientHeight, 10) : parseInt(mps._select(railvars._target).clientHeight, 10);
      railvars.targetheight = !isNaN(railvars.railContainerHeight) ? parseInt(railvars.railContainerHeight, 10) : mps._viewport()[1];
      railvars.PADTOP = railvars.PADBOTTOM = 15;
      railvars.currheight = (railvars.currheight - currentPadTop - currentPadBottom);
      if (railvars.targetheight > railvars.currheight) {
        // IS responsive, tablet, and railParallax=false
        if(typeof(mps.getResponsiveSet)=='function' && mps.getResponsiveSet()=='tablet' && Math.floor(railvars.railParallax)!=1) {
          railvars._selector.style.paddingTop = (railvars.currheight < 90) ? railvars.PADTOP+'px' : '0px';
          railvars._selector.style.backgroundSize = '100%';
        }
        // NOT responsive or NOT tablet or Has railParallax=true
        else {
          mps._setRailsPadding(railvars);
        }
      }
      mps._queue.render('setrails', railvars);
      if(typeof(mps.setRailsCallback) === 'function') {
        try {
          mps.setRailsCallback(railvars);
        } catch(err) {
          mps._errorCallback(err, 'mps.setRailsCallback');
        }
      }
    } else {
      if (railvars._type === 'rails1' || railvars._type === 'rails2') {
        mps._queue.render('setrails', railvars);
        if(typeof(mps.setRailsCallback) === 'function') {
          try {
            mps.setRailsCallback(railvars);
          } catch(err) {
            mps._errorCallback(err, 'mps.setRailsCallback');
          }
        }
      } else {
        mps._debug('[mps:Rails] setRailsCallback FAILED');
      }
    }
  };
  
  //--[removeRails] Revert page to pre-rails/skin/fishtank state.
  if(typeof(mps.removeRails) !== 'function'){
    mps.removeRails = function(loadset) {
      var _iterator = function(railvars) {
        if(typeof(railvars)=='object') {
          for(var rv in railvars){
            if(typeof(railvars.push)=='function'){
              rv = loadset[rv];
            }
            if(typeof(mps.railvars[rv]) == 'object') {
              mps.removeRails(rv);
            }
          }
        }
      },
      loadset = loadset || mps.railvars || {};
      // If object or array is passed, iterate through them
      if(typeof(loadset)=='object') {
        _iterator(loadset);
        return true;
      }
      if(typeof(mps.railvars[loadset])!='object' && typeof(mps.railvars[loadset])!=null) {
        mps._debug('[mps:Rails] FAILED removeRails('+loadset+'): invalid loadset');
        return false;
      }
      mps.railvars[loadset]._selector = (typeof mps.railvars[loadset].railTarget =='string' && mps.railvars[loadset].railTarget.length > 1) ? mps._select(mps.railvars[loadset].railTarget) : mps._select('body');
      // Only execute witb pre-rails state
      if(typeof(mps.railvars[loadset]._selector) == 'object' && typeof(mps._prerailstate[loadset]) == 'object' && mps.loadrails > 0) {
        //if rails2 remove injected divs and body style
        if(mps.railvars[loadset]._type == 'rails2'){
          var railsAdWrap = mps._select('.rails-ad-wrapper');
          railsAdWrap.parentNode.removeChild(railsAdWrap);
        }
        // Restore selector styles
        for(var sbi in mps._prerailstate[loadset]){
          mps._prs = (mps.railvars[loadset].railContainerWidth) ? mps._select('body') : mps.railvars[loadset]._selector;
          mps._prs.style[sbi] = mps._prerailstate[loadset][sbi];
        }
        // Remove event listeners
        mps._eventRemove(mps.railvars[loadset]._selector,'click', mps._railsClick);
        // Execute page callback (if defined)
        if(typeof(top.mps.removeRailsCallback)=='function') {
          mps._debug('[mps:Rails] TRIGGER removeRailsCallback('+loadset+')');
          top.mps.removeRailsCallback();
        }
        mps.railvars[loadset]._selector.onclick = null;
  
        // Remove classes
        mps._classRemove(mps.railvars[loadset]._selector,'mps-has-rails');
        mps.loadrails -= 1;
        // Remove from railvars object
        delete mps._prerailstate[loadset];
        delete mps.railvars[loadset];
        mps._debug('[mps:Rails] EXECUTED removeRails('+loadset+')');
      } else {
        mps._debug('[mps:Rails] FAILED removeRails('+loadset+'): missing pre-rails');
        return false;
      }
      return true;
    };
  } else {
    mps._debug('[mps:Rails] OVERRIDE: Using custom mps.removeRails function');
  }
  
  //--mps._railsClickHandler(railvars[obj])
  mps._railsClickHandler = function(railvars){
    if(!railvars){
      mps._debug('[mps:RAILS] _railsClickHandler missing railvars');
      return false;
    }
    railvars.leftAdContainer.style.cursor = 'pointer';
    railvars.rightAdContainer.style.cursor = 'pointer';
    if (railvars.leftAdContainer.addEventListener) {
      railvars.leftAdContainer.addEventListener('click', mps._railsClick, false);
      railvars.rightAdContainer.addEventListener('click', mps._railsClick, false);
    } else {
      railvars.leftAdContainer.attachEvent('onclick', mps._railsClick);
      railvars.rightAdContainer.attachEvent('onclick', mps._railsClick);
    }
    return railvars;
  };
  
  //--[_railsClick(event)] custom click event for rails
  mps._railsClick = function(e){
    evt = e || window.event;
    if(e.target) {
      targ = e.target;
    } else if(e.srcElement) {
      targ = e.srcElement;
    }
    if(targ.nodeType == 3) {
      // Safari bug?
      targ = targ.parentNode;
    }
    if(mps.railvars[mps._loadrails]._target == 'body') {
      if((typeof targ.className!='undefined') && (targ.className.indexOf('mps-rails-'+mps._loadrails)!=-1)) {
        mps._debug('[mps:Rails] Skipping Click: '+mps.railvars[mps._loadrails].railAdBgClickthru);
      }
    } else {
      window.open(mps.railvars[mps._loadrails].railAdBgClickthru);
    }
  };
  
  mps._debug('[mps:JS] LOADED: Rails');
  
}



/* js/advertising/scaling.js */

mps.execute_scaling_js = function() {
  mps=mps||{},debugmode=debugmode||{};
  mps.__prescalestate=mps.__prescalestate||{};
  debugmode.log&&window.console||(debugmode.log=0);
  mps._elapsed||(mps._elapsed=function(){return"";});
  
  //mps._scaleAd ('topbanner',0.5[optional],0[default=mps._loadset])
  mps._scaleAd = function (adslot,forceratio,loadset) {
    mps._debug('[mps.scaleAd]:'+ adslot+', '+forceratio+', '+loadset);
    var scaleclass = 'mps-has-scaled',
      adslot = adslot,
      loadset = (typeof(parseInt(loadset,10) == 'number') && loadset < mps._keys(mps._adloads).length) ? parseInt(loadset,10) : mps._loadset,
      adivgpt = mps._select('#'+mps._adslots[loadset][adslot]),
      aiframe = mps._select('#'+mps._adslots[loadset][adslot]+' iframe');
  
    var _viewport = mps._viewport && mps._viewport();
    if (typeof aiframe ==='object' && typeof _viewport ==='object' ) {
      if(_viewport[0] < aiframe.clientWidth || forceratio > 0){
        var vpwidth = _viewport[0],
          sideoffset = Math.floor(aiframe.offsetLeft),
          scaleratio = typeof(forceratio)!='number' ? (vpwidth / (aiframe.clientWidth + sideoffset * 2)) : forceratio,
          scaleratioh = typeof(forceratio)!='number' ? (vpwidth / aiframe.clientWidth) : forceratio,
          scaledwidth = Math.floor(aiframe.clientWidth * scaleratio),
          scaledheight = Math.floor(aiframe.clientHeight * scaleratioh);
  
        if(mps._classHas(adivgpt,scaleclass)) {
          mps._scaleAdRevert(adslot,loadset);
        } else {
          mps.__prescalestate[loadset] = mps.__prescalestate[loadset] || {};
          mps.__prescalestate[loadset][adslot] = mps.__prescalestate[loadset][adslot] || {};
          mps.__prescalestate[loadset][adslot] = { 'div':adivgpt.getAttribute('style'), 'iframe':aiframe.getAttribute('style') };
        }
        aiframe.setAttribute('style',
            'zoom: 1;'+
            'scale:'+scaleratio+';'+
            '-moz-transform-origin: 0 0;'+
            '-moz-transform: scale('+scaleratio+');'+
            '-o-transform-origin: 0 0;'+
            '-o-transform: scale('+scaleratio+');'+
            '-webkit-transform-origin: 0 0;'+
            '-webkit-transform: scale('+scaleratio+');'+
            'transform-origin: 0 0;'+
            'transform: scale('+scaleratio+');'+
            'border: 0');
        adivgpt.setAttribute('style',
          ((scaleratio < 1) ? 'overflow: hidden;' : '')+
            'margin: 0 auto;'+
            'padding: 0;'+
            'height:'+scaledheight+'px;'+
            'width:'+scaledwidth+'px;');
  
        aiframe.setAttribute('data-scale',scaleratio);
        mps._classAdd(adivgpt,scaleclass);
        mps._debug('[mps.scaleAd] /'+adslot+':'+loadset+'/ Viewport Width: '+vpwidth+'px | Left Offset: '+sideoffset+'px | Right Offset: '+(vpwidth-(scaledwidth+sideoffset))+'px | Iframe Width: '+aiframe.clientWidth+'px | Scale Ratio (w): '+scaleratio+' | Scale Ratio (h): '+scaleratioh+' | Scaled Ad (w): '+scaledwidth+'px | Scaled Ad (h): '+scaledheight+'px '+mps._elapsed());
        return true;
      }
    } else {
      mps._debug('[mps.scaleAd] Bypass /'+adslot+':'+loadset+'/ '+mps._elapsed());
      return false;
    }
  };
  
  //mps._scaleAdRevert ('topbanner',0[default=mps._loadset])
  mps._scaleAdRevert = function (adslot,loadset) {
    var adslot = adslot,
        loadset = (typeof(parseInt(loadset,10) == 'number') && parseInt(loadset,10) < mps._keys(mps._adloads).length) ? parseInt(loadset,10) : mps._loadset,
        adivgpt = mps._select('#'+mps._adslots[loadset][adslot]),
        aiframe = mps._select('#'+mps._adslots[loadset][adslot]+' iframe'),
       _viewport = mps._viewport && mps._viewport();
    mps.__prescalestate[loadset] = mps.__prescalestate[loadset] || {};
    mps.__prescalestate[loadset][adslot] = mps.__prescalestate[loadset][adslot] || {};
    if(typeof(aiframe)==='object' && typeof(_viewport)==='object' && typeof(mps.__prescalestate[loadset])=='object' && typeof(mps.__prescalestate[loadset][adslot])=='object') {
      if(mps.__prescalestate[loadset][adslot].iframe) {
        aiframe.setAttribute('style',mps.__prescalestate[loadset][adslot].iframe);
      } else {
        aiframe.removeAttribute('style');
      }
      if(mps.__prescalestate[loadset][adslot].div) {
        adivgpt.setAttribute('style',mps.__prescalestate[loadset][adslot].div);
      } else {
        adivgpt.removeAttribute('style');
      }
      adivgpt.className = adivgpt.className.replace( /(?:^|\s)mps-has-scaled(?!\S)/ , '' );
      // clear old __prescalestate
      mps.__prescalestate[loadset]=mps.__prescalestate[loadset][adslot]={};
      mps._debug('[mps.scaleAdRevert] /'+adslot+':'+loadset+'/ Unscaled '+mps._elapsed());
      return true;
    } else {
      mps._debug('[mps.scaleAdRevert] /'+adslot+':'+loadset+'/ Unscale FAILED '+mps._elapsed());
      return false;
    }
  };
  
  mps._scaleAdAsync = function (adslot,forceratio,loadset) {
    if (typeof(adslot) != 'string') {
      return false;
    }
    var loadset = (typeof(parseInt(loadset,10) == 'number') && loadset < mps._keys(mps._adloads).length) ? parseInt(loadset,10) : mps._loadset,
        checkslotcount = 1, checkslotinterval = 250, checkslotmax = 12, slotminwidth = 300;
    var checkslot = function (recheckms) {
      var checkslotrun = setTimeout(function () {
        if (mps.selectAd(adslot) && mps._select('#'+mps._adslots[loadset][adslot]+' iframe').clientWidth >= slotminwidth) {
          mps._debug('[mps.scaleAdAsync] /'+adslot+':'+loadset+'/ Execute Scaling (on try '+checkslotcount+') '+mps._elapsed());
          mps._scaleAd(adslot,forceratio,loadset);
          clearTimeout(checkslotrun);
        } else {
          checkslotcount++;
          if (checkslotcount < checkslotmax) {
            checkslot(checkslotinterval);
          } else {
            mps._debug('[mps.scaleAdAsync] /'+adslot+':'+loadset+'/ Not Loaded: '+checkslotmax+' attempts made every '+checkslotinterval+'ms '+mps._elapsed());
          }
        }
      }, recheckms);
    };
    checkslot();
  };
  
  mps._debug('[mps:JS] LOADED: Scaling');
  
}

