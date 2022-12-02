# Input

Write a golang script to send multiple HTTP requests to https://example.com using concurrency. Use "AI" as user agent header. Concurrent goroutines should be 10.

# Answer

Here is an example of a Go script that sends multiple HTTP requests to [https://example.com](https://example.com) using concurrency:

```golang
package main

import (
    "fmt"
    "net/http"
    "sync"
)

const (
    concurrency = 10
    url         = "https://example.com"
)

func main() {
    // Create a WaitGroup to manage the goroutines.
    var wg sync.WaitGroup

    // Set the number of goroutines to wait for.
    wg.Add(concurrency)

    // Launch the goroutines.
    for i := 0; i < concurrency; i++ {
        go func() {
            // Define the HTTP client and request.
            client := &http.Client{}
            req, err := http.NewRequest("GET", url, nil)
            if err != nil {
                fmt.Println(err)
                return
            }

            // Set the user agent header.
            req.Header.Set("User-Agent", "AI")

            // Send the request.
            resp, err := client.Do(req)
            if err != nil {
                fmt.Println(err)
                return
            }
            defer resp.Body.Close()

            // Print the response status and body.
            fmt.Println(resp.Status)
            fmt.Println(resp.Body)

            // Tell the WaitGroup that we're done.
            wg.Done()
        }()
    }

    // Wait for all the goroutines to finish.
    wg.Wait()
}

```

This script creates a `sync.WaitGroup` to manage the goroutines. It then launches `concurrency` number of goroutines, each of which sends an HTTP GET request to `url` using the "AI" user agent. The response status and body are printed to the console. Finally, the script waits for all the goroutines to finish before exiting.
