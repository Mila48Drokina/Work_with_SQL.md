create table if not exists Musical_genre (
id serial primary key,
name varchar (100) not null);
	
create table if not exists Genre_Artisits (
Artist_id integer references Artist(id),
Musical_genre_id integer references Musical_genre(id),
constraint Musical_genre_id primary key (Artist_id, Musical_genre_id)
);
create table if not exists Albums (
id serial primary key,
Name varchar (100) not null,
Year_of_release integer CHECK (Year_of_release <= 2025 )
);

create table if not exists Tracks (
id serial primary key,
track_name varchar (100) not null,
track_duration integer not null,
Album_id integer references Albums(id)
);

create table if not exists Artists (
id serial primary key,
Name varchar (100) not null);

create table if not exists AlbumsArtists (
Album_id integer references Albums(id),
Artist_id integer references Artists(id),
constraint AlbumsArtists_id primary key (Album_id, Artist_id)
);

create table if not exists Track_Collection (
track_id integer references Tracks(id),
Collection_id integer references Collection(id),
constraint Track_Collection_id primary key (track_id, collection_id));

create table if not exists Collection (
id serial primary key,
Collection_name varchar (50) not null,
Year_of_release integer not null
);



