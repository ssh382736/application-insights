可以监控的数据:
timings of page loads
AJAX calls
counts and details of browser exceptions 
AJAX failures
users and session counts.


如何监控：
<script type="text/javascript">
var appInsights=window.appInsights||function(a){
  function b(a){c[a]=function(){var b=arguments;c.queue.push(function(){c[a].apply(c,b)})}}var c={config:a},d=document,e=window;setTimeout(function(){var b=d.createElement("script");b.src=a.url||"https://az416426.vo.msecnd.net/scripts/a/ai.0.js",d.getElementsByTagName("script")[0].parentNode.appendChild(b)});try{c.cookie=d.cookie}catch(a){}c.queue=[];for(var f=["Event","Exception","Metric","PageView","Trace","Dependency"];f.length;)b("track"+f.pop());if(b("setAuthenticatedUserContext"),b("clearAuthenticatedUserContext"),b("startTrackEvent"),b("stopTrackEvent"),b("startTrackPage"),b("stopTrackPage"),b("flush"),!a.disableExceptionTracking){f="onerror",b("_"+f);var g=e[f];e[f]=function(a,b,d,e,h){var i=g&&g(a,b,d,e,h);return!0!==i&&c["_"+f](a,b,d,e,h),i}}return c
  }({
      instrumentationKey:"<your instrumentation key>"
  });

window.appInsights=appInsights,appInsights.queue&&0===appInsights.queue.length&&appInsights.trackPageView();
</script>

把这段代码放进想要监控的页面<head></head>中

如果使用的是angularJS的话，使用http://ngmodules.org/modules/angular-appinsights 中的方式引入:
<script type="text/javascript">
    var appInsights=window.appInsights||function(config){
    function i(config){t[config]=function(){var i=arguments;t.queue.push(function(){t[config].apply(t,i)})}}var t={config:config},u=document,e=window,o='script',s='AuthenticatedUserContext',h='start',c='stop',l='Track',a=l+'Event',v=l+'Page',y=u.createElement(o),r,f;y.src=config.url||'https://az416426.vo.msecnd.net/scripts/a/ai.0.js';u.getElementsByTagName(o)[0].parentNode.appendChild(y);try{t.cookie=u.cookie}catch(p){}for(t.queue=[],t.version='1.0',r=['Event','Exception','Metric','PageView','Trace','Dependency'];r.length;)i('track'+r.pop());return i('set'+s),i('clear'+s),i(h+a),i(c+a),i(h+v),i(c+v),i('flush'),config.disableExceptionTracking||(r='onerror',i('_'+r),f=e[r],e[r]=function(config,i,u,e,o){var s=f&&f(config,i,u,e,o);return s!==!0&&t['_'+r](config,i,u,e,o),s}),t
    }({});
    window.appInsights=appInsights;
</script>
把这段代码放进想要监控的页面<head></head>中

先要引入angular-appinsights module
然后在页面中使用下面代码引入module
<script type="text/javascript" src="angular-appinsights.js"></script>
