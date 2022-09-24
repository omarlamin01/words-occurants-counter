<template>
    <div id="search-area">
        <div class="container">
            <div class="row">
                <div class="eight columns offset-by-two">
                    <h1 class="headline">Words Occurants Counter</h1>
                </div>
            </div>

            <div class="row">
                <div class="eight columns offset-by-two">
                    <form class="wiki-search-form">
                        <textarea
                            id="wiki-search-input"
                            v-model="input"
                            placeholder="Enter texte for analyze"
                            class="wiki-search-input"
                        />
                        <button
                            class="button btn btn-wiki"
                            @click.prevent="search"
                        >
                            Analyze
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'App',
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>

<style>
form {
    max-width: 300px;
    margin: 10px auto;
    padding: 10px 20px;
    background: #f4f7f8;
    border-radius: 8px;
}
#search-area .container {
    position: relative;
    width: 100%;
    max-width: 1140px;
    margin: 0 auto;
    padding: 0 20px;
    box-sizing: border-box;
}

#search-area .column,
#search-area .columns {
    width: 100%;
    float: left;
    box-sizing: border-box;
}

@media (min-width: 400px) {
    #search-area .container {
        width: 85%;
        padding: 0;
    }
}

@media (min-width: 550px) {
    #search-area .container {
        width: 80%;
    }

    #search-area .column,
    #search-area .columns {
        margin-left: 4%;
    }

    #search-area .column:first-child,
    #search-area .columns:first-child {
        margin-left: 0;
    }

    #search-area .one.column,
    #search-area .one.columns {
        width: 4.66667%;
    }

    #search-area .two.columns {
        width: 13.33333%;
    }

    #search-area .three.columns {
        width: 22%;
    }

    #search-area .four.columns {
        width: 30.66667%;
    }

    #search-area .five.columns {
        width: 39.33333%;
    }

    #search-area .six.columns {
        width: 48%;
    }

    #search-area .seven.columns {
        width: 56.66667%;
    }

    #search-area .eight.columns {
        width: 65.33333%;
    }

    #search-area .nine.columns {
        width: 74%;
    }

    #search-area .ten.columns {
        width: 82.66667%;
    }

    #search-area .eleven.columns {
        width: 91.33333%;
    }

    #search-area .twelve.columns {
        width: 100%;
        margin-left: 0;
    }

    #search-area .one-third.column {
        width: 30.66667%;
    }

    #search-area .two-thirds.column {
        width: 65.33333%;
    }

    #search-area .one-half.column {
        width: 48%;
    }

    #search-area .offset-by-one.column,
    #search-area .offset-by-one.columns {
        margin-left: 8.66667%;
    }

    #search-area .offset-by-two.column,
    #search-area .offset-by-two.columns {
        margin-left: 17.33333%;
    }

    #search-area .offset-by-three.column,
    #search-area .offset-by-three.columns {
        margin-left: 26%;
    }

    #search-area .offset-by-four.column,
    #search-area .offset-by-four.columns {
        margin-left: 34.66667%;
    }

    #search-area .offset-by-five.column,
    #search-area .offset-by-five.columns {
        margin-left: 43.33333%;
    }

    #search-area .offset-by-six.column,
    #search-area .offset-by-six.columns {
        margin-left: 52%;
    }

    #search-area .offset-by-seven.column,
    #search-area .offset-by-seven.columns {
        margin-left: 60.66667%;
    }

    #search-area .offset-by-eight.column,
    #search-area .offset-by-eight.columns {
        margin-left: 69.33333%;
    }

    #search-area .offset-by-nine.column,
    #search-area .offset-by-nine.columns {
        margin-left: 78%;
    }

    #search-area .offset-by-ten.column,
    #search-area .offset-by-ten.columns {
        margin-left: 86.66667%;
    }

    #search-area .offset-by-eleven.column,
    #search-area .offset-by-eleven.columns {
        margin-left: 95.33333%;
    }

    #search-area .offset-by-one-third.column,
    #search-area .offset-by-one-third.columns {
        margin-left: 34.66667%;
    }

    #search-area .offset-by-two-thirds.column,
    #search-area .offset-by-two-thirds.columns {
        margin-left: 69.33333%;
    }

    #search-area .offset-by-one-half.column,
    #search-area .offset-by-one-half.column {
        margin-left: 52%;
    }
}

#search-area .container:after,
#search-area .row:after,
#search-area .u-cf {
    content: "";
    display: table;
    clear: both;
}

#search-area .button,
#search-area button {
    display: inline-block;
    height: 38px;
    padding: 0 30px;
    color: #555555;
    text-align: center;
    font-size: 11px;
    font-weight: 600;
    line-height: 38px;
    letter-spacing: .1rem;
    text-transform: uppercase;
    text-decoration: none;
    white-space: nowrap;
    background-color: transparent;
    border-radius: 4px;
    border: 1px solid #bbb;
    cursor: pointer;
    box-sizing: border-box;
}

#search-area input[type="submit"], input[type="reset"], input[type="button"] {
    display: inline-block;
    height: 38px;
    padding: 0 30px;
    color: #555555;
    text-align: center;
    font-size: 11px;
    font-weight: 600;
    line-height: 38px;
    letter-spacing: .1rem;
    text-transform: uppercase;
    text-decoration: none;
    white-space: nowrap;
    background-color: transparent;
    border-radius: 4px;
    border: 1px solid #bbb;
    cursor: pointer;
    box-sizing: border-box;
}

#search-area .button:hover,
#search-area button:hover {
    color: #333;
    border-color: #888888;
    outline: 0;
}

#search-area input[type="submit"]:hover, #search-area input[type="reset"]:hover, #search-area input[type="button"]:hover {
    color: #333;
    border-color: #888888;
    outline: 0;
}

#search-area .button:focus,
#search-area button:focus {
    color: #333;
    border-color: #888888;
    outline: 0;
}

#search-area input[type="submit"]:focus, i#search-area nput[type="reset"]:focus, #search-area input[type="button"]:focus {
    color: #333;
    border-color: #888888;
    outline: 0;
}

#search-area .button.button-primary,
#search-area button.button-primary {
    color: #fff;
    background-color: #33c3f0;
    border-color: #33c3f0;
}

#search-area input[type="submit"].button-primary, input[type="reset"].button-primary, input[type="button"].button-primary {
    color: #fff;
    background-color: #33c3f0;
    border-color: #33c3f0;
}

#search-area .button.button-primary:hover,
#search-area button.button-primary:hover {
    color: #fff;
    background-color: #1eaedb;
    border-color: #1eaedb;
}

#search-area input[type="submit"].button-primary:hover, #search-area input[type="reset"].button-primary:hover, #search-area input[type="button"].button-primary:hover {
    color: #fff;
    background-color: #1eaedb;
    border-color: #1eaedb;
}

#search-area .button.button-primary:focus,
#search-area button.button-primary:focus {
    color: #fff;
    background-color: #1eaedb;
    border-color: #1eaedb;
}

#search-area input[type="submit"].button-primary:focus, #search-area input[type="reset"].button-primary:focus, #search-area input[type="button"].button-primary:focus {
    color: #fff;
    background-color: #1eaedb;
    border-color: #1eaedb;
}

#search-area input[type="email"], #search-area input[type="number"], #search-area input[type="search"], #search-area input[type="text"], #search-area input[type="tel"], #search-area input[type="url"], #search-area input[type="password"] {
    height: 38px;
    padding: 6px 10px;
    background-color: #fff;
    border: 1px solid #d1d1d1;
    border-radius: 4px;
    box-shadow: none;
    box-sizing: border-box;
}
</style>
