Search Box Implementation
This project features a search box implementation using HTML, CSS, and JavaScript. It allows users to search for products displayed on a webpage and filter them based on the search query.

Features
Search Box: Users can type in a search query in the search box to filter products dynamically.
Product Display: Products are displayed in a grid layout with images, titles, and prices.
Responsive Design: The webpage is designed to be responsive and can adapt to various screen sizes.

HTML:
html
Copy code

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Search Box</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
</head>
<body>
    <!-- HTML content -->
</body>
</html>
<!DOCTYPE html>: Declares the document type and version of HTML.
<html lang="en">: Specifies the language of the document.
<head>: Contains meta-information about the document, such as the character set, viewport settings, and title.
<meta charset="UTF-8">: Specifies the character encoding for the document.
<meta name="viewport" content="width=device-width, initial-scale=1.0">: Configures the viewport settings for mobile devices.
<title>Search Box</title>: Sets the title of the webpage.
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">: Links to an external stylesheet provided by Font Awesome for icon styling.

CSS:
css
Copy code

- {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  }

/_ CSS rules _/
\*: Targets all elements.
margin: 0; padding: 0;: Resets margin and padding for all elements.
box-sizing: border-box;: Sets box-sizing property to border-box for easier layout calculations.
font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;: Specifies the font family for the entire document.

JavaScript:
javascript
Copy code

<script>
    // JavaScript functions
</script>
<script>: Contains JavaScript code.
function searchProducts() { ... }: Defines a function searchProducts() to handle product search based on user input.
function clearSearch() { ... }: Defines a function clearSearch() to clear the search input and display all products.

Sure, let's break down the JavaScript code line by line:

javascript
Copy code
function searchProducts() {
Defines a JavaScript function named searchProducts. This function is triggered when the user types in the search input field.
javascript
Copy code
const searchText = document.getElementById('search').value.trim().toUpperCase();
Retrieves the value entered into the search input field with the id search.
Trims any leading or trailing whitespace from the input.
Converts the input text to uppercase for case-insensitive comparison.
javascript
Copy code
const products = document.querySelectorAll('.product');
Selects all elements with the class product using querySelectorAll and stores them in the products variable.
These elements represent the list of products displayed on the webpage.
javascript
Copy code
let found = false;
Initializes a boolean variable found with the value false. This variable is used to keep track of whether a matching product has been found during the search.
javascript
Copy code
products.forEach(product => {
Iterates over each product element in the products NodeList using the forEach method.
javascript
Copy code
const productName = product.querySelector('.p-details h2').textContent.toUpperCase();
Selects the <h2> element within the product element's .p-details class and retrieves its text content.
Converts the text content to uppercase for case-insensitive comparison.
This represents the name of the product.
javascript
Copy code
if (productName.includes(searchText) || searchText === '') {
Checks if the product name contains the search text (searchText) or if the search input is empty.
If either condition is true, the product is considered a match, and the following actions are performed.
javascript
Copy code
product.style.display = 'flex';
Sets the display CSS property of the current product element to 'flex', making it visible.
This ensures that matching products are displayed to the user.
javascript
Copy code
if (!found && searchText !== '') {
    product.parentElement.prepend(product);
    found = true;
}
Checks if a matching product has not been found (!found) and if the search input is not empty (searchText !== '').
If both conditions are true, the current product is moved to the top of the product list.
This ensures that the most relevant matching product appears at the top of the list.
The found variable is set to true to indicate that a matching product has been found.
javascript
Copy code
} else {
    product.style.display = 'none';
}
If the product name does not contain the search text and the search input is not empty, the product is hidden (display: none).
This ensures that non-matching products are not displayed to the user.
javascript
Copy code
});
Ends the forEach loop, indicating the completion of processing for all product elements.
javascript
Copy code
}
function clearSearch() {
Defines a JavaScript function named clearSearch. This function is triggered when the user clicks the clear search button.
javascript
Copy code
document.getElementById('search').value = '';
Clears the value of the search input field by setting it to an empty string.
javascript
Copy code
search();
Calls the search() function after clearing the search input. However, it seems there is a typo here, as the function should be searchProducts() instead of search().
<b> deep </b>
productName.includes(searchText): This condition checks if the productName, which represents the name of the current product, includes the searchText. The includes() method is used to determine whether one string may be found within another string. If the productName contains the searchText, or if the searchText is an empty string (|| searchText === ''), then the condition evaluates to true.

product.style.display = 'flex';: If the condition mentioned above evaluates to true, it means the product matches the search criteria or the search field is empty. In this case, the display CSS property of the current product (product) is set to 'flex', making it visible on the webpage.

if (!found && searchText !== '') { ... }: This nested if statement is executed if a matching product is found (!found) and the search input is not empty (searchText !== ''). It ensures that only the first matching product is moved to the top of the product list.

product.parentElement.prepend(product);: The prepend() method is used to insert the current product (product) as the first child of its parent element. In this case, the product is moved to the top of the product list by prepending it to its parent element, which effectively changes its position in the list.

found = true;: After moving the first matching product to the top of the list, the found variable is set to true. This helps in tracking whether a matching product has already been found during the search process. If found is true, subsequent matching products will not be moved to the top of the list.


window.location.reload(); to refresh the page
