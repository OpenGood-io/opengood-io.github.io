# OpenGood.io Organization GitHub Pages Site

Public Web site for OpenGood.io using Hugo and GitHub Pages.

## Where can I find the site?

The site is hosted as a GitHub pages static content Web site at [http://opengood.io](http://opengood.io).

## How do I create content for the site?

The content is stored under the `content` directory in this repo and is written in
[Markdown](https://daringfireball.net/projects/markdown/syntax).


## How does content get published to the site?

The content is automatically generated from this repo using a tool called
[Hugo](https://gohugo.io) and published to a GitHub pages static content Web site at
[http://opengood.io](http://opengood.io).

## Development

### Local

[Install Hugo](https://gohugo.io/overview/installing/) and start a live-reloading server in this directory:

```bash
hugo server --baseUrl=http://localhost --port=1313
```

#### Adding a Chapter

To add a new chapter:

```bash
hugo new --kind chapter chapter_name/_index.md
```

#### Adding a Section

To add a new section under a chapter:

```bash
hugo new chaptername/section.md
```

### References

* Hugo Docker Image: `monachus/hugo`
* [Hugo Docker Image GitHub Repo](https://github.com/oskapt/docker-hugo)

## Deployment

### Concourse CI

### Pipeline Setup

#### Login to Concourse

```bash
fly -t opengood-io login -c http://concourse.opengood.io:8080 -k
```

#### Deploy Pipeline to Concourse

```bash
fly -t opengood-io set-pipeline -p opengood-io.github.io -c ci/pipeline.yml -l ci/credentials.yml
```

#### Pipeline Debugging

```bash
fly -t concourse intercept -j opengood-io.github.io/JOB_NAME
```

### Deployment Process

Concourse automatically publishes each Git commit to GitHub as a `static content Web site` to a GitHub pages branch.

## Distribution

`opengood-io.github.io` is generated via Hugo and distributed via GitHub Pages.

## Disclaimer

`opengood-io.github.io` is a Web site from the OpenGood.io library of OSS projects, frameworks, and solutions.
