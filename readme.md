# Objective

Capture the tables in the ACA plan. Instruct LLM to be as accurate as possible when understanding the struture of the table.

The cost is around one cent and the processing took around 1 min.

The JSON files are not altered in any way.

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

- for `If you need immediate medical attention` and `Urgent care` the `Limitations, Exceptions, & Other Important Information` is incorrect


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
    - try Google Gemini and others
    - special treatment for certain types of tables
    - only one table per page is recognized
    - try higher resolution
    
- don't do by page but rather by table (merging pages)
    - the context window might not be big enough

- A more ambitious project would be to create LLM agent which would be comunicating with the LLM. For instance, via this workflow:
    - the idea is to mix business logic with LLM interaction
    - it also would be good send examples (similar pages)

    1. Ask how many tables are on the page?
    2. Is the first page a left over page from the previous page (upload previous page)
    3. Loop through all tables and ask for row and column headers.
    4. ...