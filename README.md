# Get upfront fare for product with start/end location
RideRequestParameters rideRequestParameters = new RideRequestParameters.Builder().setPickupCoordinates(37.77f, -122.41f)
       .setProductId(productId)
       .setDropoffCoordinates(37.49f, -122.41f)
       .build();
RideEstimate rideEstimate = service.estimateRide(rideRequestParameters).execute().body();
String fareId = rideEstimate.getFareId();

# Request ride with upfront fare for product with start/end location
RideRequestParameters rideRequestParameters = new RideRequestParameters.Builder().setPickupCoordinates(37.77f, -122.41f)
       .setProductId(productId)
       .setFareId(fareId)
       .setDropoffCoordinates(37.49f, -122.41f)
       .build();
Ride ride = service.requestRide(rideRequestParameters).execute().body();
String rideId = ride.getRideId();
