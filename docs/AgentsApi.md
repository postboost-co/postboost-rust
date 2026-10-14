# \AgentsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**approve_agent_proposal**](AgentsApi.md#approve_agent_proposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/approve | Approve and apply an agent proposal
[**create_agent**](AgentsApi.md#create_agent) | **POST** /{workspaceUuid}/agents | Switch on a background agent
[**delete_agent**](AgentsApi.md#delete_agent) | **DELETE** /{workspaceUuid}/agents/{agentUuid} | Delete a background agent
[**get_agent_run**](AgentsApi.md#get_agent_run) | **GET** /{workspaceUuid}/agent-runs/{runUuid} | Get an agent run with its proposals
[**list_agent_proposals**](AgentsApi.md#list_agent_proposals) | **GET** /{workspaceUuid}/agent-proposals | List agent proposals (approval queue)
[**list_agent_runs**](AgentsApi.md#list_agent_runs) | **GET** /{workspaceUuid}/agents/{agentUuid}/runs | Run history of an agent
[**list_agents**](AgentsApi.md#list_agents) | **GET** /{workspaceUuid}/agents | List background agents
[**reject_agent_proposal**](AgentsApi.md#reject_agent_proposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/reject | Reject an agent proposal
[**run_agent**](AgentsApi.md#run_agent) | **POST** /{workspaceUuid}/agents/{agentUuid}/run | Run a background agent now
[**update_agent**](AgentsApi.md#update_agent) | **PUT** /{workspaceUuid}/agents/{agentUuid} | Update a background agent



## approve_agent_proposal

> models::ApproveAgentProposal200Response approve_agent_proposal(workspace_uuid, proposal_uuid, agent_proposal_decision)
Approve and apply an agent proposal

Applies the proposal at once: `hold_post` moves the post back to draft, `edit_caption` replaces the caption, `retry_account` saves the shortened caption (if any) on that account's version and publishes that account again, `reconnect_account` only records the decision. When the post was edited, deleted or left the schedule since the proposal was made (for `retry_account`: the account is no longer failed, the post is publishing, or the plan does not allow scheduling), nothing changes and the proposal becomes `stale`. Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**proposal_uuid** | **uuid::Uuid** |  | [required] |
**agent_proposal_decision** | Option<[**AgentProposalDecision**](AgentProposalDecision.md)> |  |  |

### Return type

[**models::ApproveAgentProposal200Response**](approveAgentProposal_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_agent

> models::CreateAgent201Response create_agent(workspace_uuid, workspace_agent_input)
Switch on a background agent

Creates an agent (one per type per workspace). It first runs within five minutes, then on its `schedule`. **Pre-publish checker** looks at posts scheduled in the next `horizon_hours` and proposes holding (back to draft) posts that would fail: disconnected accounts, network requirements, daily caps, the X allowance and links that answer an error. It proposes caption edits that drop `banned_phrases`. With `ai_review: true` it also asks AI to review up to `max_ai_reviews_per_run` posts per run (one AI credit each). **Failed-post fixer** looks at posts that failed on an account in the last `lookback_hours` and proposes, per post and account, `reconnect_account` (the account's token expired), or `retry_account`, with a caption trimmed to the network limit when the text is over it. One open proposal per post and account. It uses no AI. Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**workspace_agent_input** | [**WorkspaceAgentInput**](WorkspaceAgentInput.md) |  | [required] |

### Return type

[**models::CreateAgent201Response**](createAgent_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_agent

> models::DeleteAgent200Response delete_agent(workspace_uuid, agent_uuid)
Delete a background agent

Removes the agent. Its run history and proposals stay. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**agent_uuid** | **uuid::Uuid** |  | [required] |

### Return type

[**models::DeleteAgent200Response**](deleteAgent_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_agent_run

> models::RunAgent202Response get_agent_run(workspace_uuid, run_uuid)
Get an agent run with its proposals

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**run_uuid** | **uuid::Uuid** |  | [required] |

### Return type

[**models::RunAgent202Response**](runAgent_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_agent_proposals

> models::ListAgentProposals200Response list_agent_proposals(workspace_uuid, status, per_page, page)
List agent proposals (approval queue)

Proposals of all agents in the workspace, newest first. Defaults to `pending`.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**status** | Option<**String**> |  |  |[default to pending]
**per_page** | Option<**i32**> |  |  |[default to 20]
**page** | Option<**i32**> |  |  |

### Return type

[**models::ListAgentProposals200Response**](listAgentProposals_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_agent_runs

> models::ListAgentRuns200Response list_agent_runs(workspace_uuid, agent_uuid, per_page, page)
Run history of an agent

Runs of the agent, newest first, with what each checked and proposed and the AI credits it used.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**agent_uuid** | **uuid::Uuid** |  | [required] |
**per_page** | Option<**i32**> |  |  |[default to 20]
**page** | Option<**i32**> |  |  |

### Return type

[**models::ListAgentRuns200Response**](listAgentRuns_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_agents

> models::ListAgents200Response list_agents(workspace_uuid)
List background agents

Background agents switched on for the workspace. Agents run on a schedule, record every run and never change a post themselves: each change is a proposal that a workspace admin or member approves. Available types: `pre_publish_checker`, `failed_post_fixer`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListAgents200Response**](listAgents_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reject_agent_proposal

> models::ApproveAgentProposal200Response reject_agent_proposal(workspace_uuid, proposal_uuid, agent_proposal_decision)
Reject an agent proposal

Records the rejection (and optional note); nothing changes on the post. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**proposal_uuid** | **uuid::Uuid** |  | [required] |
**agent_proposal_decision** | Option<[**AgentProposalDecision**](AgentProposalDecision.md)> |  |  |

### Return type

[**models::ApproveAgentProposal200Response**](approveAgentProposal_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## run_agent

> models::RunAgent202Response run_agent(workspace_uuid, agent_uuid)
Run a background agent now

Queues a run outside the schedule (`trigger: manual`). Six per hour. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**agent_uuid** | **uuid::Uuid** |  | [required] |

### Return type

[**models::RunAgent202Response**](runAgent_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_agent

> models::CreateAgent201Response update_agent(workspace_uuid, agent_uuid, workspace_agent_update)
Update a background agent

Changes the name, schedule, settings or `enabled`. Settings you leave out keep their value. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**agent_uuid** | **uuid::Uuid** |  | [required] |
**workspace_agent_update** | [**WorkspaceAgentUpdate**](WorkspaceAgentUpdate.md) |  | [required] |

### Return type

[**models::CreateAgent201Response**](createAgent_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

