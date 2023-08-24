# DataRaceBench-ML

DataRaceBench-ML (DRB-ML) is an extension of the original DataRaceBench, tailored specifically for data race analysis within the context of machine learning.

## Structure of Data
Each record in DRB-ML contains the following fields:
- "ID": A unique index number starting from 1. It preserves the original ordering in DRB and is stored as an integer.
- "name": The original filename of the DRB file. This is directly copied from the DRB filenames and stored as a string.
- "DRB\_code": The original code present in DRB microbenchmarks. It is copied verbatim from the DRB benchmarks and stored as a string.
- "trimmed\_code": The DRB\_code with all comments removed. We employed a script to process each microbenchmark in DRB and store the comment-free code as a string.
- "code\_len": An integer value representing the string length of the trimmed code. This label aids in thresholding data to match the input size constraints of various machine learning models, ensuring compatibility and adaptability.
- "data\_race": This is a boolean value representing the data race condition in DRB. The presence of a data race is indicated by 1, and its absence by 0.
- "data\_race\_label": This label indicates the type of data race condition (race-yes or race-no) that DRB marks. We used DRB metadata to generate this label and stored it as a string variable.
- "var\_pairs": This is a list of pairs of variables associated with a data race. It is empty when "data\_race" is 0. Each item follows the format [VAR0, VAR1], where VAR1 depends on VAR0, and each variable has the following attributes:
    - "name": Variable names stored as a string variable.
    - "line": The line number indicating the variable's location, stored as an integer variable.
    - "col": The column number showing the variable's location, stored as an integer variable.
    - "operation": The operation performed on the variable, stored as a string variable. The value is either "w" (representing a write operation) or "r" (representing a read operation).

## Usage
DRB-ML is formatted in JSON, making it straightforward to load in any programming environment.

## Get in Touch
For inquiries or contributions, please reach out to lechen AT iastate.edu.




