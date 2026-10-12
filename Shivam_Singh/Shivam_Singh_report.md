# RIDE flaky-test detection — Shivam_Singh

iDFlakies + NonDex: 100 project modules built and were run (97 distinct projects); 19 more candidates were skipped because they could not be cloned or built on JDK 8/11/17.
Settings: iDFlakies 2.0.0 (random-class-method) and NonDex 2.2.1. The 24 modules from iDFlakies' own project list (run Oct 9) used 20 iDFlakies rounds and 10 NonDex runs; the 76 modules from IDoFT (run Oct 11) used 5 rounds / 3 runs with time limits (10 min iDFlakies, 8 min NonDex). Builds tried JDK 8, then 11, then 17. FlakeSync (UT-SE-Research/FlakeSync @ 54ebfa3b5e) ran all six goals with a 6-8 min limit per test; IDoFT has async (NOD) flaky tests in only ~50 Maven projects, so the 100 FlakeSync tests span 36 projects that built.

## Answers

1. **iDFlakies:** 135 flaky tests
2. **NonDex:** 592 flaky tests
3. **Detected by both:** 29
4. **Unique across both:** 698

### New vs. already in IDoFT

"New" = the fully-qualified test name does not appear anywhere in IDoFT `pr-data.csv`.

| | Flaky tests | New (not in IDoFT) |
|---|---:|---:|
| iDFlakies | 135 | 9 |
| NonDex | 592 | 100 |
| Detected by both | 29 | 0 |
| Unique across both | 698 | 109 |

## FlakeSync

100 async (NOD) flaky tests from IDoFT were run through FlakeSync on 36 distinct projects that built (36 more candidates could not be built).

| Outcome | Tests |
|---|---:|
| failure reproduced by delay injection; root cause not isolated | 71 |
| no concurrent methods found | 23 |
| critical points found (no patch) | 5 |
| time cap reached in concurrentfind | 1 |

## Per project (iDFlakies + NonDex)

| Project | Module | Build | iDFlakies | NonDex | Both | Unique |
|---|---|---|---:|---:|---:|---:|
| Apache/Struts | plugins/portlet | install ok | 0 | 0 | 0 | 0 |
| BroadleafCommerce/BroadleafCommerce | common | install ok | 1 | 2 | 0 | 3 |
| FasterXML/java-classmate | (root) | install ok | 0 | 2 | 0 | 2 |
| GoogleCloudPlatform/DataflowTemplates | (root) | install ok | 0 | 0 | 0 | 0 |
| GoogleCloudPlatform/spring-cloud-gcp | spring-cloud-gcp-data-spanner | install ok | 0 | 29 | 0 | 29 |
| Huawei/vCenter_Plugin_DME | dmestore-service | install ok | 1 | 0 | 0 | 1 |
| IBM/vpc-java-sdk | modules/vpc | install ok | 0 | 51 | 0 | 51 |
| Meituan-Dianping/groupmeal-java-sdk | (root) | install ok | 0 | 1 | 0 | 1 |
| OryxProject/oryx | framework/oryx-common | install ok | 0 | 1 | 0 | 1 |
| SAP/pair-distribution-app | (root) | install ok | 0 | 7 | 0 | 7 |
| TestingResearchIllinois/starts | (root) | install ok | 0 | 1 | 0 | 1 |
| Wikidata-Toolkit/Wikidata-Toolkit | wdtk-wikibaseapi | install ok | 0 | 19 | 0 | 19 |
| alibaba/easy-retry | easy-retry-extensions | install ok | 0 | 0 | 0 | 0 |
| alibaba/easyexcel | (root) | install ok | 2 | 0 | 0 | 2 |
| amzn/amazon-hub-counter-sdk-java | (root) | install ok | 0 | 1 | 0 | 1 |
| apache/aries-cdi | cdi-extender | install ok | 0 | 2 | 0 | 2 |
| apache/bookkeeper | bookkeeper-server | install ok | 0 | 0 | 0 | 0 |
| apache/cloudstack | plugins/network-elements/opendaylight | install ok | 0 | 2 | 0 | 2 |
| apache/commons-collections | (root) | install ok | 0 | 29 | 0 | 29 |
| apache/incubator-dubbo | dubbo-cluster | install ok | 4 | 0 | 0 | 4 |
| apache/incubator-dubbo | dubbo-rpc/dubbo-rpc-dubbo | install ok | 4 | 3 | 0 | 7 |
| apache/incubator-dubbo | dubbo-serialization/dubbo-serialization-fst | install ok | 1 | 0 | 0 | 1 |
| apache/incubator-kie-drools | drools-model/drools-model-codegen | install ok | 0 | 123 | 0 | 123 |
| apache/incubator-seata | server | install ok | 0 | 0 | 0 | 0 |
| apache/maven-dependency-plugin | (root) | install ok | 0 | 2 | 0 | 2 |
| apache/maven-doxia | doxia-modules/doxia-module-markdown | install ok | 0 | 1 | 0 | 1 |
| apache/pdfbox | (root) | install ok | 0 | 1 | 0 | 1 |
| apache/shenyu | shenyu-admin | install ok | 0 | 0 | 0 | 0 |
| apache/streampipes | streampipes-extensions-management | install ok | 0 | 8 | 0 | 8 |
| apolloconfig/apollo-java | apollo-openapi | install ok | 0 | 1 | 0 | 1 |
| authorjapps/zerocode | core | install ok | 0 | 0 | 0 | 0 |
| awspring/spring-cloud-aws | spring-cloud-aws-context | install ok | 0 | 0 | 0 | 0 |
| bbottema/simple-java-mail | modules/simple-java-mail | install ok | 0 | 1 | 0 | 1 |
| braintree/braintree_java | (root) | install ok | 0 | 1 | 0 | 1 |
| castle/castle-java | (root) | install ok | 0 | 13 | 0 | 13 |
| classgraph/classgraph | (root) | install ok | 0 | 2 | 0 | 2 |
| codingchili/excelastic | (root) | install ok | 1 | 0 | 0 | 1 |
| ctco/cukes | cukes-http | install ok | 1 | 0 | 0 | 1 |
| dianping/cat | cat-client | install ok | 0 | 0 | 0 | 0 |
| dromara/hutool | hutool-core | install ok | 0 | 8 | 0 | 8 |
| dropwizard/dropwizard | dropwizard-logging | install ok | 1 | 0 | 0 | 1 |
| eBay/taxonomy-sdk | (root) | install ok | 0 | 1 | 0 | 1 |
| elasticjob/elastic-job-lite | elastic-job-lite-core | install ok | 3 | 1 | 0 | 4 |
| espertechinc/esper | runtime | install ok | 0 | 0 | 0 | 0 |
| fhoeben/hsac-fitnesse-fixtures | (root) | install ok | 1 | 0 | 0 | 1 |
| fromage/redpipe | redpipe-templating-freemarker | install ok | 0 | 1 | 0 | 1 |
| gchq/koryphe | core | install ok | 0 | 5 | 0 | 5 |
| google/gson | gson | install ok | 0 | 49 | 0 | 49 |
| googleapis/google-auth-library-java | appengine | install ok | 1 | 0 | 0 | 1 |
| graphhopper/graphhopper | core | install ok | 0 | 0 | 0 | 0 |
| hexagonframework/spring-data-ebean | (root) | install ok | 1 | 0 | 0 | 1 |
| hs-web/hsweb-framework | hsweb-commons/hsweb-commons-dao/hsweb-commons-dao-mybatis | install ok | 0 | 1 | 0 | 1 |
| immutables/immutables | value-fixture | install ok | 0 | 0 | 0 | 0 |
| intel/jndn-utils | (root) | install ok | 0 | 3 | 0 | 3 |
| intuit/karate | karate-core | install ok | 0 | 2 | 0 | 2 |
| jReddit/jReddit | (root) | install ok | 0 | 2 | 0 | 2 |
| jenkinsci/jenkins | test | install ok | 0 | 0 | 0 | 0 |
| jfree/jfreechart | (root) | install ok | 0 | 0 | 0 | 0 |
| jhipster/jhipster-registry | (root) | install ok | 1 | 1 | 0 | 2 |
| json-iterator/java | (root) | install ok | 6 | 9 | 1 | 14 |
| junit-team/junit4 | (root) | install ok | 0 | 7 | 0 | 7 |
| kagkarlsson/db-scheduler | (root) | install ok | 0 | 7 | 0 | 7 |
| kevinsawicki/http-request | lib | install ok | 28 | 28 | 28 | 28 |
| kiegroup/optaplanner | optaplanner-core | install ok | 0 | 3 | 0 | 3 |
| ktuukkan/marine-api | (root) | install ok | 12 | 0 | 0 | 12 |
| liquibase/liquibase | liquibase-core | install ok | 0 | 1 | 0 | 1 |
| microsoft/botbuilder-java | libraries/bot-connector | install ok | 0 | 4 | 0 | 4 |
| mybatis/mybatis-dynamic-sql | (root) | install ok | 0 | 25 | 0 | 25 |
| nationalsecurityagency/timely | server | install ok | 0 | 4 | 0 | 4 |
| nutzam/nutz | (root) | install ok | 6 | 5 | 0 | 11 |
| okta/okta-hooks-sdk-java | hooks | install ok | 0 | 15 | 0 | 15 |
| openpojo/openpojo | (root) | install ok | 4 | 2 | 0 | 6 |
| oracle/oci-java-sdk | bmc-objectstorage/bmc-objectstorage-extensions | install ok | 0 | 0 | 0 | 0 |
| oracle/tribuo | Reproducibility | install ok | 0 | 4 | 0 | 4 |
| orbit/orbit | actors/runtime | install ok | 0 | 1 | 0 | 1 |
| orika-mapper/orika | core | install ok | 0 | 5 | 0 | 5 |
| pedrovgs/Algorithms | (root) | install ok | 0 | 1 | 0 | 1 |
| perwendel/spark | (root) | install ok | 0 | 0 | 0 | 0 |
| pholser/junit-quickcheck | guava | install ok | 1 | 0 | 0 | 1 |
| qos-ch/logback | logback-core | install ok | 0 | 0 | 0 | 0 |
| sabidea23/SmartTranslator | (root) | install ok | 0 | 0 | 0 | 0 |
| seata/seata | common | install ok | 0 | 1 | 0 | 1 |
| skyscreamer/JSONassert | (root) | install ok | 0 | 1 | 0 | 1 |
| sonatype-nexus-community/nexus-repository-helm | (root) | install ok | 1 | 1 | 0 | 2 |
| spring-projects/spring-hateoas | (root) | install ok | 0 | 39 | 0 | 39 |
| spring-projects/spring-ws | spring-ws-security | install ok | 0 | 0 | 0 | 0 |
| square/burst | burst-junit4 | install ok | 0 | 1 | 0 | 1 |
| swagger-api/swagger-core | modules/swagger-jaxrs2 | install ok | 0 | 46 | 0 | 46 |
| tabulapdf/tabula-java | (root) | install ok | 0 | 1 | 0 | 1 |
| tbsalling/aismessages | (root) | install ok | 2 | 0 | 0 | 2 |
| techa03/goodsKill | goodskill-seckill-provider/goodskill-service | install ok | 0 | 1 | 0 | 1 |
| thinkaurelius/titan | titan-test | install ok | 0 | 0 | 0 | 0 |
| tomsun28/sureness | core | install ok | 0 | 1 | 0 | 1 |
| tools4j/unix4j | unix4j-core/unix4j-command | install ok | 1 | 0 | 0 | 1 |
| twilio/authy-java | (root) | install ok | 0 | 2 | 0 | 2 |
| undertow-io/undertow | websockets-jsr | install ok | 2 | 0 | 0 | 2 |
| wikidata/wikidata-toolkit | wdtk-dumpfiles | install ok | 3 | 0 | 0 | 3 |
| wikidata/wikidata-toolkit | wdtk-util | install ok | 2 | 0 | 0 | 2 |
| wildfly/wildfly | naming | install ok | 44 | 0 | 0 | 44 |
| zavtech/morpheus-core | (root) | install ok | 0 | 0 | 0 | 0 |
| AmadeusITGroup/workflow-cps-global-lib-http-plugin | (root) | install failed | 0 | 0 | 0 | 0 |
| AuthMe/AuthMeReloaded | (root) | install failed | 0 | 0 | 0 | 0 |
| FasterXML/jackson-dataformats-text | yaml | install failed | 0 | 0 | 0 | 0 |
| FasterXML/jackson-jaxrs-providers | base | install failed | 0 | 0 | 0 | 0 |
| FasterXML/jackson-module-jsonSchema | (root) | install failed | 0 | 0 | 0 | 0 |
| HubSpot/Singularity | SingularityService | install failed | 0 | 0 | 0 | 0 |
| apache/rocketmq-dashboard | rocketmq-dashboard | install failed | 0 | 0 | 0 | 0 |
| blockchain-jd-com/utils | utils-serialize | clone failed | 0 | 0 | 0 | 0 |
| hub4j/github-api | github | install failed | 0 | 0 | 0 | 0 |
| jolokia/jolokia | jolokia-spring | install failed | 0 | 0 | 0 | 0 |
| lets-blade/blade | blade-core | install failed | 0 | 0 | 0 | 0 |
| networknt/light-4j | config | checkout failed | 0 | 0 | 0 | 0 |
| spring-cloud/spring-cloud-gateway | (root) | install failed | 0 | 0 | 0 | 0 |
| spring-projects/spring-data-gemfire | (root) | install failed | 0 | 0 | 0 | 0 |
| spring-projects/spring-data-r2dbc | (root) | install failed | 0 | 0 | 0 | 0 |
| stanfordnlp/CoreNLP | (root) | install failed | 0 | 0 | 0 | 0 |
| twilio/twilio-java | (root) | checkout failed | 0 | 0 | 0 | 0 |
| uniVocity/univocity-parsers | core | install failed | 0 | 0 | 0 | 0 |
| wso2/carbon-apimgt | components/apimgt/org.wso2.carbon.apimgt.core | install failed | 0 | 0 | 0 | 0 |

Files: `Shivam_Singh_idflakies.csv`, `Shivam_Singh_nondex.csv` (one row per flaky test), `Shivam_Singh_flakesync.csv` (one row per test run through FlakeSync), `Shivam_Singh_summary.csv` (counts incl. new vs. IDoFT), `Shivam_Singh_per_project.csv`, `logs/`.
