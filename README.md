# StaticJekyllWebsiteTemplate-Public

A publicly available template starting point for building `Jekyll`-based static websites.

## Requirements

This site uses `Ruby` gems.  A `Ruby` development environment with `Bundler` must be installed in order to run this site.

The tool `rbenv` was selected to allow for the use of the latest versions of `Ruby` and `Bundler` in a `Debian` environment.  `Rbenv` is a lightweight `Ruby` version management tool which allows the user to easily switch `Ruby` versions. By default `rbenv` doesn’t handle installation of `Ruby` versions, so `ruby-build`--a tool which assists in the installation of any `Ruby` version--must also be installed. It is available as a standalone program and as a plugin for `rbenv`.

The environment can be prepared for development as follows:

1. Update the packages index database:

    ```bash
    sudo apt update
    ```

2. Upgrade those packages which have a new release available to the platform, as defined in packages index database:

    ```bash
    sudo apt upgrade -y
    ```

3. Install common build tools:

    ```bash
    sudo apt install build-essential
    ```

4. Install `zlib`--a library implementing the deflate compression method found in `gzip` and `PKZIP` (this package includes the development support files):

    ```bash
    sudo apt install zlib1g-dev
    ```

5. Install `autoconf` (should already be installed):

    ```bash
    sudo apt install autoconf
    ```

6. Install `bison` (should already be installed):

    ```bash
    sudo apt install bison
    ```

7. Install the packages required for the `ruby-build` tool to build `Ruby` from source:

    ```bash
    sudo apt install git curl libssl-dev libreadline-dev libyaml-dev libncurses5-dev libffi-dev libgdbm-dev
    ```

8. Install both `rbenv` and `ruby-build`:

    ```bash
    curl -sL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash -
    ```

    **NOTE**: The script will clone both rbenv and ruby-build repositories from GitHub to ~/.rbenv directory. The installer script also calls another script which will try to verify the installation.

9. Add `$HOME/.rbenv/bin` to the user `PATH`:

    ```bash
    echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(rbenv init -)"' >> ~/.bashrc
    source ~/.bashrc
    ```

10. Determine the latest stable version of `Ruby` available by listing available versions:

    ```bash
    rbenv install -l
    ```

11. Install the latest stable version of `Ruby`:

    ```bash
    rbenv install 2.7.1
    ```

12. Set the latest stable version of `Ruby` as the global default version:

    ```bash
    rbenv global 2.7.1
    ```

13. Verify that `Ruby` was properly installed by printing the version number:

    ```bash
    ruby -v
    ```

    **NOTE**: The expected result should appear as follows:

    ```bash
    # ruby 2.7.1p83 (2020-03-31 revision a0c7c23c9c) [x86_64-linux]
    ```

14. Verify that `rbenv` is properly set up using this `rbenv-doctor` script:

    ```bash
    curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash
    ```

15. Set up `Ruby` to install gems to `~/gems` by default:

    ```bash
    echo '# Set up Ruby to install gems to `~/gems` by default' >> ~/.bashrc
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    echo 'export PATH="$GEM_HOME/bin:$PATH"' >> ~/.bashrc
    source ~/.bashrc
    ```

16. Install `Bundler`:

    ```bash
    gem install bundler
    ```

    **NOTE**: `Bundler` parses `Gemfile` configuration files to determine and download gem project dependencies.

For more information regarding `rbenv` installation refer to the GitHub repository: [rbenv](https://github.com/rbenv/rbenv).

For more information regarding generic `Ruby` installation refer to the `Jekyll` page: [Installation](https://jekyllrb.com/docs/installation/).

## Usage

There are very few steps required to run this site.  First its dependencies must be installed, and then it can be served.

1. To avoid `Ruby` gem versioning conflicts, configure local `Ruby` gem install path:

    ```bash
    bundle config set path 'vendor/bundle'
    ```

1. Install the `Ruby` gem dependencies for the site:

    ```bash
    bundle install
    ```

1. Serve the site:

    ```bash
    bundle exec jekyll serve --trace
    ```

## Directory Structure

`StaticJekyllWebsiteTemplate-Public` is designed to leverage the following directory structure:

```plaintext
.
├── build/
│   └── [ ... ]
│
├── source/
│   ├── assets/
│   │   ├── fonts/
│   │   │   └── [ ... ].[ otf | ttf ]
│   │   │
│   │   └── images/
│   │       ├── favicon.[ png | svg ]
│   │       └── [ ... ].[ bmp | jpg | png | svg | ... ]
│   │
│   ├── collections/
│   │   ├── _drafts/
│   │   │   └── [ ... ].[ html | md ]
│   │   │
│   │   └── _posts/
│   │       └── [yyyy]-[MM]-[dd]-[ ... ].[ html | md ]
│   │
│   ├── css/
│   │   ├── _base.[ css | sass | scss ]
│   │   ├── _layout.[ css | sass | scss ]
│   │   └── [ ... ].[ css | sass | scss ]
│   │
│   ├── data/
│   │   ├── settings.[ csv | json | tsv | yaml | yml ]
│   │   └── [ ... ].[ csv | json | tsv | yaml | yml ]
│   │
│   ├── includes/
│   │   ├── footer.[ html | md ]
│   │   ├── header.[ html | md ]
│   │   └── [ ... ].[ html | md ]
│   │
│   ├── js/
│   │   └── [ ... ].js
│   │
│   ├── layouts/
│   │   ├── default.[ html | md ]
│   │   ├── page.[ html | md ]
│   │   ├── post.[ html | md ]
│   │   └── [ ... ].[ html | md ]
│   │
│   ├── pages/
│   │   ├── 404.[ html | md ]
│   │   └── [ ... ].[ html | md ]
│   │
│   ├── temporary/
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
| build/                  | Directory for generated site     |
| source/                 | Directory for site source files  |
| _config.[ toml \| yml ] | Jekyll configuration file        |
| .gitignore              | File specifying Git ignore rules |
| Gemfile                 | Ruby Gem dependencies file       |
| Gemfile.lock            | Ruby Gem dependencies lock file  |
| LICENSE                 | Project license file             |
| README.md               | Project informational file       |

For information regarding the defualt Jekyll site directory structure, refer to the Jekyll page: [Directory Structure](https://jekyllrb.com/docs/structure/).

Additional details regarding each file and directory may be found below.

### Build/

The `build/` directory acts as a container for the files generated by Jekyll.  All the files required to serve the site will end up here.

### Source/

The `source/` directory acts as a container for all the component files required to generate the site.  Jekyll will only attempt to compile files stored under this directory.  Additionally, paths specified in the Jekyll configuration file will be relative to the `source/` directory.

A brief description of the `source/` directory structure can be found in the following chart:

| Entries              | Brief                                           |
| -------------------- | ----------------------------------------------- |
| assets/              | Directory for content assets                    |
| collections/         | Directory for related content groups            |
| css/                 | Directory for source styles                     |
| data/                | Directory for Jekyll dynamic configuration data |
| includes/            | Directory for commonly-includable content       |
| js/                  | Directory for source JavaScript files           |
| layouts/             | Directory for content-wrapping layout templates |
| pages/               | Directory for website pages                     |
| temporary/           | Directory for temporary data                    |
| .jekyll-metadata     | Temporary Jekyll metadata                       |
| index.[ html \| md ] | Home page                                       |

### Assets/

The `assets/` directory acts as a container for custom site assets such as fonts and images.

A brief description of the `assets/` directory structure can be found in the following chart:

| Entries | Brief                       |
| ------- | --------------------------- |
| fonts/  | Directory for custom fonts  |
| images/ | Directory for custom images |

Additional subdirectories may be included to support audio and video files as required.

For more information regarding including assets in the generated pages or making them available for download, please refer to the Jekyll entry: [Including images and resources](https://jekyllrb.com/docs/posts/#including-images-and-resources).

### Fonts/

The `fonts/` directory acts as a container for custom fonts.

Example entries:

- [ ... ].[ otf | ttf ]

Fonts are treated as static files by Jekyll, and won't be processed.  For more information regarding static files, please refer to the Jekyll page: [Static Files](https://jekyllrb.com/docs/static-files/).

### Images/

The `images/` directory acts as a container for custom images.

Example entries:

- favicon.[ ico | png | svg ]
- [ ... ].[ bmp | jpg | png | svg | ... ]

Images are treated as static files by Jekyll, and won't be processed.  For more information regarding static files, please refer to the Jekyll page: [Static Files](https://jekyllrb.com/docs/static-files/).

### Collections/

The `collections/` directory acts as a container for collection subdirectories, each of which group related content.

Drafts and posts each compose distinct collections and are available by default.  Custom collections such as `cats` and `dogs` could also be made.  Given that example the corresponding files would need to be added to the `_cats/` and `_dogs/` subdirectories respectively.

A brief description of the `collections/` directory structure can be found in the following chart:

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

Drafts are considered to be part of a `drafts` collection and as such will be found under the `_drafts` subdirectory of the `collections_dir` (`collections/`).

Example entries:

- [ ... ].[ html | md ]

For more information regarding drafts, please refer to the Jekyll entry: [Drafts](https://jekyllrb.com/docs/posts/#drafts).

### _posts/

The `_posts/` directory acts as a container for finished blog posts.

The file names for finished blog posts must be prefixed with the publication date.  Posts with future publication dates will not be shown on the site unless Jekyll is configured with:

```yml
future: true
```

Posts are considered to be part of a `posts` collection and as such will be found under the `_posts` subdirectory of the `collections_dir` (`collections/`).

Example entries:

- [yyyy]-[MM]-[dd]-[ ... ].[ html | md ]

For more information regarding posts, please refer to the Jekyll page: [Posts](https://jekyllrb.com/docs/posts/).

### CSS/

The `css/` directory acts as a container for style files.

These files are sass partials that can be imported into `main.scss` which will then be processed into a single stylesheet `main.css` that defines the styles to be used by the site.

These files are processed by Jekyll using the rules specified by the `sass` variable of the Jekyll configuration file.

Example entries:

- _base.[ css | sass | scss ]
- _layout.[ css | sass | scss ]
- [ ... ].[ css | sass | scss ]

For more information regarding SASS integration with Jekyll, please refer to the Jekyll page: [Assets](https://jekyllrb.com/docs/assets/).

### Data/

The `data/` directory acts as a container for site-specific custom data files.

These custom data members are accessible in the front-matter of the site content as `site.data.<data_subpath_uri>`.

Example entries:

- Settings.[ csv | json | tsv | yaml | yml ]
- [ ... ].[ csv | json | tsv | yaml | yml ]

For more information regarding data files, please refer to the Jekyll page: [Data Files](https://jekyllrb.com/docs/datafiles/).

### Includes/

The `includes/` directory acts as a container for reusable content.

During compilation Jekyll replaces include commands with the content specified in the included file.

By default the Liquid include command:

```liquid
\{\% include path/to/file.html \%\}
```

will search for the corresponding file relative to the `includes/` directory.

Example entries:

- footer.[ html | md ]
- header.[ html | md ]
- [...].[ html | md ]

For more information regarding includes, please refer to the Jekyll page: [Includes](https://jekyllrb.com/docs/includes/).

### JS/

The `js/` directory acts as a container for JavaScript files.

Example entries:

- [ ... ].js

### Layouts/

The `layouts/` directory acts as a container for layouts.

Layouts reduce code duplication providing scaffolding for page content in the form of reusable templates.

Example entries:

- default.[ html | md ]
- page.[ html | md ]
- post.[ html | md ]
- [ ... ].[ html | md ]

For more information regarding layouts, please refer to the Jekyll page: [Layouts](https://jekyllrb.com/docs/layouts/).

### Pages/

The `pages/` directory groups unrelated files that are used to display standalone content not organized by date.

Since paths to pages are mirrored in the `destination` (`build/`) directory, permalinks will need to be specified in the front-matter of each page to remove the likely undesired `pages/` URL infix.

Example entries:

- 404.[ html \| md ]
- [ ... ].[ html | md ]

For more information regarding page files, please refer to the Jekyll page: [Pages](https://jekyllrb.com/docs/pages/).

### Temporary/

The `temporary/` directory acts as a container for temporary files that are used for site generation, which should not be under version control.

A brief description of the `temporary/` directory structure can be found in the following chart:

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
