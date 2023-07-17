var parsed,theme="light",localThemeKey="theme",themeRecord=localStorage.getItem("theme");!themeRecord||(parsed=JSON.parse(themeRecord))&&parsed.mode&&(theme=parsed.mode),"dark"===theme&&document.body.classList.add("dark")body{background:#fff}body.dark{background:#191919}@keyframes startup-shimmer-animation{0%{transform:translateX(-100%) translateZ(0)}100%{transform:translateX(100%) translateZ(0)}}@keyframes startup-shimmer-fade-in{0%{opacity:0}100%{opacity:1}}@keyframes startup-spinner-rotate{0%{transform:rotate(0) translateZ(0)}100%{transform:rotate(360deg) translateZ(0)}}#initial-loading-spinner{position:fixed;height:100vh;width:100vw;z-index:-1;display:none;align-items:center;justify-content:center;opacity:.5}#initial-loading-spinner svg{height:24px;width:24px;animation:startup-spinner-rotate 1s linear infinite;transform-origin:center center;pointer-events:none}#skeleton{background:#fff;position:fixed;height:100vh;width:100vw;z-index:-1;display:none;overflow:hidden}#initial-loading-spinner.show,#skeleton.show{display:flex}body.dark #skeleton{background:#191919}.notion-front-page #skeleton,.notion-mobile #skeleton{display:none}#skeleton-sidebar{background-color:#fbfbfa;box-shadow:inset -1px 0 0 0 rgba(0,0,0,.025);display:flex;width:240px;flex-direction:column;padding:12px 14px;overflow:hidden}body.dark #skeleton-sidebar{background-color:#202020;box-shadow:inset -1px 0 0 0 rgba(255,255,255,.05)}#skeleton.isElectron #skeleton-sidebar{padding-top:46px}#skeleton .row{display:flex;margin-bottom:8px;align-items:center}#skeleton .row.fadein{animation:1s ease-in 0s 1 normal both running startup-shimmer-fade-in}#skeleton .chevron{width:12px;height:12px;display:block;margin-right:4px;fill:rgba(227,226,224,.5)}body.dark #skeleton .chevron{fill:#2f2f2f}.startup-shimmer{background:rgba(227,226,224,.5);overflow:hidden;position:relative}body.dark .startup-shimmer{background:#2f2f2f}.startup-shimmer::before{content:"";position:absolute;height:100%;width:100%;z-index:1;animation:1s linear infinite startup-shimmer-animation;background:linear-gradient(90deg,transparent 0,rgba(255,255,255,.4) 50%,transparent 100%)}body.dark .startup-shimmer::before{background:linear-gradient(90deg,transparent 0,rgba(86,86,86,.4) 50%,transparent 100%)}#skeleton .icon{width:20px;height:20px;border-radius:4px}#skeleton .text{height:10px;border-radius:10px}#skeleton .draggable{-webkit-app-region:drag;position:absolute;top:0;left:0;width:100%;height:36px;display:none}#skeleton.isElectron .draggable{display:block}(t=>{function e(e){e=t.localStorage&&t.localStorage.getItem(e),e=e&&JSON.parse(e);if(e&&e.value)return e.value}var i=document.getElementById("skeleton"),d=document.getElementById("skeleton-sidebar"),n=document.getElementById("initial-loading-spinner"),o=e("LRU:KeyValueStore2:sidebar"),a=e("LRU:KeyValueStore2:current-user-id"),l="undefined"!=typeof global||t.__isElectron,r=/ReactNative|MobileNative|Android|iPad|iPhone|iPod|Windows Phone/.test(navigator.userAgent);!i||void 0===a||r||l?n&&n.classList.add("show"):(i.classList.add("show"),d&&o&&(!1===o.expanded&&d.remove(),0<o.width&&(d.style.width=String(o.width)+"px")))})(window) ::-webkit-scrollbar { width: 10px; height: 10px; } ::-webkit-scrollbar { background: transparent; } ::-webkit-scrollbar-track { background: #EDECE9; } ::-webkit-scrollbar-thumb { background:#D3D1CB; } ::-webkit-scrollbar-thumb:hover { background:#AEACA6; }

[ 
![📶](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)

ChinaUnicom



](https://chinatelecomoperators.notion.site/chinatelecomoperators/ChinaUnicom-5959008dfc2a477baf90471682f770fd?pvs=18)

/

![](https://chinatelecomoperators.notion.site/icons/wrench_green.svg?mode=light)

Node.js 通用配置说明

Search

Try Notion

![](https://chinatelecomoperators.notion.site/icons/wrench_green.svg?mode=light)

Node.js 通用配置说明

[ 
多账号设置方式



](https://chinatelecomoperators.notion.site/Node-js-6eac6d91ef984248811bfaf5f44a3759?pvs=25#389085e15505489293d08e32be9312c5)

[ 
使用短信验证码登录



](https://chinatelecomoperators.notion.site/Node-js-6eac6d91ef984248811bfaf5f44a3759?pvs=25#eb41cec0326849cf8e863e2dbbbca341)

[ 
不使用短信验证码登录



](https://chinatelecomoperators.notion.site/Node-js-6eac6d91ef984248811bfaf5f44a3759?pvs=25#0750df5b02524f49b0927137462208ba)

[ 
所有环境变量



](https://chinatelecomoperators.notion.site/Node-js-6eac6d91ef984248811bfaf5f44a3759?pvs=25#c14a90b831b34afca7eb3365e3868216)

多账号设置方式

复制出一个新文件 文件名为 \_liubang\_10010.js

即为 另一个账号 liubang

它将读取 10010v4-liubang-box.dat 里的配置

它使用的所有环境变量前缀对应变化

例如从 ChinaUnicom\_10010v4\_mobile 对应的变为 liubang\_10010v4\_mobile

同理 短信验证码相关的文件也改成 \_liubang\_10010\_sms\_sign.js 和 \_liubang\_10010\_send\_sms.js

不同账号使用自定义通知

此时在执行到 加载sendNotify.js 文件发送通知时, 会优先加载 \_liubang\_sendNotify.js 来发送通知. 比如你不想使用青龙通用的 sendNotify.js, 你可以自己准备一个 \_liubang\_sendNotify.js

使用短信验证码登录

发送短信验证码

将尝试从环境变量中读取手机号

Shell

Copy

ChinaUnicom\_10010v4\_mobile=18600000000  node 10010\_send\_sms.js

​

使用短信验证码登录

将尝试从环境变量中读取手机号和短信验证码

Shell

Copy

ChinaUnicom\_10010v4\_mobile=18600000000  ChinaUnicom\_10010v4\_code=1234  node 10010\_sms\_sign.js

​

此时已经自动存好了 cookie token_online appId

如果你不理解, 那么你可以将上述脚本执行日志里的 cookie token_online appId 自己复制出来使用.

不使用短信验证码登录

自己配置 Cookie TokenOnline AppId 手机号(mobile) 服务密码(password) 对应的环境变量

执行一次

(如果是青龙或者你写到了什么初始化脚本里)删掉 Cookie TokenOnline 的环境变量

为什么要删掉? 参考下一条![👇🏻](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)​

所有环境变量

![🤔](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)

不要设一个固定的环境变量然后不删掉….因为会优先从环境变量读取 等于每次都是一个固定的值. 它不会被更新…

还是有人看不懂

意思就是不要设置一个固定的值 比如 cookie

因为本脚本不会更新环境变量

你设了一个固定的 cookie 就会每次都用这个固定的 cookie

维护在线状态等逻辑得到的新 cookie 也不会在下次被用到

![🤔](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)

要 删掉 不要 禁用 因为青龙里的禁用还是会设置环境变量的值, 只不过是设为 空字符串

青龙里环境变量不能有空格 你可以这么做:

![](https://chinatelecomoperators.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F055d94ba-9eea-406f-86bb-8a877eb3b369%2FUntitled.png?id=cd53f2c4-7a79-4852-8f68-a3c94ecaccd9&table=block&spaceId=075c6d4d-bde7-49d5-9bd4-06141d2f80d9&width=2000&userId=&cache=v2)

在这里 写

Plain Text

Copy

$.setdata(`剩 \[通用有限.剩余\] 今用 \[所有通用.今日用量\] 今免 \[所有免流.今日用量\]\\n总用 \[所有通用.已用\] 总免 \[所有免流.已用\]`, KEY_DESC)

​

然后手动执行两次

第一次它会被写入 dat

第二次以后 它就会被使用. 可以去删掉它或者不管它.

以后脚本被定时拉库覆盖了也不影响.

语法

Markdown

Copy

$.setdata(``, KEY_DESC)

​

某个 环境变量 对应的 key 自己在下面找![👇🏻](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)​

JSON

Copy

\[{  "环境变量名":  "ChinaUnicom\_10010v4\_debug",  "key":  "KEY_DEBUG",  "name":  "调试模式(一般不开 开了通知爆炸)",  "val":  false,  "type":  "boolean",  "desc":  "默认不开启调试. 开启后将推送自动登录等信息"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_mobile",  "key":  "KEY_MOBILE",  "name":  "手机号",  "val":  "",  "type":  "text",  "desc":  "联通客户端登录手机号"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_code",  "key":  "KEY_CODE",  "name":  "验证码(执行验证码登录才需要填)",  "placeholder":  "",  "val":  "",  "type":  "text",  "desc":  "登录短信验证码"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_password",  "key":  "KEY_PASSWORD",  "name":  "服务密码",  "val":  "",  "type":  "text",  "desc":  "联通客户端登录的服务密码"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_appId",  "key":  "KEY_APPID",  "name":  "appId",  "val":  "",  "type":  "text",  "desc":  "联通客户端 appId"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_cookie",  "key":  "KEY_COOKIE",  "name":  "Cookie",  "val":  "",  "type":  "text",  "desc":  "Cookie"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_token_online",  "key":  "KEY\_TOKEN\_ONLINE",  "name":  "TokenOnline",  "val":  "",  "type":  "text",  "desc":  "TokenOnline"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_min_usage",  "key":  "KEY\_MIN\_USAGE",  "name":  "最小用量通知阈值(单位 M) ",  "val":  0,  "type":  "number",  "desc":  "通知模板内的任一一项用量 >= 该数值时 才会通知. 例 \[通用有限.用量\] 表示这段时间内 有限的通用包的差额. 如果你要无变化时不通知, 这里可以设为 0.01"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_normal\_limited\_only",  "key":  "KEY\_NORMAL\_LIMITED_ONLY",  "name":  "仅在 \[通用有限.用量\] >= 最小用量通知阈值 时, 进行通知",  "val":  false,  "type":  "boolean",  "desc":  "默认关闭. 开启后, 仅在 \[通用有限.用量\] >= 最小用量通知阈值 时, 才会通知"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_new\_pkg\_notify_disabled",  "key":  "KEY\_NEW\_PKG\_NOTIFY\_DISABLED",  "name":  "关闭新增包通知",  "val":  false,  "type":  "boolean",  "desc":  "默认检测到新包时会发送通知"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_title",  "key":  "KEY_TITLE",  "name":  "通知标题模板",  "val":  "",  "type":  "textarea",  "desc":  "默认: \[套餐\], 例: 流邦卡19元套餐. 变量看文档"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_subt",  "key":  "KEY_SUBT",  "name":  "通知副标题模板",  "val":  "",  "type":  "textarea",  "desc":  "默认: \[时长\] 跳 \[所有通用.用量\] 免 \[所有免流.用量\], 例: 18分钟 跳 10M 免 10M. 变量看文档"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_desc",  "key":  "KEY_DESC",  "name":  "通知正文模板",  "val":  "",  "type":  "textarea",  "desc":  "默认: 通用剩 \[通用有限.剩余\] 免流剩 \[免流有限.剩余\], 例: 通用剩 5.03G 免流剩 26.35G. 若定向无限, 推荐使用: 剩 \[通用有限.剩余\] 今用 \[所有通用.今日用量\] 今免 \[所有免流.今日用量\] 变量看文档"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_bark",  "key":  "KEY_BARK",  "name":  "使用 Bark 通知",  "val":  "",  "type":  "textarea",  "desc":  "\[推送标题\]/\[推送内容\]会被自动替换 形如 https://api.day.app/XXXXXXXXX/\[推送标题\]/\[推送内容\]?group=10010&autoCopy=1&isArchive=1&icon=https%3A%2F%2Fraw.githubusercontent.com%2Fanker1209%2Ficon%2Fmain%2Fzglt.png&sound=shake&level=timeSensitive 具体看文档"  },  {  "环境变量名":  "ChinaUnicom\_10010v4\_config",  "key":  "KEY_CONFIG",  "name":  "设置(没需求不用设)",  "val":  "",  "type":  "text"  }\]

​

![🤔](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)

加个传送门吧 [![](https://chinatelecomoperators.notion.site/icons/gear_gray.svg)通用配置说明](https://chinatelecomoperators.notion.site/220d744a17714025b8e34b7e6e40165e?pvs=24)

window.CONFIG={env:"production",isAdminMode:!1,isDevelopingInAirplaneMode:!1,isLocalhost:!1,offline:!0,version:"23.12.0.152",domainBaseUrl:"https://www.notion.so",adminUrl:"https://admin.notion.so",publicDomainName:"notion.site",protocol:"notion",staticS3:{url:"https://prod-notion-assets.s3-us-west-2.amazonaws.com",bucket:"prod-notion-assets"},lastUpdatedTime:1689359961481,api:{http:"/api/v3"},googleOAuth:{clientId:"905154081809-858sm3f0qnalqd9d44d9gecjtrdji9tf.apps.googleusercontent.com"},messageStore:{url:"https://msgstore.www.notion.so",api:"/api/v1"},stripe:{key:"pk\_live\_vuNO27XGTCbXjVwneiECILjT"},revenueCat:{apiResponseMaxAge:6048e5,entitlementIDs:{personal:"notion.id.personal\_pro"},productIDs:{personal:{monthly:"notion.id.personal\_pro\_monthly",yearly:"notion.id.personal\_pro\_yearly"}}},intercom:{appId:"gpfdrxfd",adminId:"3483686"},mutiny:{personalKey:"1149e901f65fc47c"},partnerStack:{apiKey:"pk\_6nwYfqCKEoPt2lTuU8Veswm2zArJ3Apq"},segment:{writeKey:"g1mMn2qquRcv7exBIVDivoKl9cOrdxLA"},amplitude:{apiKey:"af43d4b535912f7751949bfb061d8659"},pricing:{invoiceDaysUntilDue:30,free:{spaceBlockLimit:1e3,fileUploadMaxBytes:5e6},team\_free:{spaceBlockLimit:1e3,fileUploadMaxBytes:5e6},personal\_free:{fileUploadMaxBytes:5e6},student:{productId:"prod\_FhChFoDp7gS1Ba"},personal:{productId:"prod\_CpavZFCbxF2YGx",monthlyPrice:500,yearlyPrice:4800},team:{productId:"prod\_CpawK4ih14xs4t",monthlyPricePerMember:1e3,yearlyPricePerMember:9600},plus:{productId:"prod\_CpawK4ih14xs4t",monthlyPricePerMember:1e3,yearlyPricePerMember:9600},business:{productId:"prod\_LEnFERYcTgENz8",monthlyPricePerMember:1800,yearlyPricePerMember:18e3},enterprise:{productId:"prod\_Cpb8M1AFEFhdy1",monthlyPricePerMember:2500,yearlyPricePerMember:24e3},ai:{productId:"prod\_N6tyEr9FFSTXJo",monthlyPricePerMember:1e3,yearlyPricePerMember:9600}},desktopS3:{url:"https://s3-us-west-2.amazonaws.com/desktop-release.notion-static.com"},publicFileS3:{url:"https://s3-us-west-2.amazonaws.com/public.notion-static.com",bucket:"public.notion-static.com"},temporaryFileS3:{url:"https://s3-us-west-2.amazonaws.com/temporary.notion-static.com",bucket:"temporary.notion-static.com"},secureFileS3:{url:"https://s3-us-west-2.amazonaws.com/secure.notion-static.com",bucket:"secure.notion-static.com"},secureFileConfig:{origins:{s:"secure.notion-static.com"},s3BaseDomainName:"s3.us-west-2.amazonaws.com",rootPath:"/f",protocol:"https",hostname:"file.notion.so"},loggly:{token:"9b01b08e-c969-4e27-837c-805d1fc6ec7b"},splunk:{token:"EA76605A-F565-4B17-A496-34435622A1EB"},embedly:{key:"421626497c5d4fc2ae6b075189d602a2"},iframely:{key:"222a85036317ca50d3ba5f321bfda6f0"},iframely\_prod:{key:"656ac74fac4fff346b811dca7919d483"},aif:{url:"https://aif.notion.so/aif-production.html"},contentful:{spaceId:"spoqsaf9291f",contentDeliveryToken:"AGqteRpWD8aE\_kxy\_s7_hSFAlKCh5qf-RctSU6vV6u0",contentPreviewToken:"uR2ZVAs-9TMKDq0YKYVtczFplx6P9p06huCibZDJZKA"},iOSAppId:1232780281,facebook:{pixelId:"499229960464487"},statsig:{apiKey:"client-Tgza5wNFa8dVt9BdeUfG6Vkm29bHxX10MhoztTMzLBB"},googleReCaptcha:{siteKey:"6LcvqigfAAAAAPaPL3j2YLldFcZVGwKvG9TmjDgK"},turnstile:{sitekey:"0x4AAAAAAADLq8YYJOHc6qqw"},google:{clientId:"905154081809-858sm3f0qnalqd9d44d9gecjtrdji9tf.apps.googleusercontent.com"},sprig:{environmentId:"2HKBN1wgCwHr"}}

![Save as Text](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAYAAACqaXHeAAAEFUlEQVR4Xu2az4scRRTH36teRBdkEDwqbH7swWDEixdPSk6awyaBzCYSwiLERYhR2OnqHuKPgRW6q3r3koSFKGKIImYTyA8UPHjJPxBBTRB/IMGTt70Nmp16oYaeMDSzM9U91ZlNuvq0y3S/et9Pf9+rHzMIFb+w4vrBAXAOqDgBVwKTNIAQ4hQibnDOL04qj4k5QAixDxF/TIW/xjm/OQkIEwMgpZwHgG+1aKXU0TAMu38/7MsBeNjEe+M5B7gScD3ANUE3C7hp0K0D3ELIrQTdUtjtBR6dzVCSJHMA8Jfv+7+Ou4coYy+QJMmLALDL9/3rpvkZ7wbjOK4zxi4R0SYRHQjD8HvTQQbdZxtAHMf7EfEaIk4ppebDMFw3yS83AB1UQ2CM1X3fv2oySNkAkiQ5qJRa1+LTsY5wzi+Z5GYMgIhQSnkeEU+kgTuIeLgoBFsO0OKJ6DIAeOnL+ZxzvoiIZBVAL5gQ4jMbEGwAGCQ+CIJ3TIT37jF2QH9QGxDGBWBDvNZUCIB+cFwI4wCI4/gIY+zrftvnffNjOWCrclBKHTM93CwKIBX/Te/lEdG5IAjey2P7/nsLO6APwllEPJn+T0qpt0wgFAFgW/xYJZDpCbkh5AVQhnhrANKekAtCHgBSyuMAcMGW7a2WQFEnmALIigeAFc65X7Tms8+N3QOyAaWUCQA0RvUEEwBli7daAv0gshAAYCH7BegoAFEU7fQ878++qdrqm7cyDQ6z4SgIOQGUIr40B/TADIMwCoCOsbKyskcp9STn/Jatmi+9B2QHEEK0EPGTXk/olYMJgLJElzYLbJWwlFI3Rd0c9aV3aQsA8F+lvhjJQiCiHxDxDU2kMr8PyEB4YJjKANCKB0GoFIBBELY1ACnlV0Q0xxh71cZpcM/3QoiTiHgWAPTR2ss2YydJsoOIviOijXa7/Xqr1fp/qwY9dCkspZwFgN/Thz/inH9qc2pKkuTY5ubm7Waz+ZPNuEKI04jYzZUx9kKj0fitEIA4jvcyxn7uzl1Ey0EQfGwz0bJiSSmXAeDDdIZ5KQzDXxyALQgMLQHnAFcCrgdUuwlGUbTb87w/0lngTBAE75fVuW3GlVKuAcC7Oman05ltNpv6YGXgNbQJtlqtJ6anpzcA4CkA+HtmZma2Xq93bCZrO1YURc8wxu4i4tMA0K7VarXFxcV7hQCky9YvAODt1AVXAGCNMWb0xaNtcaPiEdFeIvoAEXem+X4ZBEE398IAVldXn+90OvpE5tlRCWynz4no36mpqVeWlpb+GQuAflgI8RwiSgA4up1EDsnlLmPszUajcWdUvrmOxfXCyPO8Q0qpXM+NSsLW57o0lVK32+32jWEboP7xtqUQW0BM4jgAJpQe53ucAx7nt2uirfIOuA9jAw9ug6hl7AAAAABJRU5ErkJggg== "Save as Text")