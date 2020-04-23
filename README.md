# StaticJekyllWebsiteTemplate-Public

A publicly available template starting point for building Jekyll-based static websites.

## Requirements

This site uses Ruby gems.  A Ruby development environment with Bundler must be installed in order to run this site.

For more information regarding Ruby installation refer to the Jekyll page: [Installation](https://jekyllrb.com/docs/installation/).

## Usage

There are very few steps required to run this site.  First its dependencies must be installed, and then it can be served.

1. Install the Ruby gem dependencies for the site:

    ```bash
    bundle install
    ```

1. Serve the site:

    ```bash
    bundle exec jekyll serve --trace
    ```

## Directory Structure

StaticJekyllWebsiteTemplate-Public is designed to leverage the following directory structure:

```plaintext
.
├── Build/
│   └── [ ... ]
│
├── Source/
│   ├── Assets/
│   │   ├── Fonts/
│   │   │   └── [ ... ].[ otf | ttf ]
│   │   │
│   │   └── Images/
│   │       ├── favicon.[ png | svg ]
│   │       └── [ ... ].[ bmp | jpg | png | svg | ... ]
│   │
│   ├── Collections/
│   │   ├── _drafts/
│   │   │   └── [ ... ].[ html | md ]
│   │   │
│   │   └── _posts/
│   │       └── [yyyy]-[MM]-[dd]-[ ... ].[ html | md ]
│   │
│   ├── CSS/
│   │   ├── _base.[ css | sass | scss ]
│   │   ├── _layout.[ css | sass | scss ]
│   │   └── [ ... ].[ css | sass | scss ]
│   │
│   ├── Data/
│   │   ├── Settings.[ csv | json | tsv | yaml | yml ]
│   │   └── [ ... ].[ csv | json | tsv | yaml | yml ]
│   │
│   ├── Includes/
│   │   ├── footer.[ html | md ]
│   │   ├── header.[ html | md ]
│   │   └── [ ... ].[ html | md ]
│   │
│   ├── JS/
│   │   └── [ ... ].js
│   │
│   ├── Layouts/
│   │   ├── default.[ html | md ]
│   │   ├── page.[ html | md ]
│   │   ├── post.[ html | md ]
│   │   └── [ ... ].[ html | md ]
│   │
│   ├── Pages/
│   │   ├── 404.[ html | md ]
│   │   └── [ ... ].[ html | md ]
│   │
│   ├── Temporary/
│   │   └── .jekyll-cache
│   │       └── [ ... ]
│   │
│   ├── .jekyll-metadata
│   └── index.[ html | md ]
│
├── _config.[ toml | yml ]
├── .gitignore
├── Gemfile
├── Gemfile.lock
├── LICENSE
└── README.md
```

A brief description of the top-level directory structure can be found in the following chart:

| Entries                 | Brief                            |
| ----------------------- | -------------------------------- |
| Build/                  | Directory for generated site     |
| Source/                 | Directory for site source files  |
| _config.[ toml \| yml ] | Jekyll configuration file        |
| .gitignore              | File specifying Git ignore rules |
| Gemfile                 | Ruby Gem dependencies file       |
| Gemfile.lock            | Ruby Gem dependencies lock file  |
| LICENSE                 | Project license file             |
| README.md               | Project informational file       |

For information regarding the defualt Jekyll site directory structure, refer to the Jekyll page: [Directory Structure](https://jekyllrb.com/docs/structure/).

Additional details regarding each file and directory may be found below.

### Build/

The `Build/` directory acts as a container for the files generated by Jekyll.  All the files required to serve the site will end up here.

### Source/

The `Source/` directory acts as a container for all the component files required to generate the site.  Jekyll will only attempt to compile files stored under this directory.  Additionally, paths specified in the Jekyll configuration file will be relative to the `Source/` directory.

A brief description of the `Source/` directory structure can be found in the following chart:

| Entries              | Brief                                           |
| -------------------- | ----------------------------------------------- |
| Assets/              | Directory for content assets                    |
| Collections/         | Directory for related content groups            |
| CSS/                 | Directory for source styles                     |
| Data/                | Directory for Jekyll dynamic configuration data |
| Includes/            | Directory for commonly-includable content       |
| JS/                  | Directory for source JavaScript files           |
| Layouts/             | Directory for content-wrapping layout templates |
| Pages/               | Directory for website pages                     |
| Temporary/           | Directory for temporary data                    |
| .jekyll-metadata     | Temporary Jekyll metadata                       |
| index.[ html \| md ] | Home page                                       |

### Assets/

The `Assets/` directory acts as a container for custom site assets such as fonts and images.

A brief description of the `Assets/` directory structure can be found in the following chart:

| Entries | Brief                       |
| ------- | --------------------------- |
| Fonts/  | Directory for custom fonts  |
| Images/ | Directory for custom images |

Additional subdirectories may be included to support audio and video files as required.

For more information regarding including assets in the generated pages or making them available for download, please refer to the Jekyll entry: [Including images and resources](https://jekyllrb.com/docs/posts/#including-images-and-resources).

### Fonts/

The `Fonts/` directory acts as a container for custom fonts.

Example entries:

- [ ... ].[ otf | ttf ]

Fonts are treated as static files by Jekyll, and won't be processed.  For more information regarding static files, please refer to the Jekyll page: [Static Files](https://jekyllrb.com/docs/static-files/).

### Images/

The `Images/` directory acts as a container for custom images.

Example entries:

- favicon.[ ico | png | svg ]
- [ ... ].[ bmp | jpg | png | svg | ... ]

Images are treated as static files by Jekyll, and won't be processed.  For more information regarding static files, please refer to the Jekyll page: [Static Files](https://jekyllrb.com/docs/static-files/).

### Collections/

The `Collections/` directory acts as a container for collection subdirectories, each of which group related content.

Drafts and posts each compose distinct collections and are available by default.  Custom collections such as `cats` and `dogs` could also be made.  Given that example the corresponding files would need to be added to the `_cats/` and `_dogs/` subdirectories respectively.

A brief description of the `Collections/` directory structure can be found in the following chart:

| Entries   | Brief                              |
| --------- | ---------------------------------- |
| _drafts/  | Directory for WIP blog draft posts |
| _posts/   | Directory for published blog posts |
| _[ ... ]/ | Directory for custom collection    |

For more information regarding Jekyll collections, please refer to the Jekyll page: [Collections](https://jekyllrb.com/docs/collections/).

### _drafts/

The `_drafts/` directory acts as a container for WIP posts.

Drafts will not be shown on the site unless Jekyll is configured with:

```yml
show_drafts: true
```

Drafts are considered to be part of a `drafts` collection and as such will be found under the `_drafts` subdirectory of the `collections_dir` (`Collections/`).

Example entries:

- [ ... ].[ html | md ]

For more information regarding drafts, please refer to the Jekyll entry: [Drafts](https://jekyllrb.com/docs/posts/#drafts).

### _posts/

The `_posts/` directory acts as a container for finished blog posts.

The file names for finished blog posts must be prefixed with the publication date.  Posts with future publication dates will not be shown on the site unless Jekyll is configured with:

```yml
future: true
```

Posts are considered to be part of a `posts` collection and as such will be found under the `_posts` subdirectory of the `collections_dir` (`Collections/`).

Example entries:

- [yyyy]-[MM]-[dd]-[ ... ].[ html | md ]

For more information regarding posts, please refer to the Jekyll page: [Posts](https://jekyllrb.com/docs/posts/).

### CSS/

The `CSS/` directory acts as a container for style files.

These files are sass partials that can be imported into `main.scss` which will then be processed into a single stylesheet `main.css` that defines the styles to be used by the site.

These files are processed by Jekyll using the rules specified by the `sass` variable of the Jekyll configuration file.

Example entries:

- _base.[ css | sass | scss ]
- _layout.[ css | sass | scss ]
- [ ... ].[ css | sass | scss ]

For more information regarding SASS integration with Jekyll, please refer to the Jekyll page: [Assets](https://jekyllrb.com/docs/assets/).

### Data/

The `Data/` directory acts as a container for site-specific custom data files.

These custom data members are accessible in the front-matter of the site content as `site.data.<data_subpath_uri>`.

Example entries:

- Settings.[ csv | json | tsv | yaml | yml ]
- [ ... ].[ csv | json | tsv | yaml | yml ]

For more information regarding data files, please refer to the Jekyll page: [Data Files](https://jekyllrb.com/docs/datafiles/).

### Includes/

The `Includes/` directory acts as a container for reusable content.

During compilation Jekyll replaces include commands with the content specified in the included file.

By default the Liquid include command:

```liquid
{% include path/to/file.html %}
```

will search for the corresponding file relative to the `Includes/` directory.

Example entries:

- footer.[ html | md ]
- header.[ html | md ]
- [...].[ html | md ]

For more information regarding includes, please refer to the Jekyll page: [Includes](https://jekyllrb.com/docs/includes/).

### JS/

The `JS/` directory acts as a container for JavaScript files.

Example entries:

- [ ... ].js

### Layouts/

The `Layouts/` directory acts as a container for layouts.

Layouts reduce code duplication providing scaffolding for page content in the form of reusable templates.

Example entries:

- default.[ html | md ]
- page.[ html | md ]
- post.[ html | md ]
- [ ... ].[ html | md ]

For more information regarding layouts, please refer to the Jekyll page: [Layouts](https://jekyllrb.com/docs/layouts/).

### Pages/

The `Pages/` directory groups unrelated files that are used to display standalone content not organized by date.

Since paths to pages are mirrored in the `destination` (`Build`) directory, permalinks will need to be specified in the front-matter of each page to remove the likely undesired `Pages/` URL infix.

Example entries:

- 404.[ html \| md ]
- [ ... ].[ html | md ]

For more information regarding page files, please refer to the Jekyll page: [Pages](https://jekyllrb.com/docs/pages/).

### Temporary/

The `Temporary/` directory acts as a container for temporary files that are used for site generation, which should not be under version control.

A brief description of the `Temporary/` directory structure can be found in the following chart:

| Entries        | Brief                              |
| -------------- | ---------------------------------- |
| .jekyll-cache/ | Directory for WIP blog draft posts |

### .jekyll-cache/

The `.jekyll-cache/` directory acts as a container for temporary files cached by Jekyll to expedite subsequent builds.

In order for this directory to be generated, the `safe` and `disable_disk_cache` variables in the Jekyll configuration file must each be false.

### .jekyll-metadata

Incremental regeneration helps shorten build times by only generating documents and pages that were updated since the previous build. It does this by keeping track of both file modification times and inter-document dependencies in the `.jekyll-metadata` file.

Adding the following line to the front-matter of a file will force it to be regenerated during the build process, even if neither the file nor its dependencies have changed:

```yml
regenerate: true
```

For more information regarding the `.jekyll-metadata` file, refer to the Jekyll page: [Incremental Regeneration](https://jekyllrb.com/docs/configuration/incremental-regeneration/#incremental-regeneration).

### 404.[ html | md ]

The page that will be displayed when a site navigation error occurs is defined by its `404.[ html | md ]` file.

For more information regarding custom `404.[ html | md ]` pages, refer to the Jekyll page: [Custom 404 Page](https://jekyllrb.com/tutorials/custom-404-page/#on-github-pages).

### index.[ html | md ]

The default page to show for the website when no other page is specified is defined by its `index.[ html | md ]` file.

### _config.[ toml | yml ]

The Jekyll configuration file for the site, `_config.[ toml | yml ]`, details its structure, build rules, etc.

For more information regarding the `_config.[ toml | yml ]` file refer to the annotation in file or visit the Jekyll page: [Configuration](https://jekyllrb.com/docs/configuration/).

### .gitignore

The rules Git uses for ignoring files when creating commits are defined in the `.gitignore` file.

For more information regarding the `.gitignore` file refer to the annotation in file or visit the Git page: [gitignore](https://git-scm.com/docs/gitignore).

### Gemfile

A `Gemfile` describes the gem dependencies required to execute associated
Ruby code.

For more information regarding the `Gemfile` refer to the annotation in file or visit the Bundler page: [Gemfile](https://bundler.io/man/gemfile.5.html).

### Gemfile.lock

A `Gemfile.lock` file describes the gem dependencies required to execute associated
Ruby code along with the exact versions of those gems being used.

The `Gemfile.lock` file is generated when Bundler installs the specific versions of the gems listed in the `Gemfile`.

For more information regarding the `Gemfile.lock` file visit the Bundler page: [Gemfile](https://bundler.io/man/gemfile.5.html).

### LICENSE

The LICENSE file defines the set of license rights under which the repository is licensed.

For more information regarding the GPLv3 license refer to the GNU page: [GNU General Public License](https://www.gnu.org/licenses/gpl-3.0.en.html).

### README.md

The `README.md` file contains information about the website structure and usage.

README files often contain instructions and additional help, and details about patches or updates.