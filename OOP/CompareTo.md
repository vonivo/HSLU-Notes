Die `compareTo()`-Methode kann über das Interface `Compareable<T>` implementiert werden.
Die `compareTo()`-Methode definiert die **natürliche Ordnung**.


## Beispielimplementation
```
@Override
public int compareTo(Person other) {
	if (other == this) {
		return true:
	}

	return Long.compare(this.id, other.id);
}
```

