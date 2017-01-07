---
layout: default
---

## Your typical test code
Here’s some typical test code found in many codebases:

```java
@Test
public void testCalculateTaxRate() {

    TaxRateCalculator calculator = new TaxRateCalculator();

    Int value = calculator.calculateRate(200, 10);

    assertEquals(300,value);
}
```

This code suffers from several issues. Under what **conditions** is the tax rate calculated? What exactly is it **doing**? What is the **expected outcome**?


## Being explicit with Spek
Spek makes it easy to define these three important aspects without resorting to long method names or underscores:

```kotlin
class SimpleTest : Spek({
    describe("a calculator") {
        val calculator = SampleCalculator()

        on("addition") {
            val sum = calculator.sum(2, 4)

            it("should return the result of adding the first number to the second number") {
                assertEquals(6, sum)
            }
        }

        on("subtraction") {
            val subtract = calculator.subtract(4, 2)

            it("should return the result of subtracting the second number from the first number") {
                assertEquals(2, subtract)
            }
        }
    }
})
```

## Tests are specifications
Tests are executable specifications of your system. They are real-time compilable code that tell you how a piece of code should behave and under what conditions is a certain outcome expected. That is why it is important to be explicit, concise and unambiguous when it comes to defining specifications. Spek helps you do that.

## Spek works with Java
Spek is written in Kotlin and as such is 100% compatible with Java. You can write your specifications (notice we say specification, not test) in Kotlin and verify new or existing code written in Java or Kotlin.
