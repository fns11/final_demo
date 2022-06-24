import requests
import streamlit as st
from streamlit_lottie import st_lottie
from PIL import Image

# Find more emojis here: https://www.webfx.com/tools/emoji-cheat-sheet/
st.set_page_config(page_title="My Webpage", page_icon=":tada:", layout="wide")


def load_lottieurl(url):
    r = requests.get(url)
    if r.status_code != 200:
        return None
    return r.json()


# Use local CSS
def local_css(file_name):
    with open(file_name) as f:
        st.markdown(f"<style>{f.read()}</style>", unsafe_allow_html=True)


local_css("style_css.txt")

# ---- LOAD ASSETS ----
lottie_coding = load_lottieurl("https://assets5.lottiefiles.com/packages/lf20_fcfjwiyb.json")
img_contact_form = Image.open("demo_image1.png")
img_lottie_animation = Image.open("demo_image1.png")

# ---- HEADER SECTION ----
with st.container():
    st.subheader("Welcome to the SSVF Portal:wave:")
    st.title("We link you with a Veteran Counselor that's here to assist you")
    st.write(
        "Q: Where did you sleep last night, tell us all about it."
    )
    st.write("[Learn More >](https://youtu.be/ix1BUgTztGU)")

# ---- WHAT I DO ----
with st.container():
    st.write("---")
    left_column, right_column = st.columns(2)
    with left_column:
        st.header("What we do to get you the assistance you need")
        st.write("##")
        st.write(
            """
            On my YouTube channel I am creating tutorials for people who:
            - are you looking for a way to look for housing.
            - are you struggling with life situations and want a change.
            - want to learn new skills and trades.
            - are you trying to work and thinking  "there has to be a better way."
            If this sounds interesting to you, consider subscribing and and filling out the forms below.
            """
        )
        st.write("[YouTube Channel >](https://youtu.be/zjTE48Ab9J0)")
    with right_column:
        st_lottie(lottie_coding, height=300, key="coding")

# ---- PROJECTS ----
with st.container():
    st.write("---")
    st.header("Forms to Fill out below ")
    st.write("##")
    image_column, text_column = st.columns((1, 2))
    with image_column:
        st.image(img_lottie_animation)
    with text_column:
        st.subheader("These forms below will better let us know your situation and if you qualify")
        st.write(
            """
            Sign up today!
            We have links to answer questions you may have!
            FAQs
            """
        )
        st.markdown("[Watch Video...](https://youtu.be/RlKJDwViNKs)")
with st.container():
    image_column, text_column = st.columns((1, 2))
    with image_column:
        st.image(img_contact_form)
    with text_column:
        st.subheader("How To instructions if you have questions about application process")
        st.write(
            """
            Forms and Information below
            FAQs’.
            """
        )
        st.markdown("[Watch Video...](https://youtu.be/FOULV9Xij_8)")

# ---- CONTACT ----
with st.container():
    st.write("---")
    st.header("Get In Touch With Me if you have any questions!") 
    st.write("##")

    # Documention: https://formsubmit.co/ !!! CHANGE EMAIL ADDRESS !!!
    contact_form = """
    <form action="https://formsubmit.co/dominica.hewett@uwforsyth.org" method="POST">
        <input type="hidden" name="_captcha" value="false">
        <input type="text" name="name" placeholder="Your name" required>
        <input type="email" name="email" placeholder="Your email" required>
        <textarea name="message" placeholder="Your message here" required></textarea>
        <button type="submit">Send</button>
    </form>
    """

    left_column, right_column = st.columns(2)
    with left_column:
        st.markdown(contact_form, unsafe_allow_html=True)
    with right_column:
        st.empty()
st.write("---")

st.title("SSVF Forms Selection")
              
#with st.form(key = "form1"):
my_form = st.form(key = "form1")
name = my_form.text_input(label = "Enter your First and Last Name")
number = my_form.slider("Enter your age", min_value=10, max_value = 100 )
submit = my_form.form_submit_button(label = "Submit this form")

col1, col2 = st.columns(2)

with col1:
    with st.form('Form1'):
        st.selectbox('Select your living status', ['Renting', 'Looking to Rent'], key=1)
        st.slider(label='Select intensity', min_value=0, max_value=100, key=4)
        submitted1 = st.form_submit_button('Submit 1')

with col2:
    with st.form('Form2'):
        st.selectbox('Select When you finished application', ['Complete', 'Incomplete'], key=2)
        st.slider(label='Select Intensity', min_value=0, max_value=100, key=3)
        submitted2 = st.form_submit_button('Submit 2')

st.text(number)

st.markdown("Forms Inside")

with st.form(key='columns_in_form'):
    cols = st.columns(3)
    for i, col in enumerate(cols):
        col.selectbox(f'Choose Your Forms', ['SSVF Screening', 'or SSVF Intake'], key=i)
    submitted = st.form_submit_button('Submit')
