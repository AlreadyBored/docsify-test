# Clone checker (RUSSIAN)

Clone checker allows you to find partially or completely copied solutions with an acceptable degree of reliability.

How to use:
	
1. Install Python https://www.python.org/downloads/
2. Clone locally https://github.com/AlreadyBored/CloneChecker
3. Install Python dependencies using `pip3` `pip3 install -r requirements.txt`, add `pip3` it in `PATH` (if necessary)
4. Generate yourself a Github token (Setting => Developer settings => Personal access tokens)
5. Make `token.cfg.example` from` token.cfg` and substitute your token there from p. 4
6. Configure parameters in `config.cfg`:
* `download_data` (true / false) - determines whether the repositories will be cloned to the `data` folder or will be checked remotely (it’s better to set this parameter `true`)
* `limit` (0-0.99) - the percentage of copied content in works that will be included in the output file (for example, if set value is 0.60 in the final list of works will be those in which 60 percent or more is the copy of other students work)
* `bundle_filename` (string) - the name for the bundle, into which each job is collected for comparison (in the folder with uploaded jobs, every uploaded job will have its own bundle)
* `recursion_limit` (integer) - the limit for the number of recursive steps
task_name (string) - the name of the folder in which the loaded code will be located
* `compare_file` (string) - the name of the csv file, that will be placed in the `scores` folder and contains 2 fields: a link to a PR with a solution and a student's github id
* `concat_pattern` (string) - a pattern for files that will go to the bundle (for example `*.ts` or `*.js` selects all files with `.ts` and `.js` extension)
* `csv_delimiter` (char) - a separator symbol in csv
7. Run the checker itself `python prog.py` ( add `python` to PATH if necessary)
The distribution of works by the percentage of copied fragments appears, as well as the resulting file, which contains works with a percentage of copied code greater than limit.
Go to the folders with works and compare the bundles using any diff tool.
