---
license: other
datasets:
- ehartford/wizard_vicuna_70k_unfiltered
language:
- en
tags:
- uncensored
inference: false
---
<div style="width: 100%;">
    <img src="https://i.imgur.com/EBdldam.jpg" alt="TheBlokeAI" style="width: 100%; min-width: 400px; display: block; margin: auto;">
</div>
<div style="display: flex; justify-content: space-between; width: 100%;">
    <div style="display: flex; flex-direction: column; align-items: flex-start;">
        <p><a href="https://discord.gg/UBgz4VXf">Chat & support: my new Discord server</a></p>
    </div>
    <div style="display: flex; flex-direction: column; align-items: flex-end;">
        <p><a href="https://www.patreon.com/TheBlokeAI">Want to contribute? TheBloke's Patreon page</a></p>
    </div>
</div>

# Eric Hartford's Wizard-Vicuna-30B-Uncensored GPTQ

This is GPTQ format quantised 4bit models of [Eric Hartford's Wizard-Vicuna 30B](https://huggingface.co/ehartford/Wizard-Vicuna-30B-Uncensored).

It is the result of quantising to 4bit using [GPTQ-for-LLaMa](https://github.com/qwopqwop200/GPTQ-for-LLaMa).

## Repositories available

* [4bit GPTQ models for GPU inference](https://huggingface.co/TheBloke/Wizard-Vicuna-30B-Uncensored-GPTQ).
* [4bit and 5bit GGML models for CPU inference](https://huggingface.co/TheBloke/Wizard-Vicuna-30B-Uncensored-GGML).
* [float16 HF format model for GPU inference and further conversions](https://huggingface.co/ehartford/Wizard-Vicuna-30B-Uncensored).

## How to easily download and use this model in text-generation-webui

Open the text-generation-webui UI as normal.

1. Click the **Model tab**.
2. Under **Download custom model or LoRA**, enter `TheBloke/Wizard-Vicuna-30B-Uncensored-GPTQ`.
3. Click **Download**.
4. Wait until it says it's finished downloading.
5. Click the **Refresh** icon next to **Model** in the top left.
6. In the **Model drop-down**: choose the model you just downloaded, `Wizard-Vicuna-30B-Uncensored-GPTQ`.
7. If you see an error in the bottom right, ignore it - it's temporary.
8. Fill out the `GPTQ parameters` on the right: `Bits = 4`, `Groupsize = None`, `model_type = Llama`
9. Click **Save settings for this model** in the top right.
10. Click **Reload the Model** in the top right.
11. Once it says it's loaded, click the **Text Generation tab** and enter a prompt!

## Provided files

**Compatible file - Wizard-Vicuna-30B-Uncensored-GPTQ-4bit.act-order.safetensors**

This will work with all versions of GPTQ-for-LLaMa. It has maximum compatibility

It was created without group_size to minimise VRAM usage, and with `--act-order` to improve inference quality. 

* `Wizard-Vicuna-30B-Uncensored-GPTQ-4bit.act-order.safetensors`
  * Works with all versions of GPTQ-for-LLaMa code, both Triton and CUDA branches
  * Works with AutoGPTQ.
  * Works with text-generation-webui one-click-installers
  * Parameters: Groupsize = None. Act-order.
  * Command used to create the GPTQ:
    ```
    python llama.py ehartford_Wizard-Vicuna-30B-Uncensored c4 --wbits 4 --act-order --true-sequential --save_safetensors Wizard-Vicuna-30B-Uncensored-GPTQ-4bit-128g.act-order.safetensors
    ```

## Want to support my work?

Thanks to [chirper.ai](chirper.ai)!

I've had a lot of people ask if they can contribute. I love providing models and helping people, but it is starting to rack up pretty big cloud computing bills.

So if you're able and willing to contribute, it'd be most gratefully received and will help me to keep providing models, and work on various AI projects.

Donaters will get priority support on any and all AI/LLM/model questions, and I'll gladly quantise any model you'd like to try.

* Patreon: https://patreon.com/TheBlokeAI
* Ko-Fi: https://ko-fi.com/TheBlokeAI
* Discord: https://discord.gg/UBgz4VXf

Patreon special mention: Jonathan Leane; Talal Aujan. Thank you both, and to all my other patrons and donaters.

# Original model card

This is [wizard-vicuna-13b](https://huggingface.co/junelee/wizard-vicuna-13b) trained with a subset of the dataset - responses that contained alignment / moralizing were removed. The intent is to train a WizardLM that doesn't have alignment built-in, so that alignment (of any sort) can be added separately with for example with a RLHF LoRA.

Shout out to the open source AI/ML community, and everyone who helped me out.

Note:  

An uncensored model has no guardrails.  

You are responsible for anything you do with the model, just as you are responsible for anything you do with any dangerous object such as a knife, gun, lighter, or car.

Publishing anything this model generates is the same as publishing it yourself.

You are responsible for the content you publish, and you cannot blame the model any more than you can blame the knife, gun, lighter, or car for what you do with it.