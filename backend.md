# Project Description

## This project is a restaurant administration backend application built with .NET 8 and C# 12.0. The application manages various entities such as restaurants, menus, tables, users, reservations, and reviews. It uses Entity Framework Core for database operations.

## Required NuGet Packages

## To run and develop this project, you need to install the following NuGet packages:
1.  Microsoft.EntityFrameworkCore.SqlServer
- Provides database connectivity to SQL Server.
- Installation: dotnet add package Microsoft.EntityFrameworkCore.SqlServer

2.	Microsoft.EntityFrameworkCore.Design
- Provides design-time services for Entity Framework Core, such as migrations.
- Installation: dotnet add package Microsoft.EntityFrameworkCore.Design

3.	AutoMapper.Extensions.Microsoft.DependencyInjection
- Integrates AutoMapper with the Dependency Injection system.
- Installation: dotnet add package AutoMapper.Extensions.Microsoft.DependencyInjection

4.	Swashbuckle.AspNetCore
- Generates Swagger/OpenAPI documentation.
- Installation: dotnet add package Swashbuckle.AspNetCore

## Installing Entity Framework Core Tools

## To use the Entity Framework Core command-line tools, you need to install the dotnet-ef tool. You can install it globally or locally.

## Global Installation: ``` dotnet tool install --global dotnet-ef ```

## Using Entity Framework Core Commands

## Use the following commands to create migrations and update the database:
1.	Create a Migration: ``` dotnet ef migrations add InitialCreate ```
2.	Update the Database: ``` dotnet ef database update ```
3.	Create a New Migration after Changes: ``` dotnet ef migrations add UpdateReviewEntity ```
4.	Update the Database with the New Migration: ``` dotnet ef database update ```

# Models
## Here are the models used in the project:

```
public class Category { 
    public int Id { get; set; }
    public required string Name { get; set; }
    public bool IsAlcoholic { get; set; }
    public bool IsVegan { get; set; }
    public string? Description { get; set; }
    public List<MenuItem> MenuItems { get; set; }
}
```

```
public class Menu { 
    public int Id { get; set; }
    public int RestaurantId { get; set; }
    public required string Name { get; set; }
    public required string Description { get; set; }
    public DateTime CreatedAt { get; set; }
    public Restaurant Restaurant { get; set; }
    public List<MenuItem> MenuItems { get; set; }
}
```

```
public class Allergen { 
    public int Id { get; set; }
    public required string Name { get; set; }
    public List<MenuItem> MenuItems { get; set; }
}
```

```
public class Contact { 
    public int Id { get; set; }
    public int RestaurantId { get; set; }
    public required string Phone { get; set; }
    public required string Email { get; set; }
    public required string Address { get; set; }
    public Restaurant Restaurant { get; set; }
}
```

```
public class Promotion { 
    public int Id { get; set; }
    public int RestaurantId { get; set; }
    public required string Title { get; set; }
    public required string Description { get; set; }
    public decimal Discount { get; set; }
    public DateTime StartDate { get; set; }
    public DateTime EndDate { get; set; }
    public bool IsActive { get; set; }
    public Restaurant Restaurant { get; set; }
}
```

```
public class Reservation { 
    public int Id { get; set; }
    public int TableId { get; set; }
    public int CustomerId { get; set; }
    public DateTime ReservationTime { get; set; }
    public ReservationStatus Status { get; set; }
    public Table Table { get; set; }
    public User Customer { get; set; }
}
```
```
public class Review { 
    public int Id { get; set; }
    public int RestaurantId { get; set; }
    public int CustomerId { get; set; }
    public int Rating { get; set; }
    public string? Comment { get; set; }
    public DateTime CreatedAt { get; set; }
    public Restaurant Restaurant { get; set; }
    public User Customer { get; set; }
}
```

```
public class Table { 
    public int Id { get; set; }
    public int RestaurantId { get; set; }
    public int TableNumber { get; set; }
    public int Capacity { get; set; }
    public required string QRCode { get; set; }
    public Restaurant Restaurant { get; set; }
    public List<Reservation> Reservations { get; set; }
}
```

```
public class MenuItem { 
    public int Id { get; set; }
    public int MenuId { get; set; }
    public int CategoryId { get; set; }
    public required string Name { get; set; }
    public required string Description { get; set; }
    public decimal Price { get; set; }
    public bool IsAvailable { get; set; }
    public string? ImageUrl { get; set; }
    public Menu Menu { get; set; }
    public Category Category { get; set; }
    public List<int> AllergenIds { get; set; }
    public List<Allergen> Allergens { get; set; }
}
```

```
public class Restaurant { 
    public int Id { get; set; }
    public required string Name { get; set; }
    public required string Address { get; set; }
    public required string Phone { get; set; }
    public required string Email { get; set; }
    public int OwnerId { get; set; }
    public DateTime CreatedAt { get; set; }
    public required decimal Latitude { get; set; }
    public required decimal Longitude { get; set; }
    public User Owner { get; set; }
    public List<Menu> Menus { get; set; }
    public List<Table> Tables { get; set; }
    public List<Review> Reviews { get; set; }
    public List<Promotion> Promotions { get; set; }
    public Contact Contact { get; set; }
}
```

```
public class User { 
    public int Id { get; set; }
    public required string Username { get; set; }
    public required string PasswordHash { get; set; }
    public required string Email { get; set; }
    public int RoleId { get; set; }
    public DateTime CreatedAt { get; set; }
    public Role Role { get; set; }
    public List<Review> Reviews { get; set; }
    public List<Reservation> Reservations { get; set; }
}
```

```
public class Role { 
    public int Id { get; set; }
    public required string Name { get; set; }
}
```

```
public enum ReservationStatus { 
    Pending,
    Confirmed,
    Cancelled
}
```

# Summary
## This documentation provides an overview of how to install the required NuGet packages, Entity Framework Core tools, and how to use the dotnet ef commands for migrations and database updates. The project aims to develop a restaurant administration backend application that manages various entities and uses Entity Framework Core for database operations.
