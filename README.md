# Shamir's Secret Sharing Implementation

## 📝 Description
This project implements a simplified version of Shamir's Secret Sharing algorithm to find the constant term of a polynomial given a set of points. The implementation uses Java and handles polynomial interpolation using the Lagrange method.

## 🚀 Project Structure
```
shamir-secret-sharing/
├── pom.xml
├── README.md
└── src/
    └── main/
        ├── java/
        │   └── ShamirSecret.java
        └── resources/
            ├── testcase1.json
            └── testcase2.json
```

## 📋 Prerequisites
* Java JDK 17 or higher
* Maven
* Any IDE (VS Code recommended)

## 📦 Dependencies
* Gson 2.10.1 (for JSON parsing)

## 🛠️ Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone [your-repository-url]
   cd shamir-secret-sharing
   ```

2. **Build the project using Maven:**
   ```bash
   mvn clean install
   ```

## ⚡ Running the Program

### Method 1: Using IDE (VS Code)
1. Open the project in VS Code
2. Install "Extension Pack for Java" if not already installed
3. Right-click on `ShamirSecret.java`
4. Select "Run Java"

### Method 2: Using Terminal
```bash
mvn exec:java -Dexec.mainClass="ShamirSecret"
```

## 📄 Input Format

The program accepts input in JSON format. Two test cases are provided in the `resources` folder:

### Test Case 1 Example:
```json
{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    }
}
```

### Input Parameters
| Parameter | Description |
|-----------|-------------|
| `n` | Number of roots provided |
| `k` | Minimum number of roots required (k = m + 1, where m is polynomial degree) |
| `base` | The base in which the y-value is encoded |
| `value` | The encoded y-value |

## 💻 Implementation Details

### Key Components

1. **Point Class**
   - Represents a point with x and y coordinates
   - Uses BigInteger for precision

2. **Base Conversion**
   - Handles conversion of y-values from various bases to decimal

3. **Lagrange Interpolation**
   - Implements polynomial interpolation to find the constant term

### Key Features
* ✅ Handles large numbers using BigInteger
* ✅ Supports multiple number bases for input values
* ✅ Implements error handling and input validation
* ✅ Provides detailed output for verification

## 🔍 Code Explanation

### Main Methods

1. **Convert From Base**
   ```java
   private static BigInteger convertFromBase(String number, int base)
   ```
   - Converts numbers from any given base to decimal

2. **Parse Points**
   ```java
   private static List<Point> parsePoints(JsonObject json, int k)
   ```
   - Parses JSON input and extracts points

3. **Lagrange Interpolation**
   ```java
   private static BigInteger lagrangeInterpolation(List<Point> points)
   ```
   - Implements Lagrange interpolation algorithm

## ⚠️ Constraints

| Constraint | Description |
|------------|-------------|
| Coefficients | All must be positive integers |
| Number Range | Within 256-bit number range |
| Roots | Number of roots provided (n) ≥ k |
| Polynomial Degree | m = k - 1 |

## 📝 Output Format

The program outputs the secret (constant term) for both test cases:
```bash
Secret for test case 1: [value]
Secret for test case 2: [value]
```

## 🧪 Testing

To verify your implementation:
1. Run the program with provided test cases
2. Check if decoded values match expected output
3. Verify number of points used matches k
4. Confirm the final secret is within expected range

## 👥 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## ✍️ Author
[Shubham Bansal]


## 🤝 Acknowledgments
* Shamir's Secret Sharing Algorithm
* Maven Build Tool
* Gson Library

## 📞 Support
For support, email [bansal4995@gmail.com]