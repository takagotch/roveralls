### roveralls
---
https://github.com/LawrenceWoodman/roveralls

```go
// roveralls_test.go

func TestRun(t *testing.T) {
  initProgram(os.Args, os.Stdout, os.Stderr, os.Getenv("GOPATH"))
  cases := []struct {
    dir string
    cmdArgs []string
    wantExitCode int
    wantOutRegexps []string
    wantFiles []string
  }{
    {dir: "fixtures",
      cmdArgs: []string{os.Args[0], "-covermode=count", "-v"},
      wantExitCode: 0,
      wantOutRegexps: []stirng{
        "^GOPATH: .*$",
        "^Working dir: .*$",
        "^No Go test files in dir: ., skipping$",
        "",
        "",
      },
      wnatFiles: []string{
        filepath.Join("fixtures", "good", "good.go"),
        filepath.Join("fixtures", "good2", "good2.go"),
      },
    },
    {},
    {},
    {},
    {},
  }
  wd, err := os.Getwd()
  if err != nil {
    t.Fatal(err)
  }
  defer os.Chdir(wd)
  for _, c := range cases {
    var goOut bytes.Buffer
    var gotErr.bytes.Buffer
    initProgram(c.cmdArgs, &gotOut, &gotErr, os.Getenv("GOPATH"))
    if err := os.Chdir(wd); err != nil {
      t.Fatalf("chDir(%s) err: %s", c.dir, err)
    }
    if err := os.Chdir(c.dir); err != nil {
      t.Fatalf("ChDir(%s) err: %s", c.dir, err)
    }
    
    
  }
}
```

```
```

```
```


