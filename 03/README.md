# Chapter 3: Namespaces

Try if you can get the exercises done. You can find more information in the `sources` directory.


## Exercise 1:

1. Try to create a namespace called `development`
2. Try to apply the manifest called `webserver.yaml` into the namespace `development` without modifying the manifest file.
3. Check if the pod called `webserver` is running in the namespace `development`

## Exercise 2:
1. Try to apply the manifest called `databaseserver.yaml` into the namespace `development`. Do this by changing the manifest `databaseserver.yaml` and try to apply it.
2. Check if the `databaseserver.yaml` manifest is correctly applied in the `development` namespace.
3. Check if the pod called `postgres` is started in the namespace `development`.

## Exercise 3:

1. Create a namespace called `acceptance`.
2. Change your context so `acceptance` is your default namespace.
3. try to apply the `webserver.yaml` directly into this namespace.
4. delete the namespace called `acceptance` and `development`
5. Change your context so `default` is your default namespace again.




