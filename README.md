Rebuilding artifacts from (Maven) Central Repository
====================================================

[![Reproducible Builds](https://reproducible-builds.org/images/logos/rb.svg) an independently-verifiable path from source to binary code](https://reproducible-builds.org/)

As part of [Reproducible Builds efforts for the JVM](https://reproducible-builds.org/docs/jvm/), this "**Reproducible Central**" project is an attempt at:
1. writing [`.buildspec`rebuild instructions](BUILDSPEC.md) for the artifacts available in the [Central Repository](https://search.maven.org/),
equivalent to the packaging instructions that are maintained by every Linux distribution
(for example Debian's [debian/rules](https://www.debian.org/doc/debian-policy/ch-source#s-debianrules) or ArchLinux's PKGBUILD), whatever the build tool used (Central Repository is not used by Maven only)
2. show the level of reproducibility obtained using previous instructions: how many output files from the rebuild are strictly equal to reference in Central Repository, how many output files are not yet reproducible and should be improved before the next release?

## What Can I Do?

<details><summary><b>Rebuild Yourself To Check Results</b></summary>

 - <details><summary><b>Prerequisites</b></summary>
    
    * [Docker](https://www.docker.com)
    
    * `dos2unix` - DOS to MAC/UNIX text file format converter. 
      
      Can be installed via [homebrew](https://brew.sh) on MAC via: `brew install dos2unix`.
   </details>

You can rebuild a project release by running:
```
./rebuild.sh content/<path/to/...>/<project>-<version>.buildspec
```
`rebuild.sh` script will use the build specification file (= [`.buildspec` file](BUILDSPEC.md)) to choose a Docker image to rebuild the project and check output against Central Repository reference binaries.

</details>

<details><summary><b>Contribute A New `.buildspec`</b></summary>

If you know a project released to Central Repository that is expected to provide Reproducible Builds, please tell us by opening an issue with details.

You can also choose one from our [list of projects waiting for a `.buildspec`](https://github.com/jvm-repo-rebuild/reproducible-central/labels/buildspec): follow our [instructions to write a new `.buildspec`)](BUILDSPEC.md#writing-a-new-buildspec) that you can contribute back with a PR.

</details>

<details><summary><b>Improve Reproducibility Score Of A Project Release</b></summary>

If a rebuild published here is not fully reproducible (it has some :warning:), there is an issue: please help to improve the situation.

You'll need to rebuild the release yourself (see previous instructions), then use [diffoscope](https://diffoscope.org/) :mag: to easily explore precise difference
between reference file from Central Repository and effective rebuild file, then debug up to the root cause of this unwanted difference:
- rebuilder bug: if the improvement has to happen at [buildspec](BUILDSPEC.md) or [rebuild script](rebuild.sh) level, don't hesitate to open an issue or a PR here,
- upstream project reproducibility issue :memo:: please contact the upstream project and help them improve the reproducibility for their next release, creating an issue in their issue tracker and adding it to Reproducible Central buildspec as `issue` parameter that will link to it with a :memo:.

</details>

<details><summary><b>Add Reproducible Builds Badge to a Project With Reproducible Releases</b></summary>

If a project has listed here at least one release with proven reproducibility success, it can add a badge like ![Reproducible Builds](https://img.shields.io/badge/Reproducible_Builds-ok-success?labelColor=1e5b96) pointing to its entries here:

```
[![Reproducible Builds](https://img.shields.io/badge/Reproducible_Builds-ok-success?labelColor=1e5b96)](https://github.com/jvm-repo-rebuild/reproducible-central#...groupId...:...artifactId...)
```

Notice the anchor in the link.

</details>

## Rebuild Results

Nightly Rebuild: [![CircleCI](https://circleci.com/gh/jvm-repo-rebuild/reproducible-central/tree/master.svg?style=shield)](https://circleci.com/gh/jvm-repo-rebuild/reproducible-central/tree/master)

<!-- BEGIN GENERATED INTRO -->
rebuilding **766 releases** of **242 projects**:
- **517** releases were found successfully **fully reproducible** (100% reproducible artifacts :heavy_check_mark:),
- 249 had issues (some unreproducible artifacts :warning:):

<!-- END GENERATED INTRO -->

<!-- BEGIN GENERATED RESULTS TABLE -->
| [Central Repository](https://search.maven.org/) groupId | artifactId(s) | versions | [result](https://reproducible-builds.org/docs/jvm/): reproducible? |
| ----------------- | --------------- | --------- | -------- |
| biz.aQute.bnd | <a name='biz.aQute.bnd:bnd-plugin-parent'></a>[bnd-plugin-parent](content/biz/aQute/bnd/plugins/README.md) | 5 | 5 :heavy_check_mark: |
| ch.qos.logback | <a name='ch.qos.logback:logback-parent'></a>[logback-parent](content/ch/qos/logback/README.md) | 3 | 1 :heavy_check_mark: / 2 :warning: |
| ch.qos.reload4j | <a name='ch.qos.reload4j:reload4j'></a>[reload4j](content/ch/qos/reload4j/README.md) | 2 | 2 :warning: |
| com.adobe.acs | <a name='com.adobe.acs:acs-aem-commons'></a>[acs-aem-commons](content/com/adobe/acs/aem-commons/README.md) | 1 | 1 :warning: |
| com.github.adangel.liquibase.ext | <a name='com.github.adangel.liquibase.ext:liquibase-percona'></a>[liquibase-percona](content/com/github/adangel/liquibase/ext/liquibase-percona/README.md) | 1 | 1 :heavy_check_mark: |
| com.github.ldapchai | <a name='com.github.ldapchai:ldapchai'></a>[ldapchai](content/com/github/ldapchai/README.md) | 4 | 4 :warning: |
| com.github.package-url | <a name='com.github.package-url:packageurl-java'></a>[packageurl-java](content/com/github/package-url/packageurl-java/README.md) | 3 | 3 :heavy_check_mark: |
| com.github.veithen.maven | <a name='com.github.veithen.maven:java-format-maven-plugin'></a>[java-format-maven-plugin](content/com/github/veithen/maven/java-format-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| com.github.veithen | <a name='com.github.veithen:parent'></a>[parent](content/com/github/veithen/parent/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| com.io7m.jade | <a name='com.io7m.jade:com.io7m.jade'></a>[com.io7m.jade](content/com/io7m/jade/README.md) | 1 | 1 :warning: |
| com.ongres.stringprep | <a name='com.ongres.stringprep:parent'></a>[parent](content/com/ongres/stringprep/README.md) | 1 | 1 :warning: |
| com.scalapenos | <a name='com.scalapenos:stamina_2.11'></a>[stamina_2.11](content/com/scalapenos/stamina/README.md) | 2 | 2 :heavy_check_mark: |
| com.taobao.arthas | <a name='com.taobao.arthas:arthas-all'></a>[arthas-all](content/com/taobao/arthas/README.md) | 14 | 14 :warning: |
| fr.vidal.oss | <a name='fr.vidal.oss:atom-jaxb'></a>[atom-jaxb](content/fr/vidal/oss/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| io.dropwizard | <a name='io.dropwizard:dropwizard-project'></a>[dropwizard-project](content/io/dropwizard/core/README.md) | 26 | 23 :heavy_check_mark: / 3 :warning: |
| io.dropwizard.metrics | <a name='io.dropwizard.metrics:metrics-parent'></a>[metrics-parent](content/io/dropwizard/metrics/README.md) | 25 | 11 :heavy_check_mark: / 14 :warning: |
| io.dropwizard.metrics5 | <a name='io.dropwizard.metrics5:metrics-parent'></a>[metrics-parent](content/io/dropwizard/metrics5/README.md) | 6 | 1 :heavy_check_mark: / 5 :warning: |
| io.fabric8 | <a name='io.fabric8:docker-maven-plugin'></a>[docker-maven-plugin](content/io/fabric8/docker-maven-plugin/README.md) | 8 | 6 :heavy_check_mark: / 2 :warning: |
| | <a name='io.fabric8:kubernetes-client-project'></a>[kubernetes-client-project](content/io/fabric8/kubernetes-client/README.md) | 7 | 7 :warning: |
| io.github.albertus82 | <a name='io.github.albertus82:jface-utils'></a>[jface-utils](content/io/github/albertus82/jface-utils/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| | <a name='io.github.albertus82:unexepack'></a>[unexepack](content/io/github/albertus82/unexepack/README.md) | 3 | 3 :warning: |
| io.github.derkrischan | <a name='io.github.derkrischan:jpdftest'></a>[jpdftest](content/io/github/derkrischan/jpdftest/README.md) | 3 | 3 :heavy_check_mark: |
| io.liftwizard | <a name='io.liftwizard:liftwizard'></a>[liftwizard](content/io/liftwizard/README.md) | 22 | 22 :heavy_check_mark: |
| io.micronaut.build | <a name='io.micronaut.build:micronaut-maven-plugin'></a>[micronaut-maven-plugin](content/io/micronaut/build/micronaut-maven-plugin/README.md) | 19 | 19 :heavy_check_mark: |
| io.wcm | <a name='io.wcm:io.wcm.caconfig.editor.parent'></a>[*.caconfig.editor.parent](content/io/wcm/caconfig/README.md) | 4 | 4 :warning: |
| | <a name='io.wcm:io.wcm.handler.richtext'></a>[*.handler.richtext](content/io/wcm/handler/README.md) | 7 | 1 :heavy_check_mark: / 6 :warning: |
| io.wcm.maven.plugins | <a name='io.wcm.maven.plugins:nodejs-maven-plugin'></a>[nodejs-maven-plugin](content/io/wcm/maven/plugins/nodejs-maven-plugin/README.md) | 1 | 1 :warning: |
| io.wcm.tooling.commons | <a name='io.wcm.tooling.commons:io.wcm.tooling.commons.content-package-builder'></a>[*.content-package-builder](content/io/wcm/tooling/README.md) | 3 | 3 :heavy_check_mark: |
| io.wcm | <a name='io.wcm:io.wcm.wcm.ui.clientlibs'></a>[*.wcm.ui.clientlibs](content/io/wcm/wcm/README.md) | 8 | 6 :heavy_check_mark: / 2 :warning: |
| net.nicoulaj.maven.plugins | <a name='net.nicoulaj.maven.plugins:checksum-maven-plugin'></a>[checksum-maven-plugin](content/net/nicoulaj/maven/plugins/checksum-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| net.sourceforge.pmd | <a name='net.sourceforge.pmd:pmd'></a>[pmd](content/net/sourceforge/pmd/README.md) | 20 | 19 :heavy_check_mark: / 1 :warning: |
| nl.hsac | <a name='nl.hsac:hsac-fitnesse-fixtures'></a>[hsac-fitnesse-fixtures](content/nl/hsac/hsac-fitnesse-fixtures/README.md) | 24 | 13 :heavy_check_mark: / 11 :warning: |
| org.apache.accumulo | <a name='org.apache.accumulo:accumulo'></a>[accumulo](content/org/apache/accumulo/README.md) | 3 | 3 :warning: |
| org.apache.activemq | <a name='org.apache.activemq:activemq-parent'></a>[activemq-parent](content/org/apache/activemq/README.md) | 2 | 2 :warning: |
| org.apache.any23 | <a name='org.apache.any23:apache-any23'></a>[apache-any23](content/org/apache/any23/README.md) | 1 | 1 :warning: |
| org.apache | <a name='org.apache:apache'></a>[apache](content/org/apache/apache/README.md) | 3 | 2 :heavy_check_mark: / 1 :warning: |
| org.apache.aries.cdi | <a name='org.apache.aries.cdi:org.apache.aries.cdi'></a>[org.apache.aries.cdi](content/org/apache/aries/cdi/README.md) | 1 | 1 :warning: |
| org.apache.camel | <a name='org.apache.camel:camel'></a>[camel](content/org/apache/camel/camel/README.md) | 1 | 1 :warning: |
| org.apache.cxf.fediz | <a name='org.apache.cxf.fediz:fediz'></a>[fediz](content/org/apache/cxf/fediz/README.md) | 1 | 1 :warning: |
| org.apache.drill | <a name='org.apache.drill:drill-root'></a>[drill-root](content/org/apache/drill/README.md) | 1 | 1 :warning: |
| org.apache.dubbo | <a name='org.apache.dubbo:dubbo'></a>[dubbo](content/org/apache/dubbo/README.md) | 4 | 4 :warning: |
| org.apache.felix | <a name='org.apache.felix:org.apache.felix.feature'></a>[*.feature](content/org/apache/felix/features/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.felix:org.apache.felix.http.parent'></a>[*.http.parent](content/org/apache/felix/http/parent/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.felix:maven-bundle-plugin'></a>[maven-bundle-plugin](content/org/apache/felix/maven-bundle-plugin/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.felix:felix-parent'></a>[felix-parent](content/org/apache/felix/pom/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.httpcomponents | <a name='org.apache.httpcomponents:httpcomponents-parent'></a>[httpcomponents-parent](content/org/apache/httpcomponents/parent/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.jackrabbit | <a name='org.apache.jackrabbit:filevault-package-maven-plugin'></a>[filevault-package-maven-plugin](content/org/apache/jackrabbit/filevault-package-maven-plugin/README.md) | 5 | 5 :heavy_check_mark: |
| org.apache.jackrabbit.vault | <a name='org.apache.jackrabbit.vault:jackrabbit-filevault'></a>[jackrabbit-filevault](content/org/apache/jackrabbit/filevault/README.md) | 7 | 7 :warning: |
| org.apache.jena | <a name='org.apache.jena:jena'></a>[jena](content/org/apache/jena/jena/README.md) | 8 | 8 :warning: |
| org.apache.jspwiki | <a name='org.apache.jspwiki:jspwiki-builder'></a>[jspwiki-builder](content/org/apache/jspwiki/README.md) | 5 | 5 :warning: |
| org.apache.karaf | <a name='org.apache.karaf:decanter'></a>[decanter](content/org/apache/karaf/decanter/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.karaf:karaf'></a>[karaf](content/org/apache/karaf/karaf/README.md) | 2 | 2 :warning: |
| org.apache.logging | <a name='org.apache.logging:logging-parent'></a>[logging-parent](content/org/apache/logging/parent/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| org.apache.maven.archetype | <a name='org.apache.maven.archetype:maven-archetype'></a>[maven-archetype](content/org/apache/maven/archetype/README.md) | 2 | 2 :heavy_check_mark: |
| org.apache.maven.doxia | <a name='org.apache.maven.doxia:doxia-sitetools'></a>[doxia-sitetools](content/org/apache/maven/doxia/doxia-sitetools/README.md) | 5 | 5 :heavy_check_mark: |
| | <a name='org.apache.maven.doxia:doxia'></a>[doxia](content/org/apache/maven/doxia/doxia/README.md) | 5 | 5 :heavy_check_mark: |
| org.apache.maven.indexer | <a name='org.apache.maven.indexer:maven-indexer'></a>[maven-indexer](content/org/apache/maven/indexer/README.md) | 1 | 1 :warning: |
| org.apache.maven.jxr | <a name='org.apache.maven.jxr:jxr'></a>[jxr](content/org/apache/maven/jxr/README.md) | 2 | 2 :heavy_check_mark: |
| org.apache.maven | <a name='org.apache.maven:maven'></a>[maven](content/org/apache/maven/maven/README.md) | 6 | 3 :heavy_check_mark: / 3 :warning: |
| | <a name='org.apache.maven:maven-parent'></a>[maven-parent](content/org/apache/maven/parent/README.md) | 2 | 2 :warning: |
| org.apache.maven.plugin-tools | <a name='org.apache.maven.plugin-tools:maven-plugin-tools'></a>[maven-plugin-tools](content/org/apache/maven/plugin-tools/maven-plugin-tools/README.md) | 3 | 3 :heavy_check_mark: |
| org.apache.maven.plugins | <a name='org.apache.maven.plugins:maven-antrun-plugin'></a>[maven-antrun-plugin](content/org/apache/maven/plugins/maven-antrun-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-artifact-plugin'></a>[maven-artifact-plugin](content/org/apache/maven/plugins/maven-artifact-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-assembly-plugin'></a>[maven-assembly-plugin](content/org/apache/maven/plugins/maven-assembly-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-checkstyle-plugin'></a>[maven-checkstyle-plugin](content/org/apache/maven/plugins/maven-checkstyle-plugin/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-compiler-plugin'></a>[maven-compiler-plugin](content/org/apache/maven/plugins/maven-compiler-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-dependency-plugin'></a>[maven-dependency-plugin](content/org/apache/maven/plugins/maven-dependency-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-deploy-plugin'></a>[maven-deploy-plugin](content/org/apache/maven/plugins/maven-deploy-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-ear-plugin'></a>[maven-ear-plugin](content/org/apache/maven/plugins/maven-ear-plugin/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-ejb-plugin'></a>[maven-ejb-plugin](content/org/apache/maven/plugins/maven-ejb-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.maven.enforcer | <a name='org.apache.maven.enforcer:enforcer'></a>[enforcer](content/org/apache/maven/plugins/maven-enforcer-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.maven.plugins | <a name='org.apache.maven.plugins:maven-gpg-plugin'></a>[maven-gpg-plugin](content/org/apache/maven/plugins/maven-gpg-plugin/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.maven.plugins:maven-invoker-plugin'></a>[maven-invoker-plugin](content/org/apache/maven/plugins/maven-invoker-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-jar-plugin'></a>[maven-jar-plugin](content/org/apache/maven/plugins/maven-jar-plugin/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-javadoc-plugin'></a>[maven-javadoc-plugin](content/org/apache/maven/plugins/maven-javadoc-plugin/README.md) | 4 | 2 :heavy_check_mark: / 2 :warning: |
| | <a name='org.apache.maven.plugins:maven-jlink-plugin'></a>[maven-jlink-plugin](content/org/apache/maven/plugins/maven-jlink-plugin/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-pdf-plugin'></a>[maven-pdf-plugin](content/org/apache/maven/plugins/maven-pdf-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-pmd-plugin'></a>[maven-pmd-plugin](content/org/apache/maven/plugins/maven-pmd-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-project-info-reports-plugin'></a>[maven-project-info-reports-plugin](content/org/apache/maven/plugins/maven-project-info-reports-plugin/README.md) | 5 | 4 :heavy_check_mark: / 1 :warning: |
| | <a name='org.apache.maven.plugins:maven-release-plugin'></a>[maven-release-plugin](content/org/apache/maven/plugins/maven-release-plugin/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-resources-plugin'></a>[maven-resources-plugin](content/org/apache/maven/plugins/maven-resources-plugin/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.maven.plugins:maven-scm-publish-plugin'></a>[maven-scm-publish-plugin](content/org/apache/maven/plugins/maven-scm-publish-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-scripting-plugin'></a>[maven-scripting-plugin](content/org/apache/maven/plugins/maven-scripting-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-shade-plugin'></a>[maven-shade-plugin](content/org/apache/maven/plugins/maven-shade-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-site-plugin'></a>[maven-site-plugin](content/org/apache/maven/plugins/maven-site-plugin/README.md) | 4 | 2 :heavy_check_mark: / 2 :warning: |
| | <a name='org.apache.maven.plugins:maven-source-plugin'></a>[maven-source-plugin](content/org/apache/maven/plugins/maven-source-plugin/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.maven.plugins:maven-war-plugin'></a>[maven-war-plugin](content/org/apache/maven/plugins/maven-war-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.plugins:maven-wrapper-plugin'></a>[maven-wrapper-plugin](content/org/apache/maven/plugins/maven-wrapper-plugin/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| org.apache.maven.reporting | <a name='org.apache.maven.reporting:maven-reporting-api'></a>[maven-reporting-api](content/org/apache/maven/reporting/maven-reporting-api/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.reporting:maven-reporting-exec'></a>[maven-reporting-exec](content/org/apache/maven/reporting/maven-reporting-exec/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.reporting:maven-reporting-impl'></a>[maven-reporting-impl](content/org/apache/maven/reporting/maven-reporting-impl/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.maven.resolver | <a name='org.apache.maven.resolver:maven-resolver-ant-tasks'></a>[maven-resolver-ant-tasks](content/org/apache/maven/resolver/maven-resolver-ant-tasks/README.md) | 4 | 4 :heavy_check_mark: |
| | <a name='org.apache.maven.resolver:maven-resolver'></a>[maven-resolver](content/org/apache/maven/resolver/maven-resolver/README.md) | 8 | 7 :heavy_check_mark: / 1 :warning: |
| org.apache.maven.scm | <a name='org.apache.maven.scm:maven-scm'></a>[maven-scm](content/org/apache/maven/scm/README.md) | 4 | 4 :heavy_check_mark: |
| org.apache.maven | <a name='org.apache.maven:maven-archiver'></a>[maven-archiver](content/org/apache/maven/shared/maven-archiver/README.md) | 2 | 2 :heavy_check_mark: |
| org.apache.maven.shared | <a name='org.apache.maven.shared:maven-artifact-transfer'></a>[maven-artifact-transfer](content/org/apache/maven/shared/maven-artifact-transfer/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.maven.shared:maven-common-artifact-filters'></a>[maven-common-artifact-filters](content/org/apache/maven/shared/maven-common-artifact-filters/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-dependency-analyzer'></a>[maven-dependency-analyzer](content/org/apache/maven/shared/maven-dependency-analyzer/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-dependency-tree'></a>[maven-dependency-tree](content/org/apache/maven/shared/maven-dependency-tree/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-filtering'></a>[maven-filtering](content/org/apache/maven/shared/maven-filtering/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.maven.shared:maven-invoker'></a>[maven-invoker](content/org/apache/maven/shared/maven-invoker/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-script-interpreter'></a>[maven-script-interpreter](content/org/apache/maven/shared/maven-script-interpreter/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-shared-resources'></a>[maven-shared-resources](content/org/apache/maven/shared/maven-shared-resources/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-shared-utils'></a>[maven-shared-utils](content/org/apache/maven/shared/maven-shared-utils/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.maven.shared:maven-verifier'></a>[maven-verifier](content/org/apache/maven/shared/maven-verifier/README.md) | 3 | 3 :heavy_check_mark: |
| org.apache.maven.skins | <a name='org.apache.maven.skins:maven-fluido-skin'></a>[maven-fluido-skin](content/org/apache/maven/skins/fluido/README.md) | 2 | 2 :heavy_check_mark: |
| org.apache.maven.surefire | <a name='org.apache.maven.surefire:surefire'></a>[surefire](content/org/apache/maven/surefire/README.md) | 1 | 1 :warning: |
| org.apache.maven.wagon | <a name='org.apache.maven.wagon:wagon'></a>[wagon](content/org/apache/maven/wagon/wagon/README.md) | 6 | 6 :heavy_check_mark: |
| org.apache.maven.wrapper | <a name='org.apache.maven.wrapper:maven-wrapper-parent'></a>[maven-wrapper-parent](content/org/apache/maven/wrapper/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.ftpserver | <a name='org.apache.ftpserver:ftpserver-parent'></a>[ftpserver-parent](content/org/apache/mina/ftpserver/README.md) | 1 | 1 :warning: |
| org.apache.mina | <a name='org.apache.mina:mina-parent'></a>[mina-parent](content/org/apache/mina/README.md) | 1 | 1 :warning: |
| org.apache.plc4x.plugins | <a name='org.apache.plc4x.plugins:plc4x-code-generaton'></a>[plc4x-code-generaton](content/org/apache/plc4x/plc4x-code-generation/README.md) | 1 | 1 :heavy_check_mark: |
| org.apache.plc4x | <a name='org.apache.plc4x:plc4x-parent'></a>[plc4x-parent](content/org/apache/plc4x/plc4x/README.md) | 1 | 1 :warning: |
| org.apache.royale.compiler | <a name='org.apache.royale.compiler:compiler'></a>[compiler](content/org/apache/royale/compiler/README.md) | 1 | 1 :warning: |
| org.apache.shiro | <a name='org.apache.shiro:shiro-root'></a>[shiro-root](content/org/apache/shiro/README.md) | 1 | 1 :warning: |
| org.apache.sling | <a name='org.apache.sling:htl-maven-plugin'></a>[htl-maven-plugin](content/org/apache/sling/htl-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:jspc-maven-plugin'></a>[jspc-maven-plugin](content/org/apache/sling/jspc-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.adapter'></a>[*.adapter](content/org/apache/sling/org.apache.sling.adapter/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.api'></a>[*.api](content/org/apache/sling/org.apache.sling.api/README.md) | 4 | 4 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.auth.core'></a>[*.auth.core](content/org/apache/sling/org.apache.sling.auth.core/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.bundleresource.impl'></a>[*.bundleresource.impl](content/org/apache/sling/org.apache.sling.bundleresource.impl/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.caconfig.api'></a>[*.caconfig.api](content/org/apache/sling/org.apache.sling.caconfig.api/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.caconfig.impl'></a>[*.caconfig.impl](content/org/apache/sling/org.apache.sling.caconfig.impl/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.caconfig.spi'></a>[*.caconfig.spi](content/org/apache/sling/org.apache.sling.caconfig.spi/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.commons.content.analyzing'></a>[*.commons.content.analyzing](content/org/apache/sling/org.apache.sling.commons.content.analyzing/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.commons.content.processing'></a>[*.commons.content.processing](content/org/apache/sling/org.apache.sling.commons.content.processing/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.commons.crypto'></a>[*.commons.crypto](content/org/apache/sling/org.apache.sling.commons.crypto/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.commons.johnzon'></a>[*.commons.johnzon](content/org/apache/sling/org.apache.sling.commons.johnzon/README.md) | 5 | 3 :heavy_check_mark: / 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.commons.log'></a>[*.commons.log](content/org/apache/sling/org.apache.sling.commons.log/README.md) | 2 | 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.commons.messaging.mail'></a>[*.commons.messaging.mail](content/org/apache/sling/org.apache.sling.commons.messaging.mail/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.commons.messaging'></a>[*.commons.messaging](content/org/apache/sling/org.apache.sling.commons.messaging/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.commons.metrics'></a>[*.commons.metrics](content/org/apache/sling/org.apache.sling.commons.metrics/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.distribution.journal.kafka'></a>[*.distribution.journal.kafka](content/org/apache/sling/org.apache.sling.distribution.journal.kafka/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.distribution.journal'></a>[*.distribution.journal](content/org/apache/sling/org.apache.sling.distribution.journal/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.engine'></a>[*.engine](content/org/apache/sling/org.apache.sling.engine/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.event'></a>[*.event](content/org/apache/sling/org.apache.sling.event/README.md) | 5 | 5 :warning: |
| | <a name='org.apache.sling:org.apache.sling.feature.analyser'></a>[*.feature.analyser](content/org/apache/sling/org.apache.sling.feature.analyser/README.md) | 2 | 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.feature.cpconverter'></a>[*.feature.cpconverter](content/org/apache/sling/org.apache.sling.feature.cpconverter/README.md) | 3 | 3 :warning: |
| | <a name='org.apache.sling:org.apache.sling.feature.extension.apiregions'></a>[*.feature.extension.apiregions](content/org/apache/sling/org.apache.sling.feature.extension.apiregions/README.md) | 5 | 5 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.feature.extension.unpack'></a>[*.feature.extension.unpack](content/org/apache/sling/org.apache.sling.feature.extension.unpack/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.feature.launcher'></a>[*.feature.launcher](content/org/apache/sling/org.apache.sling.feature.launcher/README.md) | 4 | 2 :heavy_check_mark: / 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.feature'></a>[*.feature](content/org/apache/sling/org.apache.sling.feature/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.fsresource'></a>[*.fsresource](content/org/apache/sling/org.apache.sling.fsresource/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.i18n'></a>[*.i18n](content/org/apache/sling/org.apache.sling.i18n/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.installer.console'></a>[*.installer.console](content/org/apache/sling/org.apache.sling.installer.console/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.installer.core'></a>[*.installer.core](content/org/apache/sling/org.apache.sling.installer.core/README.md) | 4 | 4 :warning: |
| | <a name='org.apache.sling:org.apache.sling.installer.factory.configuration'></a>[*.installer.factory.configuration](content/org/apache/sling/org.apache.sling.installer.factory.configuration/README.md) | 5 | 1 :heavy_check_mark: / 4 :warning: |
| | <a name='org.apache.sling:org.apache.sling.installer.factory.packages'></a>[*.installer.factory.packages](content/org/apache/sling/org.apache.sling.installer.factory.packages/README.md) | 2 | 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.installer.provider.file'></a>[*.installer.provider.file](content/org/apache/sling/org.apache.sling.installer.provider.file/README.md) | 3 | 2 :heavy_check_mark: / 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.installer.provider.jcr'></a>[*.installer.provider.jcr](content/org/apache/sling/org.apache.sling.installer.provider.jcr/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.javax.activation'></a>[*.javax.activation](content/org/apache/sling/org.apache.sling.javax.activation/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.jcr.contentloader'></a>[*.jcr.contentloader](content/org/apache/sling/org.apache.sling.jcr.contentloader/README.md) | 3 | 3 :warning: |
| | <a name='org.apache.sling:org.apache.sling.jcr.jackrabbit.accessmanager'></a>[*.jcr.jackrabbit.accessmanager](content/org/apache/sling/org.apache.sling.jcr.jackrabbit.accessmanager/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.jcr.jackrabbit.usermanager'></a>[*.jcr.jackrabbit.usermanager](content/org/apache/sling/org.apache.sling.jcr.jackrabbit.usermanager/README.md) | 3 | 3 :warning: |
| | <a name='org.apache.sling:org.apache.sling.jcr.maintenance'></a>[*.jcr.maintenance](content/org/apache/sling/org.apache.sling.jcr.maintenance/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.jcr.packageinit'></a>[*.jcr.packageinit](content/org/apache/sling/org.apache.sling.jcr.packageinit/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.jcr.resource'></a>[*.jcr.resource](content/org/apache/sling/org.apache.sling.jcr.resource/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.jcr.resourcesecurity'></a>[*.jcr.resourcesecurity](content/org/apache/sling/org.apache.sling.jcr.resourcesecurity/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.launchpad.test-services'></a>[*.launchpad.test-services](content/org/apache/sling/org.apache.sling.launchpad.test-services/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.models.api'></a>[*.models.api](content/org/apache/sling/org.apache.sling.models.api/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.models.caconfig'></a>[*.models.caconfig](content/org/apache/sling/org.apache.sling.models.caconfig/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.models.impl'></a>[*.models.impl](content/org/apache/sling/org.apache.sling.models.impl/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.models.jacksonexporter'></a>[*.models.jacksonexporter](content/org/apache/sling/org.apache.sling.models.jacksonexporter/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.models.validation-impl'></a>[*.models.validation-impl](content/org/apache/sling/org.apache.sling.models.validation-impl/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.pipes'></a>[*.pipes](content/org/apache/sling/org.apache.sling.pipes/README.md) | 2 | 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.repoinit.parser'></a>[*.repoinit.parser](content/org/apache/sling/org.apache.sling.repoinit.parser/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.resourceaccesssecurity'></a>[*.resourceaccesssecurity](content/org/apache/sling/org.apache.sling.resourceaccesssecurity/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.resourcemerger'></a>[*.resourcemerger](content/org/apache/sling/org.apache.sling.resourcemerger/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.resourceresolver'></a>[*.resourceresolver](content/org/apache/sling/org.apache.sling.resourceresolver/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.rewriter'></a>[*.rewriter](content/org/apache/sling/org.apache.sling.rewriter/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.scripting.core'></a>[*.scripting.core](content/org/apache/sling/org.apache.sling.scripting.core/README.md) | 2 | 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.scripting.sightly.repl'></a>[*.scripting.sightly.repl](content/org/apache/sling/org.apache.sling.scripting.sightly.repl/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.scripting.sightly.testing-content'></a>[*.scripting.sightly.testing-content](content/org/apache/sling/org.apache.sling.scripting.sightly.testing-content/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.scripting.sightly'></a>[*.scripting.sightly](content/org/apache/sling/org.apache.sling.scripting.sightly/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.scripting.spi'></a>[*.scripting.spi](content/org/apache/sling/org.apache.sling.scripting.spi/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.security'></a>[*.security](content/org/apache/sling/org.apache.sling.security/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.servlets.annotations'></a>[*.servlets.annotations](content/org/apache/sling/org.apache.sling.servlets.annotations/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.servlets.post'></a>[*.servlets.post](content/org/apache/sling/org.apache.sling.servlets.post/README.md) | 2 | 2 :warning: |
| | <a name='org.apache.sling:org.apache.sling.servlets.resolver'></a>[*.servlets.resolver](content/org/apache/sling/org.apache.sling.servlets.resolver/README.md) | 4 | 4 :warning: |
| | <a name='org.apache.sling:org.apache.sling.settings'></a>[*.settings](content/org/apache/sling/org.apache.sling.settings/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.sitemap'></a>[*.sitemap](content/org/apache/sling/org.apache.sling.sitemap/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.starter.content'></a>[*.starter.content](content/org/apache/sling/org.apache.sling.starter.content/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.starter'></a>[*.starter](content/org/apache/sling/org.apache.sling.starter/README.md) | 1 | 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.tenant'></a>[*.tenant](content/org/apache/sling/org.apache.sling.tenant/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.testing.caconfig-mock-plugin'></a>[*.testing.caconfig-mock-plugin](content/org/apache/sling/org.apache.sling.testing.caconfig-mock-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.testing.clients'></a>[*.testing.clients](content/org/apache/sling/org.apache.sling.testing.clients/README.md) | 4 | 4 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.testing.jcr-mock'></a>[*.testing.jcr-mock](content/org/apache/sling/org.apache.sling.testing.jcr-mock/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.apache.sling:org.apache.sling.testing.resourceresolver-mock'></a>[*.testing.resourceresolver-mock](content/org/apache/sling/org.apache.sling.testing.resourceresolver-mock/README.md) | 4 | 3 :heavy_check_mark: / 1 :warning: |
| | <a name='org.apache.sling:org.apache.sling.testing.sling-mock-oak'></a>[*.testing.sling-mock-oak](content/org/apache/sling/org.apache.sling.testing.sling-mock-oak/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.apache.sling:scriptingbundle-maven-plugin'></a>[scriptingbundle-maven-plugin](content/org/apache/sling/scriptingbundle-maven-plugin/README.md) | 3 | 3 :warning: |
| | <a name='org.apache.sling:slingfeature-maven-plugin'></a>[slingfeature-maven-plugin](content/org/apache/sling/slingfeature-maven-plugin/README.md) | 5 | 2 :heavy_check_mark: / 3 :warning: |
| org.apache.sshd | <a name='org.apache.sshd:sshd'></a>[sshd](content/org/apache/sshd/README.md) | 2 | 2 :warning: |
| org.apache.struts | <a name='org.apache.struts:struts2-parent'></a>[struts2-parent](content/org/apache/struts/README.md) | 1 | 1 :warning: |
| org.apache.tika | <a name='org.apache.tika:tika'></a>[tika](content/org/apache/tika/README.md) | 4 | 4 :warning: |
| org.apache.wayang | <a name='org.apache.wayang:wayang'></a>[wayang](content/org/apache/wayang/README.md) | 1 | 1 :warning: |
| org.apache.wss4j | <a name='org.apache.wss4j:wss4j'></a>[wss4j](content/org/apache/wss4j/README.md) | 1 | 1 :warning: |
| org.codehaus.modello | <a name='org.codehaus.modello:modello'></a>[modello](content/org/codehaus/modello/README.md) | 1 | 1 :heavy_check_mark: |
| org.codehaus.mojo | <a name='org.codehaus.mojo:animal-sniffer-parent'></a>[animal-sniffer-parent](content/org/codehaus/mojo/animal-sniffer/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.codehaus.mojo:aspectj-maven-plugin'></a>[aspectj-maven-plugin](content/org/codehaus/mojo/aspectj-maven-plugin/README.md) | 1 | 1 :warning: |
| | <a name='org.codehaus.mojo:extra-enforcer-rules'></a>[extra-enforcer-rules](content/org/codehaus/mojo/extra-enforcer-rules/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.codehaus.mojo:flatten-maven-plugin'></a>[flatten-maven-plugin](content/org/codehaus/mojo/flatten-maven-plugin/README.md) | 1 | 1 :warning: |
| | <a name='org.codehaus.mojo:mojo-parent'></a>[mojo-parent](content/org/codehaus/mojo/mojo-parent/README.md) | 5 | 5 :heavy_check_mark: |
| | <a name='org.codehaus.mojo:properties-maven-plugin'></a>[properties-maven-plugin](content/org/codehaus/mojo/properties-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.codehaus.mojo:taglist-maven-plugin'></a>[taglist-maven-plugin](content/org/codehaus/mojo/taglist-maven-plugin/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.codehaus.mojo:versions-maven-plugin'></a>[versions-maven-plugin](content/org/codehaus/mojo/versions-maven-plugin/README.md) | 3 | 3 :heavy_check_mark: |
| | <a name='org.codehaus.mojo:wagon-maven-plugin'></a>[wagon-maven-plugin](content/org/codehaus/mojo/wagon-maven-plugin/README.md) | 2 | 1 :heavy_check_mark: / 1 :warning: |
| org.codehaus.plexus | <a name='org.codehaus.plexus:plexus-archiver'></a>[plexus-archiver](content/org/codehaus/plexus/plexus-archiver/README.md) | 6 | 5 :heavy_check_mark: / 1 :warning: |
| | <a name='org.codehaus.plexus:plexus-cipher'></a>[plexus-cipher](content/org/codehaus/plexus/plexus-cipher/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.codehaus.plexus:plexus-compiler'></a>[plexus-compiler](content/org/codehaus/plexus/plexus-compiler/README.md) | 7 | 5 :heavy_check_mark: / 2 :warning: |
| | <a name='org.codehaus.plexus:plexus-components'></a>[plexus-components](content/org/codehaus/plexus/plexus-components/README.md) | 4 | 3 :heavy_check_mark: / 1 :warning: |
| | <a name='org.codehaus.plexus:plexus-interactivity'></a>[plexus-interactivity](content/org/codehaus/plexus/plexus-interactivity/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.codehaus.plexus:plexus-languages'></a>[plexus-languages](content/org/codehaus/plexus/plexus-languages/README.md) | 5 | 5 :warning: |
| | <a name='org.codehaus.plexus:plexus'></a>[plexus](content/org/codehaus/plexus/plexus-pom/README.md) | 6 | 5 :heavy_check_mark: / 1 :warning: |
| | <a name='org.codehaus.plexus:plexus-utils'></a>[plexus-utils](content/org/codehaus/plexus/plexus-utils/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.codehaus.plexus:plexus-velocity'></a>[plexus-velocity](content/org/codehaus/plexus/plexus-velocity/README.md) | 1 | 1 :heavy_check_mark: |
| org.complate | <a name='org.complate:complate-core'></a>[complate-core](content/org/complate/README.md) | 1 | 1 :heavy_check_mark: |
| org.cyclonedx | <a name='org.cyclonedx:cyclonedx-core-java'></a>[cyclonedx-core-java](content/org/cyclonedx/cyclonedx-core-java/README.md) | 20 | 20 :heavy_check_mark: |
| | <a name='org.cyclonedx:cyclonedx-maven-plugin'></a>[cyclonedx-maven-plugin](content/org/cyclonedx/cyclonedx-maven-plugin/README.md) | 8 | 8 :heavy_check_mark: |
| org.eclipse.jkube | <a name='org.eclipse.jkube:jkube'></a>[jkube](content/org/eclipse/jkube/README.md) | 9 | 9 :heavy_check_mark: |
| org.eclipse.transformer | <a name='org.eclipse.transformer:org.eclipse.transformer.parent'></a>[*.parent](content/org/eclipse/transformer/README.md) | 1 | 1 :heavy_check_mark: |
| org.fusesource.jansi | <a name='org.fusesource.jansi:jansi'></a>[jansi](content/org/fusesource/jansi/jansi/README.md) | 8 | 5 :heavy_check_mark: / 3 :warning: |
| org.jline | <a name='org.jline:jline-parent'></a>[jline-parent](content/org/jline/jline/README.md) | 2 | 2 :heavy_check_mark: |
| org.jrivard.xmlchai | <a name='org.jrivard.xmlchai:xmlchai'></a>[xmlchai](content/org/jrivard/xmlchai/README.md) | 1 | 1 :warning: |
| org.liquibase.ext | <a name='org.liquibase.ext:liquibase-percona'></a>[liquibase-percona](content/org/liquibase/ext/liquibase-percona/README.md) | 16 | 15 :heavy_check_mark: / 1 :warning: |
| org.mybatis.dynamic-sql | <a name='org.mybatis.dynamic-sql:mybatis-dynamic-sql'></a>[mybatis-dynamic-sql](content/org/mybatis/dynamic-sql/README.md) | 1 | 1 :warning: |
| org.mybatis | <a name='org.mybatis:mybatis-guice'></a>[mybatis-guice](content/org/mybatis/guice/README.md) | 1 | 1 :heavy_check_mark: |
| | <a name='org.mybatis:mybatis-parent'></a>[mybatis-parent](content/org/mybatis/parent/README.md) | 1 | 1 :heavy_check_mark: |
| org.nlpub | <a name='org.nlpub:watset'></a>[watset](content/org/nlpub/watset/README.md) | 12 | 11 :heavy_check_mark: / 1 :warning: |
| org.openapitools.openapidiff | <a name='org.openapitools.openapidiff:openapi-diff-parent'></a>[openapi-diff-parent](content/org/openapitools/openapidiff/README.md) | 1 | 1 :heavy_check_mark: |
| org.osgi | <a name='org.osgi:org.osgi.test.parent'></a>[*.test.parent](content/org/osgi/test/README.md) | 3 | 2 :heavy_check_mark: / 1 :warning: |
| org.owasp.antisamy | <a name='org.owasp.antisamy:antisamy'></a>[antisamy](content/org/owasp/antisamy/README.md) | 6 | 6 :heavy_check_mark: |
| org.quickperf | <a name='org.quickperf:quick-perf'></a>[quick-perf](content/org/quickperf/README.md) | 3 | 3 :heavy_check_mark: |
| org.simplify4u | <a name='org.simplify4u:pgp-keys-map'></a>[pgp-keys-map](content/org/simplify4u/pgp-keys-map/README.md) | 12 | 12 :heavy_check_mark: |
| org.simplify4u.plugins | <a name='org.simplify4u.plugins:pgpverify-maven-plugin'></a>[pgpverify-maven-plugin](content/org/simplify4u/plugins/pgpverify-maven-plugin/README.md) | 7 | 7 :heavy_check_mark: |
| | <a name='org.simplify4u.plugins:sign-maven-plugin'></a>[sign-maven-plugin](content/org/simplify4u/plugins/sign-maven-plugin/README.md) | 7 | 5 :heavy_check_mark: / 2 :warning: |
| org.simplify4u | <a name='org.simplify4u:slf4j-mock'></a>[slf4j-mock](content/org/simplify4u/slf4j-mock/README.md) | 2 | 2 :heavy_check_mark: |
| org.slf4j | <a name='org.slf4j:slf4j-parent'></a>[slf4j-parent](content/org/slf4j/README.md) | 1 | 1 :warning: |
| org.sonatype.nexus.archetypes | <a name='org.sonatype.nexus.archetypes:nexus-format-archetype'></a>[nexus-format-archetype](content/org/sonatype/nexus/archetypes/nexus-format-archetype/README.md) | 1 | 1 :heavy_check_mark: |
| org.tomitribe.transformer | <a name='org.tomitribe.transformer:org.eclipse.transformer.parent'></a>[org.eclipse.transformer.parent](content/org/tomitribe/transformer/README.md) | 2 | 2 :heavy_check_mark: |
| org.webjars | <a name='org.webjars:flexmonster'></a>[flexmonster](content/org/webjars/flexmonster/README.md) | 2 | 2 :heavy_check_mark: |
| | <a name='org.webjars:swagger-ui'></a>[swagger-ui](content/org/webjars/swagger-ui/README.md) | 5 | 5 :heavy_check_mark: |
| world.convex | <a name='world.convex:convex'></a>[convex](content/world/convex/README.md) | 4 | 4 :warning: |
| **Count:** | **242** | **766** | **517** :heavy_check_mark: **249** :warning: |
<!-- END GENERATED RESULTS TABLE -->

## Understanding What Is Behind

see [history](HISTORY.md)

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#

#
