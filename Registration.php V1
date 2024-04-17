<?php

    session_start();

    $servername = "localhost";
    $username = "root";
    $password = "root";
    $database = "zoodb"; //change to name of database
    $port = 8889; //MySQL port my MAMP
    $conn = new mysqli($servername, $username, $password, $database, $port);

    if ($conn->connect_error) {
        die("connection failed: "  . $conn->connect_error);
        }

        $userID = null;

        if ($_SERVER["REQUEST_METHOD"] == "POST") {
            $Firstname = $_POST["firstname"];
            $Surname= $_POST["surname"];
            $DOB = date("Y-m-d", strtotime($_POST["dateofbirth"]));
            $Email = $_POST["email"];
            $Addressline1 = $_POST["address1"];
            $Addressline2 = $_POST["address2"];
            $Mobile = $_POST["mobile"];  //doesnt works needs looking at from line 13 - end
            $Postcode = $_POST["postcode"];
            $CityTown = $_POST["city/town"];
            $Username = $_POST["username"];
            $Password = $_POST["password"];

	$currentDate = date("Y/m/d");
 $sql = "INSERT INTO customers(firstname, DOB, surname, emailaddress, addressline1, addressline2, mobile, postcode, citytown, username, password )
            VALUES ('$Firstname', '$DOB', '$Surname','$Email', '$Addressline1', '$Addressline2', $Mobile, '$Postcode', '$CityTown', '$Username', '$Password')";

    if ($conn->query($sql) === TRUE) {
       $userID = $conn->insert_id;

        echo "Registration successful! User ID: $userID";
    } else {
      echo "Error: " . $sql . "<br>" . $conn->error;

    }
}
print_r($_POST);
echo'<pre>';
var_dump($_SESSION);
echo'<pre>';
// Close the connection
$conn->close();
?>
