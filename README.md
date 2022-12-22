# Contact App

## Problem Statement

There is a console version of the contact application, which provides the CRUD (create, read, update and delete) function for contacts. Each contact has 5 fields, namely firstName, lastName, company, email and phone.

Now we need to implment the app as follows:

- Display a greeting screen and list available functions.
- Select corresponding function according to the prompts, and enter necessary information to complete operation.
- When the operation is completed, you can return to the main page, continue other operations or exit.

Below is the greeting screen, select corresponding number (1-5) to complete one operation. You can exit the app by selecting number 6.
```
Contact Application

1. Create a contact      
2. Get a contact
3. Update a contact      
4. Delete a contact      
5. Retrieve all contacts 
6. Exit contact app      

Enter your choice (1-6): 
```

With Some code snippets provided, you need to finish the **createContact, getContact, updateContact and deleteContact** methods.

## Solution

In main method, which is the entry point of the contact app, firstly, greeting screen is provided as above by using java **Scanner**.

```java
System.out.println("Contact Application");

System.out.println();

System.out.println("1. Create a contact");
System.out.println("2. Get a contact");
System.out.println("3. Update a contact");
System.out.println("4. Delete a contact");
System.out.println("5. Retrieve all contacts");
System.out.println("6. Exit contact app");

System.out.println();
System.out.print("Enter your choice (1-6): ");
```

Next, using condition flow **switch case block** to run corresponding operation.

```java
               switch (choice) {
                    case 1:
                        String contact = createContact(count, firstName, lastName, company, email, phone);
                        count++;
                        break;
                    case 2:
                        String contactInfo = getContact(contactId);
                        System.out.println(contactInfo);
                        break;
                    case 3:
                        updateContact(contactId, property, value);
                        break;
                    case 4:
                        deleteContact(contactId);
                        break;
                    case 5:
                        getAllContacts();
                        break;
                    case 6:
                        scanner.close();
                        return;
                    default:
                        System.err.println("Please select choice between 1 and 6");
                        break;
                }

```

Then, implment each operation. contactId is an auto-increment counter declared in main. Other fields need to be input via **Scanner**.

```java
public static String createContact(int contactId, String firstName, String lastName, String company, String email,
            String phone) {
    // Construct a contact info string as
    // 2::Ada::Lovelace::Babbage Industries::ada@example.com::424-1337
    // String contact = (contactId + 1) + "::" + firstName + "::" + lastName + "::" + company + "::" + email + "::" + phone;
    // Save the string to an array instance contacts.
    // contacts[contactId] = contact;
    // Return the contact info string
}
```

```java
public static String getContact(int contactId) {
        // Iterate over contacts array. Check if contact in index position is not null and has the contactId.
        // If so, return contact info as follows.
        // contactInfo = "contact name: " + firstName + " " + lastName + ", contact company: " + company  + ", contact email: " + email + ", contact phone: " + phone;
        // Hint. Using String#split("::") to retrieve each part of contact.
    }
```

```java
public static String updateContact(int contactId, String property, String value) {
        // First find contact 
        // Tell which field needs to be updated and value to be used.
        // Update correspoing part of contact and return updated contactInfo.
    }

```

```java
public static boolean deleteContact(int contactId) {
        // Search contact according to this contactId
        // If found, set the contact to null in found index. Return true to indicate success deletion.
        // Otherwise, return false.
    }
```

Finally, In order to continue after each operation completed, use **while loop** outside the switch / case code block.

```java
while (true) {
            System.out.println("Contact Application");

            .....
            System.out.print("Enter your choice (1-6): ");

            int choice = Integer.parseInt(scanner.nextLine());

            switch (choice) {
                ....
            }
```
