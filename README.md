# Py-SCSO-Compare
This is neither an official Searchcode nor an official Stackoverflow application!
## dsc_cli.py
```
usage: dsc_cli.py [-h] [-i] [-r REPO]

Download Java Code from searchcode, that contain the a StackOverflow Link.

optional arguments:
  -h, --help            show this help message and exit
  -i, --info            only get the number of results.
  -r REPO, --repo REPO  specify the repo to search by giving the repo_id.
```

## exlf_cli.py
```
usage: exlf_cli.py [-h] [-r] [-o] [-c] [-v] F

Scans Java files for a StackOverflow links and returns those in a csv
sanitized as much as possible.

positional arguments:
  F                  file to be scanned.

optional arguments:
  -h, --help         show this help message and exit
  -r, --recursive    scan a directory recursively.
  -o, --output-file  save output in csv file found in data/extracted_data.csv.
  -c, --copy-line    copy first line of the scanned file(s), removing comment
                     characters like "//". This works in tandem with
                     dsc_cli.py which writes the link to the raw file in the
                     first line with a preceding "//".
  -v, --verbose      gives a more detailed output
```

## dso_cli.py
```
usage: dso_cli.py [-h] [-q] [-b] [-a] [-o OUTPUT_FILE] [-i] [-v] I

Download code snippets from StackOverflow

positional arguments:
  I                     The id of the entity, either an answer or a question,
                        from which the code snippet(s) will be downloaded.

optional arguments:
  -h, --help            show this help message and exit
  -q, --question        Get the code snippet(s) from a question body instead.
  -b, --best-answer     When the question option is used, this option tells
                        the program to get the highest rated answer of the
                        specified question.
  -a, --accepted-answer
                        When the question option is used, this option tells
                        the program to get the accepted answer of the
                        specified question. If there is no accepted answer the
                        highest rated answer is used instead.
  -o OUTPUT_FILE, --output-file OUTPUT_FILE
                        Saves extracted code snippet to file with the
                        specified name, or if there are more than one to a
                        folder of the same name.
  -i, --input-file      Parses data from CSV file and uses that data to get
                        code snippets and downloads them into
                        data/extracted_data/. REQUIRED HEADERS:
                        Stackoverflow_Links, SC_Filepath. OPTIONAL HEADER:
                        Download.
  -v, --verbose         gives a more detailed output
```

## moss_cli_client.py
```
usage: moss_client_cli.py [-h] [-p] [-o] [-j JOIN_FILE] U F

MOSS CLI client for submitting java files to the service and downloading the
report from the service locally. Will go through the sub folders of the given
folder and submit the java files for plagiarism checks and download the
reports locally, creating a linking file in the process

positional arguments:
  U                     Your user-id for the MOSS service.
  F                     The folder whose contents you want to submit.

optional arguments:
  -h, --help            show this help message and exit
  -p, --parse           Parses the moss reports into a csv file.
  -o, --only-parse      Only parses the local moss reports and does not submit
                        files and download the reports. Requires the reports
                        and the links_to_reports html file created normally by
                        this app.
  -j JOIN_FILE, --join-file JOIN_FILE
                        When the parse or only-parse option is given, joins
                        the parsed data with the parsed data.
```
