# 常见爬虫拦截egg插件

简单通过user-agent判断是不是主流爬虫，按概率阈值进行拦截，跳转到首页。 也就是只准爬首页。

配置：

    {
        spider_flag: [], // 自定义额外的spider，小写
        threshold: 1 // 自定义按概率进行拦截的 Math.random() < threshold 才拦截
    }

内置主流的几种spider:

    let SPIDER_FLAG = [
        'baiduspider',
        '360spider',
        'bytespider',
        'toutiaospider',
        'yodaobot',
        'googlebot',
        'teoma',
        'msnbot',
        'gigabot',
        'sogou web spider',
        'sogou inst spider',
        'sogou spider',
        'semrushbot',
        'applebot',
        'serpstatbot',
        'zenmen', // 不知名漏洞扫描软件ZenMen_Sec V1.0
        'python'// 主要case有Python/3.6 aiohttp/3.0.9 和 Python-urllib/2.7
    ];

如果用户有自定义，二者会合并。


# Install

    npm i egg-antispider --save

# Usage

    // {app_root}/config/plugin.js
    exports.cors = {
        enable: true,
        package: 'egg-antispider',
    };

# Configuration
Support all configurations in antispider(https://www.npmjs.com/package/antispider).

// {app_root}/config/config.default.js
exports.antispider = {
    spider_flag: [], // 自定义额外的spider，小写
    threshold: 1 // 自定义按概率进行拦截的 Math.random() < threshold 才拦截
};