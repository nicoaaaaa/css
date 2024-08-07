HTML 引入

在博客主题文件夹下的 /layouts/partials/comments.html 中粘贴以下内容

注意：CSS 变量可自定义， 默认样式为 变量与默认值

重要！ 请将 serverURL: 后的内容修改为你自己的域名
```css
<head>
    <!-- ... -->
    <link
      rel="stylesheet"
      href="https://unpkg.com/@waline/client@v2/dist/waline.css"
    />
    <!-- ... -->
  </head>
  <body>

    <div id="waline"></div>
    <script type="module">
      import { init } from 'https://unpkg.com/@waline/client@v2/dist/waline.mjs';

      init({
        el: '#waline',
        serverURL: 'http://waline.vercel.app',   #你的waline链接地址
        lang: 'zh-CN',
        emoji: [
        '//unpkg.com/@waline/emojis@1.2.0/bmoji',
        '//unpkg.com/@waline/emojis@1.2.0/tieba',
        '//unpkg.com/@waline/emojis@1.2.0/qq',
        '//unpkg.com/@waline/emojis@1.2.0/alus',
        '//unpkg.com/@waline/emojis@1.1.0/bilibili',
        'https://cdn.jsdelivr.net/gh/norevi/waline-blobcatemojis@1.0/blobs',
        ],
        dark: 'html[class="scroll-smooth dark"]',

      });
    </script>


    <style>
      /*日间模式*/
      :root {
        /* 字体大小 */
        --waline-font-size: 16px;

        /* 白色 */
        --waline-white: #ffff;
        /* 浅灰色 */
        --waline-light-grey: #999;
        /* 深灰色 */
        --waline-dark-grey: #666;

        /* 主题色 */
        --waline-theme-color: #3b82f6;
        /* 活动状态的颜色 */
        --waline-active-color: rgb(36, 36, 36);

        /* 一般文本颜色 */
        --waline-color: #222;
        /* 背景颜色 */
        --waline-bgcolor: #fff;
        /* 较浅的背景颜色 */
        --waline-bgcolor-light: #f8f8f8;
        /* 鼠标悬停时的背景颜色 */
        --waline-bgcolor-hover: #ffff;
        /* 边框颜色 */
        --waline-border-color: #ddd;
        /* 禁用状态的背景颜色 */
        --waline-disable-bgcolor: rgba(248, 248, 248, 0.4);
        /* 禁用状态的文本颜色 */
        --waline-disable-color:#bbb;
        /* 代码块的背景颜色 */
        --waline-code-bgcolor: #282c34;

        /* 引用块的颜色 */
        --waline-bq-color: #f0f0f0;

        /* 头像 */
        --waline-avatar-size: 2.5rem;
        /* 移动设备上的头像大小 */
        --waline-m-avatar-size: calc(var(--waline-avatar-size) * 9 / 13);

        /* 徽章颜色 */
        --waline-badge-color: #3b82f6;
        /* ：徽章字体大小 */
        --waline-badge-font-size: 12px;

        /* 信息块的边框 */
        --waline-info-border: 1px solid #999;
        /* 信息块的文本颜色 */
        --waline-info-color: #999;
        /* 信息块的字体大小 */
        --waline-info-font-size: 12px;
          /* 信息块背景颜色 */
        --waline-info-bgcolor: rgba(235, 235, 235, 0.4);

        /* 渲染选择，一般边框样式 */
        --waline-border: 1px solid var(--waline-border-color);
        /* 头像的圆角半径 */
        --waline-avatar-radius: 50%;
        /* 阴影效果 */
        --waline-box-shadow: none;
      }

      /* 暗黑模式，根据用户设置 ↓ */
      html[class="scroll-smooth dark"]{
        /* 这是用于表示白色的CSS变量, 在暗模式下，白色将变为黑色*/
        --waline-white: #000;
         /* 浅灰色的CSS变量, 在暗模式下，变为深灰色 */
        --waline-light-grey: #999;
        /* --waline-light-grey: #666;*/
         /* 示深灰色, 在暗模式下，变为浅灰色 */
        --waline-dark-grey: #999;

        /* 一般文本颜色 */
        --waline-color: #c2c2c2;
         /* 背景颜色 */
        --waline-bgcolor: #1E293B;
         /* 较浅的背景颜色 */
        --waline-bgcolor-light: #2A354F;
         /* 边框颜色 */
        --waline-border-color: #666;
         /* 禁用状态的背景颜色 */
        --waline-disable-bgcolor: rgba(68, 68, 68, 0.8);
         /* 禁用状态的文本颜色 */
        --waline-disable-color: #888;

        /* 引用块颜色 */
        --waline-bq-color: #1F2D4B;

        /* 信息块背景颜色 */
        --waline-info-bgcolor: rgba(31, 45, 75, 0.8);
         /* 信息块字体 */
        --waline-info-color: #888;
        /* 信息块的边框 */
        --waline-info-border: 1px solid #d3d3d3;
      }

    </style>


  </body>
```

开启评论
```css
[article]
	showComments = true
```
在博客目录中的 /config/_default/params.toml 文件下, 将 showComments 修改为 true

也可添加在hugo.toml中

