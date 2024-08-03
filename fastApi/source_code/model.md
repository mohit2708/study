### Role Table
```python
from sqlalchemy import Boolean, Column, Integer, String, DateTime
from datetime import datetime
from sqlalchemy.orm import relationship
from database.connection import Base

class Role(Base):
    __tablename__ = "roles"

    id          = Column(Integer, primary_key=True, index=True)
    slug        = Column(String(255), nullable=True)
    name        = Column(String(255), nullable=True)
    created_at  = Column(DateTime, default=datetime.utcnow)
    updated_at  = Column(DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)
    users = relationship("User", back_populates="role")  # Define reverse relationship with User model
```


### user table
```python
from sqlalchemy import Column, Integer, String, DateTime, Boolean, ForeignKey
from datetime import datetime
from sqlalchemy.orm import relationship, Session
from database.connection import Base
from passlib.context import CryptContext

class User(Base):
    __tablename__ = 'users'

    id = Column(Integer, primary_key=True, index=True)
    role_id = Column(Integer, ForeignKey('roles.id'))  # Define foreign key relationship
    role = relationship("Role", back_populates="users")  # Define relationship with Role model
    first_name = Column(String(255), nullable = True)
    last_name = Column(String(255))
    user_name = Column(String(255), unique=True, index=True)
    email = Column(String(255), nullable=False, unique=True, index=True)
    password = Column(String(255))
    deleted_at = Column(DateTime, nullable=True)
    created_at = Column(DateTime, default=datetime.utcnow)
    updated_at = Column(DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)

    user_details = relationship("UserDetails", back_populates="user", uselist=False, cascade="all, delete") # Define relationship with UserDetails

    # Verify password(Match password) 
    @staticmethod
    def verify_password(plain_password, hashed_password):
        password_context = CryptContext(schemes=["bcrypt"], deprecated="auto")
        return password_context.verify(plain_password, hashed_password)

    # 1 type get email
    # @classmethod
    # def get_email(cls, db: Session, request):
    #     return db.query(cls).filter(cls.email == request.email).first()

    # 2 type get email
    def get_user_by_email(db: Session, request):
        return db.query(User).filter(User.email == request.email).first()
    

    """
    check user exist or not
    """
    def get_user_by_username(db: Session, request):
        return db.query(User).filter(User.user_name == request.username).first()
```

### user details.py
```python
from sqlalchemy import Column, Integer, String, DateTime, ForeignKey
from datetime import datetime
from sqlalchemy.orm import relationship
from database.connection import Base

class UserDetails(Base):
    __tablename__ = 'user_details'

    id = Column(Integer, primary_key=True, index=True)
    user_id = Column(Integer, ForeignKey('users.id', ondelete='CASCADE'))
    user = relationship("User", back_populates="user_details")

    phone_number = Column(String(20), nullable=True)
    country = Column(String(100), nullable=True)
    state = Column(String(100), nullable=True)
    city = Column(String(100), nullable=True)
    zipcode = Column(Integer, nullable=True)
    

    created_at = Column(DateTime, default=datetime.utcnow)
    updated_at = Column(DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)
```


### Genrate alembic
```python
# Genrate alembic
alembic revision --autogenerate -m "create user and blog table migrations"  #analyzes tables and creates a migration file
```
```python
alembic upgrade head  #executes the migration files to make actual changes in db
```