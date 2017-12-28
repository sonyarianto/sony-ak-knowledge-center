You are dealing with namespace.

On the header of XML usually there is like below.

```xml
xmlns:content="http://purl.org/rss/1.0/modules/content/"
```

On XML document usually there is like below and later you want to get url value from below data.

```xml
<content:encoded><![CDATA[<img width="220" height="220" src="http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028-220x220.jpg" class="attachment-thumbnail size-thumbnail wp-post-image" alt="" style="float:left; margin:0 15px 15px 0;" srcset="http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028-220x220.jpg 220w, http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028-150x150.jpg 150w" sizes="(max-width: 220px) 100vw, 220px" /><p><img class="aligncenter size-full wp-image-96280" src="http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028.jpg" alt="" width="800" height="423" srcset="http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028.jpg 800w, http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028-300x159.jpg 300w, http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028-768x406.jpg 768w, http://simamaung.com/wp-content/uploads/2017/12/LATIHAN-UNY-H6_171228_0028-940x498.jpg 940w" sizes="(max-width: 800px) 100vw, 800px" />Persib Bandung dipastikan akan memakai 4 kiper untuk menghadapi kompetisi musim 2018 mendatang. Tambahan tenaga baru hadir dari sosok Aqil Savik yang dipromosikan ke tim senior dari tim U-19. Masih berusia muda, Anwar Sanusi selaku pelatih kiper tak ingin memberikan beban terlalu banyak pada Aqil di musim debutnya.</p>
<p>&#8220;Kiper muda (Aqil) kalau saya engga terlalu (berekspektasi) lah yang penting dia cepat aja beradaptasi dengan senior-seniornya,&#8221; jelas pria yang akrab disapa Away itu ketika diwawancara seusai mengawasi latihan di UNY Fitness Center, Kamis (28/12).</p>
<p>Baginya yang terpenting saat ini Aqil bisa cepat menyatu dengan pemain lain terutama sesama kiper. Karena biasanya pemain belia kerap lambat beradaptasi karena merasa minder ketika bersanding dengan pemain yang senior. Away juga berharap kiper timnas U-19 ini bisa menyerap ilmu dari I Made Wirawan dan kolega.</p>
<p>&#8220;Itu biasanya jadi faktor sulit yang dialami pemain muda untuk beradaptasi dengan senior ada sungkan atau apa tapi sejauh ini berjalan oke sih,&#8221; terang mantan kiper Persib era Perserikatan tersebut.</p>
<p>Aqil sendiri mendapat kepercayaan dari Away mengawal gawang tim Maung Bandung saat bertanding melawan UNY FC dua hari yang lalu. Sayang dia kurang teruji karena minim ancaman dari pemain lawan. Selain itu cuaca yang tidak mendukung membuat laga dihentikan di menit 38 saja.</p>
]]></content:encoded>
```

In PHP you can do this.

```php
$content 	= $eachXpathElement->getElementsByTagNameNS('http://purl.org/rss/1.0/modules/content/', 'encoded')->item(0)->nodeValue;
```
