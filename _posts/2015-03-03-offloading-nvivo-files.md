---
published: false
---

## Offloading NVivo files Part 1

Since most of my work on QDA has involved Nvivo (I'll tell you what's right and wrong with NVivo another time), one of my first projects was to figure out how to access NVivo's data files. It turns out this isn't so complicated (at least if you are comfortable with Microsoft SQL Server - but don't worry if you aren't) as those NVivo files (with extension .nvp) are actually just Microsoft database files and can be offloaded into more friendly formats (like SQLite - by far the simplest, not to mention portable, reliable, and free, database application).

I wrote a script that will dump an NVivo file (well almost all of it) into a file containing SQL commands that can be imported into an SQLite database. The main script, [Export_NVivo.bat](https://github.com/jschultz/nvivo-interoperability/raw/master/Export_NVivo.bat), attaches your NVivo file to Microsoft SQL server, and runs an SQL script, [Export_NVivo.txt](https://github.com/jschultz/nvivo-interoperability/raw/master/Export_NVivo.txt), to produce an output file with the same name as your NVivo file but extension .sql, which can be imported into SQLite. To use these scripts, you'll need to download them both into the same directory, then use a Command Window to run:

> Export_NVivo.bat <name of your NVivo file>

For obvious reasons, I don't suggest you do this on your real live NVivo data - just make a copy of it in case for some reason Microsoft SQL server should corrupt it. Then you'll have an SQL file that can be imported using SQLite (or its GUI front end DB Browser/SQLiteBrowser).

And if you don't feel like doing this right away, [here's one I prepared earlier from NVivo's sample project 'Environmental Change Down East'](https://github.com/jschultz/nvivo-interoperability/raw/master/Sample%20project.sqlite). Go on, take a look at it.

Next installment, we'll start figuring out what those data structures mean...