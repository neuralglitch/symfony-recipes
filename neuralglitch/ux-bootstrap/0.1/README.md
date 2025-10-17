# Symfony Flex Recipe for neuralglitch/ux-bootstrap

This directory contains the Symfony Flex recipe for the UX Bootstrap bundle.

## Recipe Structure

```
flex-recipe/
├── manifest.json              # Recipe configuration
├── config/
│   └── packages/
│       └── ux_bootstrap.yaml  # Default bundle configuration
└── README.md                  # This file
```

**What the recipe does:**
- Automatically registers `NeuralGlitchUxBootstrapBundle` in `config/bundles.php`
- Creates `config/packages/ux_bootstrap.yaml` with all component defaults
- Shows post-install instructions (Bootstrap requirement, quick start)

**Users can then:**
- Customize component defaults in the generated config file
- Use components immediately with sensible defaults

## Publishing the Recipe

To make this recipe available via your custom Symfony recipes repository:

### 1. Copy to symfony-recipes Repository

Copy the entire recipe to your recipes repository:

```bash
# Clone your recipes repository
git clone https://github.com/neuralglitch/symfony-recipes.git
cd symfony-recipes

# Create the recipe directory structure
mkdir -p neuralglitch/ux-bootstrap/0.1

# Copy recipe files
cp /path/to/ux-bootstrap/flex-recipe/manifest.json neuralglitch/ux-bootstrap/0.1/
cp -r /path/to/ux-bootstrap/flex-recipe/config neuralglitch/ux-bootstrap/0.1/
```

### 2. Update index.json

Add an entry to the `index.json` in your recipes repository:

```json
{
    "recipes": {
        "neuralglitch/ux-bootstrap": [
            "0.1"
        ]
    }
}
```

### 3. Commit and Push

```bash
git add .
git commit -m "Add recipe for neuralglitch/ux-bootstrap 0.1"
git push origin main
```

### 4. Users Can Now Use It

Users add this to their `composer.json`:

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

Then:

```bash
composer require neuralglitch/ux-bootstrap
```

The recipe will automatically install!

## Recipe Versioning

- **0.1** - First public beta (v0.1.0 - v0.9.x)
- **1.0** - First stable release (v1.0.0+)

Create new recipe versions when breaking changes occur:

```
neuralglitch/ux-bootstrap/
├── 0.1/           # For v0.1.0 - v0.9.x
│   ├── manifest.json
│   └── config/
└── 1.0/           # For v1.0.0+
    ├── manifest.json
    └── config/
```

## Testing the Recipe Locally

Before publishing, test the recipe locally:

```bash
# In a test Symfony project
composer config repositories.recipes '{"type": "path", "url": "../symfony-recipes"}'
composer config extra.symfony.endpoint '["file://../symfony-recipes/index.json", "flex://defaults"]'
composer require neuralglitch/ux-bootstrap:@dev
```

## Documentation

- [Symfony Flex Recipes Documentation](https://github.com/symfony/recipes)
- [Creating Recipes](https://github.com/symfony/recipes/blob/master/CONTRIBUTING.md)
- [Recipe Format](https://github.com/symfony/flex/blob/main/doc/recipes.rst)

