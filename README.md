

🎯 How to quickly test and debug

Confirm the token locally
✅Copy the secret locally and run the same curl command from your machine (replace token) to confirm the API accepts it.
✅Confirm header format the API expects
✅Check your API docs — try "Authorization: Bearer <token>" if you are currently sending the raw token.
✅Use curl verbosity and save response + status code
✅See full HTTP response body, headers, and HTTP code instead of just the masked log. This helps confirm whether the server expects a different header or token format.
✅Confirm secrets in GitHub
✅In repository Settings > Secrets, confirm RELEVANCE_AI_AUTH_TOKEN is set and correct.
✅Confirm the scheduled workflow is running in the default branch (scheduled runs are branch-based).
Test different header forms
✅Try Authorization: Bearer ${{ secrets.RELEVANCE_AI_AUTH_TOKEN }}
✅Or try X-API-Key: ${{ secrets.RELEVANCE_AI_AUTH_TOKEN }} if docs indicate.
✅Concrete workflow snippet to capture full response and archive it

This will:
⭐send curl with a "Bearer" prefix (change if API needs something else)
⭐save full response body to response.json
⭐save headers to response_headers.txt
⭐write HTTP status code to status_code.txt
⭐upload those files as an artifact so you can download them from the run page
