I have scenario like this. I have PHP 7.2 on my system and I have source code (Symfony running on version 2.3) with PHP 5.6.

I delete `vendor` folder on Symfony and try to rebuild with `composer -vvv update`. I got error after that.

Solution is to add this on `composer.json`

```yml
"config": {
  "platform": {
    "php": "5.6"
  }
}
```

Then run `composer -vvv update` again. That's should work.
