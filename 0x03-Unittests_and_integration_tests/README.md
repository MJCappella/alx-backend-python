# Unittests and Integration Tests

This project contains tasks for learning to write unittests and integration tests in Python 3.

## Required Modules

## Tasks To Complete

+ [x] 0. **Parameterize a unit test**<br/>[test_utils.py](test_utils.py)

+ [x] 1. **Parameterize a unit test**<br/>[test_utils.py](test_utils.py) 

+ [x] 2. **Mock HTTP calls**<br/>[test_utils.py](test_utils.py)
    
+ [x] 3. **Parameterize and patch**<br/>[test_utils.py](test_utils.py)

+ [x] 4. **Parameterize and patch as decorators**<br/>[test_client.py](test_client.py)

+ [x] 5. **Mocking a property**<br/>[test_client.py](test_client.py)

+ [x] 6. **More patching**<br/>[test_client.py](test_client.py) 

+ [x] 7. **Parameterize**<br/>[test_client.py](test_client.py) 

+ [x] 8. **Integration test: fixtures**<br/>[test_client.py](test_client.py) contains a python module that meets the following requirements:
  + We want to test the `GithubOrgClient.public_repos` method in an integration test. That means that we will only mock code that sends external requests.
  + Create the `TestIntegrationGithubOrgClient(unittest.TestCase)` class and implement the `setUpClass` and `tearDownClass` which are part of the `unittest.TestCase` API.
  + Use `@parameterized_class` to decorate the class and parameterize it with fixtures found in [fixtures.py](fixtures.py). The file contains the following fixtures:
    ```
    org_payload, repos_payload, expected_repos, apache2_repos
    ```
  + The `setupClass` should mock `requests.get` to return example payloads found in the fixtures.
  + Use `patch` to start a patcher named `get_patcher`, and use `side_effect` to make sure the mock of `requests.get(url).json()` returns the correct fixtures for the various values of `url` that you anticipate to receive.
  + Implement the `tearDownClass` class method to stop the patcher.

+ [x] 9. **Integration tests**<br/>[test_client.py](test_client.py) contains a python module that meets the following requirements:
  + Implement the `test_public_repos` method to test `GithubOrgClient.public_repos`.
  + Make sure that the method returns the expected results based on the fixtures.
  + Implement `test_public_repos_with_license` to test the `public_repos` with the argument `license="apache-2.0"` and make sure the result matches the expected value from the fixtures.
