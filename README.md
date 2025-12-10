# Customer Support Chatbot
Sequence-to-sequence chatbot with attention, trained on Twitter customer support conversations. Supports Apple, Amazon, Uber, Delta, and Spotify personas.

## Quick start
```bash
pip3 install -r requirements.txt
python3 -m spacy download en
```

## Pretrained chatbots
```bash
wget https://www.dropbox.com/s/ibm49gx1gefpqju/pretrained-models.zip
unzip pretrained-models.zip && rm pretrained-models.zip
python predict.py -cs apple   # options: apple, amazon, uber, delta, spotify
```

## Train your own
```bash
wget https://www.dropbox.com/s/nmnlcncn7jtb7i9/twcs.zip
unzip twcs.zip && mkdir -p data && mv twcs.csv data && rm twcs.zip
python datasets/twitter_customer_support/format.py   # long-running
python train.py --dataset twitter-small
```

## Scripts
- `train.py`: train seq2seq models (see `-h` for flags)
- `predict.py`: chat with a trained model
