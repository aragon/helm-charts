## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add aragon https://aragon.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
aragon` to see the charts.

## Labels
To better differentiate the charts different services/applications which are usually deployed from a monorepo, each deployment/statefulset/cronjob/etc gets a label called `aragon.org/application` which defines the actual service name.

### For example
court-backend generates 3 deployements (if all are activated in the values.yaml). Each deployement will add the label `aragon.org/application` with the values `"chart.name" + "-service"`,`"chart.name" + "-server"` or `"chart.name" + "-app"`.  
  
chart name can be overwritten by the values `nameOverride` in the `values.yaml`.