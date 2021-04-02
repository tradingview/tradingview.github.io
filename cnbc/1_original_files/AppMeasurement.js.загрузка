//CNBC AppMeasurement for JavaScript version: 1.6.5
//LAST UPDATED 12-14-2018
//console.log('testing Appmeasure');

//Adobe Audience Manager Standard Library
//DIL library starts. ***Not to be altered**
"function"!==typeof window.DIL&&(window.DIL=function(a,c){var d=[],b,f;a!==Object(a)&&(a={});var g,k,m,u,w,n,q,D,x,B,K,E;g=a.partner;k=a.containerNSID;m=!!a.disableDestinationPublishingIframe;u=a.iframeAkamaiHTTPS;w=a.mappings;n=a.uuidCookie;q=!0===a.enableErrorReporting;D=a.visitorService;x=a.declaredId;B=!0===a.removeFinishedScriptsAndCallbacks;K=!0===a.delayAllUntilWindowLoad;E=!0===a.disableIDSyncs;var L,M,N,H,F,O,P,Q;L=!0===a.disableScriptAttachment;M=!0===a.disableCORSFiring;N=!0===a.disableDefaultRequest;
H=a.afterResultForDefaultRequest;F=a.dpIframeSrc;O=!0===a.testCORS;P=!0===a.useJSONPOnly;Q=a.visitorConstructor;q&&DIL.errorModule.activate();var T=!0===window._dil_unit_tests;(b=c)&&d.push(b+"");if(!g||"string"!==typeof g)return b="DIL partner is invalid or not specified in initConfig",DIL.errorModule.handleError({name:"error",message:b,filename:"dil.js"}),Error(b);b="DIL containerNSID is invalid or not specified in initConfig, setting to default of 0";if(k||"number"===typeof k)k=parseInt(k,10),
!isNaN(k)&&0<=k&&(b="");b&&(k=0,d.push(b),b="");f=DIL.getDil(g,k);if(f instanceof DIL&&f.api.getPartner()===g&&f.api.getContainerNSID()===k)return f;if(this instanceof DIL)DIL.registerDil(this,g,k);else return new DIL(a,"DIL was not instantiated with the 'new' operator, returning a valid instance with partner = "+g+" and containerNSID = "+k);var A={IS_HTTPS:"https:"===document.location.protocol,POST_MESSAGE_ENABLED:!!window.postMessage,COOKIE_MAX_EXPIRATION_DATE:"Tue, 19 Jan 2038 03:14:07 UTC"},I=
{stuffed:{}},l={},p={firingQueue:[],fired:[],firing:!1,sent:[],errored:[],reservedKeys:{sids:!0,pdata:!0,logdata:!0,callback:!0,postCallbackFn:!0,useImageRequest:!0},callbackPrefix:"demdexRequestCallback",firstRequestHasFired:!1,useJSONP:!0,abortRequests:!1,num_of_jsonp_responses:0,num_of_jsonp_errors:0,num_of_cors_responses:0,num_of_cors_errors:0,corsErrorSources:[],num_of_img_responses:0,num_of_img_errors:0,toRemove:[],removed:[],readyToRemove:!1,platformParams:{d_nsid:k+"",d_rtbd:"json",d_jsonv:DIL.jsonVersion+
"",d_dst:"1"},nonModStatsParams:{d_rtbd:!0,d_dst:!0,d_cts:!0,d_rs:!0},modStatsParams:null,adms:{TIME_TO_CATCH_ALL_REQUESTS_RELEASE:2E3,calledBack:!1,mid:null,noVisitorAPI:!1,VisitorAPI:null,instance:null,releaseType:"no VisitorAPI",isOptedOut:!0,isOptedOutCallbackCalled:!1,admsProcessingStarted:!1,process:function(e){try{if(!this.admsProcessingStarted){this.admsProcessingStarted=!0;var s=this,a,h,b,d;if("function"===typeof e&&"function"===typeof e.getInstance){if(D===Object(D)&&(a=D.namespace)&&"string"===
typeof a)h=e.getInstance(a,{idSyncContainerID:k});else{this.releaseType="no namespace";this.releaseRequests();return}if(h===Object(h)&&h instanceof e&&"function"===typeof h.isAllowed&&"function"===typeof h.getMarketingCloudVisitorID&&"function"===typeof h.getCustomerIDs&&"function"===typeof h.isOptedOut){this.VisitorAPI=e;if(!h.isAllowed()){this.releaseType="VisitorAPI not allowed";this.releaseRequests();return}this.instance=h;b=function(e){"VisitorAPI"!==s.releaseType&&(s.mid=e,s.releaseType="VisitorAPI",
s.releaseRequests())};d=h.getMarketingCloudVisitorID(b);if("string"===typeof d&&d.length){b(d);return}setTimeout(function(){"VisitorAPI"!==s.releaseType&&(s.releaseType="timeout",s.releaseRequests())},this.TIME_TO_CATCH_ALL_REQUESTS_RELEASE);return}this.releaseType="invalid instance"}else this.noVisitorAPI=!0;this.releaseRequests()}}catch(c){this.releaseRequests()}},releaseRequests:function(){this.calledBack=!0;p.registerRequest()},getMarketingCloudVisitorID:function(){return this.instance?this.instance.getMarketingCloudVisitorID():
null},getMIDQueryString:function(){var e=v.isPopulatedString,s=this.getMarketingCloudVisitorID();e(this.mid)&&this.mid===s||(this.mid=s);return e(this.mid)?"d_mid="+this.mid+"&":""},getCustomerIDs:function(){return this.instance?this.instance.getCustomerIDs():null},getCustomerIDsQueryString:function(e){if(e===Object(e)){var s="",a=[],h=[],b,d;for(b in e)e.hasOwnProperty(b)&&(h[0]=b,d=e[b],d===Object(d)&&(h[1]=d.id||"",h[2]=d.authState||0,a.push(h),h=[]));if(h=a.length)for(e=0;e<h;e++)s+="&d_cid_ic="+
t.encodeAndBuildRequest(a[e],"%01");return s}return""},getIsOptedOut:function(){this.instance?this.instance.isOptedOut([this,this.isOptedOutCallback],this.VisitorAPI.OptOut.GLOBAL,!0):(this.isOptedOut=!1,this.isOptedOutCallbackCalled=!0)},isOptedOutCallback:function(e){this.isOptedOut=e;this.isOptedOutCallbackCalled=!0;p.registerRequest()}},declaredId:{declaredId:{init:null,request:null},declaredIdCombos:{},setDeclaredId:function(e,s){var a=v.isPopulatedString,h=encodeURIComponent;if(e===Object(e)&&
a(s)){var b=e.dpid,d=e.dpuuid,c=null;if(a(b)&&a(d)){c=h(b)+"$"+h(d);if(!0===this.declaredIdCombos[c])return"setDeclaredId: combo exists for type '"+s+"'";this.declaredIdCombos[c]=!0;this.declaredId[s]={dpid:b,dpuuid:d};return"setDeclaredId: succeeded for type '"+s+"'"}}return"setDeclaredId: failed for type '"+s+"'"},getDeclaredIdQueryString:function(){var e=this.declaredId.request,s=this.declaredId.init,a=encodeURIComponent,h="";null!==e?h="&d_dpid="+a(e.dpid)+"&d_dpuuid="+a(e.dpuuid):null!==s&&(h=
"&d_dpid="+a(s.dpid)+"&d_dpuuid="+a(s.dpuuid));return h}},registerRequest:function(e){var a=this.firingQueue;e===Object(e)&&a.push(e);this.firing||!a.length||K&&!DIL.windowLoaded||(this.adms.isOptedOutCallbackCalled||this.adms.getIsOptedOut(),this.adms.calledBack&&!this.adms.isOptedOut&&this.adms.isOptedOutCallbackCalled&&(this.adms.isOptedOutCallbackCalled=!1,e=a.shift(),e.src=e.src.replace(/demdex.net\/event\?d_nsid=/,"demdex.net/event?"+this.adms.getMIDQueryString()+"d_nsid="),v.isPopulatedString(e.corsPostData)&&
(e.corsPostData=e.corsPostData.replace(/^d_nsid=/,this.adms.getMIDQueryString()+"d_nsid=")),C.fireRequest(e),this.firstRequestHasFired||"script"!==e.tag&&"cors"!==e.tag||(this.firstRequestHasFired=!0)))},processVisitorAPI:function(){this.adms.process(Q||window.Visitor)},requestRemoval:function(e){if(!B)return"removeFinishedScriptsAndCallbacks is not boolean true";var a=this.toRemove,r,h;e===Object(e)&&(r=e.script,h=e.callbackName,(r===Object(r)&&"SCRIPT"===r.nodeName||"no script created"===r)&&"string"===
typeof h&&h.length&&a.push(e));if(this.readyToRemove&&a.length){h=a.shift();r=h.script;h=h.callbackName;"no script created"!==r?(e=r.src,r.parentNode.removeChild(r)):e=r;window[h]=null;try{delete window[h]}catch(b){}this.removed.push({scriptSrc:e,callbackName:h});DIL.variables.scriptsRemoved.push(e);DIL.variables.callbacksRemoved.push(h);return this.requestRemoval()}return"requestRemoval() processed"}};f=function(){var e="http://fast.",a="?d_nsid="+k+"#"+encodeURIComponent(document.location.href);
if("string"===typeof F&&F.length)return F+a;A.IS_HTTPS&&(e=!0===u?"https://fast.":"https://");return e+g+".demdex.net/dest5.html"+a};var y={THROTTLE_START:3E4,throttleTimerSet:!1,id:"destination_publishing_iframe_"+g+"_"+k,url:f(),iframe:null,iframeHasLoaded:!1,sendingMessages:!1,messages:[],messagesPosted:[],messageSendingInterval:A.POST_MESSAGE_ENABLED?15:100,ibsDeleted:[],jsonProcessed:[],newIframeCreated:null,iframeIdChanged:!1,originalIframeHasLoadedAlready:null,attachIframe:function(){function e(){h=
document.createElement("iframe");h.id=b.id;h.style.cssText="display: none; width: 0; height: 0;";h.src=b.url;b.newIframeCreated=!0;a();document.body.appendChild(h)}function a(){t.addListener(h,"load",function(){h.className="aamIframeLoaded";b.iframeHasLoaded=!0;b.requestToProcess()})}var b=this,h=document.getElementById(this.id);h?"IFRAME"!==h.nodeName?(this.id+="_2",this.iframeIdChanged=!0,e()):(this.newIframeCreated=!1,"aamIframeLoaded"!==h.className?(this.originalIframeHasLoadedAlready=!1,a()):
(this.iframeHasLoaded=this.originalIframeHasLoadedAlready=!0,this.requestToProcess())):e();this.iframe=h},requestToProcess:function(e,a){var b=this;e&&!v.isEmptyObject(e)&&this.process(e,a);this.iframeHasLoaded&&this.messages.length&&!this.sendingMessages&&(this.throttleTimerSet||(this.throttleTimerSet=!0,setTimeout(function(){b.messageSendingInterval=A.POST_MESSAGE_ENABLED?15:150},this.THROTTLE_START)),this.sendingMessages=!0,this.sendMessages())},process:function(e,a){var b=encodeURIComponent,h,
d,c,g,f,k;a===Object(a)&&(k=t.encodeAndBuildRequest(["",a.dpid||"",a.dpuuid||""],","));if((h=e.dests)&&h instanceof Array&&(d=h.length))for(c=0;c<d;c++)g=h[c],g=[b("dests"),b(g.id||""),b(g.y||""),b(g.c||"")],this.addMessage(g.join("|"));if((h=e.ibs)&&h instanceof Array&&(d=h.length))for(c=0;c<d;c++)g=h[c],g=[b("ibs"),b(g.id||""),b(g.tag||""),t.encodeAndBuildRequest(g.url||[],","),b(g.ttl||""),"",k],this.addMessage(g.join("|"));if((h=e.dpcalls)&&h instanceof Array&&(d=h.length))for(c=0;c<d;c++)g=h[c],
f=g.callback||{},f=[f.obj||"",f.fn||"",f.key||"",f.tag||"",f.url||""],g=[b("dpm"),b(g.id||""),b(g.tag||""),t.encodeAndBuildRequest(g.url||[],","),b(g.ttl||""),t.encodeAndBuildRequest(f,","),k],this.addMessage(g.join("|"));this.jsonProcessed.push(e)},addMessage:function(e){var a=encodeURIComponent,a=q?a("---destpub-debug---"):a("---destpub---");this.messages.push(a+e)},sendMessages:function(){var e=this,a;this.messages.length?(a=this.messages.shift(),DIL.xd.postMessage(a,this.url,this.iframe.contentWindow),
this.messagesPosted.push(a),setTimeout(function(){e.sendMessages()},this.messageSendingInterval)):this.sendingMessages=!1}},J={traits:function(e){v.isValidPdata(e)&&(l.sids instanceof Array||(l.sids=[]),t.extendArray(l.sids,e));return this},pixels:function(e){v.isValidPdata(e)&&(l.pdata instanceof Array||(l.pdata=[]),t.extendArray(l.pdata,e));return this},logs:function(e){v.isValidLogdata(e)&&(l.logdata!==Object(l.logdata)&&(l.logdata={}),t.extendObject(l.logdata,e));return this},customQueryParams:function(e){v.isEmptyObject(e)||
t.extendObject(l,e,p.reservedKeys);return this},signals:function(e,a){var b,h=e;if(!v.isEmptyObject(h)){if(a&&"string"===typeof a)for(b in h={},e)e.hasOwnProperty(b)&&(h[a+b]=e[b]);t.extendObject(l,h,p.reservedKeys)}return this},declaredId:function(e){p.declaredId.setDeclaredId(e,"request");return this},result:function(e){"function"===typeof e&&(l.callback=e);return this},afterResult:function(e){"function"===typeof e&&(l.postCallbackFn=e);return this},useImageRequest:function(){l.useImageRequest=
!0;return this},clearData:function(){l={};return this},submit:function(){C.submitRequest(l);l={};return this},getPartner:function(){return g},getContainerNSID:function(){return k},getEventLog:function(){return d},getState:function(){var e={},a={};t.extendObject(e,p,{callbackPrefix:!0,useJSONP:!0,registerRequest:!0});t.extendObject(a,y,{attachIframe:!0,requestToProcess:!0,process:!0,sendMessages:!0});return{pendingRequest:l,otherRequestInfo:e,destinationPublishingInfo:a}},idSync:function(e){if(E)return"Error: id syncs have been disabled";
if(e!==Object(e)||"string"!==typeof e.dpid||!e.dpid.length)return"Error: config or config.dpid is empty";if("string"!==typeof e.url||!e.url.length)return"Error: config.url is empty";var a=e.url,b=e.minutesToLive,h=encodeURIComponent,d,a=a.replace(/^https:/,"").replace(/^http:/,"");if("undefined"===typeof b)b=20160;else if(b=parseInt(b,10),isNaN(b)||0>=b)return"Error: config.minutesToLive needs to be a positive number";d=t.encodeAndBuildRequest(["",e.dpid,e.dpuuid||""],",");e=["ibs",h(e.dpid),"img",
h(a),b,"",d];y.addMessage(e.join("|"));p.firstRequestHasFired&&y.requestToProcess();return"Successfully queued"},aamIdSync:function(e){if(E)return"Error: id syncs have been disabled";if(e!==Object(e)||"string"!==typeof e.dpuuid||!e.dpuuid.length)return"Error: config or config.dpuuid is empty";e.url="//dpm.demdex.net/ibs:dpid="+e.dpid+"&dpuuid="+e.dpuuid;return this.idSync(e)},passData:function(e){if(v.isEmptyObject(e))return"Error: json is empty or not an object";y.ibsDeleted.push(e.ibs);delete e.ibs;
C.defaultCallback(e);return e},getPlatformParams:function(){return p.platformParams},getEventCallConfigParams:function(){var e=p,a=e.modStatsParams,b=e.platformParams,h;if(!a){a={};for(h in b)b.hasOwnProperty(h)&&!e.nonModStatsParams[h]&&(a[h.replace(/^d_/,"")]=b[h]);e.modStatsParams=a}return a}},C={corsMetadata:function(){var e="none",a=!0;"undefined"!==typeof XMLHttpRequest&&XMLHttpRequest===Object(XMLHttpRequest)&&("withCredentials"in new XMLHttpRequest?e="XMLHttpRequest":(new Function("/*@cc_on return /^10/.test(@_jscript_version) @*/"))()?
e="XMLHttpRequest":"undefined"!==typeof XDomainRequest&&XDomainRequest===Object(XDomainRequest)&&(a=!1),0<Object.prototype.toString.call(window.HTMLElement).indexOf("Constructor")&&(a=!1));return{corsType:e,corsCookiesEnabled:a}}(),getCORSInstance:function(){return"none"===this.corsMetadata.corsType?null:new window[this.corsMetadata.corsType]},submitRequest:function(e){p.registerRequest(C.createQueuedRequest(e));return!0},createQueuedRequest:function(e){var a=p,b,h=e.callback,d="img",c;if(!v.isEmptyObject(w)){var g,
f,n;for(g in w)w.hasOwnProperty(g)&&(f=w[g],null!=f&&""!==f&&g in e&&!(f in e||f in p.reservedKeys)&&(n=e[g],null!=n&&""!==n&&(e[f]=n)))}v.isValidPdata(e.sids)||(e.sids=[]);v.isValidPdata(e.pdata)||(e.pdata=[]);v.isValidLogdata(e.logdata)||(e.logdata={});e.logdataArray=t.convertObjectToKeyValuePairs(e.logdata,"=",!0);e.logdataArray.push("_ts="+(new Date).getTime());"function"!==typeof h&&(h=this.defaultCallback);a.useJSONP=!0!==e.useImageRequest;a.useJSONP&&(d="script",b=a.callbackPrefix+"_"+k+"_"+
(new Date).getTime());a=this.makeRequestSrcData(e,b);!P&&(c=this.getCORSInstance())&&a.truncated&&(this.corsMetadata.corsCookiesEnabled||a.isDeclaredIdCall)&&(d="cors");return{tag:d,src:a.src,corsSrc:a.corsSrc,internalCallbackName:b,callbackFn:h,postCallbackFn:e.postCallbackFn,useImageRequest:!!e.useImageRequest,requestData:e,corsInstance:c,corsPostData:a.corsPostData,hasCORSError:!1}},defaultCallback:function(e,a){var b,h,d,c,g,f,k,x,q;if((b=e.stuff)&&b instanceof Array&&(h=b.length))for(d=0;d<h;d++)if((c=
b[d])&&c===Object(c)){g=c.cn;f=c.cv;k=c.ttl;if("undefined"===typeof k||""===k)k=Math.floor(t.getMaxCookieExpiresInMinutes()/60/24);x=c.dmn||"."+document.domain.replace(/^www\./,"");q=c.type;g&&(f||"number"===typeof f)&&("var"!==q&&(k=parseInt(k,10))&&!isNaN(k)&&t.setCookie(g,f,1440*k,"/",x,!1),I.stuffed[g]=f)}b=e.uuid;v.isPopulatedString(b)&&!v.isEmptyObject(n)&&(h=n.path,"string"===typeof h&&h.length||(h="/"),d=parseInt(n.days,10),isNaN(d)&&(d=100),t.setCookie(n.name||"aam_did",b,1440*d,h,n.domain||
"."+document.domain.replace(/^www\./,""),!0===n.secure));m||p.abortRequests||y.requestToProcess(e,a)},makeRequestSrcData:function(e,a){e.sids=v.removeEmptyArrayValues(e.sids||[]);e.pdata=v.removeEmptyArrayValues(e.pdata||[]);var b=p,d=b.platformParams,c=t.encodeAndBuildRequest(e.sids,","),f=t.encodeAndBuildRequest(e.pdata,","),n=(e.logdataArray||[]).join("&");delete e.logdataArray;var x=A.IS_HTTPS?"https://":"http://",q=b.declaredId.getDeclaredIdQueryString(),w=b.adms.instance?b.adms.getCustomerIDsQueryString(b.adms.getCustomerIDs()):
"",z;z=[];var l,m,u,B;for(l in e)if(!(l in b.reservedKeys)&&e.hasOwnProperty(l))if(m=e[l],l=encodeURIComponent(l),m instanceof Array)for(u=0,B=m.length;u<B;u++)z.push(l+"="+encodeURIComponent(m[u]));else z.push(l+"="+encodeURIComponent(m));z=z.length?"&"+z.join("&"):"";l=!1;c="d_nsid="+d.d_nsid+q+w+(c.length?"&d_sid="+c:"")+(f.length?"&d_px="+f:"")+(n.length?"&d_ld="+encodeURIComponent(n):"");d="&d_rtbd="+d.d_rtbd+"&d_jsonv="+d.d_jsonv+"&d_dst="+d.d_dst;x=x+g+".demdex.net/event";f=b=x+"?"+c+(b.useJSONP?
d+"&d_cb="+(a||""):"")+z;2048<b.length&&(b=b.substring(0,b.lastIndexOf("&")),l=!0);return{corsSrc:x+"?"+(O?"testcors=1&d_nsid="+k+"&":"")+"_ts="+(new Date).getTime(),src:b,originalSrc:f,truncated:l,corsPostData:c+d+z,isDeclaredIdCall:""!==q}},fireRequest:function(e){if("img"===e.tag)this.fireImage(e);else{var a=p.declaredId,a=a.declaredId.request||a.declaredId.init||{},a={dpid:a.dpid||"",dpuuid:a.dpuuid||""};"script"===e.tag?this.fireScript(e,a):"cors"===e.tag&&this.fireCORS(e,a)}},fireImage:function(e){var a=
p,c,h;a.abortRequests||(a.firing=!0,c=new Image(0,0),a.sent.push(e),c.onload=function(){a.firing=!1;a.fired.push(e);a.num_of_img_responses++;a.registerRequest()},h=function(c){b="imgAbortOrErrorHandler received the event of type "+c.type;d.push(b);a.abortRequests=!0;a.firing=!1;a.errored.push(e);a.num_of_img_errors++;a.registerRequest()},c.addEventListener?(c.addEventListener("error",h,!1),c.addEventListener("abort",h,!1)):c.attachEvent&&(c.attachEvent("onerror",h),c.attachEvent("onabort",h)),c.src=
e.src)},fireScript:function(e,a){var c=this,h=p,f,k,n=e.src,x=e.postCallbackFn,q="function"===typeof x,l=e.internalCallbackName;h.abortRequests||(h.firing=!0,window[l]=function(c){try{c!==Object(c)&&(c={});E&&(y.ibsDeleted.push(c.ibs),delete c.ibs);var f=e.callbackFn;h.firing=!1;h.fired.push(e);h.num_of_jsonp_responses++;f(c,a);q&&x(c,a)}catch(r){r.message="DIL jsonp callback caught error with message "+r.message;b=r.message;d.push(b);r.filename=r.filename||"dil.js";r.partner=g;DIL.errorModule.handleError(r);
try{f({error:r.name+"|"+r.message},a),q&&x({error:r.name+"|"+r.message},a)}catch(n){}}finally{h.requestRemoval({script:k,callbackName:l}),h.registerRequest()}},L?(h.firing=!1,h.requestRemoval({script:"no script created",callbackName:l})):(k=document.createElement("script"),k.addEventListener&&k.addEventListener("error",function(a){h.requestRemoval({script:k,callbackName:l});b="jsonp script tag error listener received the event of type "+a.type+" with src "+n;c.handleScriptError(b,e)},!1),k.type="text/javascript",
k.src=n,f=DIL.variables.scriptNodeList[0],f.parentNode.insertBefore(k,f)),h.sent.push(e),h.declaredId.declaredId.request=null)},fireCORS:function(a,c){function f(r){var n;try{if(n=JSON.parse(r),n!==Object(n)){h.handleCORSError(a,c,"Response is not JSON");return}}catch(q){h.handleCORSError(a,c,"Error parsing response as JSON");return}try{var x=a.callbackFn;k.firing=!1;k.fired.push(a);k.num_of_cors_responses++;x(n,c);m&&w(n,c)}catch(l){l.message="DIL handleCORSResponse caught error with message "+l.message;
b=l.message;d.push(b);l.filename=l.filename||"dil.js";l.partner=g;DIL.errorModule.handleError(l);try{x({error:l.name+"|"+l.message},c),m&&w({error:l.name+"|"+l.message},c)}catch(p){}}finally{k.registerRequest()}}var h=this,k=p,n=this.corsMetadata.corsType,x=a.corsSrc,q=a.corsInstance,l=a.corsPostData,w=a.postCallbackFn,m="function"===typeof w;if(!k.abortRequests){k.firing=!0;if(M)k.firing=!1;else try{q.open("post",x,!0),"XMLHttpRequest"===n?(q.withCredentials=!0,q.setRequestHeader("Content-Type",
"application/x-www-form-urlencoded"),q.onreadystatechange=function(){4===this.readyState&&(200===this.status?f(this.responseText):h.handleCORSError(a,c,"onreadystatechange"))}):"XDomainRequest"===n&&(q.onload=function(){f(this.responseText)}),q.onerror=function(){h.handleCORSError(a,c,"onerror")},q.ontimeout=function(){h.handleCORSError(a,c,"ontimeout")},q.send(l)}catch(u){this.handleCORSError(a,c,"try-catch")}k.sent.push(a);k.declaredId.declaredId.request=null}},handleCORSError:function(a,b,c){a.hasCORSError||
(a.hasCORSError=!0,p.num_of_cors_errors++,p.corsErrorSources.push(c),a.tag="script",this.fireScript(a,b))},handleScriptError:function(a,b){p.num_of_jsonp_errors++;this.handleRequestError(a,b)},handleRequestError:function(a,b){var c=p;d.push(a);c.abortRequests=!0;c.firing=!1;c.errored.push(b);c.registerRequest()}},v={isValidPdata:function(a){return a instanceof Array&&this.removeEmptyArrayValues(a).length?!0:!1},isValidLogdata:function(a){return!this.isEmptyObject(a)},isEmptyObject:function(a){if(a!==
Object(a))return!0;for(var b in a)if(a.hasOwnProperty(b))return!1;return!0},removeEmptyArrayValues:function(a){for(var b=0,c=a.length,d,g=[],b=0;b<c;b++)d=a[b],"undefined"!==typeof d&&null!==d&&""!==d&&g.push(d);return g},isPopulatedString:function(a){return"string"===typeof a&&a.length}},t={addListener:function(){if(document.addEventListener)return function(a,b,c){a.addEventListener(b,function(a){"function"===typeof c&&c(a)},!1)};if(document.attachEvent)return function(a,b,c){a.attachEvent("on"+
b,function(a){"function"===typeof c&&c(a)})}}(),convertObjectToKeyValuePairs:function(a,b,c){var d=[],g,f;b||(b="=");for(g in a)a.hasOwnProperty(g)&&(f=a[g],"undefined"!==typeof f&&null!==f&&""!==f&&d.push(g+b+(c?encodeURIComponent(f):f)));return d},encodeAndBuildRequest:function(a,b){return this.map(a,function(a){return encodeURIComponent(a)}).join(b)},map:function(a,b){if(Array.prototype.map)return a.map(b);if(void 0===a||null===a)throw new TypeError;var c=Object(a),d=c.length>>>0;if("function"!==
typeof b)throw new TypeError;for(var g=Array(d),f=0;f<d;f++)f in c&&(g[f]=b.call(b,c[f],f,c));return g},filter:function(a,b){if(!Array.prototype.filter){if(void 0===a||null===a)throw new TypeError;var c=Object(a),d=c.length>>>0;if("function"!==typeof b)throw new TypeError;for(var g=[],f=0;f<d;f++)if(f in c){var k=c[f];b.call(b,k,f,c)&&g.push(k)}return g}return a.filter(b)},getCookie:function(a){a+="=";var b=document.cookie.split(";"),c,d,f;c=0;for(d=b.length;c<d;c++){for(f=b[c];" "===f.charAt(0);)f=
f.substring(1,f.length);if(0===f.indexOf(a))return decodeURIComponent(f.substring(a.length,f.length))}return null},setCookie:function(a,b,c,d,f,g){var k=new Date;c&&(c*=6E4);document.cookie=a+"="+encodeURIComponent(b)+(c?";expires="+(new Date(k.getTime()+c)).toUTCString():"")+(d?";path="+d:"")+(f?";domain="+f:"")+(g?";secure":"")},extendArray:function(a,b){return a instanceof Array&&b instanceof Array?(Array.prototype.push.apply(a,b),!0):!1},extendObject:function(a,b,c){var d;if(a===Object(a)&&b===
Object(b)){for(d in b)!b.hasOwnProperty(d)||!v.isEmptyObject(c)&&d in c||(a[d]=b[d]);return!0}return!1},getMaxCookieExpiresInMinutes:function(){return((new Date(A.COOKIE_MAX_EXPIRATION_DATE)).getTime()-(new Date).getTime())/1E3/60}};"error"===g&&0===k&&t.addListener(window,"load",function(){DIL.windowLoaded=!0});var R=!1,G=function(){R||(R=!0,p.registerRequest(),U(),m||p.abortRequests||y.attachIframe(),p.readyToRemove=!0,p.requestRemoval())},U=function(){m||setTimeout(function(){N||p.firstRequestHasFired||
("function"===typeof H?J.afterResult(H).submit():J.submit())},DIL.constants.TIME_TO_DEFAULT_REQUEST)},S=document;"error"!==g&&(DIL.windowLoaded?G():"complete"!==S.readyState&&"loaded"!==S.readyState?t.addListener(window,"load",function(){DIL.windowLoaded=!0;G()}):(DIL.windowLoaded=!0,G()));p.declaredId.setDeclaredId(x,"init");p.processVisitorAPI();this.api=J;this.getStuffedVariable=function(a){var b=I.stuffed[a];b||"number"===typeof b||(b=t.getCookie(a))||"number"===typeof b||(b="");return b};this.validators=
v;this.helpers=t;this.constants=A;this.log=d;T&&(this.pendingRequest=l,this.requestController=p,this.setDestinationPublishingUrl=f,this.destinationPublishing=y,this.requestProcs=C,this.variables=I,this.callWindowLoadFunctions=G)},function(){var a=document,c;null==a.readyState&&a.addEventListener&&(a.readyState="loading",a.addEventListener("DOMContentLoaded",c=function(){a.removeEventListener("DOMContentLoaded",c,!1);a.readyState="complete"},!1))}(),DIL.extendStaticPropertiesAndMethods=function(a){var c;
if(a===Object(a))for(c in a)a.hasOwnProperty(c)&&(this[c]=a[c])},DIL.extendStaticPropertiesAndMethods({version:"6.4",jsonVersion:1,constants:{TIME_TO_DEFAULT_REQUEST:50},variables:{scriptNodeList:document.getElementsByTagName("script"),scriptsRemoved:[],callbacksRemoved:[]},windowLoaded:!1,dils:{},isAddedPostWindowLoad:function(a){this.windowLoaded="function"===typeof a?!!a():"boolean"===typeof a?a:!0},create:function(a){try{return new DIL(a)}catch(c){return(new Image(0,0)).src="http://error.demdex.net/event?d_nsid=0&d_px=14137&d_ld=name%3Derror%26filename%3Ddil.js%26partner%3Dno_partner%26message%3DError%2520in%2520attempt%2520to%2520create%2520DIL%2520instance%2520with%2520DIL.create()%26_ts%3D"+
(new Date).getTime(),Error("Error in attempt to create DIL instance with DIL.create()")}},registerDil:function(a,c,d){c=c+"$"+d;c in this.dils||(this.dils[c]=a)},getDil:function(a,c){var d;"string"!==typeof a&&(a="");c||(c=0);d=a+"$"+c;return d in this.dils?this.dils[d]:Error("The DIL instance with partner = "+a+" and containerNSID = "+c+" was not found")},dexGetQSVars:function(a,c,d){c=this.getDil(c,d);return c instanceof this?c.getStuffedVariable(a):""},xd:{postMessage:function(a,c,d){var b=1;c&&
(window.postMessage?d.postMessage(a,c.replace(/([^:]+:\/\/[^\/]+).*/,"$1")):c&&(d.location=c.replace(/#.*$/,"")+"#"+ +new Date+b++ +"&"+a))}}}),DIL.errorModule=function(){var a=DIL.create({partner:"error",containerNSID:0,disableDestinationPublishingIframe:!0}),c={harvestererror:14138,destpuberror:14139,dpmerror:14140,generalerror:14137,error:14137,noerrortypedefined:15021,evalerror:15016,rangeerror:15017,referenceerror:15018,typeerror:15019,urierror:15020},d=!1;return{activate:function(){d=!0},handleError:function(b){if(!d)return"DIL error module has not been activated";
b!==Object(b)&&(b={});var f=b.name?(b.name+"").toLowerCase():"",g=[];b={name:f,filename:b.filename?b.filename+"":"",partner:b.partner?b.partner+"":"no_partner",site:b.site?b.site+"":document.location.href,message:b.message?b.message+"":""};g.push(f in c?c[f]:c.noerrortypedefined);a.api.pixels(g).logs(b).useImageRequest().submit();return"DIL error report sent"},pixelMap:c}}(),DIL.tools={},DIL.modules={helpers:{handleModuleError:function(a,c,d){var b="";c=c||"Error caught in DIL module/submodule: ";
a===Object(a)?b=c+(a.message||"err has no message"):(b=c+"err is not a valid object",a={});a.message=b;d instanceof DIL&&(a.partner=d.api.getPartner());DIL.errorModule.handleError(a);return this.errorMessage=b}}});
DIL.tools.getSearchReferrer=function(a,c){var d=DIL.getDil("error"),b=DIL.tools.decomposeURI(a||document.referrer),f="",g="",k={queryParam:"q"};return(f=d.helpers.filter([c===Object(c)?c:{},{hostPattern:/aol\./},{hostPattern:/ask\./},{hostPattern:/bing\./},{hostPattern:/google\./},{hostPattern:/yahoo\./,queryParam:"p"}],function(a){return!(!a.hasOwnProperty("hostPattern")||!b.hostname.match(a.hostPattern))}).shift())?{valid:!0,name:b.hostname,keywords:(d.helpers.extendObject(k,f),g=k.queryPattern?
(f=(""+b.search).match(k.queryPattern))?f[1]:"":b.uriParams[k.queryParam],decodeURIComponent(g||"").replace(/\+|%20/g," "))}:{valid:!1,name:"",keywords:""}};
DIL.tools.decomposeURI=function(a){var c=DIL.getDil("error"),d=document.createElement("a");d.href=a||document.referrer;return{hash:d.hash,host:d.host.split(":").shift(),hostname:d.hostname,href:d.href,pathname:d.pathname.replace(/^\//,""),protocol:d.protocol,search:d.search,uriParams:function(a,d){c.helpers.map(d.split("&"),function(c){c=c.split("=");a[c.shift()]=c.shift()});return a}({},d.search.replace(/^(\/|\?)?|\/$/g,""))}};
DIL.tools.getMetaTags=function(){var a={},c=document.getElementsByTagName("meta"),d,b,f,g,k;d=0;for(f=arguments.length;d<f;d++)if(g=arguments[d],null!==g)for(b=0;b<c.length;b++)if(k=c[b],k.name===g){a[g]=k.content;break}return a};
DIL.modules.siteCatalyst={dil:null,handle:DIL.modules.helpers.handleModuleError,init:function(a,c,d,b){try{var f=this,g={name:"DIL Site Catalyst Module Error"},k=function(a){g.message=a;DIL.errorModule.handleError(g);return a};this.options=b===Object(b)?b:{};this.dil=null;if(c instanceof DIL)this.dil=c;else return k("dilInstance is not a valid instance of DIL");g.partner=c.api.getPartner();if(a!==Object(a))return k("siteCatalystReportingSuite is not an object");window.AppMeasurement_Module_DIL=a.m_DIL=
function(a){var b="function"===typeof a.m_i?a.m_i("DIL"):this;if(b!==Object(b))return k("m is not an object");b.trackVars=f.constructTrackVars(d);b.d=0;b.s=a;b._t=function(){var a,b,c=","+this.trackVars+",",d=this.s,g,m=[];g=[];var w={},u=!1;if(d!==Object(d))return k("Error in m._t function: s is not an object");if(this.d){if("function"===typeof d.foreachVar)d.foreachVar(function(a,b){"undefined"!==typeof b&&(w[a]=b,u=!0)},this.trackVars);else{if(!(d.va_t instanceof Array))return k("Error in m._t function: s.va_t is not an array");
if(d.lightProfileID)(a=d.lightTrackVars)&&(a=","+a+","+d.vl_mr+",");else if(d.pe||d.linkType)a=d.linkTrackVars,d.pe&&(b=d.pe.substring(0,1).toUpperCase()+d.pe.substring(1),d[b]&&(a=d[b].trackVars)),a&&(a=","+a+","+d.vl_l+","+d.vl_l2+",");if(a){b=0;for(m=a.split(",");b<m.length;b++)0<=c.indexOf(","+m[b]+",")&&g.push(m[b]);g.length&&(c=","+g.join(",")+",")}g=0;for(b=d.va_t.length;g<b;g++)a=d.va_t[g],0<=c.indexOf(","+a+",")&&"undefined"!==typeof d[a]&&null!==d[a]&&""!==d[a]&&(w[a]=d[a],u=!0)}f.includeContextData(d,
w).store_populated&&(u=!0);u&&this.d.api.signals(w,"c_").submit()}}};a.loadModule("DIL");a.DIL.d=c;return g.message?g.message:"DIL.modules.siteCatalyst.init() completed with no errors"}catch(m){return this.handle(m,"DIL.modules.siteCatalyst.init() caught error with message ",this.dil)}},constructTrackVars:function(a){var c=[],d,b,f,g,k;if(a===Object(a)){d=a.names;if(d instanceof Array&&(f=d.length))for(b=0;b<f;b++)g=d[b],"string"===typeof g&&g.length&&c.push(g);a=a.iteratedNames;if(a instanceof Array&&
(f=a.length))for(b=0;b<f;b++)if(d=a[b],d===Object(d)&&(g=d.name,k=parseInt(d.maxIndex,10),"string"===typeof g&&g.length&&!isNaN(k)&&0<=k))for(d=0;d<=k;d++)c.push(g+d);if(c.length)return c.join(",")}return this.constructTrackVars({names:"pageName channel campaign products events pe pev1 pev2 pev3".split(" "),iteratedNames:[{name:"prop",maxIndex:75},{name:"eVar",maxIndex:250}]})},includeContextData:function(a,c){var d={},b=!1;if(a.contextData===Object(a.contextData)){var f=a.contextData,g=this.options.replaceContextDataPeriodsWith,
k=this.options.filterFromContextVariables,m={},u,w,n,q;"string"===typeof g&&g.length||(g="_");if(k instanceof Array)for(u=0,w=k.length;u<w;u++)n=k[u],this.dil.validators.isPopulatedString(n)&&(m[n]=!0);for(q in f)!f.hasOwnProperty(q)||m[q]||!(k=f[q])&&"number"!==typeof k||(q=("contextData."+q).replace(/\./g,g),c[q]=k,b=!0)}d.store_populated=b;return d}};
DIL.modules.GA={dil:null,arr:null,tv:null,errorMessage:"",defaultTrackVars:["_setAccount","_setCustomVar","_addItem","_addTrans","_trackSocial"],defaultTrackVarsObj:null,signals:{},hasSignals:!1,handle:DIL.modules.helpers.handleModuleError,init:function(a,c,d){try{this.tv=this.arr=this.dil=null;this.errorMessage="";this.signals={};this.hasSignals=!1;var b={name:"DIL GA Module Error"},f="";c instanceof DIL?(this.dil=c,b.partner=this.dil.api.getPartner()):(f="dilInstance is not a valid instance of DIL",
b.message=f,DIL.errorModule.handleError(b));a instanceof Array&&a.length?this.arr=a:(f="gaArray is not an array or is empty",b.message=f,DIL.errorModule.handleError(b));this.tv=this.constructTrackVars(d);this.errorMessage=f}catch(g){this.handle(g,"DIL.modules.GA.init() caught error with message ",this.dil)}finally{return this}},constructTrackVars:function(a){var c=[],d,b,f,g;if(this.defaultTrackVarsObj!==Object(this.defaultTrackVarsObj)){f=this.defaultTrackVars;g={};d=0;for(b=f.length;d<b;d++)g[f[d]]=
!0;this.defaultTrackVarsObj=g}else g=this.defaultTrackVarsObj;if(a===Object(a)){a=a.names;if(a instanceof Array&&(b=a.length))for(d=0;d<b;d++)f=a[d],"string"===typeof f&&f.length&&f in g&&c.push(f);if(c.length)return c}return this.defaultTrackVars},constructGAObj:function(a){var c={};a=a instanceof Array?a:this.arr;var d,b,f,g;d=0;for(b=a.length;d<b;d++)f=a[d],f instanceof Array&&f.length&&(f=[],g=a[d],f instanceof Array&&g instanceof Array&&Array.prototype.push.apply(f,g),g=f.shift(),"string"===
typeof g&&g.length&&(c[g]instanceof Array||(c[g]=[]),c[g].push(f)));return c},addToSignals:function(a,c){if("string"!==typeof a||""===a||null==c||""===c)return!1;this.signals[a]instanceof Array||(this.signals[a]=[]);this.signals[a].push(c);return this.hasSignals=!0},constructSignals:function(){var a=this.constructGAObj(),c={_setAccount:function(a){this.addToSignals("c_accountId",a)},_setCustomVar:function(a,b,c){"string"===typeof b&&b.length&&this.addToSignals("c_"+b,c)},_addItem:function(a,b,c,d,
f,g){this.addToSignals("c_itemOrderId",a);this.addToSignals("c_itemSku",b);this.addToSignals("c_itemName",c);this.addToSignals("c_itemCategory",d);this.addToSignals("c_itemPrice",f);this.addToSignals("c_itemQuantity",g)},_addTrans:function(a,b,c,d,f,g,k,m){this.addToSignals("c_transOrderId",a);this.addToSignals("c_transAffiliation",b);this.addToSignals("c_transTotal",c);this.addToSignals("c_transTax",d);this.addToSignals("c_transShipping",f);this.addToSignals("c_transCity",g);this.addToSignals("c_transState",
k);this.addToSignals("c_transCountry",m)},_trackSocial:function(a,b,c,d){this.addToSignals("c_socialNetwork",a);this.addToSignals("c_socialAction",b);this.addToSignals("c_socialTarget",c);this.addToSignals("c_socialPagePath",d)}},d=this.tv,b,f,g,k,m,u;b=0;for(f=d.length;b<f;b++)if(g=d[b],a.hasOwnProperty(g)&&c.hasOwnProperty(g)&&(u=a[g],u instanceof Array))for(k=0,m=u.length;k<m;k++)c[g].apply(this,u[k])},submit:function(){try{if(""!==this.errorMessage)return this.errorMessage;this.constructSignals();
return this.hasSignals?(this.dil.api.signals(this.signals).submit(),"Signals sent: "+this.dil.helpers.convertObjectToKeyValuePairs(this.signals,"=",!0)+this.dil.log):"No signals present"}catch(a){return this.handle(a,"DIL.modules.GA.submit() caught error with message ",this.dil)}},Stuffer:{LIMIT:5,dil:null,cookieName:null,delimiter:null,errorMessage:"",handle:DIL.modules.helpers.handleModuleError,callback:null,v:function(){return!1},init:function(a,c,d){try{this.callback=this.dil=null,this.errorMessage=
"",a instanceof DIL?(this.dil=a,this.v=this.dil.validators.isPopulatedString,this.cookieName=this.v(c)?c:"aam_ga",this.delimiter=this.v(d)?d:"|"):this.handle({message:"dilInstance is not a valid instance of DIL"},"DIL.modules.GA.Stuffer.init() error: ")}catch(b){this.handle(b,"DIL.modules.GA.Stuffer.init() caught error with message ",this.dil)}finally{return this}},process:function(a){var c,d,b,f,g,k;k=!1;var m=1;if(a===Object(a)&&(c=a.stuff)&&c instanceof Array&&(d=c.length))for(a=0;a<d;a++)if((b=
c[a])&&b===Object(b)&&(f=b.cn,g=b.cv,f===this.cookieName&&this.v(g))){k=!0;break}if(k){c=g.split(this.delimiter);"undefined"===typeof window._gaq&&(window._gaq=[]);b=window._gaq;a=0;for(d=c.length;a<d&&!(k=c[a].split("="),g=k[0],k=k[1],this.v(g)&&this.v(k)&&b.push(["_setCustomVar",m++,g,k,1]),m>this.LIMIT);a++);this.errorMessage=1<m?"No errors - stuffing successful":"No valid values to stuff"}else this.errorMessage="Cookie name and value not found in json";if("function"===typeof this.callback)return this.callback()},
submit:function(){try{var a=this;if(""!==this.errorMessage)return this.errorMessage;this.dil.api.afterResult(function(c){a.process(c)}).submit();return"DIL.modules.GA.Stuffer.submit() successful"}catch(c){return this.handle(c,"DIL.modules.GA.Stuffer.submit() caught error with message ",this.dil)}}}};
DIL.modules.Peer39={aid:"",dil:null,optionals:null,errorMessage:"",calledBack:!1,script:null,scriptsSent:[],returnedData:[],handle:DIL.modules.helpers.handleModuleError,init:function(a,c,d){try{this.dil=null;this.errorMessage="";this.calledBack=!1;this.optionals=d===Object(d)?d:{};d={name:"DIL Peer39 Module Error"};var b=[],f="";this.isSecurePageButNotEnabled(document.location.protocol)&&(f="Module has not been enabled for a secure page",b.push(f),d.message=f,DIL.errorModule.handleError(d));c instanceof
DIL?(this.dil=c,d.partner=this.dil.api.getPartner()):(f="dilInstance is not a valid instance of DIL",b.push(f),d.message=f,DIL.errorModule.handleError(d));"string"===typeof a&&a.length?this.aid=a:(f="aid is not a string or is empty",b.push(f),d.message=f,DIL.errorModule.handleError(d));this.errorMessage=b.join("\n")}catch(g){this.handle(g,"DIL.modules.Peer39.init() caught error with message ",this.dil)}finally{return this}},isSecurePageButNotEnabled:function(a){return"https:"===a&&!0!==this.optionals.enableHTTPS?
!0:!1},constructSignals:function(){var a=this,c=this.constructScript(),d=DIL.variables.scriptNodeList[0];window["afterFinished_"+this.aid]=function(){try{var b=a.processData(p39_KVP_Short("c_p","|").split("|"));b.hasSignals&&a.dil.api.signals(b.signals).submit()}catch(c){}finally{a.calledBack=!0,"function"===typeof a.optionals.afterResult&&a.optionals.afterResult()}};d.parentNode.insertBefore(c,d);this.scriptsSent.push(c);return"Request sent to Peer39"},processData:function(a){var c,d,b,f,g={},k=
!1;this.returnedData.push(a);if(a instanceof Array)for(c=0,d=a.length;c<d;c++)b=a[c].split("="),f=b[0],b=b[1],f&&isFinite(b)&&!isNaN(parseInt(b,10))&&(g[f]instanceof Array||(g[f]=[]),g[f].push(b),k=!0);return{hasSignals:k,signals:g}},constructScript:function(){var a=document.createElement("script"),c=this.optionals,d=c.scriptId,b=c.scriptSrc,c=c.scriptParams;a.id="string"===typeof d&&d.length?d:"peer39ScriptLoader";a.type="text/javascript";"string"===typeof b&&b.length?a.src=b:(a.src=(this.dil.constants.IS_HTTPS?
"https:":"http:")+"//stags.peer39.net/"+this.aid+"/trg_"+this.aid+".js","string"===typeof c&&c.length&&(a.src+="?"+c));return a},submit:function(){try{return""!==this.errorMessage?this.errorMessage:this.constructSignals()}catch(a){return this.handle(a,"DIL.modules.Peer39.submit() caught error with message ",this.dil)}}};
//DIL library ends ** Above code not to be altered**

var s=s_gi(s_account)
s.visitorNamespace="nbcuniversal"
s.trackingServer=s_omniServer
s.trackingServerSecure=s_omniSecureServer
s.linkInternalFilters=s_linkInternalFilters;
s.trackDownloadLinks=true
s.trackExternalLinks=true
s.trackInlineStats=true
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,widget"
s.linkLeaveQueryString=false

s.visitor=Visitor.getInstance("A8AB776A5245B4220A490D44@AdobeOrg"); 

/* Plugin Config */
s.usePlugins=true
function s_doPlugins(s) {
	/* Add calls to plugins here */
	//Time Parting
	//time parting configuration
	s._tpDST = {
	2012:'3/11,11/4',
	2013:'3/10,11/3',
	2014:'3/9,11/2',
	2015:'3/8,11/1',
	2016:'3/13,11/6',
	2017:'3/12,11/5',
	2018:'3/11,11/4',
	2019:'3/10,11/3',
	2020:'3/8,11/1',
	2021:'3/14,11/7',
	2022:'3/13,11/6',
	2023:'3/12,11/5',
	2024:'3/10,11/3',
	2025:'3/9,11/2',
	2026:'3/8,11/1',
	2027:'3/14,11/7',
	2028:'3/12,11/5'}
	var tpA = s.getTimeParting('n','-5');
	s.contextData['cnbc.hour'] = tpA[1];// Set hour
	s.contextData['cnbc.day'] = tpA[2];// Set day
	s.contextData['cnbc.daytype'] = tpA[3];// Set day type
    s.contextData['cnbc.mid'] = visitor.getMarketingCloudVisitorID();
	//new repeat
	s.contextData['cnbc.newrepmon'] = s.getNewRepeat(30,'s_getNewRepeat30');
	s.contextData['cnbc.newrep90'] = s.getNewRepeat(90,'s_getNewRepeat90');

	//monthly visit number
	s.contextData['cnbc.sessionnumber'] = s.getVisitNum('m','s_vmonthnum','s_monthinvisit');

	//days since last visit
	s.contextData['cnbc.dayslastvisit'] = s.getDaysSinceLastVisit('s_lv');

	//Read linktrk cookie
	if(!s.Util.cookieRead('linktrk')) {
	    s.Util.cookieWrite('linktrk', '', 0);
	}
	else
	{
		s.contextData['cnbc.trknav'] = s.Util.cookieRead('linktrk');
		s.Util.cookieWrite('linktrk', '', 0);
		}

	//Auto Link Tracking
	if(!!(navigator.userAgent.match(/Trident/) && !navigator.userAgent.match(/MSIE/))){
		s.hbx_lt = "auto";
		s.setupLinkTrack(",propLT,,propLP","SC_LINKS");
		s.contextData['cnbc.trknav'] = s.propLT;
	}

	//write bedrocktrk cookie, expires in 3 months
	if(s.Util.cookieRead('bedrocktrk')) {
		var bedrockData = s.Util.cookieRead('bedrocktrk');
		//console.log('bedrockData: ' + bedrockData);
		tbedrockData = bedrockData.split('|');
		s.contextData['cnbc.bedrock0'] = tbedrockData[0];
		s.contextData['cnbc.bedrockData'] = bedrockData;
		var bedrockTrkDate = new Date();
		bedrockTrkDate.setMonth(bedrockTrkDate.getMonth() + 3);
		s.Util.cookieWrite('bedrocktrk', bedrockData, bedrockTrkDate);
	}

	//MPS customObj for Adobe Audience Manager DIL
	//Needs to be loaded before DIL code
	if(typeof mps != 'undefined') {
		mps._datamapValue=function(a,d){d=d||mps.pagevars.instance;if(!mps.pagevars)return!1;if(!mps.datamaps||!mps.datamaps[a])return mps._d("[mps/datamaps] FAILED - Data mapping set does not exist: "+a),!1;var b=d?d:mps.pagevars.instance;if(b&&"automagic"!=b&&mps.datamaps[a][b])return mps.datamaps[a][d];var b=window.location.host.split("."),c=b.pop(),c=b.pop()+"."+c;b.reverse();if(mps.datamaps[a][c])return mps.datamaps[a][c];for(var e=0;e<b.length;e++)if(c=b[e]+"."+c,mps.datamaps[a][c])return mps.datamaps[a][c];mps._l("[mps/datamaps] FAILED - Data mapping value for ["+a+"] does not exist on: "+d);return!1};

		mps.aam=mps.aam||{};

		mps.aam.INIT = function(){
		  /*--[ CONFIGURATION ]------------------------------------------------*/
		  mps.aam._scripts = {
		    'example': mps._protocol()+'//site.com/example.js',
		  }

		  mps.aam._opts = {
		    'visitornamespace':'A8AB776A5245B4220A490D44@AdobeOrg',
		  }

		  this._visitorns = mps._datamapValue('adobeorg');
		  if(this._visitorns) mps.aam._opts.visitornamespace = this._visitorns;

		  mps.aam._conf = {
		    'missingval':'UNKNOWN',
		    'rootpage':{'type':'home','cat':'home'},
		    'cleanregex':/[^-a-z0-9_~. \s]/ig,
		    'maxlength':25,
		  }

		  mps.aam.site = mps.pagevars.instance;
		  mps.aam.brand = mps.pagevars.instance.split('-')[0];

		  mps.aam._status = 0;
		  if(typeof(mps.aam.opts=='object')) mps._merge(mps.aam._opts,mps.aam.opts)
		  if(typeof(mps.aam.conf=='object')) mps._merge(mps.aam._conf,mps.aam.conf)
		  this.cd={}; this._data={};

		  mps.aam.defineData = function() {
		    this._data.cid = mps.pagevars.cid;
		    this._data.cat = mps.pagevars.cats;
		    this._data.type = mps.pagevars.type;
		    this._data.mpspath = mps._trim(mps.pagevars.path,'/').split('/');
		    this._data.pathsegs = mps._trim(window.location.pathname,'/').split('/');
		    this._data.hostsegs = window.location.host.split('.');
		    // handle path prefix format
		    if(this._data.mpspath[0].indexOf(':')>-1) {
		      var _seg = this._data.mpspath[0].split(':');
		      this._data.pathprefix = _seg[0];
		      if(_seg[1]=='') {
		        this._data.mpspath.shift();
		      } else {
		        this._data.mpspath[0] = _seg[1];
		      }
		    }
		    this._data.pageinfo={}
		    if(mpscall.is_content===0 || mpscall.is_content==='0') this._data.pageinfo.notcontent=1;
		    if(mpscall.is_content===1 || mpscall.is_content==='1') this._data.pageinfo.iscontent=1;
		    if(this._data.mpspath===0) {
		      this._data.pageinfo.home=1;
		      if(this._data.cat.length===0) this._data.cat.push(this._conf.rootpage.cat);
		      if(this._data.type=='') this._data.type=this._conf.rootpage.cat(type);
		    }
		    this._l('executed: defineData');
		    return this._data;
		  }

		  mps.aam.setData = function(){

		    // set nbcu context data variables
		    this.cd['nbcu_brand'] = mps.aam.brand;
		    this.cd['nbcu-'+mps.aam.brand+'-contenttype'] = mps.pagevars.type ? mps.pagevars.type : 'page';
		    this.cd['nbcu_cleantitle'] = mps.aam._clean(window.document.title,50).replace(/\s\s+/g,' ');
		    // set mps context data variables
		    this.cd['mps_contentid'] = this._data.cid;
		    this.cd['mps_path'] = mps.pagevars.path;
		    if(mps._ext && mps._ext._insertedads) this.cd['mps-'+mps.aam.brand+'-cats'] = this._data.cat.join('|');
		    for(var i=0; i<this._data.cat.length; i++) {
		      this.cd['mps-'+mps.aam.brand+'-cat'+(i+1)] = this._data.cat[i];
		    }
		    if(mps.pagevars.dart_mode) this.cd['mps_admode'] = mps.pagevars.dart_mode;
		    if(mps._ext && mps._ext._insertedads) this.cd['mps_adsinserted'] = mps._ext._insertedads;
		    if(mps.pagevars.dart_lazy_load) this.cd['mps_adlazyload'] = mps.pagevars.dart_lazy_load;
		    if(mps._ab && mps._ab.run && typeof(adBlockEnabled)!='undefined') this.cd['mps_adblock'] = adBlockEnabled ? 1 : 0;
		    if(typeof(mps.pagevars.cags)=='object') {
		      for(var i in mps.pagevars.cags) {
		        this.cd['mps_cag-'+mps.aam.brand+'-'+i] = mps.pagevars.cags[i];
		      }
		    }
		    if(typeof(mps.pagevars.fields)=='object') {
		      for(var i in mps.pagevars.fields) {
		        this.cd['mps_field-'+mps.aam.brand+'-'+i] = mps.pagevars.fields[i];
		      }
		    }
		    if(mps.pagevars.freewheel_section) this.cd['mps_fwssid'] = mps.pagevars.freewheel_section;
		    if(typeof(mps._loadset)=='number') this.cd['mps_loadset'] = mps._loadset;
		    if(mps.response && mps.response.page) {
		      if(mps.response.page.gpt_adid) this.cd['mps_adunitid'] = mps.response.page.gpt_adid;
		      if(mps.response.page.package) this.cd['mps_packageid'] = mps.response.page.package;
		    }
		    if(mps.pagevars.ref) this.cd['mps_refdomain'] = mps.pagevars.ref;
		    this.cd['pagename'] = mps.aam.cd['nbcu_brand']+'|'+mps.aam.cd['nbcu-'+mps.aam.brand+'-contenttype']+'|'+mps.aam.cd['mps-'+mps.aam.brand+'-cat1']+'|'+mps.aam.cd['mps_contentid']+'|'+this.cd['nbcu_cleantitle'];
		    this._l('executed: setData');
		    return this.cd;
		  }
		  mps.aam.customObj ={};
		  mps.aam._applyData = function() {
		    var _set={};
		    // merge mps.data if previously set
		    if(typeof(mps.data)=='object' && mps._keys(mps.data).length>0) this.cd = mps._merge(this.cd, mps.data)
		    for(var i in this.cd) {
		      var _cdval = this.cd[i];
		      var _isarr = 0;
		      if(typeof(_cdval)=='boolean') _cdval=_cdval+0;
		      if(typeof(_cdval)=='number') _cdval=_cdval.toString();
		      if(Object.prototype.toString.call(this.cd[i])==='[object Array]') {
		        _cdval.sort();
		        _isarr = 1;
		        //_cdval=_cdval.join(',');
		      }
		      if(typeof(_cdval)!='string' && !_isarr) {
		        this._l('(skipped applyData: '+i+')');
		        continue;
		      }
		      _set[i] = _cdval;
		      this.customObj[i] = _cdval;
		    }
		    this._l('executed: applyData');
		  }

		  mps.aam._status = 1;
		  this._l('INITIALIZED');
		  return mps.aam._status;
		}

		/*--[ INTERNAL ]------------------------------------------------*/
		mps.aam._clean=function(str,maxlength,nospaces,lowercase){
		  if(typeof(maxlength)=='undefined' && this._conf && this._conf.maxlength>0) maxlength = this._conf.maxlength;
		  if(typeof(str)=='boolean') str=str+0;
		  if(typeof(str)=='number') str=str.toString();
		  if(typeof(str)!='string') return '';
		  str = str.replace(this._conf.cleanregex,'');
		  if(nospaces) str=str.replace(' ','');
		  if(maxlength) str=str.substring(0,maxlength);
		  if(lowercase) str.toLowerCase();
		  return str;
		}
		mps.aam._getQS=function(){var a;(window.onpopstate=function(){var b,c=/\+/g,d=/([^&=]+)=?([^&]*)/g,e=window.location.search.substring(1);for(a={};b=d.exec(e);)a[decodeURIComponent(b[1].replace(c," "))]=decodeURIComponent(b[2].replace(c," "))})();return a};
		mps.aam._l=function(msg,label){
		  if(typeof(msg)=='boolean') msg=msg+0;
		  if(typeof(msg)=='number') msg=msg.toString();
		  if(typeof(msg)=='object') msg=JSON.stringify(msg);
		  if(typeof(msg)!='string') msg='<'+typeof(msg)+'>';
		  if((typeof(label)!='string'||label.length==0)&&mps.aam._l.label) label = mps.aam._l.label;
		  if(typeof(label)!='string') label='';
		  mps._d('\u2022'+label+'\u279e '+msg);
		  return msg;
		};
		mps.aam._l.label = '[mps/aam]';

		/*--[ EXECUTION ]------------------------------------------------*/
		mps.aam.EXECUTE = function(){
		  try {
		    this.defineData();
		    this.setData();
		    this._applyData();
		    this._l('EXECUTION COMPLETE');
		    this._l(this.customObj);
		    return this.customObj;
		  } catch(e) {
		    mps._d('[mps/aam] ERROR: Custom Object Execution',e)
		    return {};
		  }
		}

		if(mps.aam.INIT()) {
		  window.customObj = mps.aam.EXECUTE();
		}
	}
	//Adobe Audience Manager DIL Custom Section
	//DIL instantiation starts. Configurable section below
	var nbcuDil = DIL.create({
	    partner: "nbcu",
	    containerNSID: 0 ,
			useJSONPOnly: true,
	    uuidCookie: {
	        name: 'aam_uuid',
	        days: 30
	    }

	});
	if(typeof customObj != 'undefined'){
		//Object is present, submit data
		var nbcuDilInstance = DIL.getDil('nbcu');
		nbcuDilInstance.api.signals(customObj, 'c_');
	};
	//SC object Instantiation
	if (typeof s != 'undefined' && s === Object(s) && typeof s.account != 'undefined' && s.account) {
		_scDilObj = s_gi(s.account);
	} else {
		_scDilObj = s_gi(s_account);
	};

	//SC Object Data Collection
	DIL.modules.siteCatalyst.init(_scDilObj, nbcuDil, {
	names: ['pageName', 'channel', 'campaign', 'products', 'events', 'pe', 'referrer', 'server', 'purchaseID', 'zip', 'state'],
	        	iteratedNames: [{
	               name: 'eVar',
	               maxIndex: 75
	        	}, {
	               name: 'prop',
	               maxIndex: 75
	        	}, {
	               name: 'pev',
	               maxIndex: 3
	        	}, {
	               name: 'hier',
	               maxIndex: 4
	        	}]
	});

	//DIL instantiation ends


}
s.doPlugins=s_doPlugins

//write linktrk cookie, expires on session
function linkTrkCookie(linkValue){
	s.Util.cookieWrite('linktrk', linkValue, 0);
}

//write bedrocktrk cookie, expires in 3 months
function bedrockTrkCookie(bedrockValue){
	var bedrockTrkDate = new Date();
	bedrockTrkDate.setMonth(bedrockTrkDate.getMonth() + 3);
	s.Util.cookieWrite('bedrocktrk', bedrockValue, bedrockTrkDate);
}

/************************** PLUGINS SECTION *************************/

/*
*Replace plugin utility
*/
s.repl=new Function("x","o","n",""
+"var i=x.indexOf(o),l=n.length;while(x&&i>=0){x=x.substring(0,i)+n+x."
+"substring(i+o.length);i=x.indexOf(o,i+l)}return x");

/*
*Gets the AAM segments out of a cookie. Requires replace (repl) *
*/
s.getAamSegments=new Function("a","b",""
+"var s=this;var c=s.c_r(a);if(c){c=s.repl(c,b+'=','');}ret"
+"urn c");

/*
 * Plugin: Days since last Visit 1.1 - capture time from last visit
 */
s.getDaysSinceLastVisit=new Function("c",""
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT"
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s"
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f"
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f"
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);"
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da"
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day"
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s."
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c"
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c"
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur"
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s"
+"!=f5) return '';else return cval_s;");

/*
* Plugin: getVisitNum - version 3.0
*/
s.getVisitNum=new Function("tp","c","c2",""
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}"
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi"
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!"
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn="
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi"
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els"
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri"
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);"
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)"
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}");
s.dimo=new Function("m","y",""
+"var d=new Date(y,m+1,0);return d.getDate();");
s.endof=new Function("x",""
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x=="
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if("
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return "
+"t;");

/*
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat
 */
s.getNewRepeat=new Function("d","cn",""
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:"
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length="
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct"
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N"
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}");

/*
 * Plugin: getTimeParting 3.3
 */
s.getTimeParting=new Function("h","z",""
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont"
+"h()!=0){return'Data Not Available';}else{var H,M,D,W,U,ds,de,tm,tt,"
+"da=['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Sa"
+"turday'],d=new Date(),a=[];z=z?z:0;z=parseFloat(z);if(s._tpDST){var"
+" dso=s._tpDST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d."
+"getFullYear());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d"
+">ds&&d<de){z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime"
+"()+(d.getTimezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getH"
+"ours();M=d.getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U='AM';W='Wee"
+"kday';if(H>=12){U='PM';H=H-12;}if(H==0){H=12;}if(D==6||D==0){W='Wee"
+"kend';}D=da[D];tm=H+':'+M+U;tt=H+':'+((M>30)?'30':'00')+U;a=[tm,tt,"
+"D,W];return a;}");

/*
 * Utility Function: split v1.5 (JS 1.0 compatible)
 */
s.split=new Function("l","d",""
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x"
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");

/*
 * Plugin Utility: apl v1.1
 */
s.apl=new Function("l","v","d","u",""
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a."
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas"
+"e()));}}if(!m)l=l?l+d+v:v;return l");

/*
 * Plugin: getPercentPageViewed v1.71
 */
s.getPercentPageViewed=new Function("n",""
+"var s=this,W=window,EL=W.addEventListener,AE=W.attachEvent,E=['load"
+"','unload','scroll','resize','zoom','keyup','mouseup','touchend','o"
+"rientationchange','pan'];W.s_Obj=s;s_PPVid=(n=='-'?s.pageName:n)||s"
+".pageName||location.href;if(!W.s_PPVevent){s.s_PPVg=function(n,r){v"
+"ar k='s_ppv',p=k+'l',c=s.c_r(n||r?k:p),a=c.indexOf(',')>-1?c.split("
+"',',10):[''],l=a.length,i;a[0]=unescape(a[0]);r=r||(n&&n!=a[0])||0;"
+"a.length=10;if(typeof a[0]!='string')a[0]='';for(i=1;i<10;i++)a[i]="
+"!r&&i<l?parseInt(a[i])||0:0;if(l<10||typeof a[9]!='string')a[9]='';"
+"if(r){s.c_w(p,c);s.c_w(k,'?')}return a};W.s_PPVevent=function(e){va"
+"r W=window,D=document,B=D.body,E=D.documentElement,S=window.screen|"
+"|0,Ho='offsetHeight',Hs='scrollHeight',Ts='scrollTop',Wc='clientWid"
+"th',Hc='clientHeight',C=100,M=Math,J='object',N='number',s=W.s_Obj|"
+"|W.s||0;e=e&&typeof e==J?e.type||'':'';if(!e.indexOf('on'))e=e.subs"
+"tring(2);s_PPVi=W.s_PPVi||0;if(W.s_PPVt&&!e){clearTimeout(s_PPVt);s"
+"_PPVt=0;if(s_PPVi<2)s_PPVi++}if(typeof s==J){var h=M.max(B[Hs]||E[H"
+"s],B[Ho]||E[Ho],B[Hc]||E[Hc]),X=W.innerWidth||E[Wc]||B[Wc]||0,Y=W.i"
+"nnerHeight||E[Hc]||B[Hc]||0,x=S?S.width:0,y=S?S.height:0,r=M.round("
+"C*(W.devicePixelRatio||1))/C,b=(D.pageYOffset||E[Ts]||B[Ts]||0)+Y,p"
+"=h>0&&b>0?M.round(C*b/h):0,O=W.orientation,o=!isNaN(O)?M.abs(o)%180"
+":Y>X?0:90,L=e=='load'||s_PPVi<1,a=s.s_PPVg(s_PPVid,L),V=function(i,"
+"v,f,n){i=parseInt(typeof a==J&&a.length>i?a[i]:'0')||0;v=typeof v!="
+"N?i:v;v=f||v>i?v:i;return n?v:v>C?C:v<0?0:v};if(new RegExp('(iPod|i"
+"Pad|iPhone)').exec(navigator.userAgent||'')&&o){o=x;x=y;y=o}o=o?'P'"
+":'L';a[9]=L?'':a[9].substring(0,1);s.c_w('s_ppv',escape(W.s_PPVid)+"
+"','+V(1,p,L)+','+(L||!V(2)?p:V(2))+','+V(3,b,L,1)+','+X+','+Y+','+x"
+"+','+y+','+r+','+a[9]+(a[9]==o?'':o))}if(!W.s_PPVt&&e!='unload')W.s"
+"_PPVt=setTimeout(W.s_PPVevent,333)};for(var f=W.s_PPVevent,i=0;i<E."
+"length;i++)if(EL)EL(E[i],f,false);else if(AE)AE('on'+E[i],f);f()};v"
+"ar a=s.s_PPVg();return!n||n=='-'?a[1]:a");

/* setupLinkTrack 3.17c */
s.setupLinkTrack=new Function("vl","c","e",""
+"var s=this;var cv=s.c_r(c);if(vl){var vla=vl.split(',');}if(cv!='')"
+"{var cva=s.split(cv,'^^');if(cva[1]!=''){for(x in vla){s[vla[x]]=cv"
+"a[x];if(e){s.events=s.apl(s.events,e,',',2);}}}}s.c_w(c,'',0);if(ty"
+"peof s.linkObject!='undefined'){s.lta=[];if(typeof s.pageName!='und"
+"efined')s.lta[0]=s.pageName;if(typeof s.linkObject!=null){if(s.link"
+"Object!=0){if(s.linkObject.getAttribute('data-trknavattr')!=null){s"
+".lta[1]=s.linkObject.getAttribute('data-trknavattr');}else if(s.lin"
+"kObject.getAttribute('name')!=null){var b=s.linkObject.getAttribute"
+"('name');if(b.indexOf('&lpos=')>-1){s.lta[3]=b.match('\&lpos\=([^\&"
+"]*)')[1];}if(b.indexOf('&lid=')>-1){s.lta[1]=b.match('\&lid\=([^\&]"
+"*)')[1];}}}if(typeof s.lta[1]=='undefined'&&s.hbx_lt!='manual'){if("
+"s.linkName!=0){s.lta[1]=s.linkName;}else if(s.linkObject!=0){if(s.c"
+"leanStr(s.linkObject.innerHTML).length>0){s.lta[1]=s.cleanStr(s.lin"
+"kObject.innerHTML);}else if(s.linkObject.innerHTML.indexOf('<img')>"
+"-1){if(s.linkObject.innerHTML.indexOf('alt=')>-1){s.lta[1]=s.linkOb"
+"ject.innerHTML.match('alt=\"([^\"]*)')[1];}else{s.lta[1]=s.linkObject"
+".innerHTML.match('src=\"([^\"]*)')[1]}}else{s.lta[1]=s.linkObject.inn"
+"erHTML;}}}try{if(typeof s.trackLinkModule(s.linkObject)!='undefined"
+"'){s.lta[3]=s.trackLinkModule(s.linkObject);}}catch(e){}if(s.lta[1]"
+"!=null&&typeof s.lta[1]!='undefined'){if(typeof s.pageName!='undefi"
+"ned')s.lta[0]=s.pageName;s.lta[2]=s.pageName+' | '+s.lta[1];}}if(s."
+"linkType!=0){for(var x=0;x<vla.length;x++){s[vla[x]]=s.cleanStr(s.l"
+"ta[x]);if(e){s.events=s.apl(s.events,e,',',2);s.linkTrackVars=s.apl"
+"(s.linkTrackVars,'events',',',2);}}s.linkTrackVars=s.apl(s.linkTrac"
+"kVars,vl,',',2);}else{if(s.lta[1]){var tcv='';for(var x=0;x<s.lta.l"
+"ength;x++){tcv+=s.cleanStr(s.lta[x])+'^^'}s.c_w(c,tcv)}}s.lta=null;"
+"}");/* Plugin: Link Module Tracking 0.34 */
s.trackLinkModule=new Function("l",""
+"var s=this;var t=l.parentNode;while(t){if(t.getAttribute('id')!=nul"
+"l){return t.getAttribute('id');}else{t=t.parentNode;}}return;");
/* Utility: String Cleansing 1.0 */
s.cleanStr = function(a) {
	if (typeof a != 'undefined') { //checks to make sure a value was actually passed to the function
		if (typeof a == "string") {
			a = a.replace(/<\/?[^>]+(>|$)/g, ''); //removes HTML characters
			a = a.replace(/^\s+|\s+$/g, ''); //removes whitespace
			a = a.replace(/[\u2018\u2019\u201A]/g, "\'"); //removes unicode characters
			a = a.replace(/\t+/g, ''); //removes tab characters
			a = a.replace(/(\r\n|\n|\r)/gm,''); //removes newline characters
			return a; //returns the cleansed string
		}
	}
}

/*
 Start ActivityMap Module

 The following module enables ActivityMap tracking in Adobe Analytics. ActivityMap
 allows you to view data overlays on your links and content to understand how
 users engage with your web site. If you do not intend to use ActivityMap, you
 can remove the following block of code from your AppMeasurement.js file.
 Additional documentation on how to configure ActivityMap is available at:
 https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
*/
function AppMeasurement_Module_ActivityMap(f){function g(a,d){var b,c,n;if(a&&d&&(b=e.c[d]||(e.c[d]=d.split(","))))for(n=0;n<b.length&&(c=b[n++]);)if(-1<a.indexOf(c))return null;p=1;return a}function q(a,d,b,c,e){var g,h;if(a.dataset&&(h=a.dataset[d]))g=h;else if(a.getAttribute)if(h=a.getAttribute("data-"+b))g=h;else if(h=a.getAttribute(b))g=h;if(!g&&f.useForcedLinkTracking&&e&&(g="",d=a.onclick?""+a.onclick:"")){b=d.indexOf(c);var l,k;if(0<=b){for(b+=10;b<d.length&&0<="= \t\r\n".indexOf(d.charAt(b));)b++;
if(b<d.length){h=b;for(l=k=0;h<d.length&&(";"!=d.charAt(h)||l);)l?d.charAt(h)!=l||k?k="\\"==d.charAt(h)?!k:0:l=0:(l=d.charAt(h),'"'!=l&&"'"!=l&&(l=0)),h++;if(d=d.substring(b,h))a.e=new Function("s","var e;try{s.w."+c+"="+d+"}catch(e){}"),a.e(f)}}}return g||e&&f.w[c]}function r(a,d,b){var c;return(c=e[d](a,b))&&(p?(p=0,c):g(k(c),e[d+"Exclusions"]))}function s(a,d,b){var c;if(a&&!(1===(c=a.nodeType)&&(c=a.nodeName)&&(c=c.toUpperCase())&&t[c])&&(1===a.nodeType&&(c=a.nodeValue)&&(d[d.length]=c),b.a||
b.t||b.s||!a.getAttribute||((c=a.getAttribute("alt"))?b.a=c:(c=a.getAttribute("title"))?b.t=c:"IMG"==(""+a.nodeName).toUpperCase()&&(c=a.getAttribute("src")||a.src)&&(b.s=c)),(c=a.childNodes)&&c.length))for(a=0;a<c.length;a++)s(c[a],d,b)}function k(a){if(null==a||void 0==a)return a;try{return a.replace(RegExp("^[\\s\\n\\f\\r\\t\t-\r \u00a0\u1680\u180e\u2000-\u200a\u2028\u2029\u205f\u3000\ufeff]+","mg"),"").replace(RegExp("[\\s\\n\\f\\r\\t\t-\r \u00a0\u1680\u180e\u2000-\u200a\u2028\u2029\u205f\u3000\ufeff]+$",
"mg"),"").replace(RegExp("[\\s\\n\\f\\r\\t\t-\r \u00a0\u1680\u180e\u2000-\u200a\u2028\u2029\u205f\u3000\ufeff]{1,}","mg")," ").substring(0,254)}catch(d){}}var e=this;e.s=f;var m=window;m.s_c_in||(m.s_c_il=[],m.s_c_in=0);e._il=m.s_c_il;e._in=m.s_c_in;e._il[e._in]=e;m.s_c_in++;e._c="s_m";e.c={};var p=0,t={SCRIPT:1,STYLE:1,LINK:1,CANVAS:1};e._g=function(){var a,d,b,c=f.contextData,e=f.linkObject;(a=f.pageName||f.pageURL)&&(d=r(e,"link",f.linkName))&&(b=r(e,"region"))&&(c["a.activitymap.page"]=a.substring(0,
255),c["a.activitymap.link"]=128<d.length?d.substring(0,128):d,c["a.activitymap.region"]=127<b.length?b.substring(0,127):b,c["a.activitymap.pageIDType"]=f.pageName?1:0)};e.link=function(a,d){var b;if(d)b=g(k(d),e.linkExclusions);else if((b=a)&&!(b=q(a,"sObjectId","s-object-id","s_objectID",1))){var c,f;(f=g(k(a.innerText||a.textContent),e.linkExclusions))||(s(a,c=[],b={a:void 0,t:void 0,s:void 0}),(f=g(k(c.join(""))))||(f=g(k(b.a?b.a:b.t?b.t:b.s?b.s:void 0)))||!(c=(c=a.tagName)&&c.toUpperCase?c.toUpperCase():
"")||("INPUT"==c||"SUBMIT"==c&&a.value?f=g(k(a.value)):a.src&&"IMAGE"==c&&(f=g(k(a.src)))));b=f}return b};e.region=function(a){for(var d,b=e.regionIDAttribute||"id";a&&(a=a.parentNode);){if(d=q(a,b,b,b))return d;if("BODY"==a.nodeName)return"BODY"}}}
/* End ActivityMap Module */


/*
 ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============

AppMeasurement for JavaScript version: 1.6
Copyright 1996-2016 Adobe, Inc. All Rights Reserved
More info available at http://www.adobe.com/marketing-cloud.html
*/
function AppMeasurement(){var a=this;a.version="1.6";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.Db;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.sb=function(a){try{console.log(a)}catch(b){}};a.Ba=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a||
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.kb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&&
!/^[0-9.]+$/.test(c)&&(b=b?parseInt(b):2,b=2<b?b:2,d=c.lastIndexOf("."),0<=d)){for(;0<=d&&1<b;)d=c.lastIndexOf(".",d-1),b--;a.cookieDomain=0<d?c.substring(d):c}return a.cookieDomain};a.c_r=a.cookieRead=function(c){c=a.escape(c);var b=" "+a.d.cookie,d=b.indexOf(" "+c+"="),f=0>d?d:b.indexOf(";",d);c=0>d?"":a.unescape(b.substring(d+2+c.length,0>f?b.length:f));return"[[B]]"!=c?c:""};a.c_w=a.cookieWrite=function(c,b,d){var f=a.kb(),e=a.cookieLifetime,g;b=""+b;e=e?(""+e).toUpperCase():"";d&&"SESSION"!=
e&&"NONE"!=e&&((g=""!=b?parseInt(e?e:0):-60)?(d=new Date,d.setTime(d.getTime()+1E3*g)):1==d&&(d=new Date,g=d.getYear(),d.setYear(g+5+(1900>g?1900:0))));return c&&"NONE"!=e?(a.d.cookie=c+"="+a.escape(""!=b?b:"[[B]]")+"; path=/;"+(d&&"SESSION"!=e?" expires="+d.toGMTString()+";":"")+(f?" domain="+f+";":""),a.cookieRead(c)==b):0};a.G=[];a.da=function(c,b,d){if(a.va)return 0;a.maxDelay||(a.maxDelay=250);var f=0,e=(new Date).getTime()+a.maxDelay,g=a.d.visibilityState,m=["webkitvisibilitychange","visibilitychange"];
g||(g=a.d.webkitVisibilityState);if(g&&"prerender"==g){if(!a.ea)for(a.ea=1,d=0;d<m.length;d++)a.d.addEventListener(m[d],function(){var c=a.d.visibilityState;c||(c=a.d.webkitVisibilityState);"visible"==c&&(a.ea=0,a.delayReady())});f=1;e=0}else d||a.l("_d")&&(f=1);f&&(a.G.push({m:c,a:b,t:e}),a.ea||setTimeout(a.delayReady,a.maxDelay));return f};a.delayReady=function(){var c=(new Date).getTime(),b=0,d;for(a.l("_d")?b=1:a.pa();0<a.G.length;){d=a.G.shift();if(b&&!d.t&&d.t>c){a.G.unshift(d);setTimeout(a.delayReady,
parseInt(a.maxDelay/2));break}a.va=1;a[d.m].apply(a,d.a);a.va=0}};a.setAccount=a.sa=function(c){var b,d;if(!a.da("setAccount",arguments))if(a.account=c,a.allAccounts)for(b=a.allAccounts.concat(c.split(",")),a.allAccounts=[],b.sort(),d=0;d<b.length;d++)0!=d&&b[d-1]==b[d]||a.allAccounts.push(b[d]);else a.allAccounts=c.split(",")};a.foreachVar=function(c,b){var d,f,e,g,m="";e=f="";if(a.lightProfileID)d=a.K,(m=a.lightTrackVars)&&(m=","+m+","+a.ia.join(",")+",");else{d=a.e;if(a.pe||a.linkType)m=a.linkTrackVars,
f=a.linkTrackEvents,a.pe&&(e=a.pe.substring(0,1).toUpperCase()+a.pe.substring(1),a[e]&&(m=a[e].Cb,f=a[e].Bb));m&&(m=","+m+","+a.B.join(",")+",");f&&m&&(m+=",events,")}b&&(b=","+b+",");for(f=0;f<d.length;f++)e=d[f],(g=a[e])&&(!m||0<=m.indexOf(","+e+","))&&(!b||0<=b.indexOf(","+e+","))&&c(e,g)};a.o=function(c,b,d,f,e){var g="",m,p,k,w,n=0;"contextData"==c&&(c="c");if(b){for(m in b)if(!(Object.prototype[m]||e&&m.substring(0,e.length)!=e)&&b[m]&&(!d||0<=d.indexOf(","+(f?f+".":"")+m+","))){k=!1;if(n)for(p=
0;p<n.length;p++)m.substring(0,n[p].length)==n[p]&&(k=!0);if(!k&&(""==g&&(g+="&"+c+"."),p=b[m],e&&(m=m.substring(e.length)),0<m.length))if(k=m.indexOf("."),0<k)p=m.substring(0,k),k=(e?e:"")+p+".",n||(n=[]),n.push(k),g+=a.o(p,b,d,f,k);else if("boolean"==typeof p&&(p=p?"true":"false"),p){if("retrieveLightData"==f&&0>e.indexOf(".contextData."))switch(k=m.substring(0,4),w=m.substring(4),m){case "transactionID":m="xact";break;case "channel":m="ch";break;case "campaign":m="v0";break;default:a.Ba(w)&&("prop"==
k?m="c"+w:"eVar"==k?m="v"+w:"list"==k?m="l"+w:"hier"==k&&(m="h"+w,p=p.substring(0,255)))}g+="&"+a.escape(m)+"="+a.escape(p)}}""!=g&&(g+="&."+c)}return g};a.mb=function(){var c="",b,d,f,e,g,m,p,k,n="",r="",s=e="";if(a.lightProfileID)b=a.K,(n=a.lightTrackVars)&&(n=","+n+","+a.ia.join(",")+",");else{b=a.e;if(a.pe||a.linkType)n=a.linkTrackVars,r=a.linkTrackEvents,a.pe&&(e=a.pe.substring(0,1).toUpperCase()+a.pe.substring(1),a[e]&&(n=a[e].Cb,r=a[e].Bb));n&&(n=","+n+","+a.B.join(",")+",");r&&(r=","+r+",",
n&&(n+=",events,"));a.events2&&(s+=(""!=s?",":"")+a.events2)}if(a.visitor&&1.5<=parseFloat(a.visitor.version)&&a.visitor.getCustomerIDs){e=q;if(g=a.visitor.getCustomerIDs())for(d in g)Object.prototype[d]||(f=g[d],e||(e={}),f.id&&(e[d+".id"]=f.id),f.authState&&(e[d+".as"]=f.authState));e&&(c+=a.o("cid",e))}a.AudienceManagement&&a.AudienceManagement.isReady()&&(c+=a.o("d",a.AudienceManagement.getEventCallConfigParams()));for(d=0;d<b.length;d++){e=b[d];g=a[e];f=e.substring(0,4);m=e.substring(4);!g&&
"events"==e&&s&&(g=s,s="");if(g&&(!n||0<=n.indexOf(","+e+","))){switch(e){case "supplementalDataID":e="sdid";break;case "timestamp":e="ts";break;case "dynamicVariablePrefix":e="D";break;case "visitorID":e="vid";break;case "marketingCloudVisitorID":e="mid";break;case "analyticsVisitorID":e="aid";break;case "audienceManagerLocationHint":e="aamlh";break;case "audienceManagerBlob":e="aamb";break;case "authState":e="as";break;case "pageURL":e="g";255<g.length&&(a.pageURLRest=g.substring(255),g=g.substring(0,
255));break;case "pageURLRest":e="-g";break;case "referrer":e="r";break;case "vmk":case "visitorMigrationKey":e="vmt";break;case "visitorMigrationServer":e="vmf";a.ssl&&a.visitorMigrationServerSecure&&(g="");break;case "visitorMigrationServerSecure":e="vmf";!a.ssl&&a.visitorMigrationServer&&(g="");break;case "charSet":e="ce";break;case "visitorNamespace":e="ns";break;case "cookieDomainPeriods":e="cdp";break;case "cookieLifetime":e="cl";break;case "variableProvider":e="vvp";break;case "currencyCode":e=
"cc";break;case "channel":e="ch";break;case "transactionID":e="xact";break;case "campaign":e="v0";break;case "latitude":e="lat";break;case "longitude":e="lon";break;case "resolution":e="s";break;case "colorDepth":e="c";break;case "javascriptVersion":e="j";break;case "javaEnabled":e="v";break;case "cookiesEnabled":e="k";break;case "browserWidth":e="bw";break;case "browserHeight":e="bh";break;case "connectionType":e="ct";break;case "homepage":e="hp";break;case "events":s&&(g+=(""!=g?",":"")+s);if(r)for(m=
g.split(","),g="",f=0;f<m.length;f++)p=m[f],k=p.indexOf("="),0<=k&&(p=p.substring(0,k)),k=p.indexOf(":"),0<=k&&(p=p.substring(0,k)),0<=r.indexOf(","+p+",")&&(g+=(g?",":"")+m[f]);break;case "events2":g="";break;case "contextData":c+=a.o("c",a[e],n,e);g="";break;case "lightProfileID":e="mtp";break;case "lightStoreForSeconds":e="mtss";a.lightProfileID||(g="");break;case "lightIncrementBy":e="mti";a.lightProfileID||(g="");break;case "retrieveLightProfiles":e="mtsr";break;case "deleteLightProfiles":e=
"mtsd";break;case "retrieveLightData":a.retrieveLightProfiles&&(c+=a.o("mts",a[e],n,e));g="";break;default:a.Ba(m)&&("prop"==f?e="c"+m:"eVar"==f?e="v"+m:"list"==f?e="l"+m:"hier"==f&&(e="h"+m,g=g.substring(0,255)))}g&&(c+="&"+e+"="+("pev"!=e.substring(0,3)?a.escape(g):g))}"pev3"==e&&a.c&&(c+=a.c)}return c};a.v=function(a){var b=a.tagName;if("undefined"!=""+a.Gb||"undefined"!=""+a.wb&&"HTML"!=(""+a.wb).toUpperCase())return"";b=b&&b.toUpperCase?b.toUpperCase():"";"SHAPE"==b&&(b="");b&&(("INPUT"==b||
"BUTTON"==b)&&a.type&&a.type.toUpperCase?b=a.type.toUpperCase():!b&&a.href&&(b="A"));return b};a.xa=function(a){var b=a.href?a.href:"",d,f,e;d=b.indexOf(":");f=b.indexOf("?");e=b.indexOf("/");b&&(0>d||0<=f&&d>f||0<=e&&d>e)&&(f=a.protocol&&1<a.protocol.length?a.protocol:l.protocol?l.protocol:"",d=l.pathname.lastIndexOf("/"),b=(f?f+"//":"")+(a.host?a.host:l.host?l.host:"")+("/"!=h.substring(0,1)?l.pathname.substring(0,0>d?0:d)+"/":"")+b);return b};a.H=function(c){var b=a.v(c),d,f,e="",g=0;return b&&
(d=c.protocol,f=c.onclick,!c.href||"A"!=b&&"AREA"!=b||f&&d&&!(0>d.toLowerCase().indexOf("javascript"))?f?(e=a.replace(a.replace(a.replace(a.replace(""+f,"\r",""),"\n",""),"\t","")," ",""),g=2):"INPUT"==b||"SUBMIT"==b?(c.value?e=c.value:c.innerText?e=c.innerText:c.textContent&&(e=c.textContent),g=3):c.src&&"IMAGE"==b&&(e=c.src):e=a.xa(c),e)?{id:e.substring(0,100),type:g}:0};a.Eb=function(c){for(var b=a.v(c),d=a.H(c);c&&!d&&"BODY"!=b;)if(c=c.parentElement?c.parentElement:c.parentNode)b=a.v(c),d=a.H(c);
d&&"BODY"!=b||(c=0);c&&(b=c.onclick?""+c.onclick:"",0<=b.indexOf(".tl(")||0<=b.indexOf(".trackLink("))&&(c=0);return c};a.vb=function(){var c,b,d=a.linkObject,f=a.linkType,e=a.linkURL,g,m;a.ja=1;d||(a.ja=0,d=a.clickObject);if(d){c=a.v(d);for(b=a.H(d);d&&!b&&"BODY"!=c;)if(d=d.parentElement?d.parentElement:d.parentNode)c=a.v(d),b=a.H(d);b&&"BODY"!=c||(d=0);if(d&&!a.linkObject){var p=d.onclick?""+d.onclick:"";if(0<=p.indexOf(".tl(")||0<=p.indexOf(".trackLink("))d=0}}else a.ja=1;!e&&d&&(e=a.xa(d));e&&
!a.linkLeaveQueryString&&(g=e.indexOf("?"),0<=g&&(e=e.substring(0,g)));if(!f&&e){var n=0,r=0,q;if(a.trackDownloadLinks&&a.linkDownloadFileTypes)for(p=e.toLowerCase(),g=p.indexOf("?"),m=p.indexOf("#"),0<=g?0<=m&&m<g&&(g=m):g=m,0<=g&&(p=p.substring(0,g)),g=a.linkDownloadFileTypes.toLowerCase().split(","),m=0;m<g.length;m++)(q=g[m])&&p.substring(p.length-(q.length+1))=="."+q&&(f="d");if(a.trackExternalLinks&&!f&&(p=e.toLowerCase(),a.Aa(p)&&(a.linkInternalFilters||(a.linkInternalFilters=k.location.hostname),
g=0,a.linkExternalFilters?(g=a.linkExternalFilters.toLowerCase().split(","),n=1):a.linkInternalFilters&&(g=a.linkInternalFilters.toLowerCase().split(",")),g))){for(m=0;m<g.length;m++)q=g[m],0<=p.indexOf(q)&&(r=1);r?n&&(f="e"):n||(f="e")}}a.linkObject=d;a.linkURL=e;a.linkType=f;if(a.trackClickMap||a.trackInlineStats)a.c="",d&&(f=a.pageName,e=1,d=d.sourceIndex,f||(f=a.pageURL,e=0),k.s_objectID&&(b.id=k.s_objectID,d=b.type=1),f&&b&&b.id&&c&&(a.c="&pid="+a.escape(f.substring(0,255))+(e?"&pidt="+e:"")+
"&oid="+a.escape(b.id.substring(0,100))+(b.type?"&oidt="+b.type:"")+"&ot="+c+(d?"&oi="+d:"")))};a.nb=function(){var c=a.ja,b=a.linkType,d=a.linkURL,f=a.linkName;b&&(d||f)&&(b=b.toLowerCase(),"d"!=b&&"e"!=b&&(b="o"),a.pe="lnk_"+b,a.pev1=d?a.escape(d):"",a.pev2=f?a.escape(f):"",c=1);a.abort&&(c=0);if(a.trackClickMap||a.trackInlineStats||a.ActivityMap){var b={},d=0,e=a.cookieRead("s_sq"),g=e?e.split("&"):0,m,p,k,e=0;if(g)for(m=0;m<g.length;m++)p=g[m].split("="),f=a.unescape(p[0]).split(","),p=a.unescape(p[1]),
b[p]=f;f=a.account.split(",");m={};for(k in a.contextData)k&&!Object.prototype[k]&&"a.activitymap."==k.substring(0,14)&&(m[k]=a.contextData[k],a.contextData[k]="");a.c=a.o("c",m)+(a.c?a.c:"");if(c||a.c){c&&!a.c&&(e=1);for(p in b)if(!Object.prototype[p])for(k=0;k<f.length;k++)for(e&&(g=b[p].join(","),g==a.account&&(a.c+=("&"!=p.charAt(0)?"&":"")+p,b[p]=[],d=1)),m=0;m<b[p].length;m++)g=b[p][m],g==f[k]&&(e&&(a.c+="&u="+a.escape(g)+("&"!=p.charAt(0)?"&":"")+p+"&u=0"),b[p].splice(m,1),d=1);c||(d=1);if(d){e=
"";m=2;!c&&a.c&&(e=a.escape(f.join(","))+"="+a.escape(a.c),m=1);for(p in b)!Object.prototype[p]&&0<m&&0<b[p].length&&(e+=(e?"&":"")+a.escape(b[p].join(","))+"="+a.escape(p),m--);a.cookieWrite("s_sq",e)}}}return c};a.ob=function(){if(!a.Ab){var c=new Date,b=r.location,d,f,e=f=d="",g="",m="",k="1.2",n=a.cookieWrite("s_cc","true",0)?"Y":"N",q="",s="";if(c.setUTCDate&&(k="1.3",(0).toPrecision&&(k="1.5",c=[],c.forEach))){k="1.6";f=0;d={};try{f=new Iterator(d),f.next&&(k="1.7",c.reduce&&(k="1.8",k.trim&&
(k="1.8.1",Date.parse&&(k="1.8.2",Object.create&&(k="1.8.5")))))}catch(t){}}d=screen.width+"x"+screen.height;e=navigator.javaEnabled()?"Y":"N";f=screen.pixelDepth?screen.pixelDepth:screen.colorDepth;g=a.w.innerWidth?a.w.innerWidth:a.d.documentElement.offsetWidth;m=a.w.innerHeight?a.w.innerHeight:a.d.documentElement.offsetHeight;try{a.b.addBehavior("#default#homePage"),q=a.b.Fb(b)?"Y":"N"}catch(u){}try{a.b.addBehavior("#default#clientCaps"),s=a.b.connectionType}catch(x){}a.resolution=d;a.colorDepth=
f;a.javascriptVersion=k;a.javaEnabled=e;a.cookiesEnabled=n;a.browserWidth=g;a.browserHeight=m;a.connectionType=s;a.homepage=q;a.Ab=1}};a.L={};a.loadModule=function(c,b){var d=a.L[c];if(!d){d=k["AppMeasurement_Module_"+c]?new k["AppMeasurement_Module_"+c](a):{};a.L[c]=a[c]=d;d.Qa=function(){return d.Ua};d.Va=function(b){if(d.Ua=b)a[c+"_onLoad"]=b,a.da(c+"_onLoad",[a,d],1)||b(a,d)};try{Object.defineProperty?Object.defineProperty(d,"onLoad",{get:d.Qa,set:d.Va}):d._olc=1}catch(f){d._olc=1}}b&&(a[c+"_onLoad"]=
b,a.da(c+"_onLoad",[a,d],1)||b(a,d))};a.l=function(c){var b,d;for(b in a.L)if(!Object.prototype[b]&&(d=a.L[b])&&(d._olc&&d.onLoad&&(d._olc=0,d.onLoad(a,d)),d[c]&&d[c]()))return 1;return 0};a.qb=function(){var c=Math.floor(1E13*Math.random()),b=a.visitorSampling,d=a.visitorSamplingGroup,d="s_vsn_"+(a.visitorNamespace?a.visitorNamespace:a.account)+(d?"_"+d:""),f=a.cookieRead(d);if(b){f&&(f=parseInt(f));if(!f){if(!a.cookieWrite(d,c))return 0;f=c}if(f%1E4>v)return 0}return 1};a.M=function(c,b){var d,
f,e,g,m,k;for(d=0;2>d;d++)for(f=0<d?a.qa:a.e,e=0;e<f.length;e++)if(g=f[e],(m=c[g])||c["!"+g]){if(!b&&("contextData"==g||"retrieveLightData"==g)&&a[g])for(k in a[g])m[k]||(m[k]=a[g][k]);a[g]=m}};a.Ja=function(c,b){var d,f,e,g;for(d=0;2>d;d++)for(f=0<d?a.qa:a.e,e=0;e<f.length;e++)g=f[e],c[g]=a[g],b||c[g]||(c["!"+g]=1)};a.ib=function(a){var b,d,f,e,g,m=0,k,n="",q="";if(a&&255<a.length&&(b=""+a,d=b.indexOf("?"),0<d&&(k=b.substring(d+1),b=b.substring(0,d),e=b.toLowerCase(),f=0,"http://"==e.substring(0,
7)?f+=7:"https://"==e.substring(0,8)&&(f+=8),d=e.indexOf("/",f),0<d&&(e=e.substring(f,d),g=b.substring(d),b=b.substring(0,d),0<=e.indexOf("google")?m=",q,ie,start,search_key,word,kw,cd,":0<=e.indexOf("yahoo.co")&&(m=",p,ei,"),m&&k)))){if((a=k.split("&"))&&1<a.length){for(f=0;f<a.length;f++)e=a[f],d=e.indexOf("="),0<d&&0<=m.indexOf(","+e.substring(0,d)+",")?n+=(n?"&":"")+e:q+=(q?"&":"")+e;n&&q?k=n+"&"+q:q=""}d=253-(k.length-q.length)-b.length;a=b+(0<d?g.substring(0,d):"")+"?"+k}return a};a.Pa=function(c){var b=
a.d.visibilityState,d=["webkitvisibilitychange","visibilitychange"];b||(b=a.d.webkitVisibilityState);if(b&&"prerender"==b){if(c)for(b=0;b<d.length;b++)a.d.addEventListener(d[b],function(){var b=a.d.visibilityState;b||(b=a.d.webkitVisibilityState);"visible"==b&&c()});return!1}return!0};a.Z=!1;a.D=!1;a.Xa=function(){a.D=!0;a.i()};a.X=!1;a.Q=!1;a.Ta=function(c){a.marketingCloudVisitorID=c;a.Q=!0;a.i()};a.aa=!1;a.R=!1;a.Ya=function(c){a.visitorOptedOut=c;a.R=!0;a.i()};a.U=!1;a.N=!1;a.La=function(c){a.analyticsVisitorID=
c;a.N=!0;a.i()};a.W=!1;a.P=!1;a.Na=function(c){a.audienceManagerLocationHint=c;a.P=!0;a.i()};a.V=!1;a.O=!1;a.Ma=function(c){a.audienceManagerBlob=c;a.O=!0;a.i()};a.Oa=function(c){a.maxDelay||(a.maxDelay=250);return a.l("_d")?(c&&setTimeout(function(){c()},a.maxDelay),!1):!0};a.Y=!1;a.C=!1;a.pa=function(){a.C=!0;a.i()};a.isReadyToTrack=function(){var c=!0,b=a.visitor;a.Z||a.D||(a.Pa(a.Xa)?a.D=!0:a.Z=!0);if(a.Z&&!a.D)return!1;b&&b.isAllowed()&&(a.X||a.marketingCloudVisitorID||!b.getMarketingCloudVisitorID||
(a.X=!0,a.marketingCloudVisitorID=b.getMarketingCloudVisitorID([a,a.Ta]),a.marketingCloudVisitorID&&(a.Q=!0)),a.aa||a.visitorOptedOut||!b.isOptedOut||(a.aa=!0,a.visitorOptedOut=b.isOptedOut([a,a.Ya]),a.visitorOptedOut!=q&&(a.R=!0)),a.U||a.analyticsVisitorID||!b.getAnalyticsVisitorID||(a.U=!0,a.analyticsVisitorID=b.getAnalyticsVisitorID([a,a.La]),a.analyticsVisitorID&&(a.N=!0)),a.W||a.audienceManagerLocationHint||!b.getAudienceManagerLocationHint||(a.W=!0,a.audienceManagerLocationHint=b.getAudienceManagerLocationHint([a,
a.Na]),a.audienceManagerLocationHint&&(a.P=!0)),a.V||a.audienceManagerBlob||!b.getAudienceManagerBlob||(a.V=!0,a.audienceManagerBlob=b.getAudienceManagerBlob([a,a.Ma]),a.audienceManagerBlob&&(a.O=!0)),a.X&&!a.Q&&!a.marketingCloudVisitorID||a.U&&!a.N&&!a.analyticsVisitorID||a.W&&!a.P&&!a.audienceManagerLocationHint||a.V&&!a.O&&!a.audienceManagerBlob||a.aa&&!a.R)&&(c=!1);a.Y||a.C||(a.Oa(a.pa)?a.C=!0:a.Y=!0);a.Y&&!a.C&&(c=!1);return c};a.k=q;a.p=0;a.callbackWhenReadyToTrack=function(c,b,d){var f;f={};
f.bb=c;f.ab=b;f.Za=d;a.k==q&&(a.k=[]);a.k.push(f);0==a.p&&(a.p=setInterval(a.i,100))};a.i=function(){var c;if(a.isReadyToTrack()&&(a.Wa(),a.k!=q))for(;0<a.k.length;)c=a.k.shift(),c.ab.apply(c.bb,c.Za)};a.Wa=function(){a.p&&(clearInterval(a.p),a.p=0)};a.Ra=function(c){var b,d,f=q,e=q;if(!a.isReadyToTrack()){b=[];if(c!=q)for(d in f={},c)f[d]=c[d];e={};a.Ja(e,!0);b.push(f);b.push(e);a.callbackWhenReadyToTrack(a,a.track,b);return!0}return!1};a.lb=function(){var c=a.cookieRead("s_fid"),b="",d="",f;f=8;
var e=4;if(!c||0>c.indexOf("-")){for(c=0;16>c;c++)f=Math.floor(Math.random()*f),b+="0123456789ABCDEF".substring(f,f+1),f=Math.floor(Math.random()*e),d+="0123456789ABCDEF".substring(f,f+1),f=e=16;c=b+"-"+d}a.cookieWrite("s_fid",c,1)||(c=0);return c};a.t=a.track=function(c,b){var d,f=new Date,e="s"+Math.floor(f.getTime()/108E5)%10+Math.floor(1E13*Math.random()),g=f.getYear(),g="t="+a.escape(f.getDate()+"/"+f.getMonth()+"/"+(1900>g?g+1900:g)+" "+f.getHours()+":"+f.getMinutes()+":"+f.getSeconds()+" "+
f.getDay()+" "+f.getTimezoneOffset());a.visitor&&(a.visitor.jb&&(a.authState=a.visitor.jb()),!a.supplementalDataID&&a.visitor.getSupplementalDataID&&(a.supplementalDataID=a.visitor.getSupplementalDataID("AppMeasurement:"+a._in,a.expectSupplementalData?!1:!0)));a.l("_s");a.Ra(c)||(b&&a.M(b),c&&(d={},a.Ja(d,0),a.M(c)),a.qb()&&!a.visitorOptedOut&&(a.analyticsVisitorID||a.marketingCloudVisitorID||(a.fid=a.lb()),a.vb(),a.usePlugins&&a.doPlugins&&a.doPlugins(a),a.account&&(a.abort||(a.trackOffline&&!a.timestamp&&
(a.timestamp=Math.floor(f.getTime()/1E3)),f=k.location,a.pageURL||(a.pageURL=f.href?f.href:f),a.referrer||a.Ka||(a.referrer=r.document.referrer),a.Ka=1,a.referrer=a.ib(a.referrer),a.l("_g")),a.nb()&&!a.abort&&(a.ob(),g+=a.mb(),a.ub(e,g),a.l("_t"),a.referrer=""))),c&&a.M(d,1));a.abort=a.supplementalDataID=a.timestamp=a.pageURLRest=a.linkObject=a.clickObject=a.linkURL=a.linkName=a.linkType=k.s_objectID=a.pe=a.pev1=a.pev2=a.pev3=a.c=a.lightProfileID=0};a.tl=a.trackLink=function(c,b,d,f,e){a.linkObject=
c;a.linkType=b;a.linkName=d;e&&(a.j=c,a.r=e);return a.track(f)};a.trackLight=function(c,b,d,f){a.lightProfileID=c;a.lightStoreForSeconds=b;a.lightIncrementBy=d;return a.track(f)};a.clearVars=function(){var c,b;for(c=0;c<a.e.length;c++)if(b=a.e[c],"prop"==b.substring(0,4)||"eVar"==b.substring(0,4)||"hier"==b.substring(0,4)||"list"==b.substring(0,4)||"channel"==b||"events"==b||"eventList"==b||"products"==b||"productList"==b||"purchaseID"==b||"transactionID"==b||"state"==b||"zip"==b||"campaign"==b)a[b]=
void 0};a.tagContainerMarker="";a.ub=function(c,b){var d,f=a.trackingServer;d="";var e=a.dc,g="sc.",k=a.visitorNamespace;f?a.trackingServerSecure&&a.ssl&&(f=a.trackingServerSecure):(k||(k=a.account,f=k.indexOf(","),0<=f&&(k=k.substring(0,f)),k=k.replace(/[^A-Za-z0-9]/g,"")),d||(d="2o7.net"),e=e?(""+e).toLowerCase():"d1","2o7.net"==d&&("d1"==e?e="112":"d2"==e&&(e="122"),g=""),f=k+"."+e+"."+g+d);d=a.ssl?"https://":"http://";e=a.AudienceManagement&&a.AudienceManagement.isReady();d+=f+"/b/ss/"+a.account+
"/"+(a.mobile?"5.":"")+(e?"10":"1")+"/JS-"+a.version+(a.zb?"T":"")+(a.tagContainerMarker?"-"+a.tagContainerMarker:"")+"/"+c+"?AQB=1&ndh=1&pf=1&"+(e?"callback=s_c_il["+a._in+"].AudienceManagement.passData&":"")+b+"&AQE=1";a.gb(d);a.fa()};a.gb=function(c){a.g||a.pb();a.g.push(c);a.ha=a.u();a.Ha()};a.pb=function(){a.g=a.rb();a.g||(a.g=[])};a.rb=function(){var c,b;if(a.ma()){try{(b=k.localStorage.getItem(a.ka()))&&(c=k.JSON.parse(b))}catch(d){}return c}};a.ma=function(){var c=!0;a.trackOffline&&a.offlineFilename&&
k.localStorage&&k.JSON||(c=!1);return c};a.ya=function(){var c=0;a.g&&(c=a.g.length);a.A&&c++;return c};a.fa=function(){if(!a.A)if(a.za=q,a.la)a.ha>a.J&&a.Fa(a.g),a.oa(500);else{var c=a.$a();if(0<c)a.oa(c);else if(c=a.wa())a.A=1,a.tb(c),a.xb(c)}};a.oa=function(c){a.za||(c||(c=0),a.za=setTimeout(a.fa,c))};a.$a=function(){var c;if(!a.trackOffline||0>=a.offlineThrottleDelay)return 0;c=a.u()-a.Ea;return a.offlineThrottleDelay<c?0:a.offlineThrottleDelay-c};a.wa=function(){if(0<a.g.length)return a.g.shift()};
a.tb=function(c){if(a.debugTracking){var b="AppMeasurement Debug: "+c;c=c.split("&");var d;for(d=0;d<c.length;d++)b+="\n\t"+a.unescape(c[d]);a.sb(b)}};a.Sa=function(){return a.marketingCloudVisitorID||a.analyticsVisitorID};a.T=!1;var s;try{s=JSON.parse('{"x":"y"}')}catch(x){s=null}s&&"y"==s.x?(a.T=!0,a.S=function(a){return JSON.parse(a)}):k.$&&k.$.parseJSON?(a.S=function(a){return k.$.parseJSON(a)},a.T=!0):a.S=function(){return null};a.xb=function(c){var b,d,f;a.Sa()&&2047<c.length&&("undefined"!=
typeof XMLHttpRequest&&(b=new XMLHttpRequest,"withCredentials"in b?d=1:b=0),b||"undefined"==typeof XDomainRequest||(b=new XDomainRequest,d=2),b&&a.AudienceManagement&&a.AudienceManagement.isReady()&&(a.T?b.ra=!0:b=0));!b&&a.Ia&&(c=c.substring(0,2047));!b&&a.d.createElement&&a.AudienceManagement&&a.AudienceManagement.isReady()&&(b=a.d.createElement("SCRIPT"))&&"async"in b&&((f=(f=a.d.getElementsByTagName("HEAD"))&&f[0]?f[0]:a.d.body)?(b.type="text/javascript",b.setAttribute("async","async"),d=3):b=
0);b||(b=new Image,b.alt="");b.ua=function(){try{a.na&&(clearTimeout(a.na),a.na=0),b.timeout&&(clearTimeout(b.timeout),b.timeout=0)}catch(c){}};b.onload=b.yb=function(){b.ua();a.fb();a.ba();a.A=0;a.fa();if(b.ra){b.ra=!1;try{var c=a.S(b.responseText);a.AudienceManagement.passData(c)}catch(d){}}};b.onabort=b.onerror=b.hb=function(){b.ua();(a.trackOffline||a.la)&&a.A&&a.g.unshift(a.eb);a.A=0;a.ha>a.J&&a.Fa(a.g);a.ba();a.oa(500)};b.onreadystatechange=function(){4==b.readyState&&(200==b.status?b.yb():
b.hb())};a.Ea=a.u();if(1==d||2==d){var e=c.indexOf("?");f=c.substring(0,e);e=c.substring(e+1);e=e.replace(/&callback=[a-zA-Z0-9_.\[\]]+/,"");1==d?(b.open("POST",f,!0),b.send(e)):2==d&&(b.open("POST",f),b.send(e))}else if(b.src=c,3==d){if(a.Ca)try{f.removeChild(a.Ca)}catch(g){}f.firstChild?f.insertBefore(b,f.firstChild):f.appendChild(b);a.Ca=a.cb}b.abort&&(a.na=setTimeout(b.abort,5E3));a.eb=c;a.cb=k["s_i_"+a.replace(a.account,",","_")]=b;if(a.useForcedLinkTracking&&a.F||a.r)a.forcedLinkTrackingTimeout||
(a.forcedLinkTrackingTimeout=250),a.ca=setTimeout(a.ba,a.forcedLinkTrackingTimeout)};a.fb=function(){if(a.ma()&&!(a.Da>a.J))try{k.localStorage.removeItem(a.ka()),a.Da=a.u()}catch(c){}};a.Fa=function(c){if(a.ma()){a.Ha();try{k.localStorage.setItem(a.ka(),k.JSON.stringify(c)),a.J=a.u()}catch(b){}}};a.Ha=function(){if(a.trackOffline){if(!a.offlineLimit||0>=a.offlineLimit)a.offlineLimit=10;for(;a.g.length>a.offlineLimit;)a.wa()}};a.forceOffline=function(){a.la=!0};a.forceOnline=function(){a.la=!1};a.ka=
function(){return a.offlineFilename+"-"+a.visitorNamespace+a.account};a.u=function(){return(new Date).getTime()};a.Aa=function(a){a=a.toLowerCase();return 0!=a.indexOf("#")&&0!=a.indexOf("about:")&&0!=a.indexOf("opera:")&&0!=a.indexOf("javascript:")?!0:!1};a.setTagContainer=function(c){var b,d,f;a.zb=c;for(b=0;b<a._il.length;b++)if((d=a._il[b])&&"s_l"==d._c&&d.tagContainerName==c){a.M(d);if(d.lmq)for(b=0;b<d.lmq.length;b++)f=d.lmq[b],a.loadModule(f.n);if(d.ml)for(f in d.ml)if(a[f])for(b in c=a[f],
f=d.ml[f],f)!Object.prototype[b]&&("function"!=typeof f[b]||0>(""+f[b]).indexOf("s_c_il"))&&(c[b]=f[b]);if(d.mmq)for(b=0;b<d.mmq.length;b++)f=d.mmq[b],a[f.m]&&(c=a[f.m],c[f.f]&&"function"==typeof c[f.f]&&(f.a?c[f.f].apply(c,f.a):c[f.f].apply(c)));if(d.tq)for(b=0;b<d.tq.length;b++)a.track(d.tq[b]);d.s=a;break}};a.Util={urlEncode:a.escape,urlDecode:a.unescape,cookieRead:a.cookieRead,cookieWrite:a.cookieWrite,getQueryParam:function(c,b,d){var f;b||(b=a.pageURL?a.pageURL:k.location);d||(d="&");return c&&
b&&(b=""+b,f=b.indexOf("?"),0<=f&&(b=d+b.substring(f+1)+d,f=b.indexOf(d+c+"="),0<=f&&(b=b.substring(f+d.length+c.length+1),f=b.indexOf(d),0<=f&&(b=b.substring(0,f)),0<b.length)))?a.unescape(b):""}};a.B="supplementalDataID timestamp dynamicVariablePrefix visitorID marketingCloudVisitorID analyticsVisitorID audienceManagerLocationHint authState fid vmk visitorMigrationKey visitorMigrationServer visitorMigrationServerSecure charSet visitorNamespace cookieDomainPeriods fpCookieDomainPeriods cookieLifetime pageName pageURL referrer contextData currencyCode lightProfileID lightStoreForSeconds lightIncrementBy retrieveLightProfiles deleteLightProfiles retrieveLightData".split(" ");
a.e=a.B.concat("purchaseID variableProvider channel server pageType transactionID campaign state zip events events2 products audienceManagerBlob tnt".split(" "));a.ia="timestamp charSet visitorNamespace cookieDomainPeriods cookieLifetime contextData lightProfileID lightStoreForSeconds lightIncrementBy".split(" ");a.K=a.ia.slice(0);a.qa="account allAccounts debugTracking visitor trackOffline offlineLimit offlineThrottleDelay offlineFilename usePlugins doPlugins configURL visitorSampling visitorSamplingGroup linkObject clickObject linkURL linkName linkType trackDownloadLinks trackExternalLinks trackClickMap trackInlineStats linkLeaveQueryString linkTrackVars linkTrackEvents linkDownloadFileTypes linkExternalFilters linkInternalFilters useForcedLinkTracking forcedLinkTrackingTimeout trackingServer trackingServerSecure ssl abort mobile dc lightTrackVars maxDelay expectSupplementalData AudienceManagement".split(" ");
for(n=0;250>=n;n++)76>n&&(a.e.push("prop"+n),a.K.push("prop"+n)),a.e.push("eVar"+n),a.K.push("eVar"+n),6>n&&a.e.push("hier"+n),4>n&&a.e.push("list"+n);n="pe pev1 pev2 pev3 latitude longitude resolution colorDepth javascriptVersion javaEnabled cookiesEnabled browserWidth browserHeight connectionType homepage pageURLRest".split(" ");a.e=a.e.concat(n);a.B=a.B.concat(n);a.ssl=0<=k.location.protocol.toLowerCase().indexOf("https");a.charSet="UTF-8";a.contextData={};a.offlineThrottleDelay=0;a.offlineFilename=
"AppMeasurement.offline";a.Ea=0;a.ha=0;a.J=0;a.Da=0;a.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";a.w=k;a.d=k.document;try{if(a.Ia=!1,navigator){var y=navigator.userAgent;if("Microsoft Internet Explorer"==navigator.appName||0<=y.indexOf("MSIE ")||0<=y.indexOf("Trident/")&&0<=y.indexOf("Windows NT 6"))a.Ia=!0}}catch(z){}a.ba=function(){a.ca&&(k.clearTimeout(a.ca),a.ca=q);a.j&&a.F&&a.j.dispatchEvent(a.F);a.r&&("function"==typeof a.r?a.r():a.j&&a.j.href&&(a.d.location=
a.j.href));a.j=a.F=a.r=0};a.Ga=function(){a.b=a.d.body;a.b?(a.q=function(c){var b,d,f,e,g;if(!(a.d&&a.d.getElementById("cppXYctnr")||c&&c["s_fe_"+a._in])){if(a.ta)if(a.useForcedLinkTracking)a.b.removeEventListener("click",a.q,!1);else{a.b.removeEventListener("click",a.q,!0);a.ta=a.useForcedLinkTracking=0;return}else a.useForcedLinkTracking=0;a.clickObject=c.srcElement?c.srcElement:c.target;try{if(!a.clickObject||a.I&&a.I==a.clickObject||!(a.clickObject.tagName||a.clickObject.parentElement||a.clickObject.parentNode))a.clickObject=
0;else{var m=a.I=a.clickObject;a.ga&&(clearTimeout(a.ga),a.ga=0);a.ga=setTimeout(function(){a.I==m&&(a.I=0)},1E4);f=a.ya();a.track();if(f<a.ya()&&a.useForcedLinkTracking&&c.target){for(e=c.target;e&&e!=a.b&&"A"!=e.tagName.toUpperCase()&&"AREA"!=e.tagName.toUpperCase();)e=e.parentNode;if(e&&(g=e.href,a.Aa(g)||(g=0),d=e.target,c.target.dispatchEvent&&g&&(!d||"_self"==d||"_top"==d||"_parent"==d||k.name&&d==k.name))){try{b=a.d.createEvent("MouseEvents")}catch(n){b=new k.MouseEvent}if(b){try{b.initMouseEvent("click",
c.bubbles,c.cancelable,c.view,c.detail,c.screenX,c.screenY,c.clientX,c.clientY,c.ctrlKey,c.altKey,c.shiftKey,c.metaKey,c.button,c.relatedTarget)}catch(q){b=0}b&&(b["s_fe_"+a._in]=b.s_fe=1,c.stopPropagation(),c.stopImmediatePropagation&&c.stopImmediatePropagation(),c.preventDefault(),a.j=c.target,a.F=b)}}}}}catch(r){a.clickObject=0}}},a.b&&a.b.attachEvent?a.b.attachEvent("onclick",a.q):a.b&&a.b.addEventListener&&(navigator&&(0<=navigator.userAgent.indexOf("WebKit")&&a.d.createEvent||0<=navigator.userAgent.indexOf("Firefox/2")&&
k.MouseEvent)&&(a.ta=1,a.useForcedLinkTracking=1,a.b.addEventListener("click",a.q,!0)),a.b.addEventListener("click",a.q,!1))):setTimeout(a.Ga,30)};a.Ga();a.loadModule("ActivityMap")}
function s_gi(a){var k,q=window.s_c_il,r,n,t=a.split(","),u,s,x=0;if(q)for(r=0;!x&&r<q.length;){k=q[r];if("s_c"==k._c&&(k.account||k.oun))if(k.account&&k.account==a)x=1;else for(n=k.account?k.account:k.oun,n=k.allAccounts?k.allAccounts:n.split(","),u=0;u<t.length;u++)for(s=0;s<n.length;s++)t[u]==n[s]&&(x=1);r++}x||(k=new AppMeasurement);k.setAccount?k.setAccount(a):k.sa&&k.sa(a);return k}AppMeasurement.getInstance=s_gi;window.s_objectID||(window.s_objectID=0);
function s_pgicq(){var a=window,k=a.s_giq,q,r,n;if(k)for(q=0;q<k.length;q++)r=k[q],n=s_gi(r.oun),n.setAccount(r.un),n.setTagContainer(r.tagContainerName);a.s_giq=0}s_pgicq();