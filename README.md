# REST Assured course: GitHub Actions example

The CI example repository of the course "REST API Automation With REST Assured - A Complete Guide".
Every workflow in the GitHub Actions section was written and run here, on camera.

| Tag | What it shows |
|---|---|
| `first-workflow` | checkout, setup-java, `mvn -B test` on every push and pull request |
| `service-containers` | the job builds and starts the Students app from its Dockerfile, waits for it, then tests it |
| `secrets-matrix` | smoke tests on every pull request, regression every night on JDK 17 and 21; the API key is masked |
| `main` | the Allure report published to GitHub Pages, a comment with the link on every pull request |

The tests call Campus Lab, the course's practice API. This public repository stores no API key: each job asks
Campus Lab for a free sandbox key and hides it with `::add-mask::`. In your own project, put the key in a
repository secret and read it as `${{ secrets.CAMPUS_API_KEY }}`.

Report of the last run: https://propfuturesbot.github.io/restassured-course-ci/
