Projects

#### Table of contents

- [Youtube video-syncer](#youtube-video-syncer)
- [Sync MPV watch-later files](#sync-mpv-watch-later-files)
- [Local podcast publisher](#local-podcast-publisher)
- [Mini projects](#mini-projects)
- [Qiime2 Galaxy Wrappers](#qiime2-galaxy-wrappers)
- [Kubectl completion patching](#kubectl-completion-patching)
- [Execute-on-files](#execute-on-files)
- [Execute-in-repos](#execute-in-repos)

## Youtube video-syncer

[video-syncer](https://github.com/diepfote/golang-tools/tree/32d62f7cad6f27d7c0503ba92907fee74f0a25b1/video-syncer)  
Syncs youtube videos between 2 computers via text files.

## Sync MPV watch-later files

[sync-mpv-watch-later-files](https://github.com/diepfote/golang-tools/tree/7f86a2e32d83d6f09f6af758ed267eee826ddef6/sync-video-syncer-mpv-watch-later-files)  
Syncs `~/.config/mpv/watch_later` or `~/.local/state/mpv/watch_later` directories between 2 computers.
Uses functionality found in [video-syncer](#youtube-video-syncer) and [report-videos.sh](https://github.com/diepfote/scripts/blob/fc09c10453e8527e3fb53a3c379b128310c60b69/normal-privileges_systemd_scripts/report-videos.sh)

## Local podcast publisher  

[local podcast publisher](https://github.com/diepfote/local-podcast-publisher)  
Makes Podcasts available/downloadable on the local network.  
Particularly useful if no-one officially published it to a podcasting platform.

Note: it uses the following `ffprobe` and `ffmpeg` helpers:

* [ffprobe](https://github.com/search?q=repo%3Adiepfote%2Fscripts+ffprobe&type=code)
* [ffmpeg](https://github.com/search?q=repo%3Adiepfote%2Fscripts%20ffmpeg&type=code)

### Dynamic range compression

[download and drc a batch of files](https://github.com/diepfote/scripts/blob/939d8cde8284a62ac80ff3832c27add730d4b74c/source-me/posix-compliant-shells.sh#L443)  
As I do not like to have my ears blown out or not be able to hear
what is being said on in video/on podcast. 
So I always run dynamic range compression before I add tracks to the podcast feed.


## Vim plugins

### Mine

* [Primitive yaml sort](https://github.com/diepfote/vim-primitive-yamlsort)

### Patched

* [vim-checkbox](https://github.com/diepfote/vim-checkbox)
* [yaml-vim](https://github.com/diepfote/yaml-vim)


## Mini projects

* [github gists](https://gist.github.com/search?q=user%3Adiepfote+%22mini-project%22&ref=searchresults)


## Qiime2 Galaxy Wrappers

* Version: 2019.7
* [repo](https://github.com/diepfote/qiime2_wrappers)
* [installable package for Galaxy Project](https://toolshed.g2.bx.psu.edu/view/florianbegusch/qiime2_suite)

### What was done

We auto-generated xml config files for a [Galaxy Project](https://galaxyproject.org/) to integrate the qiime2 cli into the UI of this tool.

Qiime2 includes several commands and subcommands, each of these have their own options and flags.
These needed to be parsed from the initial help page and then converted to a xml file per command-subcommand combination.

#### Example

help output:

<p><details>

```text
(qiime2-2019.7) root@dd8a4d319d86:/data# qiime vsearch cluster-features-de-novo --help
Usage: qiime vsearch cluster-features-de-novo [OPTIONS]

  Given a feature table and the associated feature sequences, cluster the
  features based on user-specified percent identity threshold of their
  sequences. This is not a general-purpose de novo clustering method, but
  rather is intended to be used for clustering the results of quality-
  filtering/dereplication methods, such as DADA2, or for re-clustering a
  FeatureTable at a lower percent identity than it was originally clustered
  at. When a group of features in the input table are clustered into a
  single feature, the frequency of that single feature in a given sample is
  the sum of the frequencies of the features that were clustered in that
  sample. Feature identifiers and sequences will be inherited from the
  centroid feature of each cluster. See the vsearch documentation for
  details on how sequence clustering is performed.

Inputs:
  --i-sequences ARTIFACT FeatureData[Sequence]
                          The sequences corresponding to the features in
                          table.                                    [required]
  --i-table ARTIFACT FeatureTable[Frequency]
                          The feature table to be clustered.        [required]
Parameters:
  --p-perc-identity PROPORTION Range(0, 1, inclusive_start=False,
    inclusive_end=True)   The percent identity at which clustering should be
                          performed. This parameter maps to vsearch's --id
                          parameter.                                [required]
  --p-threads INTEGER Range(0, 256, inclusive_end=True)
                          The number of threads to use for computation.
                          Passing 0 will launch one thread per CPU core.
                                                                  [default: 1]
Outputs:
  --o-clustered-table ARTIFACT FeatureTable[Frequency]
                          The table following clustering of features.
                                                                    [required]
  --o-clustered-sequences ARTIFACT FeatureData[Sequence]
                          Sequences representing clustered features.
                                                                    [required]
Miscellaneous:
  --output-dir PATH       Output unspecified results to a directory
  --verbose / --quiet     Display verbose output to stdout and/or stderr
                          during execution of this action. Or silence output
                          if execution is successful (silence is golden).
  --citations             Show citations and exit.
  --help                  Show this message and exit.
```

</details></p>

generated xml:

<p><details>

```text
<?xml version="1.0" ?>
<tool id="qiime_vsearch_cluster-features-de-novo" name="qiime vsearch cluster-features-de-novo" version="2019.7">
	<description> - De novo clustering of features.</description>
	<requirements>
		<requirement type="package" version="2019.7">qiime2</requirement>
	</requirements>
	<command><![CDATA[
qiime vsearch cluster-features-de-novo

--i-sequences=$isequences
--i-table=$itable
--p-perc-identity="$ppercidentity"

#set $pthreads = '${GALAXY_SLOTS:-4}'
#if str($pthreads):
 --p-threads="$pthreads"
#end if

--o-clustered-table=oclusteredtable
--o-clustered-sequences=oclusteredsequences
;
cp oclusteredtable.qza $oclusteredtable;
cp oclusteredsequences.qza $oclusteredsequences
	]]></command>
	<inputs>
		<param format="qza,no_unzip.zip" label="--i-sequences: ARTIFACT FeatureData[Sequence] The sequences corresponding to the features in table.                                    [required]" name="isequences" optional="False" type="data"/>
		<param format="qza,no_unzip.zip" label="--i-table: ARTIFACT FeatureTable[Frequency] The feature table to be clustered.        [required]" name="itable" optional="False" type="data"/>
		
		<param label="--p-perc-identity: PROPORTION Range(0, 1, inclusive_start=False, inclusive_end=True)   The percent identity at which clustering should be performed. This parameter maps to vsearch's --id parameter.                                [required]" name="ppercidentity" optional="False" min="0" max="1" value="" exclude_min="True" exclude_max="False" type="float"/>
	</inputs>
	<outputs>
		<data format="qza" label="${tool.name} on ${on_string}: clusteredtable.qza" name="oclusteredtable"/>
		<data format="qza" label="${tool.name} on ${on_string}: clusteredsequences.qza" name="oclusteredsequences"/>
	</outputs>
	<help><![CDATA[
De novo clustering of features.
###############################

Given a feature table and the associated feature sequences, cluster the
features based on user-specified percent identity threshold of their
sequences. This is not a general-purpose de novo clustering method, but
rather is intended to be used for clustering the results of quality-
filtering/dereplication methods, such as DADA2, or for re-clustering a
FeatureTable at a lower percent identity than it was originally clustered
at. When a group of features in the input table are clustered into a single
feature, the frequency of that single feature in a given sample is the sum
of the frequencies of the features that were clustered in that sample.
Feature identifiers and sequences will be inherited from the centroid
feature of each cluster. See the vsearch documentation for details on how
sequence clustering is performed.

Parameters
----------
sequences : FeatureData[Sequence]
    The sequences corresponding to the features in table.
table : FeatureTable[Frequency]
    The feature table to be clustered.
perc_identity : Float % Range(0, 1, inclusive_start=False, inclusive_end=True)
    The percent identity at which clustering should be performed. This
    parameter maps to vsearch's --id parameter.
Returns
-------
clustered_table : FeatureTable[Frequency]
    The table following clustering of features.
clustered_sequences : FeatureData[Sequence]
    Sequences representing clustered features.
	]]></help>
<macros>
    <import>qiime_citation.xml</import>
</macros>
<expand macro="qiime_citation"/>
</tool>
```

</details></p>

## Kubectl Completion Patching

What does it do?

It allows you to add completions for custom written `kubectl`
plugins, `krew` plugins and you can even modify how things like `namespaces`
are completed.  
Lattermost I use to cache `namespaces` if the `$KUBECONFIG` is unmodified.
This way if I hit `<TAB>` after `-n` I receive suggestions without delay.

For more details [click](../terminal-config/kubectl-bash-completion-patching/index.html)

## Execute-on-files

Run arbitrary commands on files simultaneously/concurrently.

For more details [click](https://github.com/diepfote/golang-tools/tree/621f347afe3196753d8df22daa120fa024d0fdf7/execute-on-files)

## Execute-in-repos

Run arbitrary commands in git repos or plain old directories simultaneously/concurrently.

For more details [click](https://github.com/diepfote/golang-tools/tree/621f347afe3196753d8df22daa120fa024d0fdf7/execute-in-repos)

