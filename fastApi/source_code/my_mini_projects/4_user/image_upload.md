### install libraray
```python
pip install python-multipart
```
* add image field in model/users.py
```python
# in model file
image = Column(String(255), nullable=True)  # Field for image upload
```
* Import File and UploadFile from fastapi

### image upload in folder intial phase
```python
from fastapi import FastAPI, APIRouter, Depends, HTTPException
from sqlalchemy.orm import Session
from database.connection import get_db
from database.models.users import User
from fastapi.responses import JSONResponse
from datetime import datetime

from typing import Annotated
from fastapi import FastAPI, File, UploadFile, Form
import shutil
from pathlib import Path

from database.schemas.user import CustomerStore


router = APIRouter()


@router.post("/uploadfile/")

async def create_upload_file(file: UploadFile):
    MAX_FILE_SIZE = 5 * 1024 * 1024  # 5MB
    file_size = await file.read()
    if len(file_size) > MAX_FILE_SIZE:
        raise HTTPException(status_code=400, detail="File size exceeds 5MB.")

    # Reset the file pointer to the beginning
    await file.seek(0)


    # validation for image
    '''
    if file.content_type not in ["image/jpeg", "image/png"]:
        raise HTTPException(status_code=400, detail="Unsupported file type.")
    '''
    if not file.content_type.startswith("image/"):
        raise HTTPException(status_code=400, detail="Only image files are allowed.")


    # Creaet Directory
    # Define the directory for profile images
    UPLOAD_DIR = Path("uploads/image/profile_image")
    UPLOAD_DIR.mkdir(parents=True, exist_ok=True)  # Create the directory and parent directories if they don't exist


    # create time stamp and upload file in folder
    '''
    # upload image with file name
    file_path = UPLOAD_DIR / file.filename
    '''
    # Get the current timestamp
    timestamp = datetime.now().strftime("%Y%m%d%H%M%S")
    
    # Create a unique filename with timestamp
    file_extension = file.filename.split(".")[-1]  # Extract file extension
    unique_filename = f"{timestamp}_{file.filename}"
    file_path = UPLOAD_DIR / unique_filename

    db_user = User(
            first_name=first_name,
            image = str(file_path)
        )

    # Save the file
    with file_path.open("wb") as buffer:
        shutil.copyfileobj(file.file, buffer)

    return {"filename": unique_filename, "file_path": str(file_path)}
```

### image upload in databse and firstname, lastname
```python
# databse->schemas->user
class CustomerStore(BaseModel):
    first_name: str
    last_name: str
```

```python
from fastapi import FastAPI, APIRouter, Depends, HTTPException
from sqlalchemy.orm import Session
from database.connection import get_db
from database.models.users import User
from database.models.roles import Role
from database.models.user_details import UserDetails

from fastapi.responses import JSONResponse  # Include for message response.
from sqlalchemy.exc import SQLAlchemyError

from database.schemas.user import UserCreate, UserLogin

import bcrypt # for hashed password 

router = APIRouter()


@router.post("/uploadfile/")
# async def create_upload_file(request: CustomerStore, role_id: int, file: UploadFile):
# async def create_upload_file(request: CustomerStore, file: UploadFile):
# async def create_upload_file(request: CustomerStore, file: UploadFile = File(...)):
# async def create_upload_file(file: UploadFile):
async def create_upload_file(first_name: str = Form(...), last_name: str = Form(...), file: UploadFile = File(...), db: Session = Depends(get_db)):

    MAX_FILE_SIZE = 5 * 1024 * 1024  # 5MB
    file_size = await file.read()
    if len(file_size) > MAX_FILE_SIZE:
        raise HTTPException(status_code=400, detail="File size exceeds 5MB.")

    # Reset the file pointer to the beginning
    await file.seek(0)


    # validation for image
    '''
    if file.content_type not in ["image/jpeg", "image/png"]:
        raise HTTPException(status_code=400, detail="Unsupported file type.")
    '''
    if not file.content_type.startswith("image/"):
        raise HTTPException(status_code=400, detail="Only image files are allowed.")


    # Creaet Directory
    # Define the directory for profile images
    UPLOAD_DIR = Path("uploads/image/profile_image")
    UPLOAD_DIR.mkdir(parents=True, exist_ok=True)  # Create the directory and parent directories if they don't exist


    # create time stamp and upload file in folder
    '''
    # upload image with file name
    file_path = UPLOAD_DIR / file.filename
    '''
    # Get the current timestamp
    timestamp = datetime.now().strftime("%Y%m%d%H%M%S")
    
    # Create a unique filename with timestamp
    file_extension = file.filename.split(".")[-1]  # Extract file extension
    unique_filename = f"{timestamp}_{file.filename}"
    file_path = UPLOAD_DIR / unique_filename

    db_user = User(
            first_name=first_name,
            last_name=last_name,
            image = str(file_path)
        )

    # db_user = User(**user.dict())
    db.add(db_user)
    db.commit()
    db.refresh(db_user)

    # Save the file
    with file_path.open("wb") as buffer:
        shutil.copyfileobj(file.file, buffer)

    return {"filename": unique_filename, "file_path": str(file_path)}
```
### first name and other data through request
```python
# change in scheme
from fastapi import Form
class CustomerStore(BaseModel):
    first_name: str
    last_name: str

    @classmethod
    def as_form(
        cls,
        first_name: str = Form(...),
        last_name: str = Form(...)
    ) -> "CustomerStore":
        return cls(first_name=first_name, last_name=last_name)

# change function line
from fastapi import FastAPI, File, UploadFile, Form

async def create_upload_file(request: CustomerStore = Depends(CustomerStore.as_form), file: UploadFile = File(...), db: Session = Depends(get_db)):
```

