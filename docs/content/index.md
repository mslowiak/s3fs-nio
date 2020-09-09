{! ../../README.md [ln:1-38] !} 
  
## Installation

=== "Maven" 
    
    ```
    <dependency>
        <groupId>{{ POM_GROUP_ID }}</groupId>
        <artifactId>{{ POM_ARTIFACT_ID }}</artifactId>
        <version>{{ POM_VERSION }}</version>
    </dependency>
    ```

=== "Gradle"
    
    ```
    compile group: '{{ POM_GROUP_ID }}', name: '{{ POM_ARTIFACT_ID }}', version: '{{ POM_VERSION }}'
    ```

=== "SBT"
    
    ```
    libraryDependencies += "{{ POM_GROUP_ID }}" % "{{ POM_ARTIFACT_ID }}" % "{{ POM_VERSION }}"
    ```


## Quick start

### Amazon S3 Setup

1. Open [S3 Console] and add a bucket
2. Open [IAM] and go to `Add User`
3. Set `Access Type` to `Programmatic Access` or you will get `403 Forbidden` errors.
4. Select `Attach an existing policies directly`
5. Select `AmazonS3FullAccess` policy and `Create user`
6. Copy `Access key ID` and `Secret access key` - you will need them later!

### Example

=== "1. Configure"

    Create/load a properties file in your project which defines the following properties:
    
    ```
    --8<-- "../src/test/resources/amazon-test-sample.properties"
    ``` 
    
    These properties can also be exported as environment variables.
    A complete list is available in the [Configuration Reference]

=== "2. Code"

    ```java
    --8<-- "../src/test/java/org/carlspring/cloud/storage/s3fs/ExampleClass.java"
    ```

=== "3. Test"
    ```java
    --8<-- "../src/test/java/org/carlspring/cloud/storage/s3fs/ExampleClassIT.java"
    ```


## See also

* [Contributing]
* [Configuration Reference]
* [More examples]


[<--# Links -->]: #
[Contributing]: ./contributing/index.md "Contributing"
[Configuration Reference]: ./reference/configuration.md "Configuration Reference"
[More examples]: ./reference/examples.md "More examples"
[S3 Console]: https://s3.console.aws.amazon.com/s3/home "Amazon S3 Console"
[IAM]: https://console.aws.amazon.com/iam/home "Amazon IAM"