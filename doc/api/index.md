<!--
  NB(chrisdickinson): if you move this file, be sure to update
  tools/doc/html.js to point at the new location.
-->

<!--introduced_in=v0.10.0-->

* [About these Docs](documentation.html)
* [Usage & Example](synopsis.html)

<div class="line"></div>

* [Assertion Testing](assert.html)
* [Async Hooks](async_hooks.html)
* [Buffer](buffer.html)
* [C++ Addons](addons.html)
* [C/C++ Addons - N-API](n-api.html)
* [Child Processes](child_process.html)
* [Cluster](cluster.html)
* [Command Line Options](cli.html)
* [Console](console.html)
* [Crypto](crypto.html)
* [Debugger](debugger.html)
* [Deprecated APIs](deprecations.html)
* [DNS](dns.html)
* [Domain](domain.html)
* [ECMAScript Modules](esm.html)
* [Errors](errors.html)
* [Events](events.html)
* [File System](fs.html)
* [Globals](globals.html)
* [HTTP](http.html)
* [HTTP/2](http2.html)
* [HTTPS](https.html)
* [Inspector](inspector.html)
* [Internationalization](intl.html)
* [Modules](modules.html)
* [Net](net.html)
* [OS](os.html)
* [Path](path.html)
* [Performance Hooks](perf_hooks.html)
* [Process](process.html)
* [Punycode](punycode.html)
* [Query Strings](querystring.html)
* [Readline](readline.html)
* [REPL](repl.html)
* [Stream](stream.html)
* [String Decoder](string_decoder.html)
* [Timers](timers.html)
* [TLS/SSL](tls.html)
* [Trace Events](tracing.html)
* [TTY](tty.html)
* [UDP/Datagram](dgram.html)
* [URL](url.html)
* [Utilities](util.html)
* [V8](v8.html)
* [VM](vm.html)
* [Worker Threads](worker_threads.html)
* [ZLIB](zlib.html)

<div class="line"></div>

* [GitHub Repo & Issue Tracker](https://github.com/nodejs/node)
//
<< < !doctype: html > << < html lang = "en" >
    <head > <meta charset="utf-8"> <meta "name=viewport"
content="width=device-width, initial-scale=1" > //use meta to replace to inline styles
    < title  jQuery UI Progressbar - Download Dialog 
      /title> <link rel = "stylesheet"
href = "//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css" > <link "rel=stylesheet"
href = "/resources/demos/style.css" > <script src="https://code.jquery.com/jquery-1.12.4.js" >   
  <
script src = "https://code.jquery.com/ui/1.12.1/jquery-ui.js" >
  <script> $(function () {
    var progressTimer, progressbar = $("#progressbar")
        , progressLabel = $(".progress-label")
        , dialogButtons = [{
            text: "Cancel Download"
            , click: closeDownload
        }]
        , dialog = $("#dialog")
        .dialog({
            autoOpen: false
            , closeOnEscape: false
            , resizable: false
            , buttons: dialogButtons
            , open: function () {
                progressTimer = setTimeout(progress, 2000);
            }
            , beforeClose: function () {
                downloadButton.button("option", {
                    disabled: false
                    , label: "Start Download"
                });
            }
        })
        , downloadButton = $("#downloadButton")
        .button()
        .on("click", function () {
            $(this)
                .button("option", {
                    disabled: true
                    , label: "Downloading..."
                });
            dialog.dialog("open");
        });
    progressbar.progressbar({
        value: false
        , change: function () {
            progressLabel.text("Current Progress: " + progressbar.progressbar("value") + "%");
        }
        , complete: function () {
            progressLabel.text("Complete!");
            dialog.dialog("option", "buttons", [{
                text: "Close"
                , click: closeDownload
            }]);
            $(".ui-dialog button")
                .last()
                .trigger("focus");
        }
    });

    function progress() {
        var val = progressbar.progressbar("value") || 0;
        progressbar.progressbar("value", val + Math.floor(Math.random() * 3));
        if (val <= 99) {
            progressTimer = setTimeout(progress, 50);
        }
    }

    function closeDownload() {
        clearTimeout(progressTimer);
        dialog.dialog("option", "buttons", dialogButtons)
            .dialog("close");
        progressbar.progressbar("value", false);
        progressLabel.text("Starting download...");
        downloadButton.trigger("focus");
    }
})
{
<
/script ><
style > 
  progressbar 
  {
    margin - top: 20 px;
}.progress - label {
    font - weight: bold;
    text - shadow: 1 px 1 px 0#ff;
}.ui - dialog - titlebar - close {
    display: none;
  /head > 
  body> <div id="dialog"
title="File Download" > < 
div: class = "progress-label" > Starting download...
div> <
div:id="progressbar"> <
  <button id = "downloadButton" > Start Download <
  /div 
                                                       >
  < 
  /button >
    < 
      /body > < 
    /
html >
}
