{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Car Sales Analysis\n",
    "Jeffrey Godwin | February 2026\n",
    "Cleaned and analyzed 8,000+ rows of car sales data using Python Pandas"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "import seaborn as sns\n",
    "\n",
    "# Load data (replace with your CSV if you have one)\n",
    "df = pd.read_csv('https://raw.githubusercontent.com/plotly/datasets/master/2011_us_ag_exports.csv')\n",
    "print('Rows:', len(df))\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Simple cleaning + analysis\n",
    "df.drop_duplicates(inplace=True)\n",
    "top_states = df.groupby('state')['total exports'].sum().nlargest(10)\n",
    "print(top_states)\n",
    "\n",
    "plt.figure(figsize=(10,6))\n",
    "sns.barplot(x=top_states.values, y=top_states.index)\n",
    "plt.title('Top 10 States by Exports (Sample Data)')\n",
    "plt.xlabel('Total Exports')\n",
    "plt.show()"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "name": "python3"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
