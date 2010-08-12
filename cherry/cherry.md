!SLIDE

# Cherry #

!SLIDE commandline incremental

	$ git log --oneline origin/gsoc-index ^HEAD
	b0941f9 Add support for inserting empty entries on the index
	8c870fc Add support for extended index entries
	b376cb1 Add tests to t0601 to cover the TREE extension
	edc438e Move test resources to a common directory
	933cb11 Add support for the TREE index extension
	6018dbf Add unit tests for index manipulation

	$ git cherry -v HEAD origin/gsoc-index
	+ 6018dbfa702b818590ae682bf9bbede716ef290e Add unit tests for index manipulation
	+ 933cb118437ee8a4422e956197a8a4f09fd7e9df Add support for the TREE index extension
	+ edc438eedf6854c51e1a0d7954a6849046f5a4f6 Move test resources to a common directory
	+ b376cb120f0113294b80e7fd540d5dc197797764 Add tests to t0601 to cover the TREE extension
	+ 8c870fcebb8f625a8e172a49a44153af8f37c8b7 Add support for extended index entries
	+ b0941f9c70ffe67f0387a827b338e64ecf3190f0 Add support for inserting empty entries on the index

!SLIDE commandline incremental

	$ git cherry-pick 6018dbfa70
	Finished one cherry-pick.
	[test e144b96] Add unit tests for index manipulation
	 Author: Vicent Marti <tanoku@gmail.com>
	 4 files changed, 209 insertions(+), 0 deletions(-)
	$ git cherry-pick edc438eedf
	(output)
	$ git cherry-pick b376cb1
	(output)

	$ git cherry -v HEAD origin/gsoc-index
	- 6018dbfa702b818590ae682bf9bbede716ef290e Add unit tests for index manipulation
	+ 933cb118437ee8a4422e956197a8a4f09fd7e9df Add support for the TREE index extension
	- edc438eedf6854c51e1a0d7954a6849046f5a4f6 Move test resources to a common directory
	- b376cb120f0113294b80e7fd540d5dc197797764 Add tests to t0601 to cover the TREE extension
	+ 8c870fcebb8f625a8e172a49a44153af8f37c8b7 Add support for extended index entries
	+ b0941f9c70ffe67f0387a827b338e64ecf3190f0 Add support for inserting empty entries on the index

	