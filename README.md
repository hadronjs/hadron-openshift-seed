
## Deploy Hadron on OpenShift PaaS in 5 minutes

With this seed project you will be able to get your [Hadron](https://github.com/hadronjs/hadron) blog up and running
on the OpenShift PaaS in around 5 minutes (...and for free BTW).

* Create a free account at [http://openshift.redhat.com](http://openshift.redhat.com) if you don't have one yet.
* Install the `rhc` utility for your platform([instructions](https://www.openshift.com/developers/rhc-client-tools-install)).
* Create a namespace, if you haven't already done so
```
$ rhc domain create <yournamespace>
```

* Create a `nodejs-0.10` application (you can name it anything via `-a`)
```
$ rhc app create -a hadron -t nodejs-0.10
```

* Checkout the `hadron-seed` repository
```
$ cd hadron
$ git remote add hadron-seed -m master git://github.com/hadronjs/hadron-seed.git
$ git pull -s recursive -X theirs hadron-seed master
```

* Checkout the `hadron-openshift` repository
```
$ git remote add hadron-openshift -m master git://github.com/hadronjs/hadron-openshift-seed.git
$ git pull -s recursive -X theirs hadron-openshift master
```

* Then push the repo to OpenShift
```
$ git push
```

* That's it, you can now access Hadron at http://hadron-$yournamespace.rhcloud.com

