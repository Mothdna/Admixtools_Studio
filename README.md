# qpAdm 与 D-stat 工作台 v1.7.57

单文件网页版古 DNA 群体遗传学工作台，可在浏览器内直接载入 PLINK（bed/bim/fam）或 EIGENSTRAT（ind/snp/geno）数据，计算 f₂/Fst、f₃、f₄/D、qpAdm、PCA 与 Admixture。

## 文件说明

| 文件 | 用途 |
|---|---|
| `index.html` | 网站入口，GitHub Pages 会自动识别 |
| `qpAdm与Dstat工作台_v1.7.57.html` | 同内容、带版本号的副本，便于归档与本地打开 |
| `.nojekyll` | 关闭 Jekyll 处理，保证文件按原样发布 |
| `README.md` | 本说明 |

页面为单文件自包含（样式、脚本、图标全部内联），不依赖任何本地资源。唯一的运行期外部依赖是导出功能所用的 `docx` 库（jsDelivr CDN），断网时其余功能不受影响。

## 上架步骤（网页方式，无需命令行）

1. 登录 GitHub，右上角 `+` → `New repository`。
2. 仓库名随意（例如 `qpadm-dstat`），可见性选 `Public`（Pages 免费版需要公开仓库），不要勾选初始化 README。
3. 进入仓库 → `Add file` → `Upload files`，把本压缩包解压后的全部文件拖进去（含 `index.html`、`.nojekyll`、`README.md` 及版本号副本）。
4. 底部 `Commit changes` 提交到 `main` 分支。
5. 仓库 → `Settings` → 左侧 `Pages` → `Source` 选 `Deploy from a branch` → 分支 `main`、目录 `/ (root)` → `Save`。
6. 等待约 1 分钟，页面顶部会显示站点地址，形如 `https://<你的用户名>.github.io/<仓库名>/`。

## 上架步骤（命令行方式）

```bash
git init
git add .
git commit -m "qpAdm 与 D-stat 工作台 v1.7.57"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

推送后在 `Settings → Pages` 按上面的第 5 步开启即可。

## 使用提示

- 数据文件只在浏览器内存中解析，不会上传到任何服务器；离线版可直接双击 `index.html` 使用。
- 载入大数据集（如 1.6G 的 bed）时请预留充足内存，首次载入耗时数分钟属正常。
- 「计算设置」只负责读取与分组，读取完成后各计算板块需要在搜索框里手动选样本。
- 导出统一为 Excel（.docx 容器），需要联网加载导出库。
- 模型判定口径：通过 = p ≥ 0.1、每个源群体 SE ≤ 0.05、全部权重满足 0 < w < 1；优秀 = 通过且 p > 0.5、每个 |Z| ≥ 2。
