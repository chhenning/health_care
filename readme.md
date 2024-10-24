# Objective

Capture the tables the in ACA plan. Instruct LLM to be as accurate as possible when understanding the struture of the table.

## Page 0

- LLM extract correctly one table
- text looks good and complete including url

## Page 1

- complex table with rows inside cells
- table is captured correctly

### Not Good

- LLM is ignoring left over table on the top of the page
- the "what you will pay" is ignored
- the cell for `If you need drugs to treat your illness or condition` is split into several rows


## Page 2

- looks good

## Page 3

- Bad: `*See Vision Services section` is not shared with second row

## Page 4

- no table

## Page 5

- LLM is making up `Scenario` from text before
- numbers are correct

- Bad: Scenario text in parenthesis is missing
- Bad: Included services are missing

## Page 6

- no table

## Page 7

- no table

## Page 8

- no table

## Page 9
- no table


# Next Steps

- improve extracting tables, for instance we could ask for row and column headers
    - special treatment for certain types of tables
    - only one table per page is recognized

- don't do by page but rather by table (merging pages)

- A more ambitious project would be to create a chatbot that ingest the plan and can answer questions
    - need to create a vector store (embeddings) of the plan data (strucutred text)
    