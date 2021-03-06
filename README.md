Firefox for iOS [![codebeat badge](https://codebeat.co/badges/67e58b6d-bc89-4f22-ba8f-7668a9c15c5a)](https://codebeat.co/projects/github-com-mozilla-firefox-ios) [![BuddyBuild](https://dashboard.buddybuild.com/api/statusImage?appID=57bf25c0f096bc01001e21e0&branch=master&build=latest)](https://dashboard.buddybuild.com/apps/57bf25c0f096bc01001e21e0/build/latest) [![codecov](https://codecov.io/gh/mozilla-mobile/firefox-ios/branch/master/graph/badge.svg)](https://codecov.io/gh/mozilla-mobile/firefox-ios/branch/master)
===============

Download on the [App Store](https://itunes.apple.com/app/firefox-web-browser/id989804926).

This branch (master)
-----------

This branch is for mainline development that will ship in *v9.0*.

This branch only works with Xcode 9 (currently in beta), and supports iOS 9.x, 10, and 11.

This branch is written in Swift 3.1.

Please make sure you aim your pull requests in the right direction.

For bug fixes and features for the upcoming v8.0 release, please see the *v8.x* branch.

Getting involved
----------------

We encourage you to participate in this open source project. We love Pull Requests, Bug Reports, ideas, (security) code reviews or any kind of positive contribution. Please read the [Community Participation Guidelines](https://www.mozilla.org/en-US/about/governance/policies/participation/).

* IRC:            [#mobile](https://wiki.mozilla.org/IRC) for general discussion and [#mobistatus](https://wiki.mozilla.org/IRC) for team status updates.
* Mailing list:   [mobile-firefox-dev@mozilla.org](https://mail.mozilla.org/listinfo/mobile-firefox-dev).
* Bugs:           [File a new bug](https://bugzilla.mozilla.org/enter_bug.cgi?bug_file_loc=http%3A%2F%2F&bug_ignored=0&op_sys=iOS%20&product=Firefox%20for%20iOS&rep_platform=All) • [Existing bugs](https://bugzilla.mozilla.org/describecomponents.cgi?product=Firefox%20for%20iOS) 

Want to contribute but don't know where to start? Here is a list of [Good First Bugs.](http://www.joshmatthews.net/bugsahoy/?mobileios=1&simple=1)

Likewise, the design and UX is still in flux. Don't get attached to them. They will change tomorrow!
https://mozilla.invisionapp.com/share/HA254M642#/screens/63057282?maintainScrollPosition=false

*GitHub issues are enabled* on this repository, but we encourage you to file a bug (see above). We'll accept issues to track work items that don't yet have a pull request, and also as an early funnel for bug reports, but Bugzilla is the source of truth for lots of good reasons — issues will be shifted into Bugzilla, and pull requests need a bug number.

Building the code
-----------------

> __As of Sept. 16, 2016, this project requires Xcode 8.__

1. Install the latest [Xcode developer tools](https://developer.apple.com/xcode/downloads/) from Apple.
1. Install Carthage
    ```shell
    brew update
    brew install carthage
    ```
1. Clone the repository:
    ```shell
    git clone https://github.com/mozilla-mobile/firefox-ios
    ```
1. Pull in the project dependencies:
    ```shell
    cd firefox-ios
    sh ./bootstrap.sh
    ```
1. Open `Client.xcodeproj` in Xcode.
1. Build the `Fennec` scheme in Xcode.

## Contributor guidelines

### Creating a pull request
* All pull requests must be associated with a specific bug in [Bugzilla](https://bugzilla.mozilla.org/).
 * If a bug corresponding to the fix does not yet exist, please [file it](https://bugzilla.mozilla.org/enter_bug.cgi?op_sys=iOS&product=Firefox%20for%20iOS&rep_platform=All).
 * You'll need to be logged in to create/update bugs, but note that Bugzilla allows you to sign in with your GitHub account.
* Use the bug number/title as the name of pull request. For example, a pull request for [bug 1135920](https://bugzilla.mozilla.org/show_bug.cgi?id=1135920) would be titled "Bug 1135920 - Create a top sites panel".
* Finally, upload an attachment to the bug pointing to the GitHub pull request.
 1. Click <b>Add an attachment</b>.
 2. Next to <b>File</b>, click <b>Paste text as attachment</b>.
 3. Paste the URL of the GitHub pull request.
 4. Enter "Pull request" as the description.
 5. Finally, flag the pull request for review. Set the <b>review</b> field to "?", then enter the name of the person you'd like to review your patch. If you don't know whom to add as the reviewer, click <b>suggested reviewers</b> and select a name from the dropdown list.

<b>Pro tip: To simplify the attachment step, install the [Github Bugzilla Tweaks](https://github.com/autonome/Github-Bugzilla-Tweaks) addon. This will add a button that takes care of the first four attachment steps for you.</b>

### Swift style
* Swift code should generally follow the conventions listed at https://github.com/raywenderlich/swift-style-guide.
  * Exception: we use 4-space indentation instead of 2.

### Whitespace
* New code should not contain any trailing whitespace.
* We recommend enabling both the "Automatically trim trailing whitespace" and "Including whitespace-only lines" preferences in Xcode (under Text Editing).
* <code>git rebase --whitespace=fix</code> can also be used to remove whitespace from your commits before issuing a pull request.

### Commits
* Each commit should have a single clear purpose. If a commit contains multiple unrelated changes, those changes should be split into separate commits.
* If a commit requires another commit to build properly, those commits should be squashed.
* Follow-up commits for any review comments should be squashed. Do not include "Fixed PR comments", merge commits, or other "temporary" commits in pull requests.
