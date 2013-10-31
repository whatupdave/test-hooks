list hooks:

curl -u $TEST_HOOKS https://api.github.com/repos/whatupdave/test-hooks/hooks

Set up the hook:

curl -u $TEST_HOOKS -XPOST https://api.github.com/repos/whatupdave/test-hooks/hooks -d '{
  "name": "web",
  "active": true,
  "events": ["push","pull_request","pull_request_review_comment"],
  "config": {
    "url": "$TUNNEL_URL",
    "content_type": "json"
  }
}'


