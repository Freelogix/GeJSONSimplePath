# GeJSONSimplePath
SimplePath is a simple manipulator for JSON structures in GeJSON

```
String jsonStr="{\"book\":{\"pages\":15}}";
JSONParser parser = new JSONParser(jsonStr);
 
JSONObject o = (JSONObject) parser.parse();

System.out.println(o.toString());

SimplePath x = new SimplePath();

// TEST 1
try {
	x.get(o,"book.pages");
	System.out.println(x.getRestultType());
		switch(x.getResultType()) {
		case JSONData.DATA_TYPE_INT:
			System.out.println(((JSONData)x.getResult()).getInt());
		break;
		case JSONData.DATA_TYPE_OBJECT:
			System.out.println(((JSONObject)x.getResult()).toString());
		break;
		}
	}catch (ManipulatorException e) {
		System.out.println(e.getMessage());
}
```
