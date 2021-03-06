---
extensions:
  preset: gfm
title: Lolcat-as-a-Service (LaaS)

---

<h1 id="lolcat-as-a-service-laas">Lolcat-as-a-Service (LaaS)</h1>
<p>An API to lolcat (and figlet, cowsay etc. coming soon!) your text.</p>

<table>
<thead>
<tr>
<th><a href="https://github.com/lxhom/lolcat-as-a-service">Source code</a></th>
<th><a href="https://deta.sh">Hoster</a></th>
<th><a href="https://laas.cf/lolcat?html=true&amp;freq=0.1&amp;text=%20____________________________________________%20%0A/%20%20_%20%20%20%20%20%20%20%20%20%20_%20%20%20%20%20%20%20%20%20%20%20_%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%5C%0A%7C%20%7C%20%7C%20%20%20%20___%20%7C%20%7C%20___%20__%20_%7C%20%7C_%20%20%20%20__%20_%20___%20%20%20%20%7C%0A%7C%20%7C%20%7C%20%20%20/%20_%20%5C%7C%20%7C/%20__/%20_%60%20%7C%20__%7C%20%20/%20_%60%20/%20__%7C%20%20%20%7C%0A%7C%20%7C%20%7C__%7C%20%28_%29%20%7C%20%7C%20%28_%7C%20%28_%7C%20%7C%20%7C_%20%20%7C%20%28_%7C%20%5C__%20%5C%20%20%20%7C%0A%7C%20%7C_____%5C___/%7C_%7C%5C___%5C__%2C_%7C%5C__%7C%20%20%5C__%2C_%7C___/%20%20%20%7C%0A%7C%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7C%0A%7C%20%20%20%20%20%20%20%20%20%20____%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20_%20%20%20%20%20%20%20%20%20%20%20%7C%0A%7C%20%20%20__%20_%20%20/%20___%7C%20%20___%20_%20____%20%20%20_%28_%29%20___%20___%20%20%7C%0A%7C%20%20/%20_%60%20%7C%20%5C___%20%5C%20/%20_%20%5C%20%27__%5C%20%5C%20/%20/%20%7C/%20__/%20_%20%5C%20%7C%0A%7C%20%7C%20%28_%7C%20%7C%20%20___%29%20%7C%20%20__/%20%7C%20%20%20%5C%20V%20/%7C%20%7C%20%28_%7C%20%20__/%20%7C%0A%7C%20%20%5C__%2C_%7C%20%7C____/%20%5C___%7C_%7C%20%20%20%20%5C_/%20%7C_%7C%5C___%5C___%7C%20%7C%0A%5C%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20/%0A%20--------------------------------------------%20%0A%20%20%20%20%20%20%20%20%5C%20%20%20%5E__%5E%0A%20%20%20%20%20%20%20%20%20%5C%20%20%28oo%29%5C_______%0A%20%20%20%20%20%20%20%20%20%20%20%20%28__%29%5C%20%20%20%20%20%20%20%29%5C/%5C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7C%7C----w%20%7C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7C%7C%20%20%20%20%20%7C%7C%0A">Example request</a></th>
</tr>
</thead>
<tbody></tbody>
</table><blockquote>
<p>Note for cURL users: Use <a href="https://laas.cf">https://laas.cf</a> instead of <a href="https://LaaS.cf">https://LaaS.cf</a> when using cURL because <a href="https://deta.sh">Deta, the provider that hosts this service for free</a> doesn't recognize uppercase URL's and cURL sends the domain in uppercase if you type it in uppercase, unlike browsers like Chrome.</p>
</blockquote>
<h2 id="lolcat">Lolcat</h2>
<h3 id="query-parameters">Query parameters:</h3>

<table>
<thead>
<tr>
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Effect</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr>
<td>spread</td>
<td>No</td>
<td>float</td>
<td>Inclination of the rainbow stripes (character widths per line height. High values (&gt;1000) give almost horizontal stripes, low values (0.1) almost vertical ones)</td>
<td>8.0</td>
</tr>
<tr>
<td>freq</td>
<td>No</td>
<td>float</td>
<td>Frequency of the rainbow (low values around  0.0001 give almost monochrome screens)</td>
<td>0.3</td>
</tr>
<tr>
<td>html</td>
<td>No</td>
<td>boolean</td>
<td>Use HTML tags instead of ANSI escape codes</td>
<td>false</td>
</tr>
<tr>
<td>text</td>
<td><kbd>GET</kbd> only</td>
<td>string</td>
<td>Text to lolcat</td>
<td><kbd>POST</kbd> body</td>
</tr>
</tbody>
</table><h3 id="kbdpostkbd-"><kbd>POST</kbd> <code>/</code></h3>
<p>Alias for <code>/lolcat</code>. Use this endpoint with a text post body to lolcat the text. Example:</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -d "$(fortune)" https://laas.cf  
</code></pre>
<h3 id="kbdpostgetkbd-lolcat"><kbd>POST/GET</kbd> <code>/lolcat</code></h3>
<p>Use this endpoint with a text post body or the <code>text</code> parameter to lolcat the text. Example:</p>
<pre class=" language-shell"><code class="prism  language-shell">curl -d "$(fortune)" https://laas.cf/lolcat # or  
curl "https://laas.cf/lolcat?text=$(fortune | urlencode)"  
</code></pre>

