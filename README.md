# bpm-ga-classic
Bliss Point Media GA Classic Lower funnel metrics example

In order to carry a timestamp from a higher-funnel action into a lower-funnel action, we use a cookie to save and retrieve it when needed. When the lower-funnel action that we want to measure occurs, we send an event with the category name 'BpmSessionStartDelta', along with a delta (in millis) to the start of the session.

To retrieve this information, make a custom query as follows:
	Dimensions: Date, Hour, Minute, Event Action
	Metrics: New Users (or whatever you want)
	Filter: Event Category, "Exact", "BpmSessionStartDelta"

The Date/Hour/Minute in the report signify the timestamp of the lower-funnel event. Then by subtracting the milliseconds specified by Event Action, we can retrieve the session start time.
