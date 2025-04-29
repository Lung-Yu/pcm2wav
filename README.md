# PCM to WAV 轉換工具 / PCM to WAV Converter

這個工具提供了將 PCM (Pulse-Code Modulation) 音訊檔案轉換成 WAV 格式的功能。支援通過 C 程式直接使用或是透過 Python 調用 shared library 的方式使用。

This tool provides functionality to convert PCM (Pulse-Code Modulation) audio files to WAV format. It supports both direct C program usage and Python integration through a shared library.

## 功能特點 / Features

- 支援 PCM 轉 WAV 格式轉換 / Supports PCM to WAV format conversion
- 提供 C 語言和 Python 兩種使用介面 / Provides both C and Python interfaces
- 音訊參數配置 / Audio Configuration:
  - 單聲道 / Mono channel (1 channel)
  - 取樣率 / Sample rate: 8000 Hz
  - 位元深度 / Bit depth: 16-bit
  - PCM 音訊格式 / PCM audio format (0x0001)

## 使用方式 / Usage

### 1. 直接編譯執行 C 程式 / Direct C Program Compilation and Execution

```bash
make
./pcm2wav.out
```

### 2. 編譯成共享函式庫供 Python 使用 / Compile as Shared Library for Python

1. 編譯生成 .so 檔 / Compile to generate .so file:
```bash
make build
```

2. 執行 Python 範例 / Run Python example:
```bash
python pcm2wav_sample.py
```

## Python 使用說明 / Python Usage Guide

Python 範例程式提供兩種使用方式 / The Python example provides two usage methods:

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

## 檔案結構 / File Structure

- `pcm_convert_wav.c`: 主要的轉換程式實作 / Main conversion program implementation
- `wave.hpp`: WAV 檔案格式的標頭定義 / WAV file format header definition
- `Makefile`: 編譯配置文件 / Compilation configuration file
- `pcm2wav_sample.py`: Python 調用範例 / Python usage example
- `libpcm2wav.so`: 編譯後的共享函式庫 / Compiled shared library
- `test6.pcm`, `test10.pcm`: 測試用的 PCM 音訊檔案 / PCM audio test files

## 技術規格 / Technical Specifications

WAV 檔案格式包含以下部分 / WAV file format includes:
- RIFF 區塊描述 / RIFF chunk descriptor
- fmt 子區塊（包含音訊格式資訊）/ fmt sub-chunk (contains audio format information)
- data 子區塊（包含實際音訊資料）/ data sub-chunk (contains actual audio data)

## 授權說明 / License

本專案採用 MIT 授權條款。詳細內容請參閱 [LICENSE](LICENSE) 檔案。

This project is licensed under the MIT License. For more details, please refer to the [LICENSE](LICENSE) file.

MIT 授權允許您 / The MIT License allows you to:
- 自由使用、複製、修改和散布本軟體 / Freely use, copy, modify, and distribute this software
- 將本軟體用於商業用途 / Use this software for commercial purposes
- 修改原始碼並發布修改後的版本 / Modify the source code and release modified versions

唯一的要求是在所有副本中都必須包含原始授權聲明和免責聲明。
The only requirement is that the original license notice and disclaimer must be included in all copies.
