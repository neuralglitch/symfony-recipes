# Google Fonts Bundle

Integrate Google Fonts seamlessly into your Symfony application with intelligent font loading, local font locking for production, and full AssetMapper support.

## Features

- 🎨 **Twig function** for easy font integration
- 🚀 **Development mode**: Load fonts from Google CDN with preconnect hints
- 📦 **Production mode**: Lock and serve fonts locally via AssetMapper
- ⚡ **Performance optimized**: CSS variables, intelligent weight selection, font subsetting
- 🔍 **CLI commands**: Search, import, lock, and manage fonts
- 🎯 **Monospace support**: Separate fonts for body text and code elements

## Usage

### In Templates

```twig
{# templates/base.html.twig #}
<!DOCTYPE html>
<html>
    <head>
        {# Regular font for body and headings #}
        {{ google_fonts('Ubuntu', '300 400 700', 'normal') }}
        
        {# Monospace font for code elements #}
        {{ google_fonts('JetBrains Mono', '400 500', 'normal', null, true) }}
    </head>
    <body>
        {# Your content #}
    </body>
</html>
```

### Console Commands

```bash
# Search for fonts
php bin/console gfonts:search "Robot"

# Import a specific font
php bin/console gfonts:import "Roboto" --weights="400,700" --styles="normal,italic"

# Lock all used fonts for production
php bin/console gfonts:lock

# Check font status
php bin/console gfonts:status

# Remove unused fonts
php bin/console gfonts:prune
```

## Configuration

The bundle is configured in `config/packages/google_fonts.yaml`:

```yaml
google_fonts:
    api_key: '%env(GOOGLE_FONTS_API_KEY)%'  # Required for search/import
    use_locked_fonts: false                  # Enable locked fonts
    fonts_dir: '%kernel.project_dir%/assets/fonts'
    manifest_file: '%kernel.project_dir%/assets/fonts.json'
```

## API Key (Optional)

To use `gfonts:search` and `gfonts:import` commands, get a free API key:

1. Visit https://console.cloud.google.com/apis/credentials
2. Create a new API key
3. Enable "Google Fonts Developer API"
4. Add to `.env.local`:

```
GOOGLE_FONTS_API_KEY=your_api_key_here
```

## Production Setup

1. Lock fonts before deployment:
   ```bash
   php bin/console gfonts:lock
   ```

2. Commit the generated files:
   ```bash
   git add assets/fonts/ assets/fonts.json
   ```

3. AssetMapper will automatically serve versioned fonts in production

## Documentation

Full documentation: https://github.com/neuralglitch/google-fonts
