# Input

I have this JSON: 

```
{
	"id": "0001",
	"type": "donut",
	"name": "Cake",
	"ppu": 0.55,
	"batters":
		{
			"batter":
				[
					{ "id": "1001", "type": "Regular" },
					{ "id": "1002", "type": "Chocolate" },
					{ "id": "1003", "type": "Blueberry" },
					{ "id": "1004", "type": "Devil's Food" }
				]
		},
	"topping":
		[
			{ "id": "5001", "type": "None" },
			{ "id": "5002", "type": "Glazed" },
			{ "id": "5005", "type": "Sugar" },
			{ "id": "5007", "type": "Powdered Sugar" },
			{ "id": "5006", "type": "Chocolate with Sprinkles" },
			{ "id": "5003", "type": "Chocolate" },
			{ "id": "5004", "type": "Maple" }
		]
}
```

Write a jq rule to print all types from "batter" and print the output.

# Answer: 

To print all types from "batter" in the given JSON object, you can use the following jq rule:

```
jq '.batters.batter[].type'

```

This jq rule uses the following syntax:

-   `.batters` - accesses the "batters" object in the JSON
-   `.batter` - accesses the "batter" array within the "batters" object
-   `[]` - iterates over all elements in the "batter" array
-   `.type` - accesses the "type" field in each element of the "batter" array

Applying this jq rule to the given JSON object will produce the following output:

```
"Regular"
"Chocolate"
"Blueberry"
"Devil's Food"

```

You can use the `-r` option when running jq to print the output in raw format, without the enclosing double quotes around each element. For example, the following command will produce the same output as above, but without the double quotes around each element:

```
jq -r '.batters.batter[].type'

```

I hope this helps! Let me know if you have any other questions.