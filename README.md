# 谱理论

## 主要内容

Bourbaki《数学原本》(Éléments de mathématique) 中《谱理论》一卷的自学笔记。

## 说明

本笔记按 Bourbaki 原书的章节层级组织，对应关系如下：

| Bourbaki 原书 | 本笔记 | 本仓库中的示例 |
|---|---|---|
| 章（Chapitre） | `Content/` 下的**章目录** | `1_Normed_Algebras/` |
| 节（§） | 章目录下的**节目录** | `1_Generalities_on_algebras/` |
| 小节（1、2、…） | 节目录下的 **`.tex` 文件** | `1_Unital_algebras.tex` |

- 目录与文件名取该层级标题的**英译**，并加编号前缀（`1_`、`2_`…，不加前导零）。
- 中文标题写在 `\chapter{...}` 与 `\section{...}` 中：`\chapter{}` 用该**节目录**名的中译，`\section{}` 用该**文件**名的中译。
- 每层目录各有一个 `index.tex`，按顺序汇总对下一层的 `\input`。

正文的写作规定详见模板《笔记写作》中的《正文写作规范》；tex 层面（定理环境用法、符号库维护等）的规定另见该模板的 README。

## 内容结构

```
Content/
├─ 1_Normed_Algebras/
│  ├─ 1_Generalities_on_algebras/
│  ├─ 2_Normed_algebras/
│  ├─ 3_Commutative_Banach_algebras/
│  ├─ 4_Holomorphic_functional_calculus/
│  ├─ 5_Regular_commutative_Banach_algebras/
│  ├─ 6_Involutive_normed_algebras/
│  └─ 7_Algebras_of_continuous_functions_on_a_compact_space/
├─ 2_Appendix/
├─ 3_Locally_Compact_Commutative_Groups/
│  ├─ 1_Fourier_transform/
│  ├─ 2_Structure_of_locally_compact_commutative_groups/
│  └─ 3_Harmonic_synthesis_in_the_spaces_L^1G_L^2G_L^∞G/
├─ 4_Compact_Linear_Maps_and_Perturbations/
│  ├─ 1_Compact_linear_maps/
│  ├─ 2_Examples_of_compact_linear_maps/
│  ├─ 3_Fredholm_endomorphisms_and_Riesz_endomorphisms/
│  ├─ 4_Perturbations_in_Banach_spaces/
│  ├─ 5_Perturbation_by_a_compact_linear_map/
│  └─ 6_Spectral_properties_of_endomorphisms_of_Banach_spaces/
├─ 5_HiIbertian_Spectral_Theory/
│  ├─ 1_Compact_operators_on_a_Hilbert_space/
│  ├─ 2_Normal_endomorphisms/
│  ├─ 3_Distributions_and_tempered_distributions/
│  ├─ 4_Partial_operators/
│  └─ 5_Normal_partial_operators_and_the_spectral_theorem/
└─ 6_Unitary_Representations/
   ├─ 1_Unitary_representations/
   ├─ 2_Representations_of_locally_compact_groups/
   ├─ 3_Functions_of_positive_type/
   └─ 4_Representations_of_compact_groups/
```

## 文件结构

```
main.tex          编译入口
structure.sty     样式包：页面设置、定理环境、引用、数学符号库
quiver.sty        交换图支持
Content/          分章正文，每章一个目录，由 index.tex 汇总 \input
commit.py         一键提交并推送（说明见 commit.md）
setup_mode.py     习题编排模式切换（说明见 setup_mode.md）
README.md         本文件：项目说明
CHANGELOG.md      更新日志：tex 配置调整与正文内容调整
```

各脚本的选项与功能分别见 [commit.md](commit.md) 与 [setup_mode.md](setup_mode.md)；符号库由上层目录的 `symbols.py` 统一管理。

## 编译

本笔记使用自建的【笔记写作】模板（样式包 `structure.sty`），须用 **XeLaTeX** 编译：

```bash
xelatex main.tex
```

- **编译环境**：XeLaTeX。模板依赖 ctexbook 与 XeLaTeX 特性，**不支持 pdfLaTeX**。
- **TeXStudio**：建议 4.0 或更高版本。
- `main.pdf` 未纳入版本控制，需本地编译生成。
