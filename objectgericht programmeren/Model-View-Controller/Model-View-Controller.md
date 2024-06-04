Het MVC-patroon bestaat uit drie delen:
- Het __Model__: de data die weergegeven worden zal worden
- De __View__: de visuele weergave van (een deel van) het model
- De __controller__: zorgt dat aanpassingen aan het model mogelijk zijn

Een MVC-patroon wordt meestal als volgt aangemaakt:
1. Elke view registreert zich bij het model
2. De controller gebruikt methoden om dingen aan het model aan te passen
3. Elke keer de controller iets aanpast aan de view, geeft dit feit door aan alle (geregistreerde) views.
4. De views vragen op hun beurt weer aan het model wat de nieuwe data is.

Een controller heeft dus nooit rechtstreeks contact met een view. De twee belangrijkste interfaces voor dit patroon zijn `InvalidationListener`, voor elke view en `Observable` voor het model.

## Het model
Het model moet vooral velden bevatten met data, en implementeert de interface `Observable`, met de methoden `addListener()` en `removeListener()`. De simpelste implementatie is een lijst bijhouden met alle geregistreerde views. Er moet ook een methode `fireInvalidationEvent()` zijn die aan alle views laat weten dat de data is aangepast. 

Om de interactie met de controller mogelijk te maken, moet de view ook setters hebben waarde de controller aankan. 

```java
public class Model implements Observable{
	private List<InvalidationListener> listeners;

	public Model(){...}

	public void addListener(InvalidationListener listener){
		listeners.add(listener);
	}

	public void removeListener(InvalidationListener listener){
		listeners.remove(listener);
	}

	public void fireInvalidationEvent(){
		for(InvalidationListener l : listeners){
			l.invalidated(this);
		}
	}
}
```

## De view
Een view moet enkel de functie `invalidated(Observable model)` hebben en in deze functie de data opnieuw ophalen.

