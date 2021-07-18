  
// ==UserScript==
// @name         Arras.io multibox script
// @namespace    http://tampermonkey.net/k
// @description  press F to set your main window (sends packets to the bot windows), then press T to start the actual multibox script (recieves then sends the same packets that were sent from the main window)
// @version      emo logan paul
// @author       shlong#2873
// @match        *://arras.io/*
// @grant        GM_getValue
// @grant        GM_setValue
// @grant        GM_addValueChangeListener
// ==/UserScript==
//sdfjhsdkjfhjsdakjfhsadkjfhsdakjfhsadf

(() => {
    "use strict";
    const overrideWS = WebSocket.prototype.send;
    let ws, packet;
    let main = false, initiation = false;

    WebSocket.prototype.send = function (data) {
        if (main) {
            GM_setValue("WSVal", Array.from(new Uint8Array(data)));
        }
        ws = this;
        return overrideWS.call(this, data);
    };

    GM_addValueChangeListener("WSVal", () => {
        initiation = GM_getValue("SendToAll");
        packet = GM_getValue("WSVal");
        if (initiation && !main && GM_getValue("SendToAll") !== null) {
            ws.send(new Uint8Array(packet));
        }
    });

    document.addEventListener("keydown", (e) => {
        if (e.keyCode == 70) {
            main = !main;
            console.log("%c [F] Main Window: " + main, "color: #f700ff; font-size: 2em;");
        }
        if (e.keyCode == 84) {
            GM_setValue("SendToAll", initiation = !initiation);
            console.log("%c [T] Multibox: " + initiation, "color: #00ff2f; font-size: 2em;");
        }
    });
})();
