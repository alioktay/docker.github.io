# Docs @ Docker

Welcome to the repo for our documentation. This is the source for the URL
served at https://docs.docker.com/.

Feel free to send us pull requests and file issues. Our docs are completely
open source and we deeply appreciate contributions from our community!

## Providing feedback

We really want your feedback, and we've made it easy. You can edit, rate, or
file an issue at the bottom of every page on docs.docker.com.

**Please only file issues about the documentation in this repository.** One way
to think about this is that you should file a bug here if your issue is that you
don't see something that should be in the docs, or you see something incorrect
or confusing in the docs.

- If your problem is a general question about how to configure or use Docker,
  consider asking a question on https://forums.docker.com instead.

- If you have an idea for a new feature or behavior change in a specific aspect
  of Docker, or have found a bug in part of Docker, please file that issue in
  the project's code repository.

## Contributing

We value your documentation contributions, and we want to make it as easy
as possible to work in this repository. One of the first things to decide is
which branch to base your work on. If you get confused, just ask and we will
help. If a reviewer realizes you have based your work on the wrong branch, we'll
let you know so that you can rebase it.

>**Note**: To contribute code to Docker projects, see the
[Contribution guidelines](opensource/project/who-written-for).

### Overall doc improvements

Most commits will be made against the `master` branch. This include:

- Conceptual and task-based information not specific to new features
- Restructuring / rewriting
- Doc bug fixing
- Typos and grammar errors

One quirk of this project is that the `master` branch is where the live docs are
published from, so upcoming features can't be documented there. See
[Specific new features for a project](#specific-new-features-for-a-project)
for how to document upcoming features. These feature branches will be periodically
merged with `master`, so don't worry about fixing typos and documentation bugs
there.

>Do you enjoy creating graphics? Good graphics are key to great documentation,
and we especially value contributions in this area.

### Specific new features for a project

Our docs cover many projects which release at different times. **If, and only if,
your pull request relates to a currently unreleased feature of a project, base
your work on that project's `vnext` branch.** These branches were created by
cloning `master` and then importing a project's `master` branch's docs into it
(at the time of the migration), in a way that preserved the commit history. When
a project has a release, its `vnext` branch will be merged into `master` and your
work will be visible on docs.docker.com.

The following `vnext` branches currently exist:

- **[vnext-engine](https://github.com/docker/docker.github.io/tree/vnext-engine):**
  docs for upcoming features in the [docker/docker](https://github.com/docker/docker/)
  project

- **[vnext-compose](https://github.com/docker/docker.github.io/tree/vnext-compose):**
  docs for upcoming features in the [docker/compose](https://github.com/docker/compose/)
  project

- **[vnext-distribution](https://github.com/docker/docker.github.io/tree/vnext-distribution):**
  docs for upcoming features in the [docker/distribution](https://github.com/docker/distribution/)
  project

- **[vnext-opensource](https://github.com/docker/docker.github.io/tree/vnext-opensource):**
  docs for upcoming features in the [docker/opensource](https://github.com/docker/opensource/)
  project

- **[vnext-swarm](https://github.com/docker/docker.github.io/tree/vnext-swarm):**
  docs for upcoming features in the [docker/swarm](https://github.com/docker/swarm/)
  project

- **[vnext-toolbox](https://github.com/docker/docker.github.io/tree/vnext-toolbox):**
  docs for upcoming features in the [docker/toolbox](https://github.com/docker/toolbox/)
  project

- **[vnext-kitematic](https://github.com/docker/docker.github.io/tree/vnext-kitematic):**
  docs for upcoming features in the [docker/kitematic](https://github.com/docker/kitematic/)
  project


## Staging

You have three options:

1.  Clone this repo and run our staging container:

    ```bash
    git clone https://github.com/docker/docker.github.io.git
    cd docker.github.io
    docker-compose up
    ```

    If you haven't got Docker Compose installed,
    [follow these installation instructions](https://docs.docker.com/compose/install/).

    The container runs in the background and incrementally rebuilds the site each
    time a file changes. You can keep your browser open to http://localhost:4000/
    and refresh to see your changes. The container runs in the foreground, but
    you can use `CTRL+C` to get the command prompt back. To stop the container,
    issue the following command:

    ```bash
    docker-compose down
    ```

2.  Use Jekyll directly. Clone this repo, [install Ruby 2.3 or higher
    (required)](https://www.ruby-lang.org/en/documentation/installation/),
    [install the GitHub Pages Ruby gem](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/),
    then run `jekyll serve` from within the directory.

    The `jekyll serve` process runs in the foreground, and starts a web server
    running on http://localhost:4000/ by default. To stop it, use `CTRL+C`.
    You can continue working in a second terminal and Jekyll will rebuild the
    website incrementally. Refresh the browser to preview your changes.

3.  Use Github Pages, with or without a local clone. Fork this repo in GitHub,
    change your fork's repository name to `YOUR_GITHUB_USERNAME.github.io`, and
    make changes to the Markdown files in your `master` branch. Browse to
    https://<YOUR_GITHUB_USERNAME>.github.io/ to preview the changes.

## Important files

- `/_data/toc.yaml` defines the left-hand navigation for the docs
- `/js/menu.js` defines most of the docs-specific JS such as TOC generation and menu syncing
- `/css/documentation.css` defines the docs-specific style rules
- `/_layouts/docs.html` is the HTML template file, which defines the header and footer, and includes all the JS/CSS that serves the docs content

## Relative linking for GitHub viewing

Feel free to link to `../foo.md` so that the docs are readable in GitHub, but keep in mind that Jekyll templating notation
`{% such as this %}` will render in raw text and not be processed. In general it's best to assume the docs are being read
directly on docs.docker.com.

## Style guide

If you have questions about how to write for Docker's documentation, please see
the [style guide](https://docs.docker.com/opensource/doc-style/). The style guide provides
guidance about grammar, syntax, formatting, styling, language, or tone. If
something isn't clear in the guide, please submit an issue to let us know or
submit a pull request to help us improve it.

### Generate the man pages

For information on generating man pages (short for manual page), see the README.md
document in [the man page directory](https://github.com/docker/docker/tree/master/man)
in this project.

## Copyright and license

Code and documentation copyright 2016 Docker, inc, released under the Apache 2.0 license.
