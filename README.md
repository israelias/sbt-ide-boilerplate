# SBT IDE Boilerplate

## Configs
* Use Java 11
  * `brew install openjdk@11`
* Link the brew to jvm
  * `sudo ln -sfn /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk`
* Add 11 to home path
  * `echo 'export PATH="/opt/homebrew/opt/openjdk@11/bin:$PATH"' >> ~/.zshrc`
* Install sbt
  * `brew install sbt`
* Use latest sbt version in new project
  * `cd sbt-ide-boilerplate`
  * `sbt`
  * `sbt:sbt-ide-boilerplate> set scalaVersion := "2.13.10"`
* Seed a template
  * `sbt new scala/scala-seed.g8`

## References
* [scala](https://www.scala-lang.org/download/)
* [scala-sbt](https://www.scala-sbt.org/)