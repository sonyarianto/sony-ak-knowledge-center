```php
// content
$xPathQuery = $xPathDoc->query("YOUR_XPATH_QUERY_HERE");

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
$content = $innerHtml;

// filtering phase
@$xmlDoc->loadHTML($content);
$domNodeList = $xmlDoc->getElementsByTagname('*');
$domElemsToRemove = array();
foreach ($domNodeList as $domElement) {
  if($domElement->nodeName == 'YOUR_TAG_HERE' && $domElement->getAttribute('YOUR_ATTRIBUTE_HERE') == 'YOUR_ATTRIBUTE_VALUE_HERE') {
    $domElemsToRemove[] = $domElement;
  }
}
foreach($domElemsToRemove as $domElement){
  $domElement->parentNode->removeChild($domElement);
}
$content = $xmlDoc->saveHTML();

// cleaning up phase
$content = preg_replace('~<(?:!DOCTYPE|/?(?:html|body))[^>]*>\s*~i', '', $content);
$content = trim(str_replace (array("\r\n", "\n", "\r"), '', $content));

// custom cleaning up phase
$content = preg_replace('#<a.*?>(.*?)</a>#i', '\1', $content); // remove hyperlinks
```
