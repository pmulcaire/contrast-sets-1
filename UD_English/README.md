- `stats.py` compares the two conllu source files (one containing the original trees, one containing altered trees), finds the manually altered adpositions, and writes a json dictionary with the indices of those adpositions and their original and altered *grand-heads* (i.e. the head of the head, in this case usually a verb or noun, the target of the attachment change). It also prints some statistics about the data (e.g. the number of times the grand-head changes from X pos tag to Y pos tag, the counts of the arc labels from the adpositions' heads to their grand-heads).
- `eval_json_predictions.py` takes the parser predictions and the json dictionary from `stats.py` and checks how often the predicted grand-heads of the target adpositions match the true grand-heads from the conllu files.