# 🎈 Blank app template

import streamlit as st
import math

st.set_page_config(page_title="Kalkulator pH & pOH", layout="centered")

# Title
st.title("🧪 Kalkulator pH & pOH Larutan")

# Description
st.write("""
Aplikasi ini membantu menghitung nilai pH dan pOH larutan berdasarkan input konsentrasi ion [H⁺] atau [OH⁻].
""")

# Sidebar for input
with st.sidebar:
    st.header("Input Parameter")
    ion_type = st.radio("Pilih jenis ion yang diketahui:", ("[H⁺]", "[OH⁻]"))
    concentration = st.number_input(f"Masukkan konsentrasi {ion_type} (mol/L):", min_value=1e-14, max_value=1.0, format="%.2e")
    show_dark_mode = st.checkbox("Aktifkan Mode Gelap")

# Apply dark mode
if show_dark_mode:
    st.markdown(
        """
        <style>
            body { background-color: #1e1e1e; color: white; }
            .stApp { background-color: #1e1e1e; }
        </style>
        """, unsafe_allow_html=True
    )
