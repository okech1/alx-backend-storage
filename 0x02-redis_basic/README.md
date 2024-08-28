0x02. Redis basic
Overview
This project covers the basics of Redis, an in-memory data structure store used as a database, cache, and message broker. Redis provides various data structures such as strings, hashes, lists, sets, and sorted sets, and supports operations like setting and getting values, performing transactions, and more.

Requirements
Ubuntu 18.04 LTS or later
Redis installed
Python 3.x with redis-py library installed
Installation
Installing Redis
Update Package List:

bash
Copy code
sudo apt update
Install Redis:

bash
Copy code
sudo apt install redis-server
Start Redis Service:

bash
Copy code
sudo systemctl start redis-server
Enable Redis on Boot:

bash
Copy code
sudo systemctl enable redis-server
Verify Redis Installation:

bash
Copy code
sudo systemctl status redis-server
You should see Redis running as active (running).

Python Redis Client
Install redis-py:
bash
Copy code
pip3 install redis
Basic Commands
Redis CLI Commands
Start Redis CLI:

bash
Copy code
redis-cli
Set a Value:

bash
Copy code
SET key value
Get a Value:

bash
Copy code
GET key
Delete a Key:

bash
Copy code
DEL key
Check Key Existence:

bash
Copy code
EXISTS key
Python with Redis
Here is an example of using Redis with Python:

python
Copy code
import redis

# Connect to Redis server
r = redis.Redis(host='localhost', port=6379, db=0)

# Set a value
r.set('key', 'value')

# Get a value
value = r.get('key')
print(value.decode('utf-8'))  # Output: value

# Delete a key
r.delete('key')

# Check if key exists
exists = r.exists('key')
print(exists)  # Output: 0 (key does not exist)
Configuration
Redis configuration file is located at /etc/redis/redis.conf. You can modify this file to configure various Redis settings, such as persistence, security, and network settings. After making changes, restart Redis to apply them:

bash
Copy code
sudo systemctl restart redis-server
Troubleshooting
Redis Not Starting: Check Redis logs at /var/log/redis/redis-server.log for any errors.
Connection Issues: Ensure Redis server is running and you are connecting to the correct host and port.
Additional Resources
Redis Official Documentation
redis-py Documentation

