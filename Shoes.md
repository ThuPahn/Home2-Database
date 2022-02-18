# CREATE DATABASE shoes

**Tạo bảng category**

```sql
CREATE TABLE category(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name TEXT NOT NULL
)
```

**Tạo bảng brand**

```sql
CREATE TABLE brand(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name TEXT NOT NULL
)
```

**Tạo bảng gender**

```sql
CREATE TABLE gender(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name TEXT NOT NULL
)
```

**Tạo bảng item**

```sql
CREATE TABLE item(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name TEXT NOT NULL,
    description TEXT,
    image TEXT,
    id_category INT,
    id_brand INT,
    status TEXT NOT NULL,
    id_gender INT,
    quantity INT NOT NULL,

    FOREIGN KEY(id_category) REFERENCES category(id),
    FOREIGN KEY(id_brand) REFERENCES brand(id),
    FOREIGN KEY(id_gender) REFERENCES gender(id)
)
```

**Tạo bảng price**

```sql
CREATE TABLE price(
    id INT PRIMARY KEY AUTO_INCREMENT,
    id_item INT,
    price BIGINT NOT NULL,
    date DATE,

    FOREIGN KEY(id_item) REFERENCES item(id)
)
```

**Tạo bảng size**

```sql
CREATE TABLE size(
    id INT PRIMARY KEY AUTO_INCREMENT,
    size INT NOT NULL
)
```

**Tạo bảng item size**

```sql
CREATE TABLE item_size(
    id_item INT,
    id_size INT,

    PRIMARY KEY(id_item, id_size),

    FOREIGN KEY(id_item) REFERENCES item(id),
    FOREIGN KEY(id_size) REFERENCES size(id)
)
```

**Tạo bảng color**

```sql
CREATE TABLE color(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name TEXT NOT NULL
)
```

**Tạo bảng item_color**

```sql
CREATE TABLE item_color(
    id_item INT,
    id_color INT,

    PRIMARY KEY(id_item, id_color),

    FOREIGN KEY(id_item) REFERENCES item(id),
    FOREIGN KEY(id_color) REFERENCES color(id)
)
```

**Tạo bảng users**

```sql
CREATE TABLE users(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name TEXT NOT NULL,
    username TEXT NOT NULL,
    password TEXT NOT NULL,
    email TEXT NOT NULL,
    mobile TEXT NOT NULL,
    id_gender INT,
    dob DATE NOT NULL,
    start_at DATE,
    status TEXT NOT NULL,
    address TEXT NOT NULL,
    role TEXT NOT NULL,

    FOREIGN KEY(id_gender) REFERENCES gender(id)
)
```

![image](https://user-images.githubusercontent.com/95139699/154616869-d5c9ff27-d751-4bc3-9bcc-5eb58e905de8.png)
