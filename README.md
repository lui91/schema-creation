# Data cleaning and schema creation from

SQL schema creation from requirements. (Excercise from [Datacamp](https://app.datacamp.com/))

1.  Data loading and cleaning following data requirements from a csv. file:

![image](/imgs/schema.png)

2. Creation of the following schema:

## client

| column           | data type | description                                                |
| ---------------- | --------- | ---------------------------------------------------------- |
| `id`             | `serial`  | Client ID - primary key                                    |
| `age`            | `integer` | Client's age in years                                      |
| `job`            | `text`    | Client's type of job                                       |
| `marital`        | `text`    | Client's marital status                                    |
| `education`      | `text`    | Client's level of education                                |
| `credit_default` | `boolean` | Whether the client's credit is in default                  |
| `housing`        | `boolean` | Whether the client has an existing housing loan (mortgage) |
| `loan`           | `boolean` | Whether the client has an existing personal loan           |

<br>

## campaign

| column                       | data type | description                                                                          |
| ---------------------------- | --------- | ------------------------------------------------------------------------------------ |
| `campaign_id`                | `serial`  | Campaign ID - primary key                                                            |
| `client_id`                  | `serial`  | Client ID - references `id` in the `client` table                                    |
| `number_contacts`            | `integer` | Number of contact attempts to the client in the current campaign                     |
| `contact_duration`           | `integer` | Last contact duration in seconds                                                     |
| `pdays`                      | `integer` | Number of days since contact in previous campaign (`999` = not previously contacted) |
| `previous_campaign_contacts` | `integer` | Number of contact attempts to the client in the previous campaign                    |
| `previous_outcome`           | `boolean` | Outcome of the previous campaign                                                     |
| `campaign_outcome`           | `boolean` | Outcome of the current campaign                                                      |
| `last_contact_date`          | `date`    | Last date the client was contacted                                                   |

<br>

## economics

| column                 | data type | description                                                              |
| ---------------------- | --------- | ------------------------------------------------------------------------ |
| `client_id`            | `serial`  | Client ID - references `id` in the `client` table                        |
| `emp_var_rate`         | `float`   | Employment variation rate (quarterly indicator)                          |
| `cons_price_idx`       | `float`   | Consumer price index (monthly indicator)                                 |
| `euribor_three_months` | `float`   | Euro Interbank Offered Rate (euribor) three month rate (daily indicator) |
| `number_employed`      | `float`   | Number of employees (quarterly indicator)                                |

# Process

- [Project](project.ipynb)
