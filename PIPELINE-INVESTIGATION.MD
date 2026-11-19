ISSUE 1 : 

1. wrong command -> script npm-run-test-ci was given instead of npm test in the ci.yml under test validation with name as Run test Suite.
2. Flaky timestamp -> Exact matching on new Date().toISOString() fails under network/processor latency in the runner. Fix: Verify timestamp validity or use regex match.
with below code provided it resolved the timestamp issue :
expect(res.body.timestamp).toBeDefined();
expect(new Date(res.body.timestamp).getTime()).not.toBeNaN();

