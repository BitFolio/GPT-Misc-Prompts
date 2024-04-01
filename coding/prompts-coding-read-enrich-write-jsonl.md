# Working with a jsonl file

## Read it, enrich it and write to a new jsonl
```
Using python, write an application that will (1) read a jsonl file and parse the file, (2) the contents of the jsonl file is in the format of {"input_text": {"question": "A question?", "context": "This question reflects concerns about..."}, "output_text": "An answer"}, (3) loop over the contents of the file, (4) and create a prompt for each question, context and answer and pass the new prompt to openai's gpt-3-5-turbo, while asking the model to improve the answer and rewrite the answer, (5) then write the question, context and the new answer to a new jsonl file.
```
