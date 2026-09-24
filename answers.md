TASK 3 OBSERVATIONS

1. POST request: When the probe body was twice I received a 201 response both times. Also, the device count increased each time (from 5 to 6), which indicated that two separate devices were created.

2. PUT request: When the attic device was updated twice using the same body and I received a 200 response both times. The device count remained at 6, and nothing changed after the second request.

3. DELETE requests: When the fridge device was deleted I received a 200 response, and as a result the device count decreased to 5. When I tried to delete it again, I received a 404 response because the device had already been deleted. The device count remained at 5.

I discovered that PUT and DELETE are idempotent because repeating the same request does not cause any further change to the resource's state, even though DELETE returns a different status code when the resource is already gone. POST is not idempotent because repeating the same request creates a new device each time.
