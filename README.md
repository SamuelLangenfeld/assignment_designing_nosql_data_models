# assignment_designing_nosql_data_models
I'll have one data model hold the SQL please
Sam Langenfeld and Austin Smith


Basic
========

1. Users collection

  Username- String
  Password- String
  Firstname- String
  Lastname- String
  Preference_settings: {
    Birthday: date
    Gender: Char
    PhoneNum: String
      -numbers only, 10 digits
    Location: {
      City: String
      State: String
      Country: String
    }
    VisibleSettings:[{Birthday: boolean}, {Gender: boolean}, etc]
  }


  Intermediate
  ============

  1.

  You're building a restaurant table reserving app that allows users to reserve tables for specified numbers of people. The app will need to show only tables that are available and the times they are available. The app will need to store reservations under a given name with a phone number and number of guests.

  Tables
    TableNum:{
      id: integer
      windows:{
        [{SpecificTime: availble/not}]
      }
    }


  Users{
    User:{
      Id: Integer
      Reservations:{
        TableNum,
        Window,
        Guests: Integer
      }
      PhoneNumber: Integer
    }
  }


  2.

  You're building a backend for a university that requires students to be able to login. Once logged in, the students can view the exam grades for their classes. They should be able to view results by semester. Each semester should only show the classes in which that student is enrolled that semester.

  Students{
    Username: String,
    Password: String,
    Semesters: {
      SemesterId: {
        [classIds]//Integers
      }
    }
  }
