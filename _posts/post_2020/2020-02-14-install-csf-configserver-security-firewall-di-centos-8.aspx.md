---
title: 'Install CSF (ConfigServer Security & Firewall) di CentOS 8'
author: Dzubayyan Ahmad
type: post
date: 2020-02-14T16:43:36+00:00
url: /install-csf-configserver-security-firewall-di-centos-8.aspx
tags:
  - All
  - linux
  - Tutorial

---
<h1 id="Install-CSF-ConfigServer-Security-amp-Firewall-di-CentOS-8" class="part" data-startline="1" data-endline="1">
  Install CSF (ConfigServer Security & Firewall) di CentOS 8
</h1>

<p class="part" data-startline="3" data-endline="3">
  Halo semua, Server perlu sebuah keamanan atau sebuah firewall. Nah kali ini kita akan membahas mengenai yang namanya CSF atau ConfigServer Security & Firewall. Untuk CSF ini seringkali di terapkan di web hosting, selain itu cocok juga untuk sebuah keamanan server dan website. Karena di CSF akan memblock sebuah serangan bertubi-tubi dan tidak memberikan akses kembali.
</p>

<p class="part" data-startline="5" data-endline="5">
  CSF (ConfigServer Security & Firewall) ini salah satu sistem keamanan yang baik dan sangat apik. Selain itu juga CSF sangat mudah di operasikan. CSF adalah firewall Statefull Packet Inspection (SPI) yang berbasis OpenSource, Selain itu CSF juga bisa di gunakan aplikasi keamanan Login / Intrusion Detection Security untuk server.
</p>

<h2 id="Feature-CSF-ConfigServer-Security-amp-Firewall" class="part" data-startline="7" data-endline="7">
  Feature CSF (ConfigServer Security & Firewall)
</h2>

<p class="part" data-startline="8" data-endline="8">
  Dan untuk CSF itu sendiri mempunyai fitur. Dan kurang lebih feature dari CSF seperti ini :
</p>

<ul class="part" data-startline="9" data-endline="21">
  <li class="" data-startline="9" data-endline="9">
    Daemon process untuk mengecheck kegagalan login SSH, IMAP, SMTP, POP3, FTP, htpassword, dan masih banyak lagi.
  </li>
  <li class="" data-startline="10" data-endline="10">
    Kemampuan memblock koneksi.
  </li>
  <li class="" data-startline="11" data-endline="11">
    Proteksi paket BOGON
  </li>
  <li class="" data-startline="12" data-endline="12">
    SYN Flood protection
  </li>
  <li class="" data-startline="13" data-endline="13">
    Directory and file watching
  </li>
  <li class="" data-startline="14" data-endline="14">
    IDS (Intrusion Detection System)
  </li>
  <li class="" data-startline="15" data-endline="15">
    DDOS Protection
  </li>
  <li class="" data-startline="16" data-endline="16">
    Ping of Death Protection
  </li>
  <li class="" data-startline="17" data-endline="17">
    Port scan tracking and blocking
  </li>
  <li class="" data-startline="18" data-endline="18">
    Port Flooding Detection
  </li>
  <li class="" data-startline="19" data-endline="19">
    IPv6 Support with ip6tables
  </li>
  <li class="" data-startline="20" data-endline="21">
    Integrated with the CloudFlare Firewall
  </li>
</ul>

<h2 id="Install-CSF-ConfigServer-Security-amp-Firewall-di-CentOS-81" class="part" data-startline="22" data-endline="22">
  Install CSF (ConfigServer Security & Firewall) di CentOS 8
</h2>

<p class="part" data-startline="24" data-endline="24">
  Jika di dalam server tersebut tidak sedang menjalankan service yang sangat critical atau sedang tidak menjadi server produksi, teman-teman bisa upgrade package yang terinstall kemudian reboot server nya.
</p>

<p class="part" data-startline="26" data-endline="26">
  Pastikan masuk menggunakan user <code>root</code> untuk root biasanya diberi simbol <code>#</code>
</p>

<ol class="part" data-startline="28" data-endline="29">
  <li class="" data-startline="28" data-endline="29">
    Jika sudah masuk menggunakan akun <code>root</code> silahkan teman-teman upgrade dan install package depency nya. Lalu reboot.
  </li>
</ol>

<pre class="part" data-startline="30" data-endline="32"><code class="shell=bash hljs">&lt;span class="hljs-attribute">yum&lt;/span> upgrade -y 
</code></pre>

<p class="part" data-startline="33" data-endline="33">
  install depency
</p>

<pre class="part" data-startline="34" data-endline="36"><code class="shell=bash hljs">yum &lt;span class="hljs-keyword">install&lt;/span> perl-libwww-perl net-tools perl-LWP-Protocol-https -y
</code></pre>

<p class="part" data-startline="37" data-endline="37">
  dan reboot
</p>

<pre class="part" data-startline="38" data-endline="40"><code class="bash=shell hljs">&lt;span class="hljs-attribute">reboot&lt;/span>
</code></pre>

<ol class="part" start="2" data-startline="41" data-endline="41">
  <li class="" data-startline="41" data-endline="41">
    Jika sudah selesai upgrade package, install package <code>@perl</code>
  </li>
</ol>

<pre class="part" data-startline="42" data-endline="44"><code class="shell=bash hljs">&lt;span class="hljs-attribute">yum&lt;/span> install &lt;span class="hljs-variable">@perl&lt;/span> -y
</code></pre>

<ol class="part" start="3" data-startline="45" data-endline="45">
  <li class="" data-startline="45" data-endline="45">
    Kemudian check versi perl nya
  </li>
</ol>

<pre class="part" data-startline="46" data-endline="60"><code class="shell=bash hljs">[root@venus ~]&lt;span class="hljs-comment"># perl -v&lt;/span>

This &lt;span class="hljs-keyword">is&lt;/span> perl &lt;span class="hljs-number">5&lt;/span>, version &lt;span class="hljs-number">26&lt;/span>, subversion &lt;span class="hljs-number">3&lt;/span> (v5&lt;span class="hljs-number">.26&lt;/span>&lt;span class="hljs-number">.3&lt;/span>) built &lt;span class="hljs-keyword">for&lt;/span> x86_64-linux-thread-multi
(with &lt;span class="hljs-number">51&lt;/span> registered patches, see perl -V &lt;span class="hljs-keyword">for&lt;/span> more detail)

Copyright &lt;span class="hljs-number">1987&lt;/span>&lt;span class="hljs-number">-2018&lt;/span>, Larry Wall

Perl may be copied only under the terms &lt;span class="hljs-keyword">of&lt;/span> either the Artistic License &lt;span class="hljs-keyword">or&lt;/span> the
GNU General Public License, which may be found &lt;span class="hljs-keyword">in&lt;/span> the Perl &lt;span class="hljs-number">5&lt;/span> source kit.

Complete documentation &lt;span class="hljs-keyword">for&lt;/span> Perl, including FAQ lists, should be found &lt;span class="hljs-literal">on&lt;/span>
&lt;span class="hljs-keyword">this&lt;/span> system using &lt;span class="hljs-string">"man perl"&lt;/span> &lt;span class="hljs-keyword">or&lt;/span> &lt;span class="hljs-string">"perldoc perl"&lt;/span>.  If you have access to the
Internet, point your browser at http:&lt;span class="hljs-regexp">//&lt;/span>www.perl.org/, the Perl Home Page.
</code></pre>

<ol class="part" start="4" data-startline="61" data-endline="61">
  <li class="" data-startline="61" data-endline="61">
    Setelah selesai instalasi package <code>perl</code> selanjutnya adalah mendownload file instalasi CSF.
  </li>
</ol>

<pre class="part" data-startline="62" data-endline="64"><code class="bash=shell hljs">&lt;span class="hljs-attribute">curl&lt;/span> -SL https://download.configserver.com/csf.tgz | tar -xzf -
</code></pre>

<ol class="part" start="5" data-startline="65" data-endline="65">
  <li class="" data-startline="65" data-endline="65">
    Masuk ke directory yang barusaja di download. Yaitu directory <code>csf</code>
  </li>
</ol>

<pre class="part" data-startline="66" data-endline="68"><code class="bash=shell hljs">&lt;span class="hljs-built_in">cd&lt;/span> csf
</code></pre>

<ol class="part" start="6" data-startline="69" data-endline="69">
  <li class="" data-startline="69" data-endline="69">
    Jalankan installer. Untuk instalasi CSF ini akan berjalan secara otomatis menggunakan script tersebut.
  </li>
</ol>

<pre class="part" data-startline="70" data-endline="72"><code class="bash=shell hljs">&lt;span class="hljs-selector-tag">sh&lt;/span> &lt;span class="hljs-selector-tag">install&lt;/span>&lt;span class="hljs-selector-class">.sh&lt;/span>
</code></pre>

<ol class="part" start="7" data-startline="73" data-endline="73">
  <li class="" data-startline="73" data-endline="73">
    Jika sudah selesai akan muncul tulisan
  </li>
</ol>

<pre class="part" data-startline="74" data-endline="76"><code>Installation Completed
</code></pre>

<ol class="part" start="8" data-startline="77" data-endline="77">
  <li class="" data-startline="77" data-endline="77">
    Dan selanjutnya melakukan test instalasi, dengan menjalankan command
  </li>
</ol>

<pre class="part" data-startline="78" data-endline="80"><code>perl /usr/local/csf/bin/csftest.pl
</code></pre>

<ol class="part" start="9" data-startline="81" data-endline="81">
  <li class="" data-startline="81" data-endline="81">
    Dan akan muncul tampilan kurang lebih seperti ini :
  </li>
</ol>

<pre class="part" data-startline="82" data-endline="97"><code>[root@venus ~]# perl /usr/local/csf/bin/csftest.pl
Testing ip_tables/iptable_filter...OK
Testing ipt_LOG...OK
Testing ipt_multiport/xt_multiport...OK
Testing ipt_REJECT...OK
Testing ipt_state/xt_state...OK
Testing ipt_limit/xt_limit...OK
Testing ipt_recent...OK
Testing xt_connlimit...OK
Testing ipt_owner/xt_owner...OK
Testing iptable_nat/ipt_REDIRECT...OK
Testing iptable_nat/ipt_DNAT...OK

RESULT: csf should function on this server
</code></pre>

<h2 id="Konfigurasi-dan-Start-CSF-di-CentOS-8" class="part" data-startline="99" data-endline="99">
  Konfigurasi dan Start CSF di CentOS 8
</h2>

<p class="part" data-startline="100" data-endline="101">
  Setelah menginstall CSF di server selanjutnya mengkonfigurasi. Untuk konfigurasi utama ada di <code>/etc/csf/csf.conf</code>. Edit file tersebut untuk memodifikasi rule dari firewall. Untuk melihat TCP dan UDP port yang di ijinkan bisa di check dibawah ini.<br /> <img decoding="async" class="" src="https://i.imgur.com/o61bvAz.png" alt="" />
</p>

<p class="part" data-startline="103" data-endline="103">
  Selanjutnya adalah mendisable mode testing, Untuk mendisablenya bisa menggunakan command berikut ini.
</p>

<pre class="part" data-startline="104" data-endline="106"><code class="shell=bash hljs">perl -&lt;span class="hljs-built_in">pi&lt;/span> -w -e &lt;span class="hljs-string">"s/TESTING = \"1\"/TESTING = \"0\"/"&lt;/span> /etc/csf/csf.conf
</code></pre>

<p class="part" data-startline="108" data-endline="108">
  Selanjutnya mengabaikan IP yang sudah di allow sebelumnya saat testing.
</p>

<pre class="part" data-startline="109" data-endline="111"><code class="shell=bash hljs">perl -&lt;span class="hljs-built_in">pi&lt;/span> -w -e &lt;span class="hljs-string">"s/IGNORE_ALLOW = \"0\"/IGNORE_ALLOW = \"1\"/"&lt;/span> /etc/csf/csf.conf
</code></pre>

<p class="part" data-startline="113" data-endline="113">
  Dan selanjutnya adalah membuat service CSF berjalan setiap booting.
</p>

<pre class="part" data-startline="114" data-endline="116"><code class="shell=bash hljs">systemctl &lt;span class="hljs-built_in">enable&lt;/span> --now csf
</code></pre>

<p class="part" data-startline="117" data-endline="117">
  Dan check apakah service sudah berjalan.
</p>

<pre class="part" data-startline="118" data-endline="136"><code class="shell=bash hljs">[root@venus ~]# systemctl status csf
● csf.service - &lt;span class="hljs-symbol">ConfigServer&lt;/span> &lt;span class="hljs-symbol">Firewall&lt;/span> & &lt;span class="hljs-symbol">Security&lt;/span> - csf
   &lt;span class="hljs-symbol">Loaded&lt;/span>: loaded (/usr/lib/systemd/system/csf.service; enabled; vendor preset: disabled)
   &lt;span class="hljs-symbol">Active&lt;/span>: active (exited) since &lt;span class="hljs-symbol">Fri&lt;/span> &lt;span class="hljs-number">2020&lt;/span>&lt;span class="hljs-number">-02&lt;/span>&lt;span class="hljs-number">-14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> &lt;span class="hljs-symbol">UTC&lt;/span>; &lt;span class="hljs-number">2&lt;/span>min &lt;span class="hljs-number">25&lt;/span>s ago
  &lt;span class="hljs-symbol">Process&lt;/span>: &lt;span class="hljs-number">6927&lt;/span> &lt;span class="hljs-symbol">ExecStart&lt;/span>=/usr/sbin/csf --initup (code=exited, status=&lt;span class="hljs-number">0&lt;/span>/&lt;span class="hljs-symbol">SUCCESS&lt;/span>)
 &lt;span class="hljs-symbol">Main&lt;/span> &lt;span class="hljs-symbol">PID&lt;/span>: &lt;span class="hljs-number">6927&lt;/span> (code=exited, status=&lt;span class="hljs-number">0&lt;/span>/&lt;span class="hljs-symbol">SUCCESS&lt;/span>)

&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">ACCEPT&lt;/span>  all opt    in * out lo  ::/&lt;span class="hljs-number">0&lt;/span>  -&gt; ::/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">LOGDROPOUT&lt;/span>  all opt    in * out !lo  ::/&lt;span class="hljs-number">0&lt;/span>  -&gt; ::/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">LOGDROPIN&lt;/span>  all opt    in !lo out *  ::/&lt;span class="hljs-number">0&lt;/span>  -&gt; ::/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: csf: &lt;span class="hljs-symbol">FASTSTART&lt;/span> loading &lt;span class="hljs-symbol">DNS&lt;/span> (&lt;span class="hljs-symbol">IPv4&lt;/span>)
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: csf: &lt;span class="hljs-symbol">FASTSTART&lt;/span> loading &lt;span class="hljs-symbol">DNS&lt;/span> (&lt;span class="hljs-symbol">IPv6&lt;/span>)
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">LOCALOUTPUT&lt;/span>  all opt -- in * out !lo  &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>  -&gt; &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">LOCALINPUT&lt;/span>  all opt -- in !lo out *  &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>  -&gt; &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">LOCALOUTPUT&lt;/span>  all opt    in * out !lo  ::/&lt;span class="hljs-number">0&lt;/span>  -&gt; ::/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com csf[&lt;span class="hljs-number">6927&lt;/span>]: &lt;span class="hljs-symbol">LOCALINPUT&lt;/span>  all opt    in !lo out *  ::/&lt;span class="hljs-number">0&lt;/span>  -&gt; ::/&lt;span class="hljs-number">0&lt;/span>
&lt;span class="hljs-symbol">Feb&lt;/span> &lt;span class="hljs-number">14&lt;/span> &lt;span class="hljs-number">15&lt;/span>:&lt;span class="hljs-number">20&lt;/span>:&lt;span class="hljs-number">42&lt;/span> venus.masdzub.com systemd[&lt;span class="hljs-number">1&lt;/span>]: &lt;span class="hljs-symbol">Started&lt;/span> &lt;span class="hljs-symbol">ConfigServer&lt;/span> &lt;span class="hljs-symbol">Firewall&lt;/span> & &lt;span class="hljs-symbol">Security&lt;/span> - csf.
</code></pre>

<h2 id="Contoh-penggunaan-CSF" class="part" data-startline="138" data-endline="138">
  Contoh penggunaan CSF
</h2>

<h3 id="Block-IP-atau-subnet" class="part" data-startline="140" data-endline="140">
  Block IP atau subnet
</h3>

<pre class="part" data-startline="141" data-endline="144"><code class="shell=bash hljs">&lt;span class="hljs-attribute">csf&lt;/span> -d &lt;span class="hljs-number">66.254.114.41&lt;/span>
csf -d &lt;span class="hljs-number">66.254.114.0&lt;/span>/&lt;span class="hljs-number">24&lt;/span>
</code></pre>

<p class="part" data-startline="145" data-endline="145">
  dan akan keluar
</p>

<pre class="part" data-startline="146" data-endline="150"><code class="shell=bash hljs">&lt;span class="hljs-attribute">Adding&lt;/span> &lt;span class="hljs-number">66.254.114.41&lt;/span> to csf.deny and iptables DROP…
DROP  all opt -- in !lo out *  &lt;span class="hljs-number">66.254.114.41&lt;/span>  -&gt; &lt;span class="hljs-number">0.0.0.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>  
LOGDROPOUT  all opt -- in * out !lo  &lt;span class="hljs-number">0.0.0.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>  -&gt; &lt;span class="hljs-number">66.254.114.41&lt;/span>
</code></pre>

<h3 id="Menghapus-IP-atau-Subnet-yang-terblock" class="part" data-startline="152" data-endline="152">
  Menghapus IP atau Subnet yang terblock
</h3>

<pre class="part" data-startline="153" data-endline="156"><code class="shell=bash hljs">&lt;span class="hljs-attribute">csf&lt;/span> -dr &lt;span class="hljs-number">66.254.114.41&lt;/span>
csf -dr &lt;span class="hljs-number">66.254.114.0&lt;/span>/&lt;span class="hljs-number">24&lt;/span>
</code></pre>

<p class="part" data-startline="157" data-endline="157">
  akan muncul seperti ini
</p>

<pre class="part" data-startline="158" data-endline="162"><code class="shell=bash hljs">&lt;span class="hljs-attribute">Removing&lt;/span> rule...
DROP  all opt -- in !lo out *  &lt;span class="hljs-number">66.254.114.41&lt;/span>  -&gt; &lt;span class="hljs-number">0.0.0.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>
LOGDROPOUT  all opt -- in * out !lo  &lt;span class="hljs-number">0.0.0.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>  -&gt; &lt;span class="hljs-number">66.254.114.41&lt;/span>
</code></pre>

<h3 id="Menambah-whitelist-IP-di-firewall" class="part" data-startline="163" data-endline="163">
  Menambah whitelist IP di firewall
</h3>

<pre class="part" data-startline="164" data-endline="166"><code class="shell=bash hljs">&lt;span class="hljs-selector-tag">csf&lt;/span> &lt;span class="hljs-selector-tag">-a&lt;/span> 173&lt;span class="hljs-selector-class">.114&lt;/span>&lt;span class="hljs-selector-class">.182&lt;/span>&lt;span class="hljs-selector-class">.163&lt;/span>
</code></pre>

<p class="part" data-startline="167" data-endline="167">
  dan akan muncul seperti ini
</p>

<pre class="part" data-startline="168" data-endline="173"><code class="shell=bash hljs">[root@venus ~]&lt;span class="hljs-comment"># csf -a 173.114.182.163&lt;/span>
Adding &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span> to csf.allow &lt;span class="hljs-keyword">and&lt;/span> iptables ACCEPT...
ACCEPT  all opt -- &lt;span class="hljs-keyword">in&lt;/span> !lo out *  &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span>  -&gt; &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>
ACCEPT  all opt -- &lt;span class="hljs-keyword">in&lt;/span> * out !lo  &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>  -&gt; &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span>
</code></pre>

<h3 id="Mengecheck-IP-terblock--whitelist" class="part" data-startline="174" data-endline="174">
  Mengecheck IP terblock / whitelist
</h3>

<pre class="part" data-startline="175" data-endline="177"><code class="shell=bash hljs">&lt;span class="hljs-selector-tag">csf&lt;/span> &lt;span class="hljs-selector-tag">-g&lt;/span> 173&lt;span class="hljs-selector-class">.114&lt;/span>&lt;span class="hljs-selector-class">.182&lt;/span>&lt;span class="hljs-selector-class">.163&lt;/span>
</code></pre>

<p class="part" data-startline="178" data-endline="178">
  jika terblock akan muncul seperti ini
</p>

<pre class="part" data-startline="179" data-endline="195"><code class="shell=bash hljs">[&lt;span class="hljs-meta">root@venus ~&lt;/span>]&lt;span class="hljs-meta"># csf -g 173.114.182.163&lt;/span>

Table  Chain            num   pkts bytes target     prot opt &lt;span class="hljs-keyword">in&lt;/span>     &lt;span class="hljs-keyword">out&lt;/span>     source               destination

filter DENYIN           &lt;span class="hljs-number">1&lt;/span>        &lt;span class="hljs-number">0&lt;/span>     &lt;span class="hljs-number">0&lt;/span> DROP       all  --  !lo    *       &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span>      &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>

filter DENYOUT          &lt;span class="hljs-number">1&lt;/span>        &lt;span class="hljs-number">0&lt;/span>     &lt;span class="hljs-number">0&lt;/span> LOGDROPOUT  all  --  *      !lo     &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>            &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span>


ip6tables:

Table  Chain            num   pkts bytes target     prot opt &lt;span class="hljs-keyword">in&lt;/span>     &lt;span class="hljs-keyword">out&lt;/span>     source               destination
No matches found &lt;span class="hljs-keyword">for&lt;/span> &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span> &lt;span class="hljs-keyword">in&lt;/span> ip6tables

csf.deny: &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span> &lt;span class="hljs-meta"># Manually denied: 173.114.182.163 (ip-173-114-182-163.anahca.spcsdns.net) - Fri Feb 14 16:30:09 2020&lt;/span>
</code></pre>

<p class="part" data-startline="196" data-endline="196">
  dan jika di whitelist akan seperti ini
</p>

<pre class="part" data-startline="197" data-endline="213"><code class="shell=bash hljs">[&lt;span class="hljs-meta">root@venus ~&lt;/span>]&lt;span class="hljs-meta"># csf -g 173.114.182.163&lt;/span>

Table  Chain            num   pkts bytes target     prot opt &lt;span class="hljs-keyword">in&lt;/span>     &lt;span class="hljs-keyword">out&lt;/span>     source               destination

filter ALLOWIN          &lt;span class="hljs-number">1&lt;/span>        &lt;span class="hljs-number">0&lt;/span>     &lt;span class="hljs-number">0&lt;/span> ACCEPT     all  --  !lo    *       &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span>      &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>

filter ALLOWOUT         &lt;span class="hljs-number">1&lt;/span>        &lt;span class="hljs-number">0&lt;/span>     &lt;span class="hljs-number">0&lt;/span> ACCEPT     all  --  *      !lo     &lt;span class="hljs-number">0.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>&lt;span class="hljs-number">.0&lt;/span>/&lt;span class="hljs-number">0&lt;/span>            &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span>


ip6tables:

Table  Chain            num   pkts bytes target     prot opt &lt;span class="hljs-keyword">in&lt;/span>     &lt;span class="hljs-keyword">out&lt;/span>     source               destination
No matches found &lt;span class="hljs-keyword">for&lt;/span> &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span> &lt;span class="hljs-keyword">in&lt;/span> ip6tables

csf.allow: &lt;span class="hljs-number">173.114&lt;/span>&lt;span class="hljs-number">.182&lt;/span>&lt;span class="hljs-number">.163&lt;/span> &lt;span class="hljs-meta"># Manually allowed: 173.114.182.163 (ip-173-114-182-163.anahca.spcsdns.net) - Fri Feb 14 16:31:41 2020&lt;/span>
</code></pre>

<h2 id="Kesimpulan" class="part" data-startline="215" data-endline="215">
  Kesimpulan
</h2>

<p class="part" data-startline="216" data-endline="216">
  Kurang lebih seperti itulah cara install CSF dan contoh penggunaan dari csf secara singkat. Cukup itu dulu. Jika artikel ini di rasa membantu mohon di bantu untuk di share ke teman lainnya. <img decoding="async" class="emoji" src="https://assets.hackmd.io/build/emojify.js/dist/images/basic/smile.png" alt=":smile:" />
</p>