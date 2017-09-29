# SONM Node API
The API is to be used by SONM CLI, SONM Wallet and other external applications to manage SONM node and to invoke SONM functions.
## Market API
**GetPrices(SlotSpec) []Orders** // Searches for BID and ASK orders in Marketplace for Virtual Order Book
**GetAvailable(SlotSpec) Integer** // Counts local resources at Hub, that fit Virtual Order Book
**ExecuteOrder(Order, auto Bool) OrderInfo** // Place and execute order. Auto flags if node should cancel or reexecute order automatically.
**CancelOrder(OrderId) OrderInfo** // Cancel order
**GetOrders() []OrderInfo** // List my active orders
**GetOrderInfo(OrderId) OrderInfo** // Get order details
## Deal API
**GetDeals() []DealInfo** // List node's deals
**GetDealInfo(DealId) DealInfo** // Get deal details
**FinishDeal(DealId, DealResult) DealInfo** // Finish deal
**event DealToStart(DealInfo)** // Emitted when the deal is approved
**event DealToStop(DealInfo)** // Emitted when it's time to finish deal
## Task API
**StartTask(TaskSpec) TaskInfo** // Execute task
**StopTask(TaskId) TaskInfo** // Stop the task
**GetTasks(Task) []TaskInfo** // List local tasks
**GetTaskInfo(TaskId) TaskInfo** // Get task detail
**GetTaskLogs(TaskId) TaskLogs** // Get task logs
**event TaskStopped(TaskInfo)** // Emitted when the task is stopped
## Hub management API
**GetWorkers() []Worker** // List Hub's available workers
**RegisterWorker(Hash)** Worker // Register new worker
**UnregisterWorker(Hash)** // Unregister worker
**UpdateWorkerProps(WorkerId, ResProps) Worker** // Set worker resource properties
**GetWorks() []WorkInfo** // List Hub's works (allocated tasks)
**GetWorkInfo(WorkId) WorkInfo** // Get Work detail
# Internal SONM API
## Marketplace API
AAA: The calling node must prove Ethereum Id.
**GetOrders(VobSpec) []Order** // Get current orders in VOB
**PlaceOrder(Order)** // Place new order
**CancelOrder(OrderId)** // Cancel order
**CheckOrder(OrderId)** // Check if order was published
## Locator API
**Resolve(hubId Hash) []ipaddr** // Resolves Hub Ethereum Id to Ip addresses
**Publish(hubId Hash, []ipaddr)** // Publish Hub ip addresses
## Hub API
AAA: The calling node must prove Ethereum Id.
**ProposeDeal(Deal) bool** // Propose a deal to Hub. Result is true if accepted
**StartWork(DealId, TaskSpec) WorkInfo** // Start work for selected deal
**StopWork(WorkInfoId) WorkInfo** // Stop work
**GetWorkInfo(WorkInfo) WorkInfo** // Get work status
**GetLogs(WorkInfoId) []LogEntries** // Get log entries
**Register(Worker)** // Worker registers at Hub
**Unregister(WorkerId)** // Worker disconnects
**SetWorkerProps(WorkerId, ResProps)** // Set worker resource properties
## Worker API
AAA: The calling node must prove Ethereum Id.
**StartWork(TaskSpec) ContainerId** // Start work for selected deal
**StopWork(ContainerId)** // Stop work
**GetWorkInfo(ContainerId) String** // Get work status
**GetLogs(ContainerId) []LogEntries** // Get log entries
# Structures
![Class diagram](https://raw.githubusercontent.com/sonm-io/docs/master/arch/API_class_diagram.png)
