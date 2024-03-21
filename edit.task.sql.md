create table if not exists Department (
id serial primary key,
name varchar (70) not null
);

create table if not exists Worker (
id serial primary key,
name varchar (70) not null,
age integer check (age > 18),
department_id integer NOT NULL references Department(id),
boss_id integer NOT NULL references Worker(id)
);