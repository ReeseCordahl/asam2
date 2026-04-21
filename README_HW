# Running ASAM2

While working with ASAM2, there were several setup steps and requirements needed to ensure the software ran correctly:

## Key Notes

1. **Protein Preparation**
   - Downloaded each protein structure from RCSB as a `.pdb` file
   - Cleaned the structures in PyMOL by removing:
     - Solvent molecules
     - Non-polymer components

2. **File Organization**
   - Created a dedicated directory in my home folder to store all processed protein `.pdb` files

3. **Compute Environment**
   - Initially attempted to run on the gateway node, which was inefficient
   - Switched to a proper compute node for better performance

4. **GPU Requirements**
   - ASAM2 requires GPU access for efficient execution
   - GPU downtime temporarily delayed results during this process

5. **Conda Environment Setup**
   - Created and activated a Conda environment to run ASAM2 properly

6. **Execution Workflow**
   - Followed ASAM2 documentation to:
     - Specify correct input `.pdb` files
     - Define output directories
     - Configure run parameters

---

## Example Commands (RIXI Sequence)

### Navigate to ASAM2 Directory
```bash
cd ~/asam2
```

### Request GPU Node
```bash
salloc --gres=gpu:1 --mem=64G --time=01:00:00
```

### Load Required Modules
```bash
module purge
module load Miniforge3
```

### Create and Activate Conda Environment
```bash
conda create --name asamt
conda activate asamt
```

### Create Output Directory
```bash
mkdir -p ~/asam2_outputs/rixi
```

### Run ASAM2
```bash
python3 scripts/generate_ensemble.py \
  -c config/atlas_model.yaml \
  -i ~/asam2_proteins/rixi_final.pdb \
  -o ~/asam2_outputs/rixi/rixi \
  -n 50 \
  -b 8 \
  -d cuda
```
