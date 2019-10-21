![csplogo](https://user-images.githubusercontent.com/12301571/67168219-4d618900-f3a2-11e9-9460-b79eff997c35.PNG)

# cmd.csp.similarity
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/swelcker/cmd.csp.similarity/graphs/commit-activity)
[![GitHub release](https://img.shields.io/github/release/swelcker/cmd.csp.similarity.svg)](https://GitHub.com/swelcker/cmd.csp.similarity/releases/)
[![GitHub tag](https://img.shields.io/github/tag/swelcker/cmd.csp.similarity.svg)](https://GitHub.com/swelcker/cmd.csp.similarity/tags/)
[![GitHub commits](https://img.shields.io/github/commits-since/swelcker/cmd.csp.similarity/master.svg)](https://GitHub.com/swelcker/cmd.csp.similarity/commit/)
[![GitHub contributors](https://img.shields.io/github/contributors/swelcker/cmd.csp.similarity.svg)](https://GitHub.com/swelcker/cmd.csp.similarity/graphs/contributors/)

A library implementing different string similarity and distance measures for ease of use. A dozen of algorithms (including Levenshtein edit distance and sibblings, Jaro-Winkler, Longest Common Subsequence, cosine similarity etc.) are currently implemented.
Used in the Cognitive Service Platform cmd.csp for NLP and classifier part.


### Prerequisites

There are no prerequisites. 

Included dependencies:
```xml
<dependency>
    <groupId>net.jcip</groupId>
    <artifactId>jcip-annotations</artifactId>
    <version>1.0</version>
</dependency>
```
### Installing/Usage

To use, merge the following into your Maven POM (or the equivalent into your Gradle build script):

```xml
<repository>
  <id>github</id>
  <name>GitHub swelcker Apache Maven Packages</name>
  <url>https://maven.pkg.github.com/swelcker</url>
</repository>

<dependency>
  <groupId>cmd.csp</groupId>
  <artifactId>cspsimilarity</artifactId>
  <version>1.0.0</version>
</dependency>
```

Then, import cmd.csp.postagger.*;` in your application :

```java
// Example
import cspsimilarity.*;
...
	private NormalizedLevenshtein engineNL = new NormalizedLevenshtein();
	private JaroWinkler engineJW = new JaroWinkler();
	private MetricLCS engineMLCS = new MetricLCS();
	private NGram engineNGRAM = new NGram(3);
	private Cosine engineCOSINE = new Cosine(9);
	private Jaccard engineJACARD = new Jaccard(9);
	private SorensenDice engineSOREDICE= new SorensenDice(9);
...
    String source = (sourceText);
    String search = (toSearch);

    double sS=0d;

    sS=(engineNL.similarity(source, search));
    sS=(engineJW.similarity(source, search));
    sS=(1d-engineMLCS.distance(source, search));
    sS=(1d-engineNGRAM.distance(source, search));
    sS=(engineCOSINE.similarity(source, search));
    sS=(engineJACARD.similarity(source, search));
    sS=(engineSOREDICE.similarity(source, search));
```

## Built With

* [Maven](https://maven.apache.org/) - Dependency Management


## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/swelcker/cmd.csp.similarity/tags). 

## Authors

* **Stefan Welcker** - *Modifications based on tdebatty/java-string-similarity* 

See also the list of [contributors](https://github.com/swelcker/cmd.csp.stemmer/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

