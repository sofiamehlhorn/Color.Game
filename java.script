var colors = [];

var squares = document.querySelectorAll(".square");
var colorDisplay = document.querySelector("#colorDisplay");
var message = document.querySelector("#message");
var h1 = document.querySelector("#h1");
var resetButton = document.querySelector("#reset");
var hardButton = document.querySelector("#hard");
var easyButton = document.querySelector("#easy");

var numSquares = 6;
var pickedColor;

function pickColor() {
    var random = Math.floor(Math.random() * colors.length);
    return colors[random];
}

function randomColor() {
    var r = Math.floor(Math.random() * 256);
    var g = Math.floor(Math.random() * 256);
    var b = Math.floor(Math.random() * 256);

    return "rgb(" + r + ", " + g + ", " + b + ")";
}

function generateRandomColors(num) {
    var arr = [];

    for (var i = 0; i < num; i++) {
        arr.push(randomColor());
    }

    return arr;
}

function changeColors(color) {
    for (var i = 0; i < squares.length; i++) {
        squares[i].style.backgroundColor = color;
    }
}

function assignColors() {
    for (var i = 0; i < squares.length; i++) {
        if (i < numSquares) {
            squares[i].style.display = "block";
            squares[i].style.backgroundColor = colors[i];
        } else {
            squares[i].style.display = "none";
        }
    }
}

function reset() {
    colors = generateRandomColors(numSquares);
    pickedColor = pickColor();

    colorDisplay.textContent = pickedColor;
    message.textContent = "";
    h1.style.backgroundColor = "#711cff";

    assignColors();
}

for (var i = 0; i < squares.length; i++) {
    squares[i].addEventListener("click", function() {
        var clickedColor = this.style.backgroundColor;

        if (clickedColor === pickedColor) {
            message.textContent = "¡Correcto!";
            changeColors(pickedColor);
            h1.style.backgroundColor = pickedColor;
        } else {
            this.style.backgroundColor = "#111225";
            message.textContent = "Intentalo nuevamente";
        }
    });
}

resetButton.addEventListener("click", function() {
    reset();
});

easyButton.addEventListener("click", function() {
    numSquares = 3;
    easyButton.classList.add("selected");
    hardButton.classList.remove("selected");
    reset();
});

hardButton.addEventListener("click", function() {
    numSquares = 6;
    hardButton.classList.add("selected");
    easyButton.classList.remove("selected");
    reset();
});

reset();
