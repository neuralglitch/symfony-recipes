<div align="center">

# Symfony Recipes
Symfony Flex recipe repository of **neuralglit.ch**

[![symfony/recipes](https://img.shields.io/badge/symfony-recipes-374151.svg?style=flat-square)](https://github.com/symfony/recipes)
[![symfony/recipes-contrib](https://img.shields.io/badge/symfony-recipes--contrib-374151.svg?style=flat-square)](https://github.com/symfony/recipes-contrib)

[![php](https://img.shields.io/badge/PHP->=8.0-4F5B93.svg?style=flat-square)](https://www.php.net)
[![composer](https://img.shields.io/badge/composer-^2.1-D48822.svg?style=flat-square)](https://getcomposer.org)
[![symfony](https://img.shields.io/badge/symfony/flex-^2-374151.svg?style=flat-square)](https://github.com/symfony/flex)

</div>

---

## Getting Started
This repository contains custom Symfony Flex recipes tailored for my Symfony bundles and packages. 
To enable recipes defined in this repository for your project, add this endpoint in your project's `composer.json` as described in the 
[Symfony documentation](https://symfony.com/doc/current/setup/flex_private_recipes.html#configure-your-project-s-composer-json-file):
```json
{
    "extra": {
        "symfony": {
            "endpoint": [
                "https://api.github.com/repos/neuralglitch/symfony-recipes/contents/index.json",
                "flex://defaults"
            ]
        }
    }
}
```

> [!WARNING]
> Without this option Composer will not use the Symfony Flex recipes for my bundles, unless the recipes were contributed to
> [symfony/recipes-contrib](https://github.com/symfony/recipes-contrib). Then you will need to follow manual installation
> instructions, if provided. 

> [!NOTE]  
> See [RECIPES.md](https://github.com/neuralglitch/symfony-recipes/blob/flex/main/RECIPES.md) for a full list of recipes that live in this repository.

## Contributing
Only authorized team members can contribute to this repository. 

## Support
If you run into any problems or have questions about the recipes, feel free to reach out. However, please note that I won't be available to assist personally.

## License
This repository is highly experimental and should only used unless the recipes are not available in the official recipes-contrib repository. 

## About me
I'm a developer passionate about creating top-notch Symfony applications. Feel free to reach out to me with any questions or collaboration opportunities!

## Acknowledgements
I would like to thank the Symfony community for their valuable contributions to the ecosystem.

---

Copyright (c) 2024 [neuralglit.ch](https://neuralglit.ch)