documenting my process of building a API from scratch using fast api

## initial steps:
 - created a virtual environment and installed dependencies
 - initialised the fastapi instance and setup an endpoint for the root that returns a simple ok message
 -  created a simple [[pydantic]] class for creating a workout
 - created a new `database.py` file imported `sqlalchemy` created an engine instance and a session local instance
 - made a base class that inherits declarativeBase