## Demo

- Search for [Tony Stark](https://paloit2016.sharepoint.com/:v:/s/TH_-THTechHive/Ec8fIv5_LCVJgTSfm7WGmdEBRSg0WAFTXIsLmgCpBo6CKw?e=mZkqqG&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D) using Firefox app
- Search for [Taylor Swift](https://paloit2016.sharepoint.com/:v:/s/TH_-THTechHive/EQ27s6sy5PRLgFMTqV8z9NkBRtXYoXEmWRa547kOj6lUdg?e=X28FJe&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D) using Firefox app

## Prerequisites:

- Python v3.10.6 installed on your system. You can download and install Python from the [official Python website](https://www.python.org/downloads/).
- For developers using Apple Silicon (M1 or above) CPUs, it is necessary to update the TensorFlow version in the `requirements.txt` file to `tensorflow-macos==2.9.1`.

  > Reference issue: https://github.com/X-PLUG/MobileAgent/issues/4

- Android Emulator or Android device.
- Android Debug Bridge (`adb`) command-line tool
- ChatGPT API key

## Running the Program

1. Open a terminal or command prompt and navigate to where the `run.py` file is located. Use the `cd` command to change directories.

2. Install any required dependencies by running the following command:

   ```
   pip install -r requirements.txt
   ```

   > Make sure that `supervision` and `numpy==1.26.4` are defined in `requirements.txt`.

3. Start Android emulator. You can check available Android Emulators with `emulator -list-avds` and then start with this command:

   ```bash
   emulator -avd <emulator>
   ```

4. Execute the following command to run the `run.py` program:

   ```bash
   python run.py --adb_path /path/to/adb --api "your API_TOKEN" --instruction "your instruction"

   # Example
   python run.py --adb_path /Users/<username>/Library/Android/sdk/platform-tools/adb --api "your API_TOKEN" --instruction "Search the information about Tony Stark using Firefox app."
   ```

   > For other instructions, go to [Mobile-Eval](README.md##Mobile-Eval) section in `README.md` file

5. The program will start running, and you can view the output or any error messages in the terminal or command prompt.

## Debugging

To see what's going on behind the scenes, you can print the response after line number 64 in `run.py`.

```python
response = inference_chat(operation_history, args.api)
print(response)
```

## Troubleshooting

- If you encounter a 404 not found error, please ensure that you are using the correct model name in `MobileAgent/api.py`. As of now, the model name is `gpt-4o` (ChatGPT-4o).
