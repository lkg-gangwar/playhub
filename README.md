
# 🎮 Play Hub

A collection of classic browser games built using **Flask** (backend) and **VanillaJS** (frontend). Includes:

* **Tic-Tac-Toe**
* **Hangman**
* **Rock Paper Scissors**
* **Two Guessing Games**:

  * You guess the computer's number.
  * The computer guesses your number using binary search.

---

## 🚀 Installation (Without Docker)

1. Install dependencies using `pip`:

   ```bash
   pip install flask
   ```

2. Create a `.env` file in the root directory:

   ```
   DOMAIN=your_local_ip_address
   PORT=port_number_you_prefer
   ```

3. Navigate to the app directory and run:

   ```bash
   cd games/src
   python app.py
   ```

---

## 🐳 Docker Setup (Recommended)

### 🔧 Dockerfile

Ensure your `Dockerfile` looks like this:

```dockerfile
FROM python:3.9

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

EXPOSE 5000

CMD ["python", "api/index.py"]
```

### 📄 requirements.txt

Ensure `flask` and other required packages are listed:

```
flask
python-dotenv
```

### 📦 Build and Run the Docker Container

1. Build the Docker image:

   ```bash
   docker build -t playhub:v1 .
   ```

2. Run the container:

   ```bash
   docker run -p 5000:5000 playhub:v1
   ```

3. Open your browser and visit:

   ```
   http://localhost:5000
   ```

> 🔁 Make sure your Flask app uses `host="0.0.0.0"` and `port=5000` in the `app.run()` call:

```python
app.run(host="0.0.0.0", port=5000)
```

---

## 🕹️ How to Play

### 1. **Tic Tac Toe**

* Player 1 is "X", Player 2 is "O".
* Alternate turns by clicking squares.
* Use `Restart` to replay, `Reset Score` to clear score.

---

### 2. **Hangman**

* Select difficulty using the dropdown in the nav.
  ![Switch Difficulty](./assets/switch_difficulty_hangman.png)
* Use:

  * `Get new word` for a new challenge
  * `Reveal Word` to give up
  * `Hint` for clues (limited)
* Tries and hint count are displayed at the top.

---

### 3. **Rock Paper Scissors**

* Choose Rock, Paper, or Scissors to play against the computer.
* Use:

  * `Play Again` to replay
  * `Reset Score` to clear stats
  * Difficulty dropdown to increase the challenge
    ![Switch Difficulty](./assets/switch_difficulty_rps.png)

---

### 4. **Guessing Games**

#### A. **You Guess**

* Set a number range, then guess the computer's number.
* Use:

  * `Reveal number` to give up
  * `Restart` to start over

#### B. **Computer Guesses**

* Set a range and input your number.
* Click `Play` to let the computer guess using binary search.
* Use `Restart` to replay.

---

🎉 **Enjoy the games and challenge your logic & luck!**



## On Local Machine

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the following dependencies

- flask

Additionally, create a .env file in the root directory with the following variables
- DOMAIN
    - your local IP address.
- PORT
    - the port you want to use.
    
Then, change your directory to the `/games/src` directory. To start, type

```bash
python app.py
```
And you're finished!

## How to play

Click on any of the 5 modes.

1. Tic Tac Toe

    First player is "X" and click on any square. Next player is "O" and click on any square that is not occupied. The game will automatically switch between the players. To restart the game, click the `Restart` button. To reset the saved score at the top, click the `Reset Score` button.

2. Hangman

    There are different difficulties you can play on. To switch the difficulty, click the dropdown on the very right of the nav.
    ![Switch Difficulty Button](./assets/switch_difficulty_hangman.png)

    If you have given up, click the `Reveal Word` button.
    
    If you want a new word, click the `Get new word` button.

    If you need a hint, click the `Hint` button. You don't have infinite hints! (# of hints are at the top)

    The number of tries you have is at the top. Good Luck!

3. Rock Paper Scissors

    In this game, you are playing against the computer so, yes, it is based on probability!

    To choose your option, click any of the three `Rock`, `Paper`, or `Scissors` buttons.

    To play again, click the `Play Again` button.

    To reset the saved score at the top, click the `Reset Score` button.

    To change difficulty, click the dropdown in the nav.
    ![Switch Difficulty Button](./assets/switch_difficulty_rps.png)

4. Guessing Games

    1. You Guess

        Enter the range you want the number to be in between and start guessing numbers in the bottom textbox.

        To reveal the number, click the `Reveal number` button

        To restart, click the `Restart` button.

    2. The Computer Guesses

        Enter the range you will choose a number between and enter your number.

        To restart, click the `Restart` button.

        When you press play, the computer will use a binary search algorithm to find your number!

    For both games you can see what guesses either you have made or the computer has made.
