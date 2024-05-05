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
