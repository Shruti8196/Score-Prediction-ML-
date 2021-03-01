import pickle
import numpy as np
import pandas as pd
import streamlit as st

st.write("""
# Simple Score Prediction Model
""")


def user_input_features():
    
    hours= st.number_input("Enter the Hours you Study-",0.5,step=0.5)
    features = np.array([hours])[:,np.newaxis]
    return features

df = user_input_features()

st.subheader('User Input(Hours Studied)-')
st.write(df[0][0])

model = pickle.load(open('linear1_model.sav', 'rb'))
predicted_y = model.predict(df)[0][0]

if df[0][0]>24:
    st.write("There are only 24 Hours a day!!!!")
    
elif df[0][0]>=10:
    st.subheader('Predicted Score-')
    x=round(np.random.random_sample(),2)
    if x==1.0:
        x=x-0.3
    if df[0][0]>=17:
        st.write(99.99)
    else:
        st.write(99+x)
else:
    st.subheader('Predicted Score-')  
    st.write(round(predicted_y))
# Run in anaconda Prompt: streamlit run Task2WebApp(Streamlit).py
