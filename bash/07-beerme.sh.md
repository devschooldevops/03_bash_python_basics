## Practice Bash script

Let's build the `beerme.sh` script step by step, to practice all the concepts of Bash scripting. 
Each step will add new functionality to the script, showcasing the power of Bash.

### Step 1: Variables

Let's start by introducing variables. As you remember, in Bash, you assign a value to a variable like this:

```bash
#!/bin/bash

# Declare a variable
beer="Heineken"

# Output the variable value
echo "You have selected $beer."
```

### Step 2: User Input

Now, let's allow the user to input their choice of beer. We'll use the `read` command to get user input.

```bash
#!/bin/bash

# Prompt the user for input
echo "What type of beer would you like?"

# Read user input into a variable
read beer

# Output the user's choice
echo "You have selected $beer."
```

### Step 3: Adding Conditionals

Let's add a conditional statement so that we can handle different types of input. We'll use an `if-else` statement to check if the user has chosen a specific type of beer.

```bash
#!/bin/bash

# Prompt the user for input
echo "What type of beer would you like?"

# Read user input into a variable
read beer

# Conditional to check the beer type
if [ "$beer" == "Heineken" ]; then
    echo "Great choice! Heineken is available."
else
    echo "Sorry, we only have Heineken at the moment."
fi
```

### Step 4: Expanding Conditionals with `elif`

Let's allow the user to choose from more than one type of beer by expanding the conditional with `elif`.

```bash
#!/bin/bash

# Prompt the user for input
echo "What type of beer would you like? (Heineken, Becks, Corona)"

# Read user input into a variable
read beer

# Conditional to check the beer type
if [ "$beer" == "Heineken" ]; then
    echo "Great choice! Heineken is available."
elif [ "$beer" == "Becks" ]; then
    echo "Becks coming right up!"
elif [ "$beer" == "Corona" ]; then
    echo "Corona is a fine choice!"
else
    echo "Sorry, we don't have $beer."
fi
```

### Step 5: Using Case Statements

As the number of options grows, `case` statements become more readable and easier to manage than multiple `elif` statements.

```bash
#!/bin/bash

# Prompt the user for input
echo "What type of beer would you like? (Heineken, Becks, Corona, Stella)"

# Read user input into a variable
read beer

# Case statement to handle multiple options
case "$beer" in
    "Heineken")
        echo "Great choice! Heineken is available."
        ;;
    "Becks")
        echo "Becks coming right up!"
        ;;
    "Corona")
        echo "Corona is a fine choice!"
        ;;
    "Stella")
        echo "Stella is a classy choice!"
        ;;
    *)
        echo "Sorry, we don't have $beer."
        ;;
esac
```

### Step 6: Adding Functions

Let's refactor our script by introducing functions to make the script more modular and maintainable.

```bash
#!/bin/bash

# Function to handle beer order
order_beer() {
    case "$1" in
        "Heineken")
            echo "Great choice! Heineken is available."
            ;;
        "Becks")
            echo "Becks coming right up!"
            ;;
        "Corona")
            echo "Corona is a fine choice!"
            ;;
        "Stella")
            echo "Stella is a classy choice!"
            ;;
        *)
            echo "Sorry, we don't have $1."
            ;;
    esac
}

# Main script
echo "What type of beer would you like? (Heineken, Becks, Corona, Stella)"
read beer

# Call the function with user input
order_beer "$beer"
```

### Step 7: Loops for Repeated Actions

Let's add a loop so that the user can order multiple beers without restarting the script.

```bash
#!/bin/bash

# Function to handle beer order
order_beer() {
    case "$1" in
        "Heineken")
            echo "Great choice! Heineken is available."
            ;;
        "Becks")
            echo "Becks coming right up!"
            ;;
        "Corona")
            echo "Corona is a fine choice!"
            ;;
        "Stella")
            echo "Stella is a classy choice!"
            ;;
        *)
            echo "Sorry, we don't have $1."
            ;;
    esac
}

# Main script with a loop for repeated orders
while true; do
    echo "What type of beer would you like? (Heineken, Becks, Corona, Stella)"
    read beer

    # Exit loop if the user types "exit"
    if [ "$beer" == "exit" ]; then
        echo "Thank you for your orders. Goodbye!"
        break
    fi

    # Call the function with user input
    order_beer "$beer"
done
```

### Step 8: Handling Invalid Input with Loops

Finally, let's ensure the user provides valid input by adding a loop inside the main loop that only accepts valid beer types.

```bash
#!/bin/bash

# Function to handle beer order
order_beer() {
    case "$1" in
        "Heineken")
            echo "Great choice! Heineken is available."
            ;;
        "Becks")
            echo "Becks coming right up!"
            ;;
        "Corona")
            echo "Corona is a fine choice!"
            ;;
        "Stella")
            echo "Stella is a classy choice!"
            ;;
        *)
            echo "Sorry, we don't have $1."
            ;;
    esac
}

# Main script with a loop for repeated orders
while true; do
    echo "What type of beer would you like? (Heineken, Becks, Corona, Stella)"
    read beer

    # Exit loop if the user types "exit"
    if [ "$beer" == "exit" ]; then
        echo "Thank you for your orders. Goodbye!"
        break
    fi

    # Validate input
    case "$beer" in
        "Heineken"|"Becks"|"Corona"|"Stella")
            order_beer "$beer"
            ;;
        *)
            echo "Invalid selection. Please choose a valid beer or type 'exit' to quit."
            ;;
    esac
done
```

### Homework:

Enhance the beer odering script so that it will log the orders in a file containing the current date in which the orders were placed

