## PWA (Progressive Web Apps)
JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.

- [What are Progressive Web Apss?](https://web.dev/what-are-pwas/)
- [How to define your install strategy](https://web.dev/define-install-strategy/)
- [What makes a good Progressive Web App?](https://web.dev/pwa-checklist/)

<br/>

## Beginner's Guide
Example
```
showOfflineWarning: function() {
            // disable the live data
            document.querySelector(".arrivals-list").classList.add('loading')
                // load html template informing the user they are offline
            var request = new XMLHttpRequest();
            request.open('GET', './offline.html', true);

            request.onload = function() {
                if (request.status === 200) {
                    // success
                    // create offline element with HTML loaded from offline.html template
                    var offlineMessageElement = document.createElement("div");
                    offlineMessageElement.setAttribute("id", "offline");
                    offlineMessageElement.innerHTML = request.responseText;
                    document.getElementById("main").appendChild(offlineMessageElement);
                } else {
                    // error retrieving file
                    console.warn('Error retrieving offline.html');
                }
            };
```
- [A Beginner’s Guide To Progressive Web Apps](https://www.smashingmagazine.com/2016/08/a-beginners-guide-to-progressive-web-apps/) by Kevin Farrugia
