
This module provides methods useful for crafting the basic Dispatch pipeline resources in Starlark.

### imageResource(name, url, digest, pipeline)


Define a new image resource in a pipeline.

Example usage: `imageResource("my-image", url="mesosphere/dispatch:latest")`


### volume(name, **kwargs)


Create a new volume given a volume source.


### secretVar(name, key)


Convenience function for adding an environment variable from a Kubernetes secret.

Example usage: `k8s.corev1.EnvVar(name="GITHUB_TOKEN", valueFrom=secretVar("scmtoken", "password"))`


### clean(name)


Sanitize a name for passing in to Kubernetes / Dispatch.


### push(**kwargs)


A sugar function for creating a new push condition.

Example usage: `action(tasks = ["test"], on = push(branches = ["master"]))`


### gitResource(name, url, revision, pipeline)


Define a new git resource in a pipeline.

Example usage: `gitResource("git", url="$(context.git.url)", revision="$(context.git.commit)")`


### storageResource(name)


Create a new S3 resource using the Dispatch default s3 configuration file.


### tag(**kwargs)


A sugar function for creating a new tag condition.

Example usage: `action(tasks = ["test"], on = tag())`


### pullRequest(**kwargs)


A sugar function for creating a new pull request condition.

Example usage: `action(tasks = ["test"], on = pullRequest(chatops=["build"]))`


### resourceVar(name, key)


Shorthand for a resource variable, returns a string "$(inputs.resources.<name>.<key>)"


