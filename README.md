# web-app-deployment-guide

<h2>Bugungi raqamli davrda veb-ishlab chiqish eng talab qilinadigan ko‘nikmalardan biriga aylandi, va shunday qilib sizlar uchun vebsaytimizni hostinga joylashni sizlar ga o‘rgatmoqchiman qadam ba qadam (ahost.uz, eskiz.uz...)</h2>

<h2>1.Qadam</h2>
<p>Birinchi o‘rinda biz domain va hosting sotib olishimiz kerak bo‘ladi va domainni faol qilamiz, faol qilish uchun Hosting nom serverlaridan foydalanamiz.</p>
<br />
<img width="1429" alt="mainserver" src="https://github.com/Asranov/web-app-deployment-guide/assets/108418860/31939424-97be-4717-942b-65f3755ebeaa">
<br />
<img width="1422" alt="domain" src="https://github.com/Asranov/web-app-deployment-guide/assets/108418860/925deeb9-4ac2-45c9-b241-931438a7aa44">
<br />
<img width="1429" alt="nameserver" src="https://github.com/Asranov/web-app-deployment-guide/assets/108418860/79ab42e7-f35b-45d5-b4c0-5ea4ea8eaff3">
<br />
<p>Bu 24 soat vaqt ichida faol bo‘ladi</p>
<br />
<h2>2.Qadam</h2>
<br />
<p>Loyihamizni build qilib uni zip qilib olamiz</p>
<br />
<img width="962" alt="buildzip" src="https://github.com/Asranov/web-app-deployment-guide/assets/108418860/3e0dd74f-6740-4536-9138-6f6d83b4d83d">
<br />
<h2>3.Qadam</h2>
<p>Build zip ni olib cPanel>FaylMenejeri>public_html ichiga zipdan chiqarib qoyamiz.</p>
<br />
<img width="1436" alt="cpanel" src="https://github.com/Asranov/web-app-deployment-guide/assets/108418860/1a8d0ae7-561d-4bb1-ae61-e90a2c692b99">
<br />
<img width="1433" alt="managerfiles" src="https://github.com/Asranov/web-app-deployment-guide/assets/108418860/8d1fdeca-42e8-4a06-86cd-41e8a531f2a6">
<br />
<h2>4.Qadam</h2>
<p>Bilamiz buni ozini joylaganimiz bilan boshqa sahifaga otsak 404 ya’ni not found qaytaradi (React, Vue xa Angular) buni fix qilish uchun public_html folder ichida birgina file yaratib ichiga ushbu kodni yozib qo‘ysak kifoya</p>
<br />
<p>.htaccess file yaratib olamiz</p>
<p>
&lt;IfModule mod_rewrite.c&gt; <br />
    RewriteEngine On <br />
    RewriteBase / <br />
    RewriteRule ^index\.html$ - [L] <br />
    RewriteCond %{REQUEST_FILENAME} !-f <br />
    RewriteCond %{REQUEST_FILENAME} !-d <br />
    RewriteRule . /index.html [L] <br />
&lt;/IfModule&gt; <br />
</p>

