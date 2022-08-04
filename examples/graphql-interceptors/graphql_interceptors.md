# Interceptors

The GraphQL `interceptors` can be used to execute custom logic before and after the resolver function gets invoked.
It can be defined as a read-only service class, which infers the `graphql:Interceptor` service object. The interceptor
service class should have the implementation of the `execute(graphql:Context context, graphql:Field 'field)`
remote method which is provided by the interceptor service object. The custom logic can be included in this remote
method. The interceptors should be provided using the `graphql:ServiceConfig` parameter named `interceptors` which
accepts an array of interceptor instances.
<br/>
Interceptors follow the `onion principle` when executing. Also, the inserting order of the interceptor instances into
the array will be the execution order of the Interceptors.
</br>
For more information on the underlying package, see the
[`graphql` package](https://lib.ballerina.io/ballerina/graphql/latest/).

::: code graphql_interceptors.bal :::

::: out graphql_interceptors.client.out :::

::: out graphql_interceptors.server.out :::