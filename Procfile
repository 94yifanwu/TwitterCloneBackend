# check ./etc/gateway.ini file with $PORT for reference. 
gateway: python3 -m bottle --bind=localhost:$PORT --debug --reload gateway
users: sandman2ctl -p $PORT sqlite+pysqlite:///init_data/users.db
timelines: sandman2ctl -p $PORT sqlite+pysqlite:///init_data/timelines.db
user-queries: datasette -p $PORT --reload init_data/users.db
timeline-queries: datasette -p $PORT --reload init_data/timelines.db
direct-messages: python3 -m bottle --bind=localhost:$PORT --debug --reload direct_message 
search-engine: python3 -m bottle --bind=localhost:$PORT --debug --reload search_engine
message-queue: python3 -m bottle --bind=localhost:$PORT --debug --reload message_queue
dynamoDB: java -Djava.library.path=./dynamodb_local/DynamoDBLocal_lib -jar ./dynamodb_local/DynamoDBLocal.jar -sharedDb
redis: redis-server --port 6379
worker: rq worker high default low --disable-job-desc-logging --quiet

