### prediction 함수에 pickle 저장 코드가 있습니다.

```python
list_dict_all = []
with torch.no_grad():
    for context, question, guid in zip(contexts, questions, guids):
        encodings = tokenizer(context, question, max_length=512, truncation=True,
                                 padding="max_length", return_token_type_ids=False)
        encodings = {key: torch.tensor([val]) for key, val in encodings.items()}   
        input_ids = encodings["input_ids"].to(device)
        attention_mask = encodings["attention_mask"].to(device)
        outputs = model(input_ids, attention_mask=attention_mask)
        start_logits, end_logits = outputs.start_logits, outputs.end_logits
        ### uploading pickle ###
        dict_all = {"input_ids":input_ids,"start_logits":start_logits,"end_logits":end_logits,"tokenizer_name":tokenizer_name,"guid":guid}
        list_dict_all.append(dict(dict_all))
```

-------


### pickle 불러올때 코드입니다.


```python
### downloading pickle ###
with open('input_ids_and_logits.pickle', 'rb') as handle:
    list_dict_all = pickle.load(handle)
    print(list_dict_all[0]["start_logits"])
### downloading pickle ###
```
