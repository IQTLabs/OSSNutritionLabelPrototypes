Open Source Software Nutrition Labels
======

IQT Labs' Open Source Software Nutrition Label Prototype is a __proof-of-concept visualization__ designed to support analysis of third-party code dependencies. 

It brings together open source software project metadata and allows users to [sort](https://github.com/IQTLabs/OSSNutritionLabelPrototypes#bar_chart-visualization-approach) their dependencies based on different criteria.

:bulb: Core Concept
-----------
Many open-source software packages are fit for consumption and some are even beneficial to the developers who rely on them. Others are more akin to junk food, enticing in the moment, easy to ingest, but sub-optimal in the long term. Still others contain the software analogue of food adulterants, which compromise basic security and effectiveness. 

Our basic premise is that software nutrition labels can help developers and enterprise program managers make better-informed decisions about third-party software on the basis of [project health](https://www.usenix.org/system/files/login/articles/login_fall20_07_link.pdf), [maintenance activity](https://www.usenix.org/system/files/login/articles/login_summer20_11_geer.pdf), and [supply chain risk](https://www.usenix.org/system/files/login/articles/login_winter20_17_geer.pdf).

:sparkles: New Prototypes
-----------

This project is:
* A work-in-process
* Co-produced by the IQT Labs Human-Machine Interfaces and Engineering teams
* Conceived as [a platform for future collaboration](https://github.com/IQTLabs/OSSNutritionLabelPrototypes#speech_balloon-contact)
* Part of an ongoing <a href="https://www.iqt.org/toward-secure-code-reuse" target="_blank">applied research initiative</a> focused on <a href="https://www.iqt.org/code-reuse-holy-grail-or-poisoned-chalice" target="_blank">third-party code dependencies</a>
* Currently available as a series of minimum working examples (MWEs) based on an internal software project, below:

|MWE #1|MWE #2|MWE #3|MWE #4|MWE #5|
|:--:|:--:|:--:|:--:|:--:|
|[![](https://img.shields.io/badge/Interactive-Demo_1-green?style=plastic&logo=CodeSandbox)](https://o5pev.csb.app/)|[![](https://img.shields.io/badge/Interactive-Demo_2-green?style=plastic&logo=CodeSandbox)](https://4z1g2.csb.app/)|[![](https://img.shields.io/badge/Interactive-Demo_3-green?style=plastic&logo=CodeSandbox)](https://ljxxn.csb.app/)|[![](https://img.shields.io/badge/Interactive-Demo_4-green?style=plastic&logo=CodeSandbox)](https://ydr79.csb.app/)|[![](https://img.shields.io/badge/Interactive-Demo_5-green?style=plastic&logo=CodeSandbox)](https://trui4.csb.app/)|

:warning: Important Disclaimers
-----------

This codebase and the demo links above contain __minimum working examples (MWEs)__ which are neither feature-complete, nor production-ready. 

<img alt="dataflow" src="https://user-images.githubusercontent.com/45634754/137221606-ab70f021-f471-4bdd-aea1-5e97ee0317bc.png">

The current MWEs focus on IQT Labs' <a href="https://github.com/IQTLabs/FakeFinder" target="_blank">FakeFinder</a> face-swap detection project. They visualize package health score data from <a href="https://snyk.io/advisor" target="_blank">Snyk Advisor</a>,<sup>*</sup> (94/100 example above) as well as associated software project metadata, for the top-level software dependencies listed in FakeFinder's various <a href="https://github.com/IQTLabs/FakeFinder/search?q=requirements" target="_blank"><code>requirements.txt</code></a> files.

```diff
- N.B. These values may have changed since our initial query in 2021. We have not set the UI to refresh automatically.
```

<details>
    <summary>The Snyk- and GitHub-derived data shown in the Open Source Software Nutrition Label Prototype are not endorsed or approved by IQT Labs, and future nutrition label releases may vary.</summary>
    <br />
    <blockquote>Please note that Snyk Advisor scores change over time and as the data underlying this demo represents a single snapshot in time, future Snyk results for these same Python software packages are likely to vary. <strong>These data are provided “as is” with no warranties of any kind, and use of this information is at your sole risk.</strong> To the maximum extent provided by law, neither IQT Labs and its affiliates nor any government agency or third party shall be liable for any damages of any kind relating to or resulting from use of the information on this site. For more information, review IQT's <a href="https://www.iqt.org/terms-of-use/" target="_blank">Terms of Use</a>.</blockquote>
</details>

:bar_chart: Visualization Approach
-------
Built in <a href="https://reactjs.org/" target="_blank">React</a> and <a href="https://www.typescriptlang.org/" target="_blank">TypeScript</a>, the Open Source Software Nutrition Label Prototype takes advantage of <a href="https://lineup-lite.js.org/docs/components" target="_blank"><code>@lineup-lite</code></a>'s multi-attribute ranking and data visualization capabilities.

This visualization approach we chose for this prototype enables users to make sophisticated comparisons. As <a href="http://data.jku-vds-lab.at/papers/2013_infovis_lineup.pdf" target="_blank">Samuel Gratzl et al. (2013)</a> explain:

> Multi-attribute rankings are ubiquitous and diverse. Popular examples include university rankings, __rankings of food products by their nutrient content, rankings of computer hardware,__ and most livable city rankings. When rankings are based on a single attribute or are completely subjective, their display is trivial and does not require elaborate visualization techniques. __If a ranking, however, is based on multiple attributes, how these attributes contribute to the rank and how changes in one or more attributes influence the ranking is not straightforward to understand. In order to interpret, modify, and compare such rankings, we need advanced visual tools.__

:building_construction: Customization
-----------

To customize this prototype with data of your own: 
* clone (or download) this repo
* modify your [rows](https://github.com/IQTLabs/OSSNutritionLabelPrototypes/blob/main/src/data/index.tsx#L15-L580) in __src/data/index.tsx__
* update your [columns](https://github.com/IQTLabs/OSSNutritionLabelPrototypes/blob/main/src/App.tsx#L49-L58) in __src/App.tsx__

That's it. There's no step four!

<details>
    <summary>Provided you can run React locally and provided you've formatted your row data and column visualizations correctly, <code>React.useMemo</code> will take care of the rest.</summary>
    <br />
    <p>As the <a href="https://react-table.tanstack.com/docs/quick-start#getting-your-data" target="_blank">react-table Quick Start Guide</a> explains:</p>
    <blockquote>It's important that we're using React.useMemo here to ensure that our data isn't recreated on every render. If we didn't use React.useMemo, the table would think it was receiving new data on every render and attempt to recalculate a lot of logic every single time.
    </blockquote>
    <br />
    <p>If you get stuck at any point, we also recommend familiarizing yourself with the <a href="https://lineup-lite.js.org/docs/components" target="_blank"><code>@lineup-lite/components</code></a> documentation.</p>
</details>

:speech_balloon: Contact
-------

Anyone interested in discussing related research or collaboration should e-mail [gsieniawski@iqt.org](mailto:gsieniawski@iqt.org).

:gift: Contributions
-------
* :scorpion: Catch a bug? [Smell an odor](http://www.cs.wm.edu/~denys/pubs/ICSE'15-BadSmells-CRC.pdf)? [Open a **New Issue** ticket detailing the problem; incl. screenshots if you can](https://github.com/IQTLabs/OSSNutritionLabelPrototypes/issues/new)
* Have pertinent and [unrestricted](https://www.copyright.gov/title17/92chap1.html#107) components to add? We look forward to reviewing new [**Pull Requests**](https://github.com/IQTLabs/OSSNutritionLabelPrototypes/pulls) that originate from feature dev. branches
* *Pro tip: the odds we'll act promptly on/respond favorably to any of the above increase exponentially if you follow [best practices](https://schubert.io/pr-feedback-poster.pdf)*

:scroll: License
-------
```ascii

  _|_|    _|_|_|      _|_|      _|_|_|  _|    _|  _|_|_|_|        _|_|          _|    
_|    _|  _|    _|  _|    _|  _|        _|    _|  _|            _|    _|      _|  _|  
_|_|_|_|  _|_|_|    _|_|_|_|  _|        _|_|_|_|  _|_|_|            _|        _|  _|  
_|    _|  _|        _|    _|  _|        _|    _|  _|              _|          _|  _|  
_|    _|  _|        _|    _|    _|_|_|  _|    _|  _|_|_|_|      _|_|_|_|  _|    _|    


```

While <code>@lineup-lite</code> uses MPL 2.0, the Open Source Software Nutrition Label Prototype is available under the [Apache 2.0 License](https://spdx.org/licenses/Apache-2.0.html).
