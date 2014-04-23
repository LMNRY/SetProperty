SetProperty
===========

A PropertyAttribute/PropertyDrawer combination that allows for properties in Unity

Example
-------
Unity allows you to serialize private fields with [SerializeField]. Use the new [SetProperty] attribute to have a 
public property set every time the field is modified in Unity's inspector. NOTE: It is okay to have private setters for
public properties. Vanilla classes (i.e. non-MonoBehaviours) also work as well.

	[SerializeField, SetProperty("Number")]
	private float number;
	public float Number
	{
		get
		{
			return number;
		}
		private set
		{
			number = Mathf.Clamp01(value);
		}
	}
