The repository contains the pre-trained automatic sleep staging model proposed by Cici and Vanessa.

## How to get started:
python predict.py

## Example results

Each batch contains the classification of 20 30-second epochs. For example, a sample PSG recording looks like this in the first few time points:
<br><br>
<img width="771" alt="Screenshot 2024-06-11 at 22 11 03" src="https://github.com/Cicicai379/automatic-sleep-staging/assets/103560915/f88a253a-d31d-48fd-bdac-679b827d55ca">
<br><br>
The EOG and EEG signals were each sampled at 100 Hz. The submental-EMG signal was electronically highpass filtered, rectified and low-pass filtered after which the resulting EMG envelope expressed in uV rms was sampled at 1Hz. Oro-nasal airflow, rectal body temperature, and the event marker were also sampled at 1Hz.
**(For a more detailed exploration of the PSG recording used here, see DEA.ipynb under the project root directory)
**
<br><br>
the predictions of the first 3 batches:
<img width="1138" alt="Screenshot 2024-06-11 at 21 57 15" src="https://github.com/Cicicai379/automatic-sleep-staging/assets/103560915/db89941a-f718-4b49-9752-af0e128a617a">
<img width="1146" alt="Screenshot 2024-06-11 at 21 58 06" src="https://github.com/Cicicai379/automatic-sleep-staging/assets/103560915/ef3ce0df-4860-4afc-bcea-87c7c2f71f90">
<img width="1207" alt="Screenshot 2024-06-11 at 22 02 16" src="https://github.com/Cicicai379/automatic-sleep-staging/assets/103560915/af02f9d3-9b0e-4459-b017-93d56b5a3976">

## How to run with my own data input:
preprocess your data by running python prepare_physionet.py 
run python predict.py
note that:
1. in both Python files, you may need to change the file path according to the location of the input data.
2. the format of the input dataset should be PSG recordings formatted like the ones in this database: https://www.physionet.org/content/sleep-edfx/1.0.0/

## Complete dataset evaluation
- training ACC. for all 10 epochs: [0.6297109082397003, 0.7537160580524345, 0.8063845973782772, 0.8628862359550562, 0.9016268726591761, 0.9328476123595506, 0.9570458801498127, 0.9702422752808989, 0.9782303370786517, 0.9846383426966292]
- testing ACC. for all 10 epochs: [0.6667086693548387, 0.6574234501008065, 0.6759978263608871, 0.6949108492943549, 0.7110438193044355, 0.7109256867439516, 0.7248298891129032, 0.7278816469254032, 0.7332527406754032, 0.7179978893649194]  

A new version with higher accuracy and a more user-friendly API as well as a GUI is coming soon.
