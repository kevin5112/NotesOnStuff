# dependency injection

Dependency injection is seen mainly used with unit testing purposes.

Let's start with an example: 
    Lets say you are testing an api and are trying to test if calling the api works.

    function callAPI(apiKey) {
            return fetch("https://getAPI.com/api?apiKey=" + apiKey);
        }

now with this function, you are just fetching some random api and hoping that you get a success `200` response.  When testing this function, you may write something like: 


    test("test for correct api url", () => {
        expect(callAPI).toBe(new Promise with 200 status???)
    })
    

Do you see the problem here? when writing the test, you don't actually know what you're exactly trying to test for.  You know fetch returns a promise but then you can only check to see if it's a 200 call?

This is where dependency injection comes in.  You can add a dependency injection to the base function `callAPI` so that you can mock the url data to see if fetch is doing the right thing.

so the new function will look like: 
    
    
    function callAPI(fetch, apiKey) {
        return fetch("https://getAPI.com/api?apiKey=" + apiKey);
    }
    
    
and the test function will look like:
    
    
    test("test for correct api url", () => {
        let fakeFetch = url => {
            expect(url).toBe("https://getAPI.com/api?apiKey=123");
        }
        return new Promise(function(resolve) {})
    }, callAPI(fakeFetch, 123))

So with this, this will mock out the fetch data and inject a `fakeFetch` into the test function, which lets you test to make sure the correct url is being passed into the `callAPI` function
        
    
