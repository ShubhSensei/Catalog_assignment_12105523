# Understanding Lagrange Interpolation and Maven
```
For those who don't know what Lagrange and Maven is... since I used them to solve this assignment.

Reference Video: https://www.youtube.com/watch?v=zdyUwzOm1zw&t=48s 
```

## 🔵 Lagrange Interpolation

### Simple Explanation
Imagine you have a few points on a graph and you want to find a smooth curve that passes through all of them. Lagrange Interpolation is like connecting these dots in a special mathematical way. It's particularly useful when you know some points of a function but don't know the actual function itself.

### Real-World Analogy
Think of it like a connect-the-dots puzzle, but instead of straight lines, you're drawing a smooth curve that perfectly passes through each dot. The method is useful in:
- Weather prediction (predicting temperature at different times)
- Computer graphics (creating smooth curves)
- Secret sharing (like in our assignment)

### Simple Example
Let's say we have three points:
- (0, 2)
- (1, 3)
- (2, 12)

The Lagrange formula would help us find a polynomial that passes through all these points. Here's how it works:

1. For each point, we create a term that:
   - Equals 1 at that point
   - Equals 0 at all other points
   - Multiply this by the y-value of our point

2. Example calculation for (0, 2):
   ```
   L₀(x) = 2 * [(x-1)(x-2)]/[(0-1)(0-2)]
   ```

3. Do this for each point and add them together:
   ```
   Final polynomial = L₀(x) + L₁(x) + L₂(x)
   ```

This gives us the polynomial: f(x) = 2 + x + 3x²

### In Our Assignment
We use Lagrange Interpolation to:
1. Take the given points (after converting them from different bases)
2. Find the polynomial that passes through these points
3. Extract the constant term (the secret)

## 🔨 Maven

### Simple Explanation
Maven is like a helpful assistant that manages your Java project. It:
- Downloads required libraries
- Organizes your project files
- Builds your project
- Runs tests
- Creates the final program

### Real-World Analogy
Think of Maven like a kitchen manager who:
- Keeps track of all ingredients (dependencies)
- Maintains a standard kitchen layout (project structure)
- Follows recipes step by step (build process)
- Ensures quality control (testing)
- Packages the final dish (deployment)

### Simple Example
Let's say you want to create a simple Java project:

1. Without Maven:
```
- Download Gson library
- Create folders manually
- Set up compilation manually
- Configure testing manually
- Package everything manually
```

2. With Maven:
```xml
<project>
    <dependencies>
        <dependency>
            <groupId>com.google.code.gson</groupId>
            <artifactId>gson</artifactId>
            <version>2.10.1</version>
        </dependency>
    </dependencies>
</project>
```
And run: `mvn clean install`

Maven automatically:
- Downloads Gson
- Creates proper folders
- Compiles code
- Runs tests
- Creates JAR file

### In Our Assignment
We use Maven to:
1. Manage the Gson dependency (for JSON parsing)
2. Organize our project structure:
   ```
   src/
   ├── main/
   │   ├── java/
   │   │   └── ShamirSecret.java
   │   └── resources/
   │       └── testcases.json
   ```
3. Build the project with one command: `mvn clean install`

### Common Maven Commands
```bash
mvn clean        # Cleans previous builds
mvn compile     # Compiles the code
mvn test        # Runs tests
mvn package     # Creates JAR file
mvn install     # Installs to local repository
```

### Maven Project Structure Explained
```
project/
├── pom.xml              # Project configuration
├── src/
│   ├── main/           # Main code
│   │   ├── java/      # Java source files
│   │   └── resources/ # Configuration files
│   └── test/          # Test code
│       ├── java/      # Test files
│       └── resources/ # Test resources
└── target/            # Compiled files
```

## 🔗 How They Work Together in Our Assignment

1. Maven sets up the project and manages Gson dependency
2. We read JSON test cases using Gson
3. Convert values from different bases to decimal
4. Use Lagrange Interpolation to find the polynomial
5. Extract the constant term (secret)

Think of it like:
- Maven is the kitchen (development environment)
- Gson is a tool (like a knife or whisk)
- Lagrange Interpolation is the recipe
- The secret is the final dish

This combination allows us to:
1. Have a well-organized project (Maven)
2. Handle input data easily (Gson)
3. Solve the mathematical problem (Lagrange)