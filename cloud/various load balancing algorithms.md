- Round Robin : [[Request|Requests]] are distributed sequentially in a circular manner to each available [[Backend Service|server]] in order.

- Least Connections : The [[Request]] is sent to the [[Backend Service|server]] with the fewest active connections, ensuring that the [[Backend Service|server]] with the least load receives the [[Request]].

- Weighted Round Robin : Each [[Backend Service|server]] is assigned a weight value, and [[Backend Service|requests]] are distributed based on the weight, giving more significant [[Backend Service|servers]] a higher proportion of traffic.

- Least Response Time : [[Request]]s are routed to the [[Backend Service|server]] with the shortest [[Response]] time to ensure faster response to [[Client|clients]].

- IP Hash : The [[Load Balancing|load balancer]] uses a hash function on the client's IP address to consistently route the [[Client]]'s [[Request]] to the same [[Backend Service|server]].

#LoadBalancing 