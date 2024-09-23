### Iteration 4: Expanding the User Model

Discuss and document:

#### What are these functions (userSchema.statics.signup() and userSchema.statics.login())?

userSchema.statics.signup() and userSchema.statics.login() are static methods defined on a Mongoose schema.

- signup() typically handles user registration, validating input and creating a new user record in the database.
- login() usually manages user authentication, verifying credentials and generating a session or token for logged-in users.

#### Why are they used?

They are used to encapsulate and organize specific logic related to user registration and authentication directly within the Mongoose schema. This makes it easier to manage these processes and keeps the codebase clean by associating user-related operations with the user model itself.

#### What are the pros and cons of using this approach?

Pros:

- Organized: Keeps registration and login logic within the user model, making the code easier to manage.
- Reusable: You can easily reuse these methods wherever you need them in your app.
- Consistent: Ensures the same logic is used everywhere for signing up and logging in.
- Clear: Provides a straightforward way to interact with the user model, like User.signup().

Cons:
- Hard to Test: The logic is tightly linked to the model, making it harder to test or change separately.
- Less Flexible: If you need different behaviors, it’s harder to customize.
- Can Get Messy: As your app grows, the model might get overloaded with too much logic.
- Mixing Responsibilities: Combines data handling and business logic, which might make the code harder to maintain.

#### What alternative approaches are available?

- Service Layer: Move the signup and login logic to separate service functions or classes, isolating business logic from the model.

- Controller Methods: Handle the signup and login logic directly within the controllers responsible for processing HTTP requests.

- Middleware: Use middleware functions to manage authentication processes, particularly for login, across different routes.

- Utility Functions/Modules: Place the signup and login logic in separate utility functions or modules, which can be imported and used where needed.