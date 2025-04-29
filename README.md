# PCM to WAV 轉換工具

這個工具提供了將 PCM (Pulse-Code Modulation) 音訊檔案轉換成 WAV 格式的功能。支援通過 C 程式直接使用或是透過 Python 調用 shared library 的方式使用。

## 功能特點

- 支援 PCM 轉 WAV 格式轉換
- 提供 C 語言和 Python 兩種使用介面
- 音訊參數配置：
  - 單聲道 (1 channel)
  - 取樣率 8000 Hz
  - 位元深度 16-bit
  - PCM 音訊格式 (0x0001)

## 使用方式

### 1. 直接編譯執行 C 程式

```bash
make
./pcm2wav.out
```

### 2. 編譯成共享函式庫供 Python 使用

1. 編譯生成 .so 檔：
```bash
make build
```

2. 執行 Python 範例：
```bash
python pcm2wav_sample.py
```

## Python 使用說明

Python 範例程式提供兩種使用方式：

### Python 2.x
```python
test_filename = "test10.pcm"
output_filename = "test10.wav"
```

### Python 3.x
```python
test_filename = "test10.pcm".encode('ascii')
output_filename = "test10.wav".encode('ascii')
```

## 檔案結構

- `pcm_convert_wav.c`: 主要的轉換程式實作
- `wave.hpp`: WAV 檔案格式的標頭定義
- `Makefile`: 編譯配置文件
- `pcm2wav_sample.py`: Python 調用範例
- `libpcm2wav.so`: 編譯後的共享函式庫
- `test6.pcm`, `test10.pcm`: 測試用的 PCM 音訊檔案

## 技術規格

WAV 檔案格式包含：
- RIFF 區塊描述
- fmt 子區塊（包含音訊格式資訊）
- data 子區塊（包含實際音訊資料）

## 授權說明

此工具為開源專案，可自由使用與修改。
