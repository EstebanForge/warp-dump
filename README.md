# Warp Dump

A nicer way to dump data on screen, for those who have not yet been introduced to Xdebug.

Warp Dump is a single-file PHP library that provides an enhanced variable dumping experience with a modern HTML/CSS/JavaScript interface. It's a lightweight alternative to Xdebug's var_dump() that requires no installation or configuration.

![Warp Dump Demo](https://img.shields.io/badge/PHP-7.4%2B-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## ✨ Features

- 🎨 **Modern UI** - Clean, responsive interface with light/dark theme support
- 🔍 **Search & Highlight** - Search through dumped data with regex support
- 📋 **Smart Copy** - Click to copy all, or select text to copy selection
- ⚡ **Zero Dependencies** - Single file inclusion, no external libraries
- 🎯 **Variable Names** - Automatically detects and displays variable names
- 📱 **Mobile Friendly** - Responsive design that works on all devices
- 💾 **Theme Persistence** - Remembers your theme preference in localStorage
- ⌨️ **Keyboard Navigation** - Use Enter/Shift+Enter for search navigation

## 🚀 Installation

### Composer (Recommended)

```bash
composer require estebanforge/warp-dump
```

Then include it in your project:

```php
require 'vendor/autoload.php';
```

### Manual Installation

Download the `warp-dump.php` file and include it in your project:

```php
require 'warp-dump.php';
```

## 📖 Usage

### Basic Usage

```php
require 'warp-dump.php';

// Dump a single variable
$name = 'John Doe';
warp_dump($name);

// Dump multiple variables
$user = ['name' => 'John', 'age' => 30];
$config = ['debug' => true, 'version' => '1.0'];
warp_dump($user, $config);

// Dump and die (like dd())
warp_dd($user);
```

### Advanced Usage

```php
// Dump complex data structures
$data = [
    'users' => [
        ['id' => 1, 'name' => 'Alice', 'active' => true],
        ['id' => 2, 'name' => 'Bob', 'active' => false],
    ],
    'metadata' => [
        'total' => 2,
        'page' => 1,
        'timestamp' => time(),
    ],
];

warp_dump($data);
```

## 🎮 Interface Features

### Theme Switching
- Click the theme toggle button to switch between light and dark themes
- Your preference is automatically saved and restored

### Search Functionality
- Type in the search box to highlight matching text
- Supports regular expressions for advanced searching
- Use ↑/↓ buttons or Enter/Shift+Enter to navigate between matches
- Press Escape or click the clear button to reset search

### Copy to Clipboard
- **Quick Copy**: Click anywhere in the dump content to copy everything
- **Selection Copy**: Select text with your mouse, then release to copy only the selection
- Visual feedback confirms when content is copied

## 🔧 Configuration

Warp Dump works out of the box with no configuration required. However, you can customize the experience:

### PHP Version Requirements
- **Minimum**: PHP 7.4+
- **Recommended**: PHP 8.0+ for best performance

### Browser Compatibility
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 🆚 Comparison

| Feature | Warp Dump | Xdebug var_dump | print_r |
|---------|-----------|-----------------|---------|
| No installation required | ✅ | ❌ | ✅ |
| Interactive UI | ✅ | ❌ | ❌ |
| Search functionality | ✅ | ❌ | ❌ |
| Copy to clipboard | ✅ | ❌ | ❌ |
| Theme switching | ✅ | ❌ | ❌ |
| Variable names | ✅ | ❌ | ❌ |
| Mobile friendly | ✅ | ❌ | ❌ |

## 🐛 Debugging Tips

### Common Use Cases

```php
// Debug API responses
$response = file_get_contents('https://api.example.com/data');
warp_dump(json_decode($response, true));

// Debug form submissions
warp_dump($_POST, $_FILES);

// Debug database results
$stmt = $pdo->query('SELECT * FROM users');
warp_dump($stmt->fetchAll(PDO::FETCH_ASSOC));

// Debug function returns
function getUserData($id) {
    // ... complex logic
    return $userData;
}
warp_dump(getUserData(123));
```

### Performance Considerations

- Warp Dump is designed for development use only
- Avoid using in production environments
- Large datasets may impact browser performance
- Consider using `warp_dd()` to stop execution after dumping critical data

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Development Setup

1. Clone the repository
2. Make your changes
3. Test with: `php -r "require 'warp-dump.php'; warp_dump(\$test_var);"`
4. Check syntax: `php -l warp-dump.php`

### Code Style

- Follow PSR-12 coding standards
- Use snake_case for function names
- Include PHPDoc blocks for all functions
- Maintain backward compatibility with PHP 7.4+

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by Laravel's `dd()` function
- Built for developers who need a better debugging experience
- Created with ❤️ by [Esteban Cuevas](https://github.com/EstebanForge)

## 🔗 Links

- [GitHub Repository](https://github.com/EstebanForge/warp-dump)
- [Packagist](https://packagist.org/packages/estebanforge/warp-dump)
- [Report Issues](https://github.com/EstebanForge/warp-dump/issues)

---

**Warp Dump** - Make debugging beautiful again! ✨