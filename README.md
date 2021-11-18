# SM360 Backend Tech Assignment

Implement a REST service for managing listings for online advertising service.  

## Terminology

 - **Listing** - a vehicle advertisement. Listing can be in one of two possible states:
   - published - available online 
   - draft - not available online
 - **Car Dealer** - an owner of the advertisement 
 - **Tier Limit** - a number of published listings a dealer can have online 

## Requirements

Service should implement following functionality:

 - Create a listing. All the created listings should have state `draft` by default;
 - Update a listing;
 - Get all listings of a dealer with a given state;
 - Publish a listing;
 - Unpublish a listing.

Please note that the number of published listings for a dealer should be less or equal to the dealer's tier limit. When publishing a listing, client should be able to choose how to deal with situation when tier limit is reached - either 
  - return an error to the client, or 
  - publish a listing, but unpublish the oldest listing of a dealer to conform to the tier limit.

Implementation of dealer configuration logic is up to you.

Keep the implemnetation simple and provide comments during the code review interview with any improvement suggestions or any additional functionality of your choice that could give value to the service.

### Minimum Entities Schema
In order to facilitate the design, you can keep your schema simple, following the below as suggested minimum for this assignment:
```
Listing:
  - id: uuid
  - dealerId: uuid
  - vehicle: string
  - price: number
  - createdAt: date
  - state: draft/published
  
Dealer:
 - id: uuid
 - name: string
```


## Notes

 - Our tech stack is mostly Java with Spring framework.
 - Please create a 'production-ready' service as you see it (documentation / tests / logs / exception handling).
 - Please provide an instruction on how to run the app.
 - Submit your solution either as a public repository (github, gitlab etc.) or as a zip archive.
