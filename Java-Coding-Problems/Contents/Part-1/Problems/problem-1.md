# <p align="center">Problem 1 - Creating a multiline SQL, JSON, and HTML string</p>
---

## Description
Let's consider the following SQL multiline string;
```sql
UPDATE "public"."office"
SET ("address_first", "address_second", "phone") =
	(SELECT "public"."employee"."first_name",
			"public"."employee"."last_name", ?
	FROM "public"."employee"
	WHERE "public"."employee"."job_title" = ?
```
## Before JDK 8
Probably the most common approach relies on straightforward concatenation via the well-known `+` operator. This way, we obtain a multiline string representation, as follows:

```java
String sql =
"UPDATE \"public\".\"office\"\n"
+ "SET (\"address_first\", \"address_second\", \"phone\") =\n"
+ " (SELECT \"public\".\"employee\".\"first_name\",\n"
+ " \"public\".\"employee\".\"last_name\", ?\n"
+ " FROM \"public\".\"employee\"\n"
+ " WHERE \"public\".\"employee\".\"job_title\" = ?";
```
