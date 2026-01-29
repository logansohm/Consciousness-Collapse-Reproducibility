import pandas as pd

PATH = "data/constructed_eta_R_dataset.csv"

df = pd.read_csv(PATH)
required = {"domain","eta","R"}
missing = required - set(df.columns)
if missing:
    raise SystemExit(f"Missing required columns: {missing}")

if df[["eta","R"]].isna().any().any():
    raise SystemExit("Found NaNs in eta or R")

print("OK")
print("Rows:", len(df))
print("Domains:", sorted(df["domain"].unique()))
print(df.head())
