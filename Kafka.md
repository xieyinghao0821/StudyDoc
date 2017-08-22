# bin/kafka-consumer-groups.sh help  
```
Command must include exactly one action: --list, --describe, --delete
Option                                 Description
------                                 -----------
--bootstrap-server <String: server to  REQUIRED (unless old consumer is
  connect to>                            used): The server to connect to.
--command-config <String: command      Property file containing configs to be
  config property file>                  passed to Admin Client and Consumer.
--delete                               Pass in groups to delete topic
                                         partition offsets and ownership
                                         information over the entire consumer
                                         group. For instance --group g1 --
                                         group g2
                                       Pass in groups with a single topic to
                                         just delete the given topic's
                                         partition offsets and ownership
                                         information for the given consumer
                                         groups. For instance --group g1 --
                                         group g2 --topic t1
                                       Pass in just a topic to delete the
                                         given topic's partition offsets and
                                         ownership information for every
                                         consumer group. For instance --topic
                                         t1
                                       WARNING: Group deletion only works for
                                         old ZK-based consumer groups, and
                                         one has to use it carefully to only
                                         delete groups that are not active.
--describe                             Describe consumer group and list
                                         offset lag (number of messages not
                                         yet processed) related to given
                                         group.
--group <String: consumer group>       The consumer group we wish to act on.
--list                                 List all consumer groups.
--new-consumer                         Use new consumer. This is the default.
--topic <String: topic>                The topic whose consumer group
                                         information should be deleted.
--zookeeper <String: urls>             REQUIRED (only when using old
                                         consumer): The connection string for
                                         the zookeeper connection in the form
                                         host:port. Multiple URLS can be
                                         given to allow fail-over.
```                                         
