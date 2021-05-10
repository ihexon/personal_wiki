<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Welcome file</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="简介">简介</h2>
<p><code>REST API</code> 是一组标准化API接口，可通过标准化HTTP请求这些API接口发起对目标系统的探测扫描和漏洞警报。<code>REST API</code>可以帮助开发者在<code>CI/CD</code>环境下自定义一些列自动化测试任务的工作流（pentesting pipeline）。</p>
<p>这一组API提供<code>Java，Python，Shell</code>等编程语言的灵活绑定，从而衍化出多种漏洞证明的<code>Payload</code>。</p>
<p>REST API 拥有一个简单的WEB UI提供开发者进行二次开发，或渗透人员利用移动端设备执行渗透测试。<br>
监听地址 <code>http://localhost:8080</code></p>
<h1 id="main-pages">Main Pages</h1>
<p><a href="http://localhost:2020">http://localhost:2020</a></p>
<h1 id="功能">功能</h1>
<ul>
<li>
<p>Support HTTP/HTTPS</p>
</li>
<li>
<p>WEB Spider</p>
<ul>
<li>Auto Authenticated</li>
<li>Database support</li>
</ul>
</li>
<li>
<p>Ajax Spider</p>
<ul>
<li>Auto Authenticated</li>
<li>Database support</li>
</ul>
</li>
<li>
<p>目录穷举</p>
<ul>
<li>Using Custom Payload</li>
</ul>
</li>
<li>
<p>端口扫描</p>
</li>
<li>
<p>Fuzzer</p>
<ul>
<li>Auto Authenticated</li>
<li>Using Custom Payload</li>
</ul>
</li>
<li>
<p>拦截/修改/重放请求</p>
<ul>
<li>Replacer</li>
</ul>
</li>
<li>
<p>Active Scanner</p>
<ul>
<li>Auto Authenticated</li>
</ul>
</li>
<li>
<p>Using third-part Script</p>
<ul>
<li>Javascript</li>
<li>Python</li>
<li>Java</li>
</ul>
</li>
</ul>
<h1 id="设置代理">设置代理</h1>
<h1 id="主动扫描">主动扫描</h1>
<p>主动扫描能主动探测系统弱点，主动探测会向目标自动发送恶意请求，并分析目标响应，自动报告弱点：</p>
<h2 id="新建主动扫描">新建主动扫描</h2>
<p><strong>NOTE</strong>:在进行主动扫描之前，目标地址需要被Proxy抓取记录，否则会提示<code>url not found</code></p>
<pre class=" language-bash"><code class="prism  language-bash">curl <span class="token string">'https://localhost:8080/HTML/ascan/action/scan/'</span> \
	-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
	-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	--compressed \
	-H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
	-H <span class="token string">'Origin: null'</span> -H <span class="token string">'Connection: keep-alive'</span> \
	-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
	--data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q&amp;url=http%3A%2F%2F192.168.118.184%3A40001%2Fvulnerabilities%2Fsqli%2F&amp;recurse=&amp;inScopeOnly=&amp;scanPolicyName=&amp;method=&amp;postData=&amp;contextId='</span>



curl <span class="token string">'https://localhost:8080/JSON/ascan/action/scan/'</span> \
	-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
	-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	--compressed \
	-H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
	-H <span class="token string">'Origin: null'</span> \
	-H <span class="token string">'Connection: keep-alive'</span> \
	-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
	--data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q&amp;url=http%3A%2F%2F192.168.118.184%3A40001%2Fvulnerabilities%2Fxss_s%2F&amp;recurse=true&amp;inScopeOnly=&amp;scanPolicyName=&amp;method=&amp;postData=&amp;contextId='</span>

</code></pre>
<h1 id="查询所有主动扫描状态">查询所有主动扫描状态</h1>
<pre class=" language-bash"><code class="prism  language-bash">curl <span class="token string">'https://localhost:8080/JSON/ascan/view/scans/'</span>\
	 -H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	 -H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span>\
	  -H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	  --compressed \
	  -H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
	  -H <span class="token string">'Origin: null'</span> \
	  -H <span class="token string">'Connection: keep-alive'</span> \
	  -H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
	  --data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q'</span>
</code></pre>
<h1 id="停止所有主动扫描">停止所有主动扫描</h1>
<pre class=" language-bash"><code class="prism  language-bash">curl <span class="token string">'https://localhost:8080/JSON/ascan/action/stopAllScans/'</span> \
		-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
		-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
		-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
		--compressed \
		-H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
		-H <span class="token string">'Origin: null'</span> \
		-H <span class="token string">'Connection: keep-alive'</span> \
		-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
		--data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q'</span>
</code></pre>
<h1 id="移除主动扫描记录">移除主动扫描记录</h1>
<pre class=" language-bash"><code class="prism  language-bash">curl <span class="token string">'https://localhost:8080/JSON/ascan/action/removeAllScans/'</span> \
	-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
	-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	--compressed \
	-H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
	-H <span class="token string">'Origin: null'</span> \
	-H <span class="token string">'Connection: keep-alive'</span> \
	-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
	--data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q'</span>
</code></pre>
<h1 id="爬虫">爬虫</h1>
<h2 id="启动爬虫">启动爬虫</h2>
<pre class=" language-bash"><code class="prism  language-bash">curl <span class="token string">'https://localhost:8080/JSON/spider/action/scan/'</span> \
	-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
	-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	--compressed \
	-H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
	-H <span class="token string">'Origin: null'</span> -H <span class="token string">'Connection: keep-alive'</span> \
	-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
	--data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q&amp;url=http%3A%2F%2F192.168.118.184%3A40001&amp;maxChildren=&amp;recurse=&amp;contextName=&amp;subtreeOnly='</span>
</code></pre>
<h2 id="查询爬虫状态：">查询爬虫状态：</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/spider/view/status/
http://localhost:8080/UI/spider/view/scans/ <span class="token comment"># 查询所有状态，包括ID，返回码</span>
</code></pre>
<h2 id="查询爬虫结果：">查询爬虫结果：</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/spider/view/results/
http://localhost:8080/UI/spider/view/fullResults/ <span class="token comment"># 所有结果</span>


curl <span class="token string">'https://localhost:8080/JSON/spider/view/scans/'</span> \
	-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
	-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	--compressed \
	-H <span class="token string">'Content-Type: application/x-www-form-urlencoded'</span> \
	-H <span class="token string">'Origin: null'</span> \
	-H <span class="token string">'Connection: keep-alive'</span> \
	-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span> \
	--data-raw <span class="token string">'apikey=mep260pcu3jbo9949iassvg99q'</span>
</code></pre>
<h2 id="暂停爬虫：">暂停爬虫：</h2>
<pre><code>http://localhost:8080/UI/spider/action/pause/
</code></pre>
<h2 id="继续爬虫">继续爬虫</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/spider/action/resume/
</code></pre>
<h2 id="查询爬虫结果">查询爬虫结果</h2>
<pre class=" language-bash"><code class="prism  language-bash">curl <span class="token string">'https://localhost:8080/JSON/spider/view/fullResults/?apikey=mep260pcu3jbo9949iassvg99q&amp;scanId=0'</span> \
	-H <span class="token string">'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:85.0) Gecko/20100101 Firefox/85.0'</span> \
	-H <span class="token string">'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8'</span> \
	-H <span class="token string">'Accept-Language: en-US,en;q=0.5'</span> \
	--compressed -H <span class="token string">'Connection: keep-alive'</span> \
	-H <span class="token string">'Upgrade-Insecure-Requests: 1'</span>
</code></pre>
<h1 id="监控访问历史">监控访问历史</h1>
<h2 id="简单查询">简单查询</h2>
<p>查询主机历史记录</p>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/core/view/hosts/
http://localhost:8080/UI/core/view/sites/
</code></pre>
<h2 id="查询指定主机下的访问记录">查询指定主机下的访问记录:</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/core/view/urls/
</code></pre>
<h2 id="复杂查询">复杂查询</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/core/view/message/
</code></pre>
<p>根据HISTORY表的HISTORYID字段查询，详细到查询<code>responseBody/requestBody/responseHeader/requestHeader/</code>时间戳/RTT(Round Trip Time)值，并以JSON数据格式返回。</p>
<h2 id="查询访问数量">查询访问数量</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/core/view/numberOfMessages/
</code></pre>
<h2 id="全局请求响应查询">全局请求/响应查询</h2>
<pre class=" language-bash"><code class="prism  language-bash">https://localhost:8080/UI/search/
</code></pre>
<h1 id="系统查询">系统查询</h1>
<h2 id="版本查询">版本查询</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/core/view/version/
</code></pre>
<h2 id="查询sql数据库位置">查询SQL数据库位置</h2>
<pre class=" language-bash"><code class="prism  language-bash">http://localhost:8080/UI/core/view/sessionLocation/
</code></pre>
<h1 id="replacer">Replacer</h1>
<p>实时替换网页内容</p>
<p>地址：</p>
<pre class=" language-xml"><code class="prism  language-xml">http://localhost:8080/UI/replacer
</code></pre>
<p>curl请求：</p>
<pre class=" language-json"><code class="prism  language-json">matchType	<span class="token string">"RESP_BODY_STR"</span>
description	<span class="token string">"Test"</span>
matchString	<span class="token string">"Welcome to Damn Vulnerable Web Application!"</span>
initiators	<span class="token string">""</span>
matchRegex	<span class="token string">"true"</span>
replacement	<span class="token string">"ZZH"</span>
enabled	<span class="token string">"true"</span>
</code></pre>
<h1 id="report">Report</h1>
<h2 id="生成报告：">生成报告：</h2>
<p>支持HTML, Markdown, JSON, XML格式报告</p>
<pre><code>http://localhost:8080/UI/core/other/htmlreport
http://localhost:8080/UI/core/other/mdreport/
http://localhost:8080/UI/core/other/jsonreport/
http://localhost:8080/UI/core/other/xmlreport/
``` 厌 世 仔 的 网 抑 云 API
---


 搜索关键词

</code></pre>
</div>
</body>

</html>
