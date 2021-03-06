# Themes

<style>
	.toggle-theme.current h2:after {
		color: #808080;
		content: " Current Theme";
		font-size: 0.65em;
		font-style: italic;
	}
</style>

Themes are pre-built combinations of layout changes, label updates, user options, and CSS. Use them as-is, or as a starting point to customize your Portal more quickly.

To see how easy it is to change the look of your Portal, click one of the themes below to update the appearance of this demo.

<div>
	<a class="toggle-theme" data-options="blackbeard" href="#">
		<h2 class="no-margin-bottom">Blackbeard</h2>
		<img title="Blackbeard Theme" src="/files/blackbeard.jpg">
	</a>

	<a class="toggle-theme" data-options="sparrow" href="#">
		<h2 class="no-margin-bottom">Sparrow Neue</h2>
		<img title="Sparrow Theme" src="/files/sparrow.jpg">
	</a>

	<a class="toggle-theme" data-options="skinnyNav" href="#">
		<h2 class="no-margin-bottom">Skinny Nav</h2>
		<img title="Skinny Nav Theme" src="/files/skinny-nav.jpg">
	</a>
</div>

<script>
	// Setup theme options object
	themeOptions = {};

	themeOptions.blackbeard = {
		styles: '/files/blackbeard.min.css',
		options: function () {
			portalOptions = window.portalOptions;

			portalOptions.templates.page = function () {
				if (mashery.globals.fullWidth) {
					return	'<div class="main content" id="main">' +
								'{{content.main}}' +
							'</div>';
				} else {
					return	'<div class="main container content" id="main">' +
								'<h1>{{content.heading}}</h1>' +
								'{{content.main}}' +
							'</div>';
				}
			};

			portalOptions.templates.userNav = null;

			portalOptions.templates.primaryNav = function () {
				var template =
					'<div class="nav-primary nav-wrap nav-collapse" id="nav-primary">' +
						'<div class="container padding-top-small padding-bottom-small">' +
							'<a id="logo" class="logo margin-bottom" href="/">{{content.logo}}</a>' +
							'<a role="button" class="nav-toggle" id="nav-primary-toggle" data-nav-toggle="#nav-primary-menu" href="#">{{content.menuToggle}}</a>' +
							'<div class="nav-menu" id="nav-primary-menu">' +
								'<ul class="nav" id="nav-primary-list">' +
									'{{content.navItemsPrimary}}' +
								'</ul>' +
								'<ul class="nav-user-list" id="nav-user-list">' +
									'{{content.navItemsUser}}' +
								'</ul>' +
								'{{content.searchForm}}' +
								(mashery.contentType === 'docs' ? '<h2 class="margin-top">In The Docs</h2><ul class="nav-docs" id="nav-docs">{{content.secondary}}</ul>' : '') +
							'</div>' +
						'</div>' +
					'</div>';
				return template;
			};


			portalOptions.templates.docs =
				'<div class="main container" id="main">' +
					'<h1>{{content.heading}}</h1>' +
					'{{content.main}}' +
				'</div>';

			portalOptions.templates.layout =
				'<div class="row row-no-padding clearfix">' +
					'<div class="grid-fourth">' +
						'<a class="screen-reader screen-reader-focusable" href="#main">Skip to content</a>' +
						'{{layout.navPrimary}}' +
					'</div>' +
					'<div class="grid-three-fourths">' +
						'{{layout.main}}' +
						'<footer class="footer" id="footer">' +
							'{{layout.footer1}}' +
							'{{layout.navSecondary}}' +
							'{{layout.footer2}}' +
						'</footer>' +
					'</div>' +
				'</div>';
		}
	};

	themeOptions.sparrow = {
		styles: '/files/sparrow.min.css',
		options: function () {
			portalOptions = window.portalOptions;

			portalOptions.templates.page = function () {
				if (mashery.globals.fullWidth) {
					return	'<div class="main content" id="main">' +
								'{{content.main}}' +
							'</div>';
				} else {
					return	'<div class="main container content" id="main">' +
								'<h1>{{content.heading}}</h1>' +
								'{{content.main}}' +
							'</div>';
				}
			};
		}
	};

	themeOptions.skinnyNav = {
		styles: '/files/skinny-nav.min.css',
		options: function () {
			portalOptions = window.portalOptions;

			portalOptions.templates.page = function () {
				if (mashery.globals.fullWidth) {
					return	'<div class="main content" id="main">' +
								'{{content.main}}' +
							'</div>';
				} else {
					return	'<div class="main container content" id="main">' +
								'<h1>{{content.heading}}</h1>' +
								'{{content.main}}' +
							'</div>';
				}
			};

			portalOptions.templates.userNav = null;

			portalOptions.templates.primaryNav =
				'<div class="nav-primary nav-wrap nav-collapse" id="nav-primary">' +
					'<div class="container padding-top-small padding-bottom-small">' +
						'<a id="logo" class="logo" href="/">{{content.logo}}</a>' +
						'<a role="button" class="nav-toggle" id="nav-primary-toggle" data-nav-toggle="#nav-primary-menu" href="#">{{content.menuToggle}}</a>' +
						'<div class="nav-menu">' +
							'<div id="nav-user-menu">' +
								'<ul class="nav" id="nav-user-list">' +
									'{{content.navItemsUser}}' +
								'</ul>' +
							'</div>' +
							'<div id="nav-primary-menu">' +
								'<ul class="nav" id="nav-primary-list">' +
									'{{content.navItemsPrimary}}' +
									'<li><a href="/search"><svg xmlns="http://www.w3.org/2000/svg" class="icon icon-link" width="16" height="16" viewBox="0 0 32 32"><title>Search</title><path d="M31.008 27.231l-7.58-6.447c-.784-.705-1.622-1.029-2.299-.998a11.954 11.954 0 0 0 2.87-7.787c0-6.627-5.373-12-12-12s-12 5.373-12 12 5.373 12 12 12c2.972 0 5.691-1.081 7.787-2.87-.031.677.293 1.515.998 2.299l6.447 7.58c1.104 1.226 2.907 1.33 4.007.23s.997-2.903-.23-4.007zM12 20a8 8 0 1 1 0-16 8 8 0 0 1 0 16z"/></svg></a></li>' +
								'</ul>' +
							'</div>' +
						'</div>' +
					'</div>' +
				'</div>';
		}
	};

	// Re-render the Portal with new options
	var toggleThemes = function () {

		'use strict';

		// Make sure toggle theme button exists before running
		if (!document.querySelector('.toggle-theme')) return;

		var isStylesheet = function (ss) {
			return !!(ss.nodeName.toLowerCase() === 'link' && ss.getAttribute('rel').toLowerCase() === 'stylesheet' && ss.getAttribute('href'));
		};

		var getStylesheet = function () {
			var title = document.querySelector('title');
			var ss = title.nextElementSibling;
			if (!ss) return;
			if (!isStylesheet(ss)) {
				do {
					ss = ss.nextElementSibling;
				} while (!isStylesheet(ss));
			}
			return ss;
		};

		var updateStyles = function (styles) {
			var ss = getStylesheet();
			if (!ss) return;
			ss.href = styles;
		};

		var updateCurrent = function (theme) {
			var current = document.querySelector('.toggle-theme.current');
			if (current) {
				current.classList.remove('current');
			}
			theme.classList.add('current');
		};

		// Update current theme
		var setCurrentTheme = function () {
			if (window.mashery.contentId !== 'docs-customizing-themes') return;
			var currentSS = getStylesheet();
			var currentTheme, currentToggle;
			for (var theme in themeOptions) {
				if (themeOptions.hasOwnProperty(theme)) {
					if (currentSS.getAttribute('href') !== themeOptions[theme].styles) continue;
					currentToggle = document.querySelector('.toggle-theme[data-options="' + theme + '"]');
					updateCurrent(currentToggle);
					break;
				}
			}
		};
		setCurrentTheme();

		// Don't reinit click listener
		if (window.toggleThemesRunning) return;
		document.addEventListener('click', function (event) {

			// Only run if theme toggle is clicked
			var toggle = event.target.closest('.toggle-theme');
			if (!toggle) return;

			// Get options
			var options = toggle.getAttribute('data-options');
			if (!options) return;

			// Stop link from working
			event.preventDefault();

			// Reset portalOptions
			m$.resetOptions();

			// Update portalOptions
			themeOptions[options].options();

			// Update stylesheet
			updateStyles(themeOptions[options].styles);

			// Clear the DOM
			// document.documentElement.classList.remove('complete');
			// document.querySelector('#app').innerHTML = '';

			// Re-render the Portal with new options
			m$.setOptions(portalOptions);
			m$.renderPortal();
			//m$.init(portalOptions);

		}, false);

		// Register that toggle theme is already initialized
		window.toggleThemesRunning = true;

	};

	toggleThemes();

</script>