"""
Experiment 05: Turn The Code
Task: Invert a dictionary and aggregate duplicate values into lists.
Author: Sanjutha D (Reg No: 212225240136)
"""

from collections import defaultdict
from typing import Dict, List, Any


def invert_dictionary(data_map: Dict[Any, Any]) -> Dict[Any, List[Any]]:
    """Inverts keys and values of a dictionary, grouping common values.

    Args:
        data_map (dict): Input dictionary with key-value pairs.

    Returns:
        dict: Inverted dictionary where keys become values mapped to lists.
    """
    inverted_map = defaultdict(list)

    for key, value in data_map.items():
        inverted_map[value].append(key)

    return dict(inverted_map)


# --- Execution and Verification ---
if __name__ == "__main__":
    sample_input = {
        "Student_A": "Pass",
        "Student_B": "Fail",
        "Student_C": "Pass",
        "Student_D": "Distinction",
        "Student_E": "Pass",}

    print("Original Input Dictionary:")
    print(sample_input)

    result = invert_dictionary(sample_input)

    print("\nInverted Output Dictionary:")
    print(result)

    Input:

Python
{"A": 10, "B": 20, "C": 10, "D": 30, "E": 20}
Expected Output:

Python
{10: ["A", "C"], 20: ["B", "E"], 30: ["D"]}
