Installation
============

1. Download
2. Rename folder to `nsm_entry_select`
3. Copy to your `/system/expressionengine/thrid_party/` directory
4. Install fieldtype
5. Create a new field.

Usage
=====

Let's say your custom field name is `my_entry_relationship`. In your templates you have one tag with a single optional parameter:

Example 1: Outputs the selected entry id's concatenated with a "|" ie: 1|2|3 Use this in `{exp:channel:entries}` tag `entry_id` parameter.

	{my_entry_relationship}

Example 2: Outputs the selected entry id's concatenated with a "," ie: 1,2,3 Use this in `{exp:query}` tag `WHERE entry_id IN()` conditional.

	<ul>
	{exp:query sql="
	    SELECT * 
	    FROM `exp_channel_titles`
	    WHERE `entry_id`
	    IN({my_entry_relationship, divider=","});
	"}
	    <li>{title}</li>
	{/exp:query}
	</ul>