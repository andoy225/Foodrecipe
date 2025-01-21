<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Recipes - Homepage</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header class="hero">
    <h1>Food Recipes</h1>
    <p>Discover, Cook, and Share Your Favorite Recipes</p>
    <a href="recipes.html" class="button">Explore Recipes</a>
  </header>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Recipes - Recipes</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Our Recipes</h1>
  </header>
  <main class="recipes">
    <div class="recipe-card">
      <img src="images/recipe1.jpg" alt="Recipe 1">
      <h2>Spaghetti Carbonara</h2>
      <p>A classic Italian dish with a creamy sauce.</p>
      <a href="recipe.html?recipe=1" class="button">View Recipe</a>
    </div>
    <div class="recipe-card">
      <img src="images/recipe2.jpg" alt="Recipe 2">
      <h2>Chicken Curry</h2>
      <p>A flavorful and spicy curry.</p>
      <a href="recipe.html?recipe=2" class="button">View Recipe</a>
    </div>
  </main>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Food Recipes - Recipes</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Our Recipes</h1>
  </header>
  <main class="recipes">
    <div class="recipe-card">
      <img src="images/recipe1.jpg" alt="Recipe 1">
      <h2>Spaghetti Carbonara</h2>
      <p>A classic Italian dish with a creamy sauce.</p>
      <a href="recipe.html?recipe=1" class="button">View Recipe</a>
    </div>
    <div class="recipe-card">
      <img src="images/recipe2.jpg" alt="Recipe 2">
      <h2>Chicken Curry</h2>
      <p>A flavorful and spicy curry.</p>
      <a href="recipe.html?recipe=2" class="button">View Recipe</a>
    </div>
  </main>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Recipe Details</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Recipe Details</h1>
  </header>
  <main>
    <h2 id="recipe-title"></h2>
    <img id="recipe-image" src="" alt="Recipe Image">
    <h3>Ingredients</h3>
    <ul id="recipe-ingredients"></ul>
    <h3>Steps</h3>
    <p id="recipe-steps"></p>
  </main>

  <script src="scripts.js"></script>
</body>
</html>

body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.hero {
  background: url('images/hero-bg.jpg') no-repeat center center/cover;
  text-align: center;
  color: white;
  padding: 60px 20px;
}

button,
.button {
  display: inline-block;
  background-color: #ff6f61;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  text-decoration: none;
  cursor: pointer;
}

.recipes {
  display: flex;
  justify-content: center;
  gap: 20px;
  padding: 20px;
}

.recipe-card {
  width: 300px;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.recipe-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}


document.addEventListener("DOMContentLoaded", () => {
  const urlParams = new URLSearchParams(window.location.search);
  const recipeId = urlParams.get("recipe");

  if (recipeId) {
    const recipes = [
      {
        id: "1",
        title: "Spaghetti Carbonara",
        image: "images/recipe1.jpg",
        ingredients: ["Spaghetti", "Eggs", "Parmesan", "Pancetta"],
        steps: "Boil pasta. Cook pancetta. Mix eggs and cheese. Combine all.",
      },
      {
        id: "2",
        title: "Chicken Curry",
        image: "images/recipe2.jpg",
        ingredients: ["Chicken", "Curry Paste", "Coconut Milk", "Vegetables"],
        steps: "Cook chicken. Add curry paste. Stir in coconut milk. Simmer.",
      },
    ];

    const recipe = recipes.find((r) => r.id === recipeId);
    if (recipe) {
      document.getElementById("recipe-title").textContent = recipe.title;
      document.getElementById("recipe-image").src = recipe.image;
      document.getElementById("recipe-ingredients").innerHTML = recipe.ingredients
        .map((ingredient) => `<li>${ingredient}</li>`)
        .join("");
      document.getElementById("recipe-steps").textContent = recipe.steps;
    }
  }
});
