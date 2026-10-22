# COMP 440: Representing and Retrieving Knowledge

Claude writes your answers here as you say them. A sentence or two is enough for each. Your
Part 0 predictions stay as you first wrote them; Part 5 asks what you would change.

**Name:** Laurice Jimu
**Date:** October 20, 2026

## Part 0: Predictions

### Questions that name a character, place or thing: which method will do better, and why?

Keyword Search, since in the plot description we probably have these details written in there and a match is likely.

### Vague descriptions: which method will do better, and why?

For vague descriptions, Embedding will probably do better because there won't be that many words that the plot shares with the question if the question is a pointed question

## Part 1: Build the TF-IDF model

### The settings you chose, and why

- `REMOVE_STOP_WORDS = True`: it removes all the noise and allows us to focus on the details that differentiate the movies.
- `MIN_MOVIES = 1`: I'll keep it at one to allow for really rare movies that have bizzare words that only come into play once
- `REPEATS_COUNT_LESS = True`: I like it because it sounds mathimatically sound

## Part 2: Top terms

### Your movies: what do the top terms get right and wrong about what makes each one distinctive?

Passion of Christ, I think Nazareth, Jesus should be the top ones, portrayal I get it but that can be applied to any movie. It did a pretty okay job I assume. I'm surprised portrayal was above Jesus

For Titanic, They Get, titanic, boards, ship , aboard well. Rose is close but not quite cause it's a fairly common name, as seen in 13 movies. Most of the numbers and the rest of the names and years are pretty useless on their own.

## Part 3: Your own searches

### Your questions, as you typed them

1. Obscure African Country is Rich in the world's most precious metal unbenkowst to the rest of the world
2. White south african guy goes to Congo to find diamonds. He meets Solomon Vandy, who has found the biggest diamond and hidden it. They go through threats from rebel soldiers and government forces to try and get the diamond, sell it and bring solomons family back
3. A boxer, Adonis Creed who rises up the ranks and becomes the best in the world. He is trained by Rocky a once world class boxer and must face adversity as his girlfriend is losing her sense of sound.

### Did the movies you meant come up? What did TF-IDF get right and wrong?

The movie that was top was Creed which came up first because I used very specific name terms. For the rest of them it had 9. Blood Diamond and 6. Black Panther. It did not do well with descriptive phrases but without a specific terms

## Part 4: The question bank

### Which kind of question did TF-IDF handle best, and which worst? By how much?

Overall the performance was appaling. Like I'd expected, it does best in detailed questions and horrenus in the reworded and vague questions

The gap was by an infinite amount becasue we had 0 for both reworded and vague but 21 for the detailed

### The misses you looked at: what do they have in common?

The movies with random normal words were predicted terribly and those with distinct words worked best

## Part 5: Embeddings

### What is a sentence embedding, in your own words?

Sentence embedding is when the questions I have whose words in sentence are turned into a list of numbers, then it ranks the movies whos numbers are similar to my questions

The question on blood diamond most likely would've been handlesd much better with words being turned into lists of numbers and compared to the description

### Where does each method do better, and why?

It looks like embeddings does better on more general and broader questions asked whereas the TF-IDF does better in the pointed super descript and niche topics. Overall however, embeddings scored much better

### Your Part 0 predictions: which held, and which would you change?

I wouldn't change any, they both hold

### How might you combine the two methods?

A combination of both might start of with embedding to get the general accuracy to bring it close to what we want and then using TF-IDF weighted slightly less so that within the smaller subset we get even more refined responses
