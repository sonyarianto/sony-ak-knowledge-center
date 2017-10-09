Suppose you have bundle in this structure.

`Developer/PropertyBundle`

Let say in folder `Developer/PropertyBundle/Twig` create file `PropertyExtension.php` and the content like this.

```php
<?php

namespace Developer\PropertyBundle\Twig;

class PropertyExtension extends \Twig_Extension
{
    public function getFilters()
    {
        return array(
            new \Twig_SimpleFilter('page_replace', array($this, 'pageReplaceFilter')),
        );
    }

    public function pageReplaceFilter($source_string, $regex_pattern, $replace_with = NULL)
    {
        $page_replace = preg_replace($regex_pattern, $replace_with, $source_string);

        return $page_replace;
    }

    public function getName()
    {
        return 'app_extension';
    }
}
```

Then on your `service.yml` add this.
```yml
services:
    app.twig_extension:
        class: Developer\PropertyBundle\Twig\PropertyExtension
        public: false
        tags:
            - { name: twig.extension }
```

OK your filter is ready let say by calling like below.

```twig
{{ '/this/is/your/page/33242-my-slug/page.24/sort.newest' | page_replace('/(\\/page\\.\\d+)/', '/page.50') }}
```

It will replace substring `/page.24` with `/page.50`
