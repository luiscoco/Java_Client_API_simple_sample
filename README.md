# Java Client API simple sample

```java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;

public class ApiExample {

    public static void main(String[] args) {
        // Replace "YOUR_USERNAME" with the GitHub username you want to fetch information about
        String username = "YOUR_USERNAME";

        // GitHub API endpoint for user information
        String apiUrl = "https://api.github.com/users/" + username;

        // Create an instance of HttpClient
        HttpClient httpClient = HttpClient.newHttpClient();

        // Create an HttpRequest with the API endpoint URI
        HttpRequest httpRequest = HttpRequest.newBuilder()
                .uri(URI.create(apiUrl))
                .build();

        try {
            // Send the request and retrieve the response
            HttpResponse<String> response = httpClient.send(httpRequest, HttpResponse.BodyHandlers.ofString());

            // Print the response body
            System.out.println("Response: " + response.body());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```








