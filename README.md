

🎯 How to quickly test and debug

Confirm the token locally                                                                                                   </br>
✅Copy the secret locally and run the same curl command from your machine (replace token) to confirm the API accepts it.    </br>
✅Confirm header format the API expects                                                                                     </br>
✅Check your API docs — try "Authorization: Bearer <token>" if you are currently sending the raw token.                      </br>
✅Use curl verbosity and save response + status code                                                                          </br>
✅See full HTTP response body, headers, and HTTP code instead of just the masked log. This helps confirm whether the server expects a different header or token format.                                                                                                                       </br>
✅Confirm secrets in GitHub                                                                                                 </br>
✅In repository Settings > Secrets, confirm RELEVANCE_AI_AUTH_TOKEN is set and correct.                                        </br>
✅Confirm the scheduled workflow is running in the default branch (scheduled runs are branch-based).                        </br>
Test different header forms                                                                                                  </br>
✅Try Authorization: Bearer ${{ secrets.RELEVANCE_AI_AUTH_TOKEN }}                                                        </br>
✅Or try X-API-Key: ${{ secrets.RELEVANCE_AI_AUTH_TOKEN }} if docs indicates                                                </br>
✅Concrete workflow snippet to capture full response and archive it                                                </br>

This will:                                                                                          </br>
⭐send curl with a "Bearer" prefix (change if API needs something else)                             </br>
⭐save full response body to response.json                                                        </br>
⭐save headers to response_headers.txt                                                             </br>
⭐write HTTP status code to status_code.txt                                                      </br>
⭐upload those files as an artifact so you can download them from the run page                 </br>
