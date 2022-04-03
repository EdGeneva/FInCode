# FInCode
My FinCode for Publc.
Feel free to disseminate.


{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 18,
   "id": "d1dfa5fc",
   "metadata": {
    "scrolled": true
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "[*********************100%***********************]  2 of 2 completed\n",
      "<class 'pandas.core.frame.DataFrame'>\n",
      "DatetimeIndex: 2575 entries, 2012-01-03 to 2022-03-25\n",
      "Data columns (total 12 columns):\n",
      " #   Column             Non-Null Count  Dtype  \n",
      "---  ------             --------------  -----  \n",
      " 0   (Adj Close, AAPL)  2575 non-null   float64\n",
      " 1   (Adj Close, KRBN)  417 non-null    float64\n",
      " 2   (Close, AAPL)      2575 non-null   float64\n",
      " 3   (Close, KRBN)      417 non-null    float64\n",
      " 4   (High, AAPL)       2575 non-null   float64\n",
      " 5   (High, KRBN)       417 non-null    float64\n",
      " 6   (Low, AAPL)        2575 non-null   float64\n",
      " 7   (Low, KRBN)        417 non-null    float64\n",
      " 8   (Open, AAPL)       2575 non-null   float64\n",
      " 9   (Open, KRBN)       417 non-null    float64\n",
      " 10  (Volume, AAPL)     2575 non-null   int64  \n",
      " 11  (Volume, KRBN)     417 non-null    float64\n",
      "dtypes: float64(11), int64(1)\n",
      "memory usage: 261.5 KB\n"
     ]
    }
   ],
   "source": [
    "#access to listed stocks\n",
    "\n",
    "import yfinance as yf\n",
    "\n",
    "symbol = {'AAPL', 'KRBN'}\n",
    "start = '2012-01-01'\n",
    "end = '2022-03-27'\n",
    "yf.pdr_override()\n",
    "\n",
    "df = yf.download(symbol, start, end)\n",
    "\n",
    "df.info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "id": "0fa30c23",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead tr th {\n",
       "        text-align: left;\n",
       "    }\n",
       "\n",
       "    .dataframe thead tr:last-of-type th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr>\n",
       "      <th></th>\n",
       "      <th colspan=\"2\" halign=\"left\">Adj Close</th>\n",
       "      <th colspan=\"2\" halign=\"left\">Close</th>\n",
       "      <th colspan=\"2\" halign=\"left\">High</th>\n",
       "      <th colspan=\"2\" halign=\"left\">Low</th>\n",
       "      <th colspan=\"2\" halign=\"left\">Open</th>\n",
       "      <th colspan=\"2\" halign=\"left\">Volume</th>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th></th>\n",
       "      <th>AAPL</th>\n",
       "      <th>KRBN</th>\n",
       "      <th>AAPL</th>\n",
       "      <th>KRBN</th>\n",
       "      <th>AAPL</th>\n",
       "      <th>KRBN</th>\n",
       "      <th>AAPL</th>\n",
       "      <th>KRBN</th>\n",
       "      <th>AAPL</th>\n",
       "      <th>KRBN</th>\n",
       "      <th>AAPL</th>\n",
       "      <th>KRBN</th>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Date</th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "      <th></th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>2012-01-03</th>\n",
       "      <td>12.575918</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.686786</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.732143</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.607143</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.621429</td>\n",
       "      <td>NaN</td>\n",
       "      <td>302220800</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2012-01-04</th>\n",
       "      <td>12.643502</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.765714</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.810000</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.617143</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.642857</td>\n",
       "      <td>NaN</td>\n",
       "      <td>260022000</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2012-01-05</th>\n",
       "      <td>12.783873</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.929643</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.948214</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.738214</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.819643</td>\n",
       "      <td>NaN</td>\n",
       "      <td>271269600</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2012-01-06</th>\n",
       "      <td>12.917512</td>\n",
       "      <td>NaN</td>\n",
       "      <td>15.085714</td>\n",
       "      <td>NaN</td>\n",
       "      <td>15.098214</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.972143</td>\n",
       "      <td>NaN</td>\n",
       "      <td>14.991786</td>\n",
       "      <td>NaN</td>\n",
       "      <td>318292800</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2012-01-09</th>\n",
       "      <td>12.897020</td>\n",
       "      <td>NaN</td>\n",
       "      <td>15.061786</td>\n",
       "      <td>NaN</td>\n",
       "      <td>15.276786</td>\n",
       "      <td>NaN</td>\n",
       "      <td>15.048214</td>\n",
       "      <td>NaN</td>\n",
       "      <td>15.196429</td>\n",
       "      <td>NaN</td>\n",
       "      <td>394024400</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "            Adj Close           Close            High             Low       \\\n",
       "                 AAPL KRBN       AAPL KRBN       AAPL KRBN       AAPL KRBN   \n",
       "Date                                                                         \n",
       "2012-01-03  12.575918  NaN  14.686786  NaN  14.732143  NaN  14.607143  NaN   \n",
       "2012-01-04  12.643502  NaN  14.765714  NaN  14.810000  NaN  14.617143  NaN   \n",
       "2012-01-05  12.783873  NaN  14.929643  NaN  14.948214  NaN  14.738214  NaN   \n",
       "2012-01-06  12.917512  NaN  15.085714  NaN  15.098214  NaN  14.972143  NaN   \n",
       "2012-01-09  12.897020  NaN  15.061786  NaN  15.276786  NaN  15.048214  NaN   \n",
       "\n",
       "                 Open          Volume       \n",
       "                 AAPL KRBN       AAPL KRBN  \n",
       "Date                                        \n",
       "2012-01-03  14.621429  NaN  302220800  NaN  \n",
       "2012-01-04  14.642857  NaN  260022000  NaN  \n",
       "2012-01-05  14.819643  NaN  271269600  NaN  \n",
       "2012-01-06  14.991786  NaN  318292800  NaN  \n",
       "2012-01-09  15.196429  NaN  394024400  NaN  "
      ]
     },
     "execution_count": 19,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "163ace56",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "login success!\n",
      "logout success!\n"
     ]
    },
    {
     "data": {
      "text/plain": [
       "<baostock.data.resultset.ResultData at 0x7fc77168d820>"
      ]
     },
     "execution_count": 15,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "#Access to listed stocks in A-Share China\n",
    "import baostock as bs\n",
    "import pandas as pd\n",
    "lg = bs.login()\n",
    "\n",
    "rs_result = bs.query_history_k_data_plus(\"sh.600000\",\n",
    "                                         fields=\"date,open,high, low, close,preclose,volume,amount,adjustflag\",\n",
    "                                         start_date='2017-07-01', \n",
    "                                         end_date='2017-12-31', \n",
    "                                         frequency=\"d\", \n",
    "                                         adjustflag=\"3\")\n",
    "df2 = rs_result.get_data()\n",
    "\n",
    "bs.logout()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "0d33bc46",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 125 entries, 0 to 124\n",
      "Data columns (total 9 columns):\n",
      " #   Column      Non-Null Count  Dtype \n",
      "---  ------      --------------  ----- \n",
      " 0   date        125 non-null    object\n",
      " 1   open        125 non-null    object\n",
      " 2   high        125 non-null    object\n",
      " 3   low         125 non-null    object\n",
      " 4   close       125 non-null    object\n",
      " 5   preclose    125 non-null    object\n",
      " 6   volume      125 non-null    object\n",
      " 7   amount      125 non-null    object\n",
      " 8   adjustflag  125 non-null    object\n",
      "dtypes: object(9)\n",
      "memory usage: 8.9+ KB\n"
     ]
    }
   ],
   "source": [
    "df2.info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "82b6bf71",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.9.7"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
