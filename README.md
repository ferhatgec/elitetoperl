# [elite](https://github.com/ferhatgec/elite)toperl
## [elite](https://github.com/ferhatgec/elite) -> perl converter

### input:
```rs
required_version is 0.1

set ProjectName as "elitetoperl"
set HOME        as env "HOME"


for argument "install" [
    use exec "cargo install --path ."

    for exists "{HOME}.cargo/bin/{ProjectName}" [
        println "{ProjectName} installed to {HOME}.cargo/bin/{ProjectName}."
    ]

    use signal "exit"
]
```

### output
```perl
#!/usr/bin/env perl
use POSIX();
my $arch = lc((POSIX::uname)[4]);
my $os = lc((POSIX::uname)[0]);
if("0.1" ne "0.1")
{
 print "elite: Required higher version\n";
 exit 1;
}
$ProjectName = "elitetoperl";
$HOME = "/home/gech";
if($#ARGV ge 0 && $ARGV[0] eq "install")
{
 system "cargo install --path .";
 if(-e "/home/gech/.cargo/bin/elitetoperl")
{
  print "elitetoperl installed to /home/gech/.cargo/bin/elitetoperl.\n";
}
 exit 1;
}
```

### elitetoperl licensed under the terms of MIT License
