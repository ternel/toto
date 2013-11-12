WTF Problème en français
====================================

> Finally a tool for typography nerds.

JoliTypo is a tool fixing [Microtypography](https://en.wikipedia.org/wiki/Microtypography) glitches inside your HTML content.

```php
use JoliTypo\Fixer;

$fixer = new Fixer(array('Ellipsis', 'Dash', 'EnglishQuotes', 'CurlyQuote', 'Hyphen'));
$fixed_content = $fixer->fix('<p>"Tell me Mr. Anderson... what good is a phone call... if you\'re unable to speak?" -- Agent Smith, <em>Matrix</em>.</p>');
```
```html
<p>&ldquo;Tell me Mr. Ander&shy;son&hellip; what good is a phone call&hellip; if you&rsquo;re unable to speak?&rdquo;&mdash;Agent Smith, <em>Matrix</em>.</p>
```
> “Tell me Mr. Anderson… what good is a phone call… if you’re unable to speak?”—Agent Smith, Matrix.

It's designed to be:

- language agnostic (you can fix `fr_FR`, `fr_CA`, `en_US`... You tell JoliTypo what to fix);
- fully tested;
- easy to integrate into modern PHP project (composer and autoload);
- robust (make use of `\DOMDocument` instead of parsing HTML with dummy regexp);
- smart enough to avoid Javascript, Code, CSS processing... (configurable protected tags list);
- fully open and usable in any project (MIT License).
