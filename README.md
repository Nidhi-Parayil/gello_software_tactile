

To launch the robots 

python scripts/gello_get_offset.py --start-joints 

env: conda activate gello_software_tactile



python experiments/launch_nodes.py --robot xarm
python experiments/run_env.py --agent=gello --use-save-interface