Security
========

DNS Over HTTPS
--------------

Rationale
~~~~~~~~~

   정부가 HTTPS 암호화통신이 적용돼 기존 URL 차단방식을 쓸 수 없는 해외
   불법사이트를 차단할 다른 방식을 찾아나섰다. 당장 필요시 제한적으로
   도메인네임서비스(DNS) 차단방식을 적용하고, HTTPS 접속시에도 평문으로
   노출되는 서버이름표시(SNI) 확장필드 값을 들여다보고 차단하는 방식을
   내년까지 개발한다는 구상이다.

http://www.zdnet.co.kr/news/news_view.asp?artice_id=20180504183255

Mac OS X
~~~~~~~~

   Here’s how to use it with DNS-over-HTTPS on OS X / MacOS:

   ::

      brew install dnscrypt-proxy

   Change line 25 in ``/usr/local/etc/dnscrypt-proxy.toml`` to
   ``server_names = ['cloudflare']``

   ::

      sudo brew services restart dnscrypt-proxy

   Then change your DNS server to ``127.0.0.1``.

https://news.ycombinator.com/item?id=16729705

Firefox
~~~~~~~

https://www.ghacks.net/2018/04/02/configure-dns-over-https-in-firefox/

Windows
~~~~~~~

https://simplednscrypt.org

iOS
~~~

https://itunes.apple.com/us/app/dnscloak-dnscrypt-doh-client/id1330471557?mt=8

Android
~~~~~~~

https://play.google.com/store/apps/details?id=app.intra

Other
~~~~~

https://github.com/jedisct1/dnscrypt-proxy

Test
~~~~

https://dnsleaktest.com
