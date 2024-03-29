# ConspEmoLLM: Conspiracy Theory Detection using an Emotion-Based Large Language Model

[The ConspEmoLLM Paper](https://arxiv.org/abs/2403.06765)

## News

📢 *Mar. 29, 2024* We release the ConspEmoLLM and ConspLLM models!

## Models

- [ConspEmoLLM-7b](https://huggingface.co/lzw1008/ConspEmoLLM-7b) 
- [ConspLLM-7b](https://huggingface.co/lzw1008/ConspLLM-7b) 



## Usage

You can use the models in your Python project with the Hugging Face Transformers library. Here is a simple example of how to load the model:

```python
from transformers import AutoTokenizer, AutoModelForCausalLM
tokenizer = AutoTokenizer.from_pretrained(MODEL_PATH)
model = AutoModelForCausalLM.from_pretrained(MODEL_PATH, device_map='auto')
```
Then follow the prompts in the paper to predict the results.


### Generate
```
generate_ids = model.generate(inputs["input_ids"], max_length=256)
response = tokenizer.batch_decode(generate_ids, skip_special_tokens=True)[0]
print(response)
```
Batch inference. The data format needs to follow data/test.json.
```python
bash src/run_inference.sh
```

### Finetune
```python
bash src/run_sft.sh
```

## License

The ConspEmoLLM and ConspLLM are licensed under [MIT]. Please find more details in the [MIT](LICENSE) file.

## Citation

If you use the series of EmoLLMs in your work, please cite our paper:

```
@article{liu2024conspemollm,
  title={ConspEmoLLM: Conspiracy Theory Detection Using an Emotion-Based Large Language Model},
  author={Liu, Zhiwei and Liu, Boyang and Thompson, Paul and Yang, Kailai and Jain, Raghav and Ananiadou, Sophia},
  journal={arXiv preprint arXiv:2403.06765},
  year={2024}
}
```

