# himalayas

Tools for understanding Redpanda locally.

### Example usage

Bundle gems
```
bundle
```

Start Redpanda with docker-compose
```
docker-compose up
```

Create a topic with rpk
```
rpk topic create my_topic -p 3 -r 1
```

Start producing messages every second
```
bundle exec rpk produce_messages my_topic --interval_in_seconds 1
```

Example calling the default script - creating a consumer, subscribing the consumer to topics, consume messages on interval (--interval_in_seconds), and delete the consumer (with ctrl-c).
```
bundle exec pandaproxy --create_consumer --consumer_group_name my_group --consumer_name my_consumer --subscribe_consumer --topics '["my_topic"]' --consume_messages --interval_in_seconds 0.5 --delete_consumer
```

Individual commands can be called as well
```
Commands:
  pandaproxy (default command)   # Run pandaproxy script with options
  pandaproxy consume_messages    # Consume messages with --consumer_group_name, --consumer_name, and --interval_in_seconds options
  pandaproxy create_consumer     # Create a consumer with --consumer_group_name and --consumer_name options
  pandaproxy delete_consumer     # Delete a consumer with --consumer_group_name and --consumer_name options
  pandaproxy help [COMMAND]      # Describe available commands or one specific command
  pandaproxy subscribe_consumer  # Subscribe a consumer with --consumer_group_name, --consumer_name, and --topics options
```
