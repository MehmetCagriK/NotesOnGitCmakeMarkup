# Q & A
1. What about lack of experience on Git?

> You can help them. Every one can and should learn such a popular version
> control system. You might have noticed its ubiquity among the developers.
> Have you ever seen ClearCase or Subversion tutorial on [Udacity][1]? Udacity
> was founded by one of the World's most prolific [person][2] and I think it is
> not an exaggeration when we say it is an online university that trains
> "Silicon Valley".

2. Which client application will be used (assuming not everybody will use
bash)?

> It is possible to use [SourceTree][3] or [GitHub Desktop][4], but I highly
> recommend using a terminal emulator. Many great developers use Command Line
> Interface (CLI).

3. What about dangerous git commands like revert, reset...? These can be
   problematic for certification.

> [Here][5] is a presentation I found at FAA's site. You will see a git example
> there. Git services have permission/protection mechanisms. You can only
> modify the remote branches you are allowed to. That said, master branch
> should be protected and well-controlled. This is what [Pull Requests][6] are all
> about.

4. Will git lfs be used?

> If we really need to. I don't think it is wise to overload the software
> repository with tons of binaries. It is not an FTP server or an artifact
> repository It is not an ftp server or an [artifact repository][7]. Artifact
> repositories are specialized to manage binary dependecies or binary outputs.

[1]: https://www.udacity.com/us
[2]: http://robots.stanford.edu/personal.html
[3]: https://www.sourcetreeapp.com/
[4]: https://desktop.github.com/
[5]: https://www.faa.gov/about/office_org/headquarters_offices/ang/offices/tc/library/v&vsummit/v&vsummit2014/presentations/Continuous%20Integration%20Verification%20in%20an%20Agile%20Environment%20Nicholas%20Bartlow.pdf
[6]: https://yangsu.github.io/pull-request-tutorial/
[7]: https://devops.stackexchange.com/questions/452/what-is-an-artifact-repository
