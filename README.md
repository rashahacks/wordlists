# wordlists

## Download Wordlist
```
wget https://raw.githubusercontent.com/rashahacks/wordlists/main/master.txt -o <filename.txt>
```
```
curl "https://raw.githubusercontent.com/rashahacks/wordlists/main/master.txt" -o <filename.txt>
```

## The Process of Adding Data
Users can extract all the possible words(parameters, values, endpoints) by piping the URLs from Burp project to few linux commands.

1. **Data Collection:** Collect URLs in Burpsuite Project
2. **Words Extraction:** Pipe the URLs to linux commands to extract words
3. **Cleaning:** Remove researcher and program related words.
4. Send a **Pull Request.**

### Data Collection:
* Hack at the organization for few days atleast and collect URLs with most of the application covered.
* Save the Burpsuite Project, Copy all URLs from HTTP history or Sitemap.
* Sort the URLs and Save in a text file.

### Words Extraction (Example)
```
cat burp_urls.txt| cut -d'/' -f4-100 | tr '/' '\n' | tr '?' '\n' | tr '&' '\n' | tr '=' '\n' | sort -u | tee wordlist.txt
cat wordlist.txt | grep -v <words-t-remove> | tee final_wordlist.txt
```

### Cleaning
Please clean the wordlist after removing your personal data and program related data (program name, sensitive words that can reveal program info).

### Pull Request
After completing all previous phases, create a PR and the team will accept your PR within a week.
