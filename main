import os
import os.path as osp
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns


def load_csv_files():
    base_path = '.' + os.sep + 'resource' + os.sep + 'rollover_simulation'
    logging_files = os.listdir(base_path)
    data_set = {}

    for i, logging_file in enumerate(logging_files):
        data_set[f'df_{i}'] = pd.read_csv(base_path + osp.join(os.sep, logging_file))

    return data_set


def plot_graph(data_set: dict):
    plt.figure(figsize=(10, 10))

    for i in range(len(data_set)):
        sns.scatterplot(x=data_set[f'df_{i}']['Time(sec)'], y=data_set[f'df_{i}']['length(mm)'], linewidth=1, edgecolor='black', label=f'df_{i}')

    plt.legend()
    plt.grid(linestyle='dashed')
    plt.tight_layout()
    plt.show()


data_set = load_csv_files()
plot_graph(data_set)
