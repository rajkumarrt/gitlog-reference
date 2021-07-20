# gitlog-reference
Gitlog reference
<h3> #git log</h3>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="Gitlog"><pre><code>
[centos@master gitpr]$ git log
commit 8bcf05ee70c9fd36d0f253a5625e03edb79268ec (HEAD -> feature.xyz, origin/feature.xyz)
Author: rajkumarrt <77945664+rajkumarrt@users.noreply.github.com>
Date:   Wed Jul 14 18:47:53 2021 +0530
</code></pre></div>
  
 <h3> #Filetering</h3>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="Gitlog"><pre><code>
<b> #Filetr by Date </b>
[centos@master gitpr]$ git log --after="2021-01-07"
commit 8bcf05ee70c9fd36d0f253a5625e03edb79268ec (HEAD -> feature.xyz, origin/feature.xyz)
Author: rajkumarrt <77945664+rajkumarrt@users.noreply.github.com>
Date:   Wed Jul 14 18:47:53 2021 +0530

git log --after="2021-01-07" --before="2021-05-07"
git log --after="today"
git log --after="yesterday"
git log --after="1 week ago"

<b> #Filter by File </b>
[centos@master gitpr]$ git log index.html
commit 8bcf05ee70c9fd36d0f253a5625e03edb79268ec (HEAD -> feature.xyz, origin/feature.xyz)
Author: rajkumarrt <77945664+rajkumarrt@users.noreply.github.com>
Date:   Wed Jul 14 18:47:53 2021 +0530

    update

commit 35e6087965c508b137e986874ab501b20506c4d9
Author: rajkumarrt <rajkumarrt@gamil.com>
Date:   Wed Jul 14 09:24:24 2021 -0400

    test file

commit 5d49fb242b5dffe21d685588ed369348ba68b484
Author: rajkumarrt <rajkumarrt@gamil.com>
Date:   Wed Jul 14 09:00:47 2021 -0400

    Index.html added
    
 <b> #Filter by Content </b>
[centos@master gitpr]$ git log -S"This is "
commit 35e6087965c508b137e986874ab501b20506c4d9
Author: rajkumarrt <rajkumarrt@gamil.com>
Date:   Wed Jul 14 09:24:24 2021 -0400

    test file

commit 5d49fb242b5dffe21d685588ed369348ba68b484
Author: rajkumarrt <rajkumarrt@gamil.com>
Date:   Wed Jul 14 09:00:47 2021 -0400

    Index.html added


</code></pre></div>

<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="Gitlog"><pre><code>
<b>#Merge commits </b>
[centos@master gitpr]$ git log master..feature
</code></pre></div>


<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="Gitlog"><pre><code>
<b>#Format output </b>
[centos@master gitpr]$ git log --pretty=format:"%Cred%an - %Cgreen%ar%n %Cblue %h -%Cgreen %s %n"
rajkumarrt - 6 days ago
  8bcf05e - update

rajkumarrt - 6 days ago
  35e6087 - test file

rajkumarrt - 6 days ago
  5d49fb2 - Index.html added

rajkumarrt - 5 days ago
  49e9dde - Update index.html

rajkumarrt - 6 days ago
  d1e181a - Merge pull request #1 from rajkumarrt/feature-a

rajkumarrt - 6 days ago
  4a57fb3 - Utils.js

rajkumarrt - 8 days ago
  101ee3f - Added the package



[centos@master gitpr]$ git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
* 8bcf05e - (HEAD -> feature.xyz, origin/feature.xyz) update (5 days ago) <rajkumarrt>
* 35e6087 - test file (5 days ago) <rajkumarrt>
* 5d49fb2 - Index.html added (5 days ago) <rajkumarrt>
* 49e9dde - (origin/main) Update index.html (5 days ago) <rajkumarrt>
*   d1e181a - Merge pull request #1 from rajkumarrt/feature-a (6 days ago) <rajkumarrt>
|\
| * 4a57fb3 - (origin/feature-a, feature-a) Utils.js (6 days ago) <rajkumarrt>
|/
* 101ee3f - (main) Added the package (8 days ago) <rajkumarrt>
* f8795a2 - Create README.md (8 days ago) <rajkumarrt>
* 7b87ff8 - main.go added (8 days ago) <rajkumarrt>
* 9a081b1 - CSS file change (8 days ago) <rajkumarrt>
* 461b64c - index.js updated (8 days ago) <rajkumarrt>
* 1df215d - First update (8 days ago) <rajkumarrt>


[centos@master gitpr]$ git log --decorate
commit 8bcf05ee70c9fd36d0f253a5625e03edb79268ec (HEAD -> feature.xyz, origin/feature.xyz)
Author: rajkumarrt <77945664+rajkumarrt@users.noreply.github.com>
Date:   Wed Jul 14 18:47:53 2021 +0530

    update

commit 35e6087965c508b137e986874ab501b20506c4d9
Author: rajkumarrt <rajkumarrt@gamil.com>
Date:   Wed Jul 14 09:24:24 2021 -0400

    test file

commit 5d49fb242b5dffe21d685588ed369348ba68b484
Author: rajkumarrt <rajkumarrt@gamil.com>
Date:   Wed Jul 14 09:00:47 2021 -0400

    Index.html added


[centos@master gitpr]$ git shortlog
rajkumarrt (12):
      First update
      index.js updated
      CSS file change
      main.go added
      Create README.md
      Added the package
      Utils.js
      Merge pull request #1 from rajkumarrt/feature-a
      Update index.html
      Index.html added
      test file
      update


[centos@master gitpr]$ git reflog
8bcf05e (HEAD -> feature.xyz, origin/feature.xyz) HEAD@{0}: rebase (continue) (finish): returning to refs/heads/feature.xyz
8bcf05e (HEAD -> feature.xyz, origin/feature.xyz) HEAD@{1}: rebase (continue): update
35e6087 HEAD@{2}: rebase (continue): test file
5d49fb2 HEAD@{3}: rebase (continue): Index.html added
49e9dde (origin/main) HEAD@{4}: pull -r origin main (start): checkout 49e9dde8bba978158cd082141e9ceb6ed8c47b1d
a4237aa HEAD@{5}: checkout: moving from feature.xyz to feature.xyz
a4237aa HEAD@{6}: commit (merge): update file
2600757 HEAD@{7}: commit: test file
2f6eadc HEAD@{8}: commit: Index.html added
4a57fb3 (origin/feature-a, feature-a) HEAD@{9}: checkout: moving from feature-a to feature.xyz
4a57fb3 (origin/feature-a, feature-a) HEAD@{10}: checkout: moving from main to feature-a
101ee3f (main) HEAD@{11}: checkout: moving from feature-a to main
4a57fb3 (origin/feature-a, feature-a) HEAD@{12}: checkout: moving from feature-a to feature-a
4a57fb3 (origin/feature-a, feature-a) HEAD@{13}: commit: Utils.js
101ee3f (main) HEAD@{14}: checkout: moving from feature-a to feature-a
101ee3f (main) HEAD@{15}: checkout: moving from main to feature-a
101ee3f (main) HEAD@{16}: checkout: moving from feature-a to main
101ee3f (main) HEAD@{17}: checkout: moving from main to feature-a
101ee3f (main) HEAD@{18}: pull: Fast-forward
f8795a2 HEAD@{19}: pull: Fast-forward
7b87ff8 HEAD@{20}: commit: main.go added
9a081b1 HEAD@{21}: Branch: renamed refs/heads/master to refs/heads/main
9a081b1 HEAD@{23}: commit: CSS file change
461b64c HEAD@{24}: commit: index.js updated
1df215d HEAD@{25}: commit (initial): First update


[centos@master gitpr]$ git log --oneline
8bcf05e (HEAD -> feature.xyz, origin/feature.xyz) update
35e6087 test file
5d49fb2 Index.html added
49e9dde (origin/main) Update index.html
d1e181a Merge pull request #1 from rajkumarrt/feature-a
4a57fb3 (origin/feature-a, feature-a) Utils.js
101ee3f (main) Added the package
f8795a2 Create README.md
7b87ff8 main.go added
9a081b1 CSS file change
461b64c index.js updated
1df215d First update

</code></pre></div>
