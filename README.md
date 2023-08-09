# 🎨 TailwindCSS WP Global Styles Plugin

This plugin takes the CSS contents of the global stylesheet from WordPress and adds it to the TailwindCSS build process.

You will have access to all the utility classes from the WordPress Global Stylesheet in your TailwindCSS build. As well as the css variables.

The goal of this plugin is to provide you with TailwindCSS intelisense for the WordPress global stylesheet. However, to ensure all the WP blocks have the correct styles, and to avoid having to include the `globalStylesheet.css` in the build, this plugin will add all the selectors to the `safelist` config option. This makes sure that all the selectors are included in the build.

## 🚀 Installation

```bash
npm install tailwindcss-wp-global-styles
```

## 📦 Usage

Add the plugin to your `tailwind.config.js` file:

```js
// tailwind.config.js
module.exports = {
	plugins: [
		require('tailwindcss-wp-global-styles')({
			globalStyes: fs.readFileSync('./path/to/wp/global.css', 'utf8'),
		}),
	],
}
```

## ⛭ Options

The `globalStyles` option is required. It should be the contents of the WordPress global stylesheet.

## ⚠️ Warning

Any `!important` declarations in the WordPress global stylesheet will be preserved in the TailwindCSS base and components. Therefore, you should keep this in mind when writing your own TailwindCSS styles. And to check the TailwindCSS Intellisense to see when `!important` is being used.

## 🪪 License

MIT

**Made by [natac13](https://github.com/natac13)**
