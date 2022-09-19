
# Jimpad - Digital Resume

https://jimpad.netlify.app/ || https://ibb.co/3m1cvGg

# Powered by **Netlify**

Netlify lets you link a **GitHub**, **GitLab**, **Bitbucket**, or **Azure DevOps** repository to a site for *continuous deployment*.

Each time you push to your Git provider, Netlify runs a build with your tool of choice and deploys the result to our powerful CDN.

## Basic build settings

With continuous deployment configured, you can specify how Netlify will build your site by going to Site settings > Build & deploy > Continuous Deployment > Build settings.

From Build settings, you can set a base directory, add a build command, and specify a publish directory. For public repos, you can also toggle your deploy log visibility.

With continuous deployment, builds are active by default. You can stop or activate builds at will for more control of your workflow.

You can link an existing site to a Git repository, change the currently linked repository, or unlink a repository by going to Site settings > Build & deploy > Continuous Deployment > Repository in the Netlify UI. Alternatively, you can use the Netlify CLI.

You can also specify some of these build settings and others in a configuration file, which allows you to change your settings depending on the deploy context. The configuration file settings override build settings specified in the UI.

## Definitions

***Base directory***: optional field for linking monorepos or sites built from a subdirectory of a repository. It specifies the directory that our buildbot changes to before starting a build. It’s where our build system checks for dependency management files such as package.json or .nvmrc. If not set, the base directory defaults to the root of the repository.

***Build command***: where you should specify the command to run to build your site if you are using a static site generator or other build tool. For example, npm run build. The build command runs in the Bash shell, allowing you to add Bash-⁠compatible syntax to the command. Visit the frameworks doc to learn about typical settings for popular tools.

***Publish directory***: directory (relative to the root of your repo) that contains the deploy-ready HTML files and assets generated by the build. If a base directory has been specified, it should be included in the publish directory path. For example, if your base directory is set to site, the publish directory should include the site/ prefix like so: site/public. Visit the frameworks doc to learn about typical settings for popular tools.

***Deploy log visibility***: privacy level for the deploy logs for a site linked to a public repo. The default setting Public logs makes deploy logs available to anyone with a deploy detail URL. You can limit deploy log access to site members by selecting Private logs.

***Active builds***: used to indicate when builds are active. Netlify builds your site according to your continuous deployment settings when you push to your Git provider.

***Stopped builds***: used to indicate when builds are stopped. Netlify will never build your site. You can build your site locally instead using Netlify CLI and then publish new deploys manually with the CLI or the API.

## Build image selection

When a build is triggered on Netlify, ***our buildbot starts a Docker container running a build image***. The build image is a snapshot of an operating system that has various software tools and other settings preinstalled and configured.

All Netlify build images are stored in a public GitHub repository. The repository README includes a list of available images and instructions for testing locally.

Although all new Netlify sites use a default build image, you can select from multiple images with different operating system and software versions. You might choose a different build image to meet a software requirement for your build tool, to try out experimental pre-release build features, or to keep up-to-date with the included operating system environment. Build image selection also enables Netlify to release breaking changes into the build image while allowing you to accommodate those changes with time to upgrade.

***We recommend upgrading to the most recent build image regularly to take advantage of the latest features and security enhancements.***

To change the build image for a site, go to Site settings > Build & deploy > Continuous Deployment > Build image selection, and select the build image you would like to use. Our buildbot will use this image for all production deploys, branch deploys, and Deploy Previews.

## Build image defaults and project dependencies

Each build image has a set of software with pre-defined default versions. You can customize these defaults.

During your project’s first build, we pin a version of Node, Ruby, Go, and Yarn that matches the default version installed on the build image. These pinned versions are stored in your project’s repository object, associating those pinned versions with your project’s Git repository. This ensures your project’s software versions will not be affected if the build image’s defaults change.
