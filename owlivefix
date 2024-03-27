// ==UserScript==
// @name         删除守望先锋直播中遮挡左侧聊天栏的马赛克
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  删除守望先锋直播的马赛克
// @author       果冻大神
// @match        https://live.bilibili.com/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // 创建一个 MutationObserver 实例
    const observer = new MutationObserver(mutationsList => {
        // 检查每个变动
        for(const mutation of mutationsList) {
            // 检查是否有节点添加或移除
            if (mutation.type === 'childList') {
                // 遍历所有新增的节点
                mutation.addedNodes.forEach(node => {
                    // 如果新增节点匹配目标元素，则移除它
                    if (node.classList.contains('web-player-module-area-mask')) {
                        node.remove();
                    }
                });
            }
        }
    });

    // 监听文档根节点的子节点变化
    observer.observe(document.documentElement, {
        childList: true,
        subtree: true
    });
})();
