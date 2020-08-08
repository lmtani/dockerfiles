# EffectorP-2

> Note: This is just a dockerfile to make it easy execute EffectorP program. Access (this link)[http://effectorp.csiro.au] to go to oficial website

Uses machine learning to predict effectors present in a given fasta file.

Usage:

'''
docker run -it --rm effector:latest bash -c "python /EffectorP_2.0/Scripts/EffectorP.py -i /EffectorP_2.0/Scripts/Effector_Testing.fasta"
'''
