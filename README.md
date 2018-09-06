# application.conf merge bug reproducer 

This project is a reproducer for https://github.com/lightbend/sbt-reactive-app/issues/148

While that bug is fixed there are possible workarounds:

1. avoid using `application.conf` in projects not managed by `sbt-reactive-app` directly and prefer `reference.conf` (consider your utility projects like libraries)
2. avoid using `application.conf` in projects not managed by `sbt-reactive-app` directly. Instead, use unique names (`my-fancy-module.conf`, `utils-lib.conf`, ...) and include them explicitly from the `application.conf` in your service using HOCON's `include`.
