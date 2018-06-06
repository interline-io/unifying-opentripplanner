# Unifying OpenTripPlanner

Fun fact: There are currently [645 forks](https://github.com/opentripplanner/OpenTripPlanner/network/members) of the main OpenTripPlanner repository on GitHub!

## Overview of Major Branches to Merge

_Click on box on the diagram to open the matching page on GitHub:_

<script src="https://unpkg.com/mermaid@7.1.0/dist/mermaid.min.js"></script>
<script>mermaid.initialize({startOnLoad:true});</script>
  <link rel="stylesheet" href="https://unpkg.com/mermaid@7.1.0/dist/mermaid.min.css">

<div class="mermaid">
graph LR
  A -->|1 conflict| D(entur:split_gtfs_and_internal_model <ul><li>adds NeTEx support</li><li>separates internal data model and data loader</li><li>enables addition of data loaders beyond GTFS</li></ul> )
  click A "https://github.com/opentripplanner/OpenTripPlanner"
  click D "https://github.com/opentripplanner/OpenTripPlanner/pull/2495"
  D -->|255 files changed| A 
  A[opentripplanner:master] -->|14 conflicts| B(camsys:vtrans-dev <ul><li> GTFS-flex support</li><li>uses custom onebusaway-vt</li></ul>)
  click B "https://github.com/opentripplanner/OpenTripPlanner/compare/master...camsys:vtrans-dev"
  B -->|82 files changed| A 
  A -->|3 conflicts| E(opentripplanner:trimet-dev <ul><li>TNC support</li><li>Expanded bike-share support</li></ul>)
  click E "https://github.com/opentripplanner/OpenTripPlanner/compare/trimet-dev"
  E -->|62 files changed| A 
  A -->|10 conflicts| C(camsys:mta-master <ul><li></li></ul>)
  C -->|191 files changed| A 
  click C "https://github.com/opentripplanner/OpenTripPlanner/compare/master...camsys:mta-master"
</div>

## Branches by directories and files changed

To work with all of these branches and forks locally, here's a [git config file](sample-git-config).

## entur:split_gtfs_and_internal_model

[Conflicts with opentripplanner:master](upstream-merge-diffs/entur.split_gtfs_and_internal_model+conveyal.master.diff)

Changes to merge into opentripplanner:master:
```
git diff opentripplanner/master --dirstat=files
   6.0% docs/
   3.5% src/main/java/org/opentripplanner/analyst/
   4.8% src/main/java/org/opentripplanner/api/adapters/
   4.8% src/main/java/org/opentripplanner/api/
   6.0% src/main/java/org/opentripplanner/graph_builder/annotation/
   5.4% src/main/java/org/opentripplanner/gtfs/mapping/
   8.0% src/main/java/org/opentripplanner/model/
   3.8% src/main/java/org/opentripplanner/profile/
   4.1% src/main/java/org/opentripplanner/routing/core/
   4.8% src/main/java/org/opentripplanner/routing/edgetype/
   3.2% src/main/java/org/opentripplanner/routing/vertextype/
   7.6% src/main/java/org/opentripplanner/routing/
   6.7% src/main/java/org/opentripplanner/updater/
  10.2% src/main/java/org/opentripplanner/
   5.1% src/test/java/org/opentripplanner/gtfs/mapping/
   3.2% src/test/java/org/opentripplanner/routing/core/
   4.8% src/test/java/org/opentripplanner/routing/
   4.1% src/test/java/org/opentripplanner/
```

## camsys:vtrans-dev

[Conflicts with opentripplanner:master](upstream-merge-diffs/camsys.vtrans-dev+conveyal.master.diff)

Changes to merge into opentripplanner:master:
```
git diff opentripplanner/master --dirstat=files
  12.8% docs/
   5.0% src/client/js/otp/locale/
   3.3% src/client/js/otp/
   4.4% src/main/java/org/opentripplanner/api/
   3.9% src/main/java/org/opentripplanner/graph_builder/module/osm/
   3.3% src/main/java/org/opentripplanner/graph_builder/module/
   3.3% src/main/java/org/opentripplanner/index/
   3.3% src/main/java/org/opentripplanner/routing/core/
   4.4% src/main/java/org/opentripplanner/routing/edgetype/flex/
   5.5% src/main/java/org/opentripplanner/routing/edgetype/
   4.4% src/main/java/org/opentripplanner/routing/impl/
   5.0% src/main/java/org/opentripplanner/routing/vertextype/
  11.1% src/main/java/org/opentripplanner/routing/
   3.3% src/main/java/org/opentripplanner/updater/bike_rental/
   7.2% src/main/java/org/opentripplanner/updater/
   7.8% src/main/java/org/opentripplanner/
   5.5% src/test/java/org/opentripplanner/
```

### opentripplanner:trimet-dev

[Conflicts with opentripplanner:master](upstream-merge-diffs/conveyal.trimet-dev+conveyal.master.diff)

Changes to merge into opentripplanner:master:
```
git diff opentripplanner/master --dirstat=files
  15.7% docs/
   3.7% src/main/java/org/opentripplanner/api/model/
   3.7% src/main/java/org/opentripplanner/api/resource/
   4.6% src/main/java/org/opentripplanner/routing/core/
   3.7% src/main/java/org/opentripplanner/routing/edgetype/
   3.7% src/main/java/org/opentripplanner/routing/impl/
   3.7% src/main/java/org/opentripplanner/routing/transportation_network_company/
   6.4% src/main/java/org/opentripplanner/routing/
   3.7% src/main/java/org/opentripplanner/updater/bike_rental/
   7.4% src/main/java/org/opentripplanner/updater/transportation_network_company/lyft/
   4.6% src/main/java/org/opentripplanner/updater/transportation_network_company/uber/
   3.7% src/main/java/org/opentripplanner/updater/transportation_network_company/
  11.1% src/main/java/org/opentripplanner/updater/
  10.1% src/main/java/org/opentripplanner/
   4.6% src/test/resources/updater/__files/
   4.6% src/
```

### camsys:mta-master

[Conflicts with opentripplanner:master](upstream-merge-diffs/camsys.mta-master+origin.master.diff)

Changes to merge into opentripplanner:master:
```
git diff opentripplanner/master --dirstat=files
   7.9% docs/
   3.3% src/main/java/org/opentripplanner/api/model/
  11.3% src/main/java/org/opentripplanner/api/resource/
   6.3% src/main/java/org/opentripplanner/graph_builder/module/
   3.7% src/main/java/org/opentripplanner/index/model/
   5.0% src/main/java/org/opentripplanner/routing/core/
   9.6% src/main/java/org/opentripplanner/routing/edgetype/
  15.9% src/main/java/org/opentripplanner/routing/
   3.3% src/main/java/org/opentripplanner/updater/stoptime/
   6.3% src/main/java/org/opentripplanner/updater/
  15.1% src/main/java/org/opentripplanner/
   3.7% src/test/java/org/opentripplanner/routing/
   3.3% src/test/java/org/opentripplanner/
```

----

[Edit this page](https://github.com/interline-io/unifying-opentripplanner/edit/master/README.md)
