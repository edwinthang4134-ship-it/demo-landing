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
- landing page 是 index.html，CSS 和 JS 写在里面；图片放在 images/
- 不用框架、不用 npm；外部库只能用 CDN，目前只允许 supabase-js 和 lucide
- 密码、secret key、service_role key 不要叫我贴进对话
- 改东西：先用一句话说要改哪里，改完用一句话说动了什么；要删文件、要跑 rm，先问我
