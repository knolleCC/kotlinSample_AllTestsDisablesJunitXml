# Kotlin Sample: allTests task disables junitXml generation

Behavior with Kotlin 1.3.61:
`allTests` task runs `jvmTest` but does not respect the `reports.junitXml.enabled` property. 

1. Run `clean` + `jvmTest`:
   * `jvmTest.reports.junitXml.enabled = true` (see build output)
   * build/test-results/jvmTest contains junitXml file
2. Run `clean` + `allTests`:
   * `jvmTest.reports.junitXml.enabled = false` (see build output)
   * build/test-results/jvmTest contains no junitXml file

Expected behavior:
`allTests` should not change any property of `jvmTest`.
