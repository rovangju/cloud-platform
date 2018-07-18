## Create a Kubernetes cluster using Kops

**Steps:**
1. Copy the [cloud-platform-live-0.yaml](https://github.com/ministryofjustice/kubernetes-investigations/blob/master/kops/cloud-platform-live-0.yaml) into a new file in the [kops directory](https://github.com/ministryofjustice/kubernetes-investigations/tree/master/kops). Name the file the name of the cluster. For this example, we'll use `cloud-platform-disaster-recovery-0.yaml`. 
2. In the `cloud-platform-disaster-recovery-0.yaml`, change the `oidcClientID` and `oidcIssuerURL` to the values generated in Auth0 for the new cluster

**Note: If launching in another region other than `eu-west-1`, the region should be changed where necessary in `cloud-platform-disaster-recovery-0.yaml`**

3. Remove the PR approval on the master branch of [`kubernetes-investigations`](https://github.com/ministryofjustice/kubernetes-investigations)
```
https://github.com/ministryofjustice/kubernetes-investigations

Settings > Branches > Untick 'Require pull request reviews before merging' > Save changes
```
4. PR the 'new' yaml to master and self merge. The merge to master kicks off cluster creation.
5. Check the pipeline output in [CodePipeline](https://eu-west-1.console.aws.amazon.com/codepipeline/home?region=eu-west-1#/view/cluster-creation-pipeline)
6. Rollback to PR approval on the master branch
``` 
https://github.com/ministryofjustice/kubernetes-investigations

Settings > Branches > Tick 'Require pull request reviews before merging' > Save changes
```


