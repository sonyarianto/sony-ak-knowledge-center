The situation like below.

```php
$str = <<<'EOD'
<description><![CDATA[
	<div>
	<a href="http://www.something.com" title="timnas indonesia senior kalah filipina sergio van dijk"><img title="timnas indonesia senior kalah filipina sergio van dijk" src="http://www.something.com/myimage.jpg" alt="Filipina Diharapkan Tembus Final AFF Cup 2016" width="200" height="125" /></a>
	</div>
	<br/>
	Tim nasional Filipina diharapkan mampu menembus final AFF Cup 2016 mendatang. Edisi tahun ini dianggap sebagai kesempatan emas bagi The Azkals untuk meraih prestasi terbaik di Piala AFF 2016 karena bertindak sebagai tuan rumah dan memiliki skuat yang cukup mumpuni. &#8220;Dalam situasi sekarang, sangat penting bagi mereka untuk terus bersama-sama sebagai sebuah tim dan menyelesaikan [&#8230;]]]></description>
EOD;

preg_match('/<\s*?img\s+[^>]*?\s*src\s*=\s*(["\'])((\\\\?+.)*?)\1[^>]*?>/', $str, $matches);

var_dump($matches);
```
