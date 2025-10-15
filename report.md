# nanochat training report

Generated: 2025-10-15 02:38:04

## Environment

### Git Information
- Branch: master
- Commit: dd6ff9a (dirty)
- Message: fix bug in fallback case of find_largest_model

### Hardware
- Platform: Linux
- CPUs: 104 cores (104 logical)
- Memory: 1007.4 GB
- GPUs: 8x NVIDIA H100 80GB HBM3
- GPU Memory: 633.5 GB total
- CUDA Version: 12.8
- Hourly Rate: $24.00/hour

### Software
- Python: 3.10.12
- PyTorch: 2.8.0+cu128


### Bloat
- Characters: 330,615
- Lines: 8,077
- Files: 42
- Tokens (approx): 82,653
- Dependencies (uv.lock lines): 2,004

Run started: 2025-10-15 02:38:07

---

## Tokenizer training
timestamp: 2025-10-15 02:39:13

- max_chars: 2,000,000,000
- doc_cap: 10,000
- vocab_size: 65,536
- train_time: 54.1851
- num_special_tokens: 9
- token_bytes_min: 1
- token_bytes_max: 32
- token_bytes_mean: 6.9197
- token_bytes_std: 2.8748


## Tokenizer evaluation
timestamp: 2025-10-15 02:39:19

### Comparison with GPT-2

| Text Type | Bytes | GPT-2 Tokens | GPT-2 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 404 | 4.50 | 375 | 4.85 | +7.2% |
| korean | 893 | 745 | 1.20 | 712 | 1.25 | +4.4% |
| code | 1259 | 576 | 2.19 | 492 | 2.56 | +14.6% |
| math | 1834 | 936 | 1.96 | 966 | 1.90 | -3.2% |
| science | 1112 | 260 | 4.28 | 228 | 4.88 | +12.3% |
| fwe-train | 4208518 | 900364 | 4.67 | 856883 | 4.91 | +4.8% |
| fwe-val | 4908443 | 1059062 | 4.63 | 1010352 | 4.86 | +4.6% |

### Comparison with GPT-4

| Text Type | Bytes | GPT-4 Tokens | GPT-4 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 387 | 4.70 | 375 | 4.85 | +3.1% |
| korean | 893 | 364 | 2.45 | 712 | 1.25 | -95.6% |
| code | 1259 | 309 | 4.07 | 492 | 2.56 | -59.2% |
| math | 1834 | 832 | 2.20 | 966 | 1.90 | -16.1% |
| science | 1112 | 249 | 4.47 | 228 | 4.88 | +8.4% |
| fwe-train | 4208518 | 874799 | 4.81 | 856883 | 4.91 | +2.0% |
| fwe-val | 4908443 | 1029691 | 4.77 | 1010352 | 4.86 | +1.9% |


## Base model training
timestamp: 2025-10-15 05:50:50

- run: speedrun
- depth: 20
- max_seq_len: 2048
- num_iterations: -1
- target_flops: -1.0000
- target_param_data_ratio: 20
- device_batch_size: 32
- total_batch_size: 524,288
- embedding_lr: 0.2000
- unembedding_lr: 0.0040
- weight_decay: 0.0000
- matrix_lr: 0.0200
- grad_clip: 1.0000
- eval_every: 250
- eval_tokens: 10,485,760
- core_metric_every: 2000
- core_metric_max_per_task: 500
- sample_every: 2000
- model_tag: 
- Number of parameters: 560,988,160
- Number of FLOPs per token: 3.491758e+09
- Calculated number of iterations: 21,400
- Number of training tokens: 11,219,763,200
- Tokens : Params ratio: 20.0000
- DDP world size: 8
- warmup_ratio: 0.0000
- warmdown_ratio: 0.2000
- final_lr_frac: 0.0000
- Minimum validation bpb: 0.8118
- Final validation bpb: 0.8118
- CORE metric estimate: 0.2284
- MFU %: 47.83%
- Total training flops: 3.917670e+19
- Total training time: 174.75m
- Peak memory usage: 75424.17MiB


## Base model loss
timestamp: 2025-10-15 05:51:41

- train bpb: 0.8147
- val bpb: 0.8119
- sample 0: <|bos|>The capital of France is Paris. It is the largest city in France and the second largest city in Europe
- sample 1: <|bos|>The chemical symbol of gold is Au. The chemical symbol of gold is Au. The chemical symbol of gold is
- sample 2: <|bos|>If yesterday was Friday, then tomorrow will be Monday. The same goes for the days of the week. The days of the
- sample 3: <|bos|>The opposite of hot is cold. The opposite of cold is hot. The opposite of cold is hot.
- sample 4: <|bos|>The planets of the solar system are: Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Neptune,
- sample 5: <|bos|>My favorite color is red. I love red because it is the color of blood. I love red
- sample 6: <|bos|>If 5*x + 3 = 13, then x is a factor of 5. If 5*x + 3 = 


## Base model evaluation
timestamp: 2025-10-15 05:55:33

- Model: base_model (step 21400)
- CORE metric: 0.2200
- hellaswag_zeroshot: 0.2628
- jeopardy: 0.1181
- bigbench_qa_wikidata: 0.5155
- arc_easy: 0.5286
- arc_challenge: 0.1217
- copa: 0.3200
- commonsense_qa: 0.1974
- piqa: 0.3754
- openbook_qa: 0.1120
- lambada_openai: 0.3742
- hellaswag: 0.2624
- winograd: 0.3114
- winogrande: 0.0718
- bigbench_dyck_languages: 0.1060
- agi_eval_lsat_ar: 0.1359
- bigbench_cs_algorithms: 0.3720
- bigbench_operators: 0.1429
- bigbench_repeat_copy_logic: 0.0312
- squad: 0.2510
- coqa: 0.1937
- boolq: -0.1444
- bigbench_language_identification: 0.1813


## Summary

- Characters: 330,615
- Lines: 8,077
- Files: 42
- Tokens (approx): 82,653
- Dependencies (uv.lock lines): 2,004

| Metric          | BASE     | MID      | SFT      | RL       |
|-----------------|----------|----------|----------|----------|
| CORE            | 0.2200   | -        | -        | -        |

Total wall clock time: 3h17m
