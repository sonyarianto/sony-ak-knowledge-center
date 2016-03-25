```php
// content
$xPathQuery = $xPathDoc->query("(//div[@class='detail']//div[@class='page']//div[@class='tru'])[1]");

// reconstructing all nodes become content data
$innerHtml = "";
$arrInnerHtml = array();
foreach($xPathQuery as $eachNode) {
  foreach($eachNode->childNodes as $eachNodeItem) {
    $tmpDoc = new DOMDocument();
    $tmpDoc->appendChild($tmpDoc->importNode($eachNodeItem, true));
    $innerHtml .= $tmpDoc->saveHTML();
  }
  $arrInnerHtml[] = $innerHtml;
  $innerHtml = "";
}
$innerHtml = trim(implode("", $arrInnerHtml));
$newsContent = $innerHtml;

// filtering phase
@$xmlDoc->loadHTML($newsContent);
$domNodeList = $xmlDoc->getElementsByTagname('*');
$domElemsToRemove = array();
foreach ($domNodeList as $domElement) {
  if($domElement->nodeName == 'div' && $domElement->getAttribute('class') == 'related') {
    $domElemsToRemove[] = $domElement;
  }
}
foreach($domElemsToRemove as $domElement){
  $domElement->parentNode->removeChild($domElement);
}
$newsContent = $xmlDoc->saveHTML();

// cleaning up phase
$newsContent = preg_replace('~<(?:!DOCTYPE|/?(?:html|body))[^>]*>\s*~i', '', $newsContent);
$newsContent = trim(str_replace (array("\r\n", "\n", "\r"), '', $newsContent));

// custom cleaning up phase
$newsContent = preg_replace('#<a.*?>(.*?)</a>#i', '\1', $newsContent); // remove hyperlinks
```
