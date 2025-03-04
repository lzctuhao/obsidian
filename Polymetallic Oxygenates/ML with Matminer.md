Firstly, use `pip install matminer pymatgen` to install Matminer and dependencies.

The [[Codes/matminer_test2.py|matminer_test2.py]] focuses on feature generation for materials science applications. Result is [[Codes/magpie_features.csv|magpie_features.csv]].******

> [!NOTE] What is **Magpie**
> 
> In data science, **Magpie** refers to a system developed by Microsoft Research that bridges the gap between Python's **Pandas API** and scalable **cloud database** engines. It aims to combine the ease of use and flexibility of Python-based data analysis tools (like Pandas) with the performance, security, and enterprise-grade capabilities of modern cloud databases. Key features include:  
> 
> 1. **Lazy Computation**: Magpie lazily pushes large-scale computations to optimized database engines (e.g., SQL DW, Spark) instead of executing them locally in Python, significantly improving scalability for big data workloads.  
> 2. **Pandas Compatibility**: It maintains compatibility with the Pandas API, allowing data scientists to use familiar syntax while transparently leveraging backend database optimizations.  
> 3. **Unified Data Layer**: Magpie virtualizes data access across multiple cloud engines, eliminating redundant data transfers and enabling seamless interoperability between tools in a data lake environment.  
> 4. **Enterprise Features**: Unlike traditional Python workflows, Magpie inherits database advantages like fine-grained access control, encryption, and tamper-proof logging.  

This contrasts with the unrelated **LLM-focused Magpie method** (mentioned in other contexts), which automates instruction dataset generation for language models. The data science Magpie specifically addresses performance and scalability challenges in Python-driven analytics.


Note:

| 原英文表头                                | 中文名称          | 意义用途                              |
| ------------------------------------ | ------------- | --------------------------------- |
| formula                              | 化学式           | 材料的化学组成表达式                        |
| composition                          | 成分对象          | pymatgen的Composition对象，用于存储元素组成信息 |
| MagpieData minimum Number            | 原子序数最小值       | 组成元素原子序数的最小值                      |
| MagpieData maximum Number            | 原子序数最大值       | 组成元素原子序数的最大值                      |
| MagpieData range Number              | 原子序数范围        | 原子序数最大值与最小值的差值                    |
| MagpieData mean Number               | 原子序数平均值       | 组成元素原子序数的算术平均值                    |
| MagpieData avg_dev Number            | 原子序数平均绝对偏差    | 原子序数与均值的平均绝对偏差                    |
| MagpieData mode Number               | 原子序数众数        | 出现次数最多的原子序数值                      |
| MagpieData minimum MendeleevNumber   | 门捷列夫数最小值      | 元素周期表位置特征数的最小值                    |
| MagpieData maximum MendeleevNumber   | 门捷列夫数最大值      | 元素周期表位置特征数的最大值                    |
| MagpieData range MendeleevNumber     | 门捷列夫数范围       | 门捷列夫数最大值与最小值的差值                   |
| MagpieData mean MendeleevNumber      | 门捷列夫数平均值      | 门捷列夫数的算术平均值                       |
| MagpieData avg_dev MendeleevNumber   | 门捷列夫数平均绝对偏差   | 门捷列夫数与均值的平均绝对偏差                   |
| MagpieData mode MendeleevNumber      | 门捷列夫数众数       | 出现次数最多的门捷列夫数值                     |
| MagpieData minimum AtomicWeight      | 原子量最小值        | 组成元素原子量的最小值                       |
| MagpieData maximum AtomicWeight      | 原子量最大值        | 组成元素原子量的最大值                       |
| MagpieData range AtomicWeight        | 原子量范围         | 原子量最大值与最小值的差值                     |
| MagpieData mean AtomicWeight         | 原子量平均值        | 原子量的加权平均值                         |
| MagpieData avg_dev AtomicWeight      | 原子量平均绝对偏差     | 原子量与均值的平均绝对偏差                     |
| MagpieData mode AtomicWeight         | 原子量众数         | 出现次数最多的原子量值                       |
| MagpieData minimum MeltingT          | 熔点最小值         | 组成元素熔点(K)的最小值                     |
| MagpieData maximum MeltingT          | 熔点最大值         | 组成元素熔点(K)的最大值                     |
| MagpieData range MeltingT            | 熔点范围          | 熔点最大值与最小值的差值                      |
| MagpieData mean MeltingT             | 熔点平均值         | 熔点的加权平均值                          |
| MagpieData avg_dev MeltingT          | 熔点平均绝对偏差      | 熔点的平均绝对偏差                         |
| MagpieData mode MeltingT             | 熔点众数          | 出现次数最多的熔点值                        |
| MagpieData minimum Column            | 周期表列号最小值      | 元素在周期表中列号的最小值                     |
| MagpieData maximum Column            | 周期表列号最大值      | 元素在周期表中列号的最大值                     |
| MagpieData range Column              | 周期表列号范围       | 列号最大值与最小值的差值                      |
| MagpieData mean Column               | 周期表列号平均值      | 列号的算术平均值                          |
| MagpieData avg_dev Column            | 周期表列号平均绝对偏差   | 列号与均值的平均绝对偏差                      |
| MagpieData mode Column               | 周期表列号众数       | 出现次数最多的列号值                        |
| MagpieData minimum Row               | 周期表行号最小值      | 元素在周期表中行号的最小值                     |
| MagpieData maximum Row               | 周期表行号最大值      | 元素在周期表中行号的最大值                     |
| MagpieData range Row                 | 周期表行号范围       | 行号最大值与最小值的差值                      |
| MagpieData mean Row                  | 周期表行号平均值      | 行号的算术平均值                          |
| MagpieData avg_dev Row               | 周期表行号平均绝对偏差   | 行号与均值的平均绝对偏差                      |
| MagpieData mode Row                  | 周期表行号众数       | 出现次数最多的行号值                        |
| MagpieData minimum CovalentRadius    | 共价半径最小值       | 元素共价半径的最小值                        |
| MagpieData maximum CovalentRadius    | 共价半径最大值       | 元素共价半径的最大值                        |
| MagpieData range CovalentRadius      | 共价半径范围        | 共价半径最大值与最小值的差值                    |
| MagpieData mean CovalentRadius       | 共价半径平均值       | 共价半径的加权平均值                        |
| MagpieData avg_dev CovalentRadius    | 共价半径平均绝对偏差    | 共价半径与均值的平均绝对偏差                    |
| MagpieData mode CovalentRadius       | 共价半径众数        | 出现次数最多的共价半径值                      |
| MagpieData minimum Electronegativity | 电负性最小值        | 元素电负性的最小值                         |
| MagpieData maximum Electronegativity | 电负性最大值        | 元素电负性的最大值                         |
| MagpieData range Electronegativity   | 电负性范围         | 电负性最大值与最小值的差值                     |
| MagpieData mean Electronegativity    | 电负性平均值        | 电负性的加权平均值                         |
| MagpieData avg_dev Electronegativity | 电负性平均绝对偏差     | 电负性与均值的平均绝对偏差                     |
| MagpieData mode Electronegativity    | 电负性众数         | 出现次数最多的电负性值                       |
| MagpieData minimum NsValence         | s轨道价电子数最小值    | 元素s轨道价电子数的最小值                     |
| MagpieData maximum NsValence         | s轨道价电子数最大值    | 元素s轨道价电子数的最大值                     |
| MagpieData range NsValence           | s轨道价电子数范围     | s轨道价电子数极差                         |
| MagpieData mean NsValence            | s轨道价电子数平均值    | s轨道价电子数的算术平均值                     |
| MagpieData avg_dev NsValence         | s轨道价电子数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NsValence            | s轨道价电子数众数     | 出现次数最多的s价电子数值                     |
| MagpieData minimum NpValence         | p轨道价电子数最小值    | 元素p轨道价电子数的最小值                     |
| MagpieData maximum NpValence         | p轨道价电子数最大值    | 元素p轨道价电子数的最大值                     |
| MagpieData range NpValence           | p轨道价电子数范围     | p轨道价电子数极差                         |
| MagpieData mean NpValence            | p轨道价电子数平均值    | p轨道价电子数的算术平均值                     |
| MagpieData avg_dev NpValence         | p轨道价电子数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NpValence            | p轨道价电子数众数     | 出现次数最多的p价电子数值                     |
| MagpieData minimum NdValence         | d轨道价电子数最小值    | 元素d轨道价电子数的最小值                     |
| MagpieData maximum NdValence         | d轨道价电子数最大值    | 元素d轨道价电子数的最大值                     |
| MagpieData range NdValence           | d轨道价电子数范围     | d轨道价电子数极差                         |
| MagpieData mean NdValence            | d轨道价电子数平均值    | d轨道价电子数的算术平均值                     |
| MagpieData avg_dev NdValence         | d轨道价电子数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NdValence            | d轨道价电子数众数     | 出现次数最多的d价电子数值                     |
| MagpieData minimum NfValence         | f轨道价电子数最小值    | 元素f轨道价电子数的最小值                     |
| MagpieData maximum NfValence         | f轨道价电子数最大值    | 元素f轨道价电子数的最大值                     |
| MagpieData range NfValence           | f轨道价电子数范围     | f轨道价电子数极差                         |
| MagpieData mean NfValence            | f轨道价电子数平均值    | f轨道价电子数的算术平均值                     |
| MagpieData avg_dev NfValence         | f轨道价电子数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NfValence            | f轨道价电子数众数     | 出现次数最多的f价电子数值                     |
| MagpieData minimum NValence          | 总价电子数最小值      | 元素总价电子数的最小值                       |
| MagpieData maximum NValence          | 总价电子数最大值      | 元素总价电子数的最大值                       |
| MagpieData range NValence            | 总价电子数范围       | 总价电子数极差                           |
| MagpieData mean NValence             | 总价电子数平均值      | 总价电子数的算术平均值                       |
| MagpieData avg_dev NValence          | 总价电子数平均绝对偏差   | 与均值的平均绝对偏差                        |
| MagpieData mode NValence             | 总价电子数众数       | 出现次数最多的总价电子数值                     |
| MagpieData minimum NsUnfilled        | s轨道未填满数最小值    | s轨道未充满电子数的最小值                     |
| MagpieData maximum NsUnfilled        | s轨道未填满数最大值    | s轨道未充满电子数的最大值                     |
| MagpieData range NsUnfilled          | s轨道未填满数范围     | 未填满数的极差                           |
| MagpieData mean NsUnfilled           | s轨道未填满数平均值    | 未填满数的算术平均值                        |
| MagpieData avg_dev NsUnfilled        | s轨道未填满数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NsUnfilled           | s轨道未填满数众数     | 出现次数最多的未填满数值                      |
| MagpieData minimum NpUnfilled        | p轨道未填满数最小值    | p轨道未充满电子数的最小值                     |
| MagpieData maximum NpUnfilled        | p轨道未填满数最大值    | p轨道未充满电子数的最大值                     |
| MagpieData range NpUnfilled          | p轨道未填满数范围     | 未填满数的极差                           |
| MagpieData mean NpUnfilled           | p轨道未填满数平均值    | 未填满数的算术平均值                        |
| MagpieData avg_dev NpUnfilled        | p轨道未填满数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NpUnfilled           | p轨道未填满数众数     | 出现次数最多的未填满数值                      |
| MagpieData minimum NdUnfilled        | d轨道未填满数最小值    | d轨道未充满电子数的最小值                     |
| MagpieData maximum NdUnfilled        | d轨道未填满数最大值    | d轨道未充满电子数的最大值                     |
| MagpieData range NdUnfilled          | d轨道未填满数范围     | 未填满数的极差                           |
| MagpieData mean NdUnfilled           | d轨道未填满数平均值    | 未填满数的算术平均值                        |
| MagpieData avg_dev NdUnfilled        | d轨道未填满数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NdUnfilled           | d轨道未填满数众数     | 出现次数最多的未填满数值                      |
| MagpieData minimum NfUnfilled        | f轨道未填满数最小值    | f轨道未充满电子数的最小值                     |
| MagpieData maximum NfUnfilled        | f轨道未填满数最大值    | f轨道未充满电子数的最大值                     |
| MagpieData range NfUnfilled          | f轨道未填满数范围     | 未填满数的极差                           |
| MagpieData mean NfUnfilled           | f轨道未填满数平均值    | 未填满数的算术平均值                        |
| MagpieData avg_dev NfUnfilled        | f轨道未填满数平均绝对偏差 | 与均值的平均绝对偏差                        |
| MagpieData mode NfUnfilled           | f轨道未填满数众数     | 出现次数最多的未填满数值                      |
| MagpieData minimum NUnfilled         | 总未填满数最小值      | 所有轨道未充满电子总数的最小值                   |
| MagpieData maximum NUnfilled         | 总未填满数最大值      | 所有轨道未充满电子总数的最大值                   |
| MagpieData range NUnfilled           | 总未填满数范围       | 总未填满数的极差                          |
| MagpieData mean NUnfilled            | 总未填满数平均值      | 总未填满数的算术平均值                       |
| MagpieData avg_dev NUnfilled         | 总未填满数平均绝对偏差   | 与均值的平均绝对偏差                        |
| MagpieData mode NUnfilled            | 总未填满数众数       | 出现次数最多的总未填满数值                     |
| MagpieData minimum GSvolume_pa       | 基态原子体积最小值     | 元素单质基态原子体积的最小值                    |
| MagpieData maximum GSvolume_pa       | 基态原子体积最大值     | 元素单质基态原子体积的最大值                    |
| MagpieData range GSvolume_pa         | 基态原子体积范围      | 原子体积的极差                           |
| MagpieData mean GSvolume_pa          | 基态原子体积平均值     | 原子体积的加权平均值                        |
| MagpieData avg_dev GSvolume_pa       | 基态原子体积平均绝对偏差  | 与均值的平均绝对偏差                        |
| MagpieData mode GSvolume_pa          | 基态原子体积众数      | 出现次数最多的原子体积值                      |
| MagpieData minimum GSbandgap         | 基态带隙最小值       | 元素单质基态带隙的最小值                      |
| MagpieData maximum GSbandgap         | 基态带隙最大值       | 元素单质基态带隙的最大值                      |
| MagpieData range GSbandgap           | 基态带隙范围        | 带隙的极差                             |
| MagpieData mean GSbandgap            | 基态带隙平均值       | 带隙的加权平均值                          |
| MagpieData avg_dev GSbandgap         | 基态带隙平均绝对偏差    | 与均值的平均绝对偏差                        |
| MagpieData mode GSbandgap            | 基态带隙众数        | 出现次数最多的带隙值                        |
| MagpieData minimum GSmagmom          | 基态磁矩最小值       | 元素单质基态磁矩的最小值                      |
| MagpieData maximum GSmagmom          | 基态磁矩最大值       | 元素单质基态磁矩的最大值                      |
| MagpieData range GSmagmom            | 基态磁矩范围        | 磁矩的极差                             |
| MagpieData mean GSmagmom             | 基态磁矩平均值       | 磁矩的加权平均值                          |
| MagpieData avg_dev GSmagmom          | 基态磁矩平均绝对偏差    | 与均值的平均绝对偏差                        |
| MagpieData mode GSmagmom             | 基态磁矩众数        | 出现次数最多的磁矩值                        |
| MagpieData minimum SpaceGroupNumber  | 空间群号最小值       | 元素单质晶体空间群编号的最小值                   |
| MagpieData maximum SpaceGroupNumber  | 空间群号最大值       | 元素单质晶体空间群编号的最大值                   |
| MagpieData range SpaceGroupNumber    | 空间群号范围        | 空间群编号的极差                          |
| MagpieData mean SpaceGroupNumber     | 空间群号平均值       | 空间群编号的算术平均值                       |
| MagpieData avg_dev SpaceGroupNumber  | 空间群号平均绝对偏差    | 与均值的平均绝对偏差                        |
| MagpieData mode SpaceGroupNumber     | 空间群号众数        | 出现次数最多的空间群编号值                     |
