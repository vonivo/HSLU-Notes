```java
@RequestMapping(value="/ex/foos", method=RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
	return "asdf"
}
``` 

`@RequestMapping` wird durch:
- `@GetMapping`
- `@PostMapping`
- `@DeleteMapping`
- `@PutMapping`
- `@PatchMapping`
Spezialisiert.


- `@PathVariable` um auf Pfad-Variablen zuzugreiffen.
```java
@GetMapping("/api/employee/{id}")
@ResponseBody
public String getEmplyById(@PathVariable("id") String id) {
	return "ID: " + id;
}
```
- `@RequestParam` um auf Get-Parameter zuzugreifen
```java
@GetMapping("/foos")
@ResponseBody
public String getFooWihtQueryParam(@RequestParam("id") String id) {
	return "ID: " + id;
}
// http://localhost:8080/foo?id=123
```
- `@RequestBody` um auf den Post-Body zuzugreifen
```java
@PostMapping("/request")
@ResponseBody
public String login(@RequestBody LoginForm login) {
	return "Username: " + login.getUsername();
}
```
- `@ResponseBody` Zeigt an, dass es sich um eine text-Antwort handelt und keine View aufgelöst werden muss.