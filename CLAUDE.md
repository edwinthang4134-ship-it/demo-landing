## 网址
- 网站：https://demo-landing-flax.vercel.app
- GitHub：https://github.com/edwinthang4134-ship-it/demo-landing

## 做什么
示范用的「周末手冲咖啡入门班」landing page（文字和 WhatsApp 号码都是示范）。

## 我的资料
- 文件夹名：demo-landing
- 放上网的方式：GitHub + Vercel
- WhatsApp 号码：60123456789（示范号码，真的要用之前要换）

## 上线
- 放上网的方式：GitHub + Vercel。GitHub 仓库已接到 Vercel，push 到 main 就自动部署
- 我说「上线」= git add -A、git commit（一句话写改了什么）、git push；Vercel 自己部署
- 「撤回」= 用 git log 列最近几次改动给我看，问我撤回哪一次；我说了再 git revert 那一次，然后 push。永远不要 git reset --hard
- 我没说「上线」不要 push
- CLAUDE.md 和 .claude/ 在 .vercelignore 里，不能放上网

## 规矩
- landing page 是 index.html，后台是 admin.html；CSS 和 JS 都写在各自的文件里；图片放在 images/
- 不用框架、不用 npm；外部库只能用 CDN，目前只允许 supabase-js 和 lucide
- 密码、secret key、service_role key 不要叫我贴进对话
- 改东西：先用一句话说要改哪里，改完用一句话说动了什么；要删文件、要跑 rm，先问我

## 后台
- 后台网址：正式网址 + /admin.html（有 noindex）。Supabase 项目：demo-landing（ref fmczytzsalhibhhftbbu，Singapore）
- 谁看得到什么：
  - 没登录的人（anon）：只能往 signups 新增 name、phone，不能读、不能改、不能删
  - 登录的人：email 在 admins 表里，才能读 signups，才能改 status 和 notes
  - 谁都不能删（没有给 delete）
- grant 和 policy：signups 先 revoke all（anon、authenticated），anon 只 grant insert (name, phone) + 一条 insert policy；authenticated 只 grant select 和 update (status, notes)，policy 都要求 email 在 admins 里。admins 表：authenticated 只能 select 自己那一行
- status 只准：新进来、联络了、成交、没兴趣
- index.html 的 createClient 一直要有 auth: { persistSession: false, autoRefreshToken: false }（不然登录过后台的浏览器，报名会被拒绝）；admin.html 不加（它要记住登录）
- 改数据库只能加、不能删：不 drop、不 delete、不 truncate
- 加员工：我在 Supabase 建好他的账号（Authentication → Users，Auto confirm），跟你说 email；你确认他 confirmed 了，再把 email（小写）加进 admins
- Authentication 里的「Allow new users to sign up」一直关着
- 后台跳去 WhatsApp：0 开头的号码，0 换成 60
