
import streamlit as st
import random
st.title("Number Guessing Game")
st.write("Guess a number between 1 and 10")
target_number = random.randint(1, 10)
guess = st.number_input("Enter your guess:", min_value=1, max_value=10, step=1)
if 'target_number' not in st.session_state:
    st.session_state.target_number = target_number
if st.button("Submit Guess"):
    if guess == st.session_state.target_number:
        st.success(f"Congratulations! You guessed it right. The number was {st.session_state.target_number}.")
        st.session_state.target_number = random.randint(1, 10)
        st.write("New number generated. Try guessing again!")
    else:
        st.warning("Oops! Wrong guess. Try again.")￼Enter