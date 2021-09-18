# UnitTestinginDotNet
This Project Implements Different Unit Testing Techniques For .Net

a. Testing using MSTest:

  1. Create a Test Project
  Go To 'Add Project'->Create 'Unit Test Project'

  2. Add a simple Test Class And Test Method.

      [TestClass]
      public class ReservationTests
      {
          [TestMethod]
          public void CanBeCancelledBy_UserIsAdmin_ReturnsTrue()
          {
              //Arrange
              var reservation = new Reservation();

              //Act
              var result = reservation.CanBeCancelledBy(new User { IsAdmin = true });

              //Assert
              Assert.IsTrue(result);
          }
        

b. Testing using NUnit:

  1. Install Packages:
    a. NUnit
    b. NUnit3TestAdapter (This is to run NUnit tests inside VS, bcoz by default VS recognizes only MSTests)

  2. Create a Test Project
  Go To 'Add Project'->Create 'Unit Test Project'

  3. Add a simple Test Class (with TestFixture Attribute) And Test Method (with Test Attribute) .

      [TestFixture]
      public class ReservationTests
      {
          [Test]
          public void CanBeCancelledBy_UserIsAdmin_ReturnsTrue()
          {
              //Arrange
              var reservation = new Reservation();

              //Act
              var result = reservation.CanBeCancelledBy(new User { IsAdmin = true });

              //We can use any of the three Assert Statement Syntax
              //Assert.IsTrue(result);
              //Assert.That(result, Is.True);
              Assert.That(result==true);
          }
