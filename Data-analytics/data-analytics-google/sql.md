# SQL

SQL is used to store, organize and analyze your data.**Structured Query Language** (or **SQL**, often pronounced “sequel”) enables data analysts to talk to their databases. SQL is one of the most useful data analyst tools, especially when working with large datasets in tables. It can help you investigate huge databases, track down text (referred to as strings) and numbers, and filter for the exact kind of data you need—much faster than a spreadsheet can.&#x20;

#### Query

A query is a request for data or information from a database.

\
A **query** is a request for data or information from a database. When you query databases, you use SQL to communicate your question or request. You and the database can always exchange information as long as you speak the same language.

Every programming language, including SQL, follows a unique set of guidelines known as **syntax**. **Syntax** is the predetermined structure of a language that includes all required words, symbols, and punctuation, as well as their proper placement. As soon as you enter your search criteria using the correct syntax, the query starts working to pull the data you’ve requested from the target database.

The syntax of every SQL query is the same:&#x20;

* Use **SELECT** to choose the columns you want to return.
* Use **FROM** to choose the tables where the columns you want are located.
* Use **WHERE** to filter for certain information.

A SQL query is like filling in a template. You will find that if you are writing a SQL query from scratch, it is helpful to start a query by writing the SELECT, FROM, and WHERE keywords in the following format:&#x20;

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/MwhC5HMJRFKIQuRzCURSDw_754b0ed1d87441a298173d87c0bfdbf1_Select_From_Where.png?expiry=1678752000000&#x26;hmac=km1zXSrQ20xzl4M25RmUdf1QH59cMvZRjfRS0vAyYNY" alt=""><figcaption></figcaption></figure>

Next, enter the table name after the FROM; the table columns you want after the SELECT; and, finally, the conditions you want to place on your query after the WHERE. Make sure to add a new line and indent when adding these, as shown below:

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/tATEidLdSU2ExInS3XlNog_a8c8eba2320243f59e18258430049353_Screen-Shot-2020-11-11-at-4.23.52-PM.png?expiry=1678752000000&#x26;hmac=sAzPVOxsFZyUvjJcHFsHwPyssmLGadXn8X9kd3p1Om0" alt="SELECT columns you want to look at FROM table the data lives in WHERE certain condition is met"><figcaption></figcaption></figure>

Following this method each time makes it easier to write SQL queries. It can also help you make fewer syntax errors.

#### **Example of a query**

Here is how a simple query would appear in BigQuery, a data warehouse on the Google Cloud Platform.

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/vNz9GfCMQiGc_RnwjMIhfQ_1d09943b48924e6cbf9915e30f771d86_Screen-Shot-2020-11-11-at-4.25.17-PM.png?expiry=1678752000000&#x26;hmac=2X6ZYgzf7U6rjhkF1RLR-416Af9k5eW_wwEIAr5drT4" alt="SELECT first_name FROM customer_data.customer_name WHERE first_name = &#x27;Tony&#x27;"><figcaption></figcaption></figure>

The above query uses three commands to locate customers with the first name Tony:

1. **SELECT** the column named **first\_name**
2. **FROM** a table named **customer\_name** (in a dataset named **customer\_data**) (The dataset name is always followed by a dot, and then the table name.)
3. But only return the data **WHERE** the first\_name is **Tony**

The results from the query might be similar to the following:

| first\_name |
| ----------- |
| Tony        |
| Tony        |
| Tony        |

As you can conclude, this query had the correct syntax, but wasn't very useful after the data was returned.

### Multiple columns in a query

In real life, you will need to work with more data beyond customers named Tony. Multiple columns that are chosen by the same SELECT command can be indented and grouped together.

If you are requesting multiple data fields from a table, you need to include these columns in your SELECT command. Each column is separated by a comma as shown below:

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/wOQ23bcrTeakNt23K23myw_8351721c783f4528a58b44435e8e8650_Screen-Shot-2020-11-11-at-4.26.17-PM.png?expiry=1678752000000&#x26;hmac=2ONdlZwHFfzi_I4wPhUO7FpleDK-QbxSOHk9GexMT04" alt="SELECT Column A, Column B, Column C FROM Table where the data lives WHERE certain condition is met"><figcaption></figcaption></figure>

Here is an example of how it would appear in BigQuery:

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/-kywAm5gQTOMsAJuYEEzSA_2dab01a4a07d4ad386cb1f56d7e3b8b6_Screen-Shot-2020-11-11-at-4.27.02-PM.png?expiry=1678752000000&#x26;hmac=bXGBOs3ZXGJGSHkUQGafDkPYXWere_FevA8Bk4ECb4M" alt="SELECT customer_id, first_name, last_name FROM customer_data.customer_name WHERE first_name = &#x27;Tony&#x27;"><figcaption></figcaption></figure>

The above query uses three commands to locate customers with the first name Tony.

1. **SELECT** the columns named **customer\_id**, **first\_name**, and **last\_name**
2. **FROM** a table named **customer\_name** (in a dataset named **customer\_data**) (The dataset name is always followed by a dot, and then the table name.)
3. But only return the data **WHERE** the first\_name is **Tony**

The only difference between this query and the previous one is that more data columns are selected. The previous query selected first\_name only while this query selects customer\_id and last\_name in addition to first\_name. In general, it is a more efficient use of resources to select only the columns that you need. For example, it makes sense to select more columns if you will actually use the additional fields in your WHERE clause. If you have multiple conditions in your WHERE clause, they may be written like this:

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/kUL18th9QOqC9fLYfeDqEw_eb2d08d4837d44ef99de7c61179418bd_Screen-Shot-2020-11-11-at-4.27.47-PM.png?expiry=1678752000000&#x26;hmac=VMNeIs83Q9x-JIuZ6DXWQ1QgX9xRialZM7eKAcXrzbs" alt="SELECT ColumnA, ColumnB, ColumnC FROM Table where the data lives WHERE Condition 1 AND condition 2 AND condition 3"><figcaption></figcaption></figure>

Notice that unlike the SELECT command that uses a comma to separate fields/variables/parameters, the WHERE command uses the AND statement to connect conditions. As you become a more advanced writer of queries, you will make use of other connectors/operators such as OR and NOT.&#x20;

Here is a BigQuery example with multiple fields used in a WHERE clause:

<figure><img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ecPw3J_NQcmD8NyfzRHJUw_5120dcd87b99400cb7f4a9014439ee18_Screen-Shot-2020-11-11-at-4.29.06-PM.png?expiry=1678752000000&#x26;hmac=PRNyQk9JeirhrkUBS4cSN4Qo6r10Ia9lNDTXVbb6WMI" alt="SELECT customer_id, first_name, last_name FROM customer_data.customer_name WHERE customer_id>0 AND first_name = &#x27;Tony&#x27;"><figcaption></figcaption></figure>

The above query uses three commands to locate customers with a valid (greater than 0) customer ID whose first name is Tony and last name is Magnolia.

1. **SELECT** the columns named **customer\_id**, **first\_name**, and **last\_name**
2. **FROM** a table named **customer\_name** (in a dataset named **customer\_data**) (The dataset name is always followed by a dot, and then the table name.)
3. But only return the data **WHERE** customer\_id is greater than **0**, first\_name is **Tony**, and last\_name is **Magnolia**.

Note that one of the conditions is a logical condition that checks to see if customer\_id is greater than zero.

If only one customer is named Tony Magnolia, the results from the query could be:

| customer\_id | first\_name | last\_name |
| ------------ | ----------- | ---------- |
| 1967         | Tony        | Magnolia   |

If more than one customer has the same name, the results from the query could be:

| customer\_id | first\_name | last\_name |
| ------------ | ----------- | ---------- |
| 1967         | Tony        | Magnolia   |
| 7689         | Tony        | Magnolia   |
