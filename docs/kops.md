## Create a Kubernetes cluster using Kops

**Steps:**
1. Copy the [live-0 yaml](https://github.com/ministryofjustice/kubernetes-investigations/blob/master/kops/cloud-platform-live-0.yaml) into a new file for your new cluster in the [kops directory](https://github.com/ministryofjustice/kubernetes-investigations/tree/master/kops)
2. In the new yaml, change the `oidcClientID` and `oidcIssuerURL` to the values generated in Auth0 for the new cluster
3. Remove PR approval on master branch of [`Kubernetes-Investigations`](https://github.com/ministryofjustice/kubernetes-investigations) repository
```
https://github.com/ministryofjustice/kubernetes-investigations

Settings > Branches > Untick *Require pull request reviews before merging* > Save changes
```
4. PR the new yaml and self merge 
5. Check pipeline output in [CodePipeline](https://eu-west-1.console.aws.amazon.com/codepipeline/home?region=eu-west-1#/view/cluster-creation-pipeline)
6. Add back PR approval on the master branch
``` 
https://github.com/ministryofjustice/kubernetes-investigations

Settings > Branches > Tick *Require pull request reviews before merging* > Save changes
```


