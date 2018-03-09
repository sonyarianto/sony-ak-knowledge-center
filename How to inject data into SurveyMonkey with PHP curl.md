```php
<?php
	function getPart($name, $value, $boundary)
	{
	  $eol = "\r\n";

	  $part = '--'. $boundary . $eol;
	  $part .= 'Content-Disposition: form-data; name="' . $name . '"' . $eol;
	  $part .= 'Content-Length: ' . strlen($value) . $eol . $eol;
	  $part .= $value . $eol;

	  return $part;
	}

	function getBody($boundary, $survey_data)
	{
	  $eol = "\r\n";

	  $body = getPart('this_is_name_of_input_1', "Question Answer 1", $boundary);
	  $body .= getPart('this_is_name_of_input_2', 'Question Answer 2' , $boundary);
	  $body .= getPart('this_is_name_of_input_3', 'Question Answer 3' , $boundary);
    $body .= getPart('survey_data', $survey_data , $boundary);
	  $body .= '--'. $boundary . '--' . $eol;

	  return $body;
	}

	$surveyUrl = "THIS_IS_THE_SURVEY_URL";

	// get the hidden key for the survey
	$curl = curl_init();
	curl_setopt($curl, CURLOPT_URL, $surveyUrl);
	curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($curl, CURLOPT_ENCODING, "");
	curl_setopt($curl, CURLOPT_CONNECTTIMEOUT, 10);
	curl_setopt($curl, CURLOPT_TIMEOUT, 30);
	curl_setopt($curl, CURLOPT_FOLLOWLOCATION, 1);
	curl_setopt($curl, CURLOPT_IPRESOLVE, CURL_IPRESOLVE_V4);
	curl_setopt($curl, CURLOPT_USERAGENT, "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.12; rv:53.0) Gecko/20100101 Firefox/53.0");
	$curlData = curl_exec($curl);
	curl_close($curl);

	$surveyData = substr($curlData, strpos($curlData, '<input type="hidden" id="survey_data" name="survey_data" value="'));
	$surveyData = substr($surveyData, strpos($surveyData, 'value="') + 7);
	$surveyData = substr($surveyData, 0, strpos($surveyData, '"'));

	// do post to survey
	$boundary = '---------------' . md5(time());

	$curl = curl_init();
	curl_setopt($curl, CURLOPT_URL, $surveyUrl);
	curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
	curl_setopt($curl, CURLOPT_ENCODING, "");
	curl_setopt($curl, CURLOPT_CONNECTTIMEOUT, 10);
	curl_setopt($curl, CURLOPT_TIMEOUT, 30);
	curl_setopt($curl, CURLOPT_CUSTOMREQUEST, 'POST');
	curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type: multipart/form-data; boundary=' . $boundary));
	curl_setopt($curl, CURLOPT_FOLLOWLOCATION, 1);
	curl_setopt($curl, CURLOPT_IPRESOLVE, CURL_IPRESOLVE_V4);
	curl_setopt($curl, CURLOPT_POSTFIELDS, getBody($boundary, $surveyData));
	curl_setopt($curl, CURLOPT_USERAGENT, "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.12; rv:53.0) Gecko/20100101 Firefox/53.0");
	$curlData = curl_exec($curl);
	curl_close($curl);

	echo "Now look on your SurveyMonkey dashboard, the data should be there.";
```
