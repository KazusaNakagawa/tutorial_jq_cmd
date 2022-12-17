## tutorial

### I/O 

* 1 Select message and committer name
  ```bash
  cat repos.json | jq '.[] | {message: .commit.message, name: .commit.committer.name}'
  ```

  ```json
  {
    "message": "docs: Document repeat(exp)",
    "name": "Nico Williams"
  }
  {
    "message": "Mention -n in IO-section and for input/inputs",
    "name": "Nico Williams"
  }
  {
    "message": "Fix iterration problem for non decimal string\n\nWhen the string transformation to number failed, all following\ntransformation failed too.\n\nThis happend because status in decNumberFromString function is\nupdated just in error case. Reusing the DEC_CONTEXT that failed\nbefore results into error even if the string is valid number.",
    "name": "Nico Williams"
  }
  {
    "message": "docs: point to Libera.Chat instead of Freenode",
    "name": "Nico Williams"
  }
  {
    "message": "Missing \"va_end\" call. This was found by running the cppcheck static analysis where it shows as error.",
    "name": "Nico Williams"
  }
  ```


* 2 Select sha and author name
  ```bash
  cat repos.json | jq '.[] | {sha: .sha, name: .commit.author.name}'
  ```

  ```json
  {
    "sha": "cff5336ec71b6fee396a95bb0e4bea365e0cd1e8",
    "name": "Mattias Wadman"
  }
  {
    "sha": "f2ad9517c72f6267ae317639ab56bbfd4a8653d4",
    "name": "Mattias Wadman"
  }
  {
    "sha": "c4d39c4d22f2b12225ca1b311708f7e084ad9ff8",
    "name": "Tomas Halman"
  }
  {
    "sha": "174db0f93552bdb551ae1f3c5c64744df0ad8e2f",
    "name": "Naïm Favier"
  }
  {
    "sha": "29cf77977ef52eec708982b19bf9d2ec17443337",
    "name": "Lukas Lansky"
  }
  ```

* 3 Specify the last list element
  ```bash
  cat repos.json | jq '.[-1] | {sha: .sha, name: .commit.author.name}'
  ```

  ```json
  {
    "sha": "29cf77977ef52eec708982b19bf9d2ec17443337",
    "name": "Lukas Lansky"
  }
  ```